Deferred Acceptance with Displacement Algorithm – Comprehensive Explanation
The Deferred Acceptance with Displacement Algorithm is a systematic and fair method for allocating students to courses based on their stated preferences, scores, and eligibility criteria. It extends the classical deferred acceptance model by incorporating the concept of displacement, allowing stronger students to replace weaker ones in capacity-constrained or grouped courses. This ensures a stable and meritocratic matching outcome while respecting course-specific rules.
1. Inputs and Definitions
The algorithm requires two main datasets: student data and course data. Each includes the following components:
• Students submit a ranked list of course preferences (e.g., Preference 1, Preference 2, ...).
• Each student has one or more score fields, such as Total Score, STEM Weighted Score, Portfolio Score, etc.
• Each course specifies:
   – A capacity limit (number of students that can be admitted).
   – A group name (if multiple courses share a common pool of seats).
   – A group constraint (total number of seats available across all courses in that group).
   – Eligibility criteria, defined as subject thresholds (e.g., Math ≥ 70).
   – Tie-breaker Subjects, an ordered list of subjects used when two students have identical ranking scores.
   
3. Initialization
At the start of the process, all students are unplaced. Each course and course group begins empty. A central data structure maintains the following information:
• Which students are currently matched to each course.
• Which students remain unplaced and what preference index they are currently applying for.
• The cumulative enrollment of each course group (if grouping is used).

5. Core Matching Process
The algorithm operates iteratively, processing each unplaced student in rounds until no further placements are possible. The process follows these steps:
1. Select an unplaced student.
2. Identify the next preferred course that the student has not yet applied to.
3. Check if the student satisfies that course’s eligibility criteria. If not, skip to the next preference.
4. If the course (or its group) has not reached capacity, the student is tentatively placed into that course.
5. If the course or its group is full, the algorithm identifies the weakest currently accepted student based on the student’s overall score.
6. Compare the new student’s ranking score to that of the weakest student. If the new student has a strictly higher ranking score, the new student replaces the weakest one (displacement occurs).
7. If scores are equal, use the tie-breaker subjects to determine priority. The student with higher scores in the ordered list of tie-breaker subjects is preferred.
8. If the tie-breaker comparison is also equal, no displacement occurs, and the new student is rejected from that course.
9. Any displaced student re-enters the pool as unplaced and proceeds to apply for their next preference.
10. The process repeats until no further moves are possible.
    
4. Displacement Logic
Displacement is a key enhancement of this algorithm. It ensures that higher-performing students can replace weaker ones when all available seats are filled. This occurs only when the student’s ranking score is higher than the weakest student in the course’s group. The displaced student is then free to apply to their next preference in subsequent rounds.
Ungrouped courses typically do not experience displacement because their capacities are treated as effectively unlimited. In such cases, any eligible student can join the course.

6. Tie-Breaker Mechanism
When two students have identical ranking scores, the algorithm evaluates their subject-specific performance based on the ordered list of tie-breaker subjects defined by the course. The comparison is lexicographic:
• Compare the first subject in the tie-breaker list.
• If one student has a higher mark, they are preferred.
• If the marks are equal, proceed to the next subject in the list.
• If all tie-breaker subjects are identical, the students are considered equivalent, and no displacement occurs.

8. Eligibility Enforcement
Before any placement is made, the algorithm ensures that the student meets the eligibility criteria for that course. Eligibility rules may include subject-specific minimum marks, overall grade thresholds, or other qualification criteria. Students who fail to meet the eligibility requirements are automatically skipped for that course.

10. Group Constraints
Courses may belong to a common group that shares a total capacity limit. For example, Physics and Chemistry might form a 'Pure Science Group' with a combined capacity of 40 students. In such cases, the algorithm monitors the total number of students across all courses in that group. When the group reaches its maximum capacity, displacement decisions are made based on the ranking score field defined for the group’s courses.

11. Termination and Stability
The algorithm terminates when every student is either successfully placed in a course or has exhausted all of their preferences. The resulting matching is stable. This means that no student can move to a more preferred course without displacing someone stronger. In other words, there are no remaining beneficial swaps that would improve both the student’s and the course’s outcomes.

12. Fairness and Transparency
The algorithm is inherently fair and transparent because placement is determined solely by defined rules: student preferences, course capacities, eligibility criteria, ranking score fields, and tie-breakers. It guarantees that higher-performing students are prioritised while ensuring that all students have equal opportunity to be considered for each course based on their preferences.

13. Summary of Advantages
• Ensures merit-based, stable, and transparent allocations.
• Automatically handles displacement of weaker students by stronger ones.
• Supports course grouping with shared capacity constraints.
• Integrates eligibility and subject-based tie-breaker rules seamlessly.
