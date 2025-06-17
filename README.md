This repository will hold the publicly released anonymized logs and scripts for DOI 10.1145/3478432.3499123

### Update on June 17, 2025
- Clarified column names in the original log datasets as follows:
  - `curr_time`: Elapsed time in milliseconds
  - `id`: Student ID
  - `question`: Question identifier in the format `q<category_number>_<question_number>`
  - `score`: Student's score at the corresponding timestamp


The `.tsv` files listed below contain entries that were removed from the original dataset during cleaning process.
#### Time-Related Cleaning
1. `corrupted_time_final.tsv` and `corrupted_time_mid.tsv`:  
   Contain all log entries for any student ID that had at least one negative `curr_time` entry in the logs.  
   These entries were excluded under the assumption that negative timestamps indicate corruption or logging errors.
2. `incomplete_time_final.tsv` and `incomplete_time_mid.tsv`:  
   Contain all log entries for student IDs who viewed fewer/more than the number of questions assigned in the exam:
   - 7 questions for the midterm  
   - 8 questions for the final  
   These students' logs were excluded based on the assumption that a valid student log is expected to include exactly all questions assigned.

#### Non-Time-Related Cleaning
1. `incomplete_non_time_final.tsv` and `incomplete_non_time_mid.tsv`:  
   Contain all log entries for student IDs who viewed fewer/more than the number of questions assigned in the exam:
   - 7 questions for the midterm  
   - 8 questions for the final  
   These students' logs were excluded based on the assumption that a valid student log is expected to include exactly all questions assigned.
