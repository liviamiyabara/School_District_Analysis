# School_District_Analysis
Week 4 module, PyCitySchools with Pandas

## School District Analysis Overview
This week the student assisted Maria, the Chief Data Scientist for the School District, to analyze the high school district data of funding, number of students, type of school, size, budget per student and student scores to provide insights about performance trends and patterns in order to make informed decisions for the School District.

An adjustment had to be made since there was evidence of academic dishonesty regarding reading and math scores for the ninth graders of Thomas High School, their grades were replaced by NaN ('Not a Number'). Now the school board wants to understand how these changes affected the overall analysis.


## Results
* How is the district summary affected?
 
  The number of schools, students and total budget did not change since there was no updates to that portion of the data. What changed was related to the average score and passing percentages, by looking at the data below, the average math score decreased 0.1% points, the average reading score did not change due to rounding (before it was 81.87784% and after cleaning the data it is 81.855796%), the passing math and passing reading percentage dropped 0.2% points each and for the overall passing percentage there is a reduction of 0.3% points.

  ![ScreenShot](https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/District%20summary.png)

* How is the school summary affected?

  The only change in the school summary is related to the Thomas High School (THS) row, highlighted in yellow below. The average math and reading score, passing percentage for math, reading and overall slighted dropped since the data was cleaned regarding THS 9th graders.

  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20summary.png)

* How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?

  As per the table below, the school summary is ordered by the highest overall passing percentage to the lowest, in terms of position in the rank, Thomas High School keeps the second place compared to the other schools, but with percentages a bit lower than before.

  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20summary%20ranking.png)

* How does replacing the ninth-grade scores affect the following:
  * Math and reading scores by grade
  The only change in the summary by grade is for Thomas High School 9th grades, the previous math and readings scores were replaced by nan (not a number) as highlighted in yellow below:
  
  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/By%20grade.png)

  * Scores by school spending
  Since Thomas High School is placed in the spending range of $630-644 per student, only the scores to that range slightly changed as highlighted in yellow below. 

  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20spending.png)
  
  Please note that if we use the formatted table, due to rounding, no changes are perceived in the summary table below. In conclusion, there are not significant differences to  the scores by school spending after the data was cleaned. 
  
  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20spending%20formatted.png)

  * Scores by school size
  Since Thomas High School is placed as a ‘Medium’ school size, only the scores to that range slightly changed (second decimal place). Just like the notes above, in the formatted table there is no difference due to rounding. The cleaned-up data of the Thomas High School 9th grades does not significantly affect the summary by school size.
  
  Summary table with 6 decimal places:

  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20size.png)

  Formatted table (no changes perceived): 

  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20size%20formatted.png)

  * Scores by school type
  
  Since Thomas High School is a Charter school, only the scores to that school type slightly changed (second decimal place). In the formatted table there is no difference in the numbers due to rounding. The cleaned-up data of the Thomas High School 9th grades does not significantly affect the summary by school type.

  Summary table with 6 decimal places:
  
  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20type.png)

  Formatted table (no changes perceived): 
  
  ![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/School%20type%20formatted.png)


## Summary
After using the loc method on the student_data_df to select all the reading scores from the 9th grade at Thomas High School and replacing them with NaN; the first main change was to calculate a new student count that would exclude the Thomas High School Students from 9th grade by using the loc method with specific conditions, “school name” only for “Thomas High School” and adding the “&” function to include only students from 9th grade:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change1.png)

The second main change was to recalculate the new passing scores based on the cleaned data and the updated number of students; updates were made to reflect the new student count into the formula:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change2.png)

The third change was related to recalculating the passing count and passing percentage for math, reading and both for the 10th – 12th graders from Thomas High School (THS). The new counts were done by using the loc method with specific conditions, setting up the “school name” to be equal to “Thomas High School” and adding the “&” function to include the scores condition (higher or equal to 70). The example below shows all the students passing math and reading from THS:

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change3.png)

The last and more complex change was the replacement of the new passing math, passing reading and overall passing percentages calculated above. The loc method was used again, but this time instead of conditions, the index of a specific row and column was applied to substitute the old percentages to the new calculations in the per_school_summary_df.

![ScreenShot]( https://github.com/liviamiyabara/School_District_Analysis/blob/main/Resources/Change4.png)

