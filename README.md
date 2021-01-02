# School_District_Analysis
Week 4 module, PyCitySchools with Pandas

## School District Analysis Overview
This week the student assisted Maria, the Chief Data Scientist for the School District, to analyze the high school district data of funding, number of students, type of school and student scores to provide insights about performance trends and patterns in order to make informed decisions for the School District.

An adjustment had to be made since there was evidence of academic dishonesty regarding reading and math scores for the ninth graders of Thomas High School, their grades were replaced by NaN ('Not a Number'). Now the school board wants to understand how these changes affected the overall analysis.

## Results
* How is the district summary affected?
* How is the school summary affected?
* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
* How does replacing the ninth-grade scores affect the following:
* Math and reading scores by grade
* Scores by school spending
* Scores by school size
* Scores by school type

## Summary
After using the loc method on the student_data_df to select all the reading scores from the 9th grade at Thomas High School and replacing them with NaN; the first main change was to calculate a new student count that would exclude the Thomas High School Students from 9th grade by using the loc method with specific conditions, “school name” only for “Thomas High School” and adding the “&” function to include only students from 9th grade:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change1.png)

The second main change was to recalculate the new passing scores based on the cleaned data and the updated number of students; updates were made to reflect the new student count into the formula:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change2.png)

The third change was related to recalculating the passing count and passing percentage for math, reading and both for the 10th – 12th graders from Thomas High School (THS). The new counts were done by using the loc method with specific conditions, setting up the “school name” to be equal to “Thomas High School” and adding the “&” function to include the scores condition (higher or equal to 70). The example below shows all the students passing math and reading from THS:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change3.png)

The last and more complex change was the replacement of the passing math, passing reading and overall passing percentage using the loc method using the index of a specific row and column:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change4.png)

