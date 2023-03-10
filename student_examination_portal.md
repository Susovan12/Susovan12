# -*- coding: utf-8 -*-
"""Student Examination Portal.ipynb

Automatically generated by Colaboratory.

Original file is located at
    https://colab.research.google.com/drive/1UFpxKf79N6vfvWPai8yniwvtOu8t20X_
"""

import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
from statistics import mean

student_dataset = pd.read_csv('/content/drive/MyDrive/Students.csv')
student_dataset.head()

update_data = student_dataset.replace('ECE2201', 'ECE2202', inplace = True)
student_dataset.append(update_data)

delete_data = student_dataset.drop(3) 
print(delete_data)

report_card_details = {'Python Programing':[75, 30, 92], 'Python_Grade':['C', 'F', 'A'], 'Physics':[80, 30, 88], 'Physics_Grade':['B', 'F', 'B']}
report_card = pd.DataFrame(report_card_details)
print(report_card)

report_card_as_array = np.array(report_card)
print(report_card_as_array)

while 1:
  if report_card_as_array[0,1] == 'F' and report_card_as_array[0,3] == 'F':
    print('Ritosmita Roy Failed in both subjects')
    break
  elif report_card_as_array[0,1] == 'F' or report_card_as_array[0,3] == 'F':
    print('Ritosmita Roy Failed in One Subject')
    break
  else:
    print('Congratulations! Ritosmita Roy Passed in both subjects')
    break

while 1:
  if report_card_as_array[1,1] == 'F' and report_card_as_array[1,3] == 'F':
    print('Himangsu Sen Failed in both subjects')
    break
  elif report_card_as_array[1,1] == 'F' or report_card_as_array[1,3] == 'F':
    print('Himangsu Sen Failed in One Subject')
    break
  else:
    print('Congratulations! Himangsu Sen Passed in both subjects')
    break

while 1:
  if report_card_as_array[2,1] == 'F' and report_card_as_array[2,3] == 'F':
    print('Keya Ghosh Failed in both subjects')
    break
  elif report_card_as_array[2,1] == 'F' or report_card_as_array[2,3] == 'F':
    print('Keya Ghosh Failed in One Subject')
    break
  else:
    print('Congratulations! Keya Ghosh Passed in both subjects')
    break

course_dataset = pd.read_csv('/content/drive/MyDrive/crs.csv', encoding = 'ISO-8859-1')
course_dataset.head()

student_performence_data = {'Class Roll Number':[1, 1, 1], 'Student Name':['Ritosmita Roy', 'Himangsu Sen', 'Keya Ghosh'], 'Python Programing_Marks':[75, 30, 92], 'Physics_Marks':[80, 30, 88]}
print(pd.DataFrame(student_performence_data))

x_axis_grades = ['A', 'B', 'C', 'D', 'E', 'F']
y_axis_students = [1, 2, 1, 0, 0, 2]
plt.plot(x_axis_grades, y_axis_students, marker = 'D')
plt.ylim(0, 6)
plt.title('Course Statistics')
plt.xlabel('Grades')
plt.ylabel('Number of Students')
plt.show()

batch_dataset = pd.read_csv('/content/drive/MyDrive/Batch.csv')
batch_dataset.head()

students_list = {'Batch Name':['CSE 2022-26', 'CSE 2021-25', 'ECE 2022-26'], 'List of Students':['CSE2201', 'CSE2101', 'ECE2201:ECE2202']}
print(pd.DataFrame(students_list))

courses_list = {'Batch Name':['CSE 2022-26', 'CSE 2021-25', 'ECE 2022-26'], 'List of Courses':['C001-C002', 'C001-C002', 'C002']}
print(pd.DataFrame(courses_list))

performence_of_student = {'Class Roll Number':[1, 1, 1], 'Student Name':['Ritosmita Roy', 'Himangsu Sen', 'Keya Ghosh'], 'Python Programing_Marks':[75, 30, 92], 'Physics_Marks':[80, 30, 88,]}
print(pd.DataFrame(performence_of_student))

ritosmita_total = 75 + 80
himangsu_total = 30 + 30
keya_total = 92 + 88

print(ritosmita_total, himangsu_total, keya_total)

students_total = [155, 60, 180]
grade = ['Ritosmita Roy', 'Himangsu Sen', 'Keya Ghosh']
exp = [0, 0, 0]
clr = ['blue', 'red', 'green']
plt.pie(students_total, labels = grade, explode = exp, autopct = '%2.2f%%', colors = clr)
plt.show()

department_dataset = pd.read_csv('/content/drive/MyDrive/Department.csv')
department_dataset.head()

list_of_batches = {'Department Name':['Computer Science and Engineering', 'Electronics and Communication Engineering'], 'List Of Batches':['CSE22-CSE21', 'ECE22'] }
print(pd.DataFrame(list_of_batches))

CSE22 = [155]
ECE22 = [180]
CSE21 = [60]

CSE22_avg = mean(CSE22)
ECE22_avg = mean(ECE22)
CSE21_avg = mean(CSE21)

print(CSE22_avg, ECE22_avg, CSE21_avg)

x_axis_batches = ['CSE22', 'ECE22', 'CSE21']
y_axis_batches = [155, 180, 60]
plt.plot(x_axis_batches, y_axis_batches, marker = 'o')
plt.ylim(60, 190)
plt.title('Department Statistics')
plt.xlabel('Batch Name')
plt.ylabel('Average Percentage')
plt.show()

examination = {'Student_Roll':[1, 1, 1], 'Java_Programing':[85, 58, 76]}
print(pd.DataFrame(examination))

x1_axis_python = [75, 30, 92]
x2_axis_physics = [80, 30, 88]
x3_axis_java = [85, 58, 76]
yaxis_batch = ['CSE22', 'ECE22', 'CSE21']
plt.xlim(20, 100)
plt.title('Examination Statistics')
plt.scatter(x1_axis_python, yaxis_batch, color = 'blue', label = 'Python')
plt.scatter(x2_axis_physics, yaxis_batch, marker = 'o', color = 'orange', label = 'Physics')
plt.scatter(x3_axis_java, yaxis_batch, marker = 'o', color = 'green', label = 'Java')
plt.legend()
plt.show()

