import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

np.random.seed()                  #marks
maths_marks = np.random.randint(0,101,100)
science_marks = np.random.randint(0,101,100)
english_marks = np.random.randint(0,101,100)

data = ({"math":maths_marks,
        "science":science_marks,
        "english":english_marks})
df = pd.DataFrame(data)                  #pandas used
df["average"] = df.mean(axis=1)

print(df)

plt.hist(df["math"], bins=10, edgecolor='black')
plt.title("Histogram of Math Marks")
plt.xlabel("marks")
plt.ylabel("no. of students")
plt.show()


plt.plot(df.index[:20], df["average"][:20])
plt.title("Average Marks of First 20 Students")
plt.xlabel("student")
plt.ylabel("average")
plt.show()


subject_average = df[["math","science","english"]].mean()
plt.bar(subject_average.index, subject_average.values, color=['blue','purple','black'])
plt.title("Average Marks in Each Subject")
plt.xlabel("subject")
plt.ylabel("average marks")
plt.show()
