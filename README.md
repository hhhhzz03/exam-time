This repository will hold the publicly released anonymized logs and scripts for DOI 10.1145/3478432.3499123

### Update on June 17, 2025
- Clarified column names in the original log datasets as follows:
  - `curr_time`: Elapsed time in milliseconds  
  - `id`: Student ID  
  - `question`: Question identifier in the format `q<category_number>_<question_number>`  
  - `score`: Student's score on the specific question at the current timestamp  

#### Time-Related Cleaning
1. `clean_time_final.tsv` and `clean_time_mid.tsv`
   Contain the cleaned time-related datasets for the final and midterm exams, respectively.  
   Each included student ID has only valid (non-negative) `curr_time` entries and a complete set of questions.

> The `.tsv` files below contain discarded entries from the original dataset from  `clean_time_final.tsv`, `clean_time_mid.tsv`:
2. `corrupted_time_final.tsv` and `corrupted_time_mid.tsv`
   Contain all log entries for any student ID with at least one negative `curr_time` value.  
   These entries were excluded under the assumption that negative timestamps indicate a corrupted log.
3. `incomplete_time_final.tsv` and `incomplete_time_mid.tsv`  
   Contain all log entries for student IDs who viewed fewer or more than the number of questions assigned in the exam:
   - 7 questions for the midterm  
   - 8 questions for the final  
   These logs were excluded based on the assumption that a valid student log should include exactly all assigned questions on midterm/final.

---

#### Non-Time-Related Cleaning
1. `clean_non_time_final.tsv` and `clean_non_time_mid.tsv`  
   Contain the cleaned non-time-related datasets for the final and midterm exams, respectively.  
   Each included student ID has a complete set of questions. **It may contains entries with negative `curr_time` value.**

> The `.tsv` files below contain discarded entries from the original dataset from `clean_non_time_final.tsv`, `clean_non_time_mid.tsv`:
2. `incomplete_non_time_final.tsv` and `incomplete_non_time_mid.tsv`  
   Contain all log entries for student IDs who viewed fewer or more than the number of questions assigned in the exam:
   - 7 questions for the midterm  
   - 8 questions for the final  
   These logs were excluded under the assumption that a valid student log should include exactly all assigned questions on midterm/final.
