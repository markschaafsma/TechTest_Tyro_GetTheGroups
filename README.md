# TechTest_Tyro_GetTheGroups

### Overview

This repository contains my Java SE 8 solution to a Technical Test, "Get the Groups", which I
did for Tyro Payments in December 2018.

### Problem
 
New Students are arriving at college. Initially the students don't know each other, and each 
has a circle of friends limited to themselves. As the semester progresses, groups of friends 
form.
 
As they arrive, each students gets an ID number, 1 to n.
 
You will be given three arrays, each aligned by index.
The first array will contain a 'queryType' which will be either 'Friend' or 'Total'.
The next two arrays, 'students1' and 'students2', will each contain a Student ID.

If the query type is 'Friends' the two students become friends.

If the query type is 'Total', you must report the sum of the sizes of the groups of friends 
for the two students.

For example, if you have n=4 students numbered 1-4 and you receive the following queries:
 
      Friend 1 2
      Friend 2 3
      Total  1 4
 
Students will start as discrete group {1},{2},{3} and {4}. Students 1 and 2 become friends 
as do 2 and 3. The new groups are {1,2}, {2,3} and {4} wihich simplies to {1,2,3} and {4}. 
We then total the number of friends for student 1 = 3 and student 4 = 1 for a total =4. 
Notice that student 3 is part of student1's circle of friends indirectly through student 2.

### Functional Description
 
Complete the function getTheGroups in the editor below. The function must return an array 
of integers where the value at each index j denotes the answer for the jth query of type Total.
 
getThe Groups has the following parameter(s):
   - n: the number of students, integer
   - queryType [queryType[1],...queryTpe[q]]: an array of query type strings
   - student1 [student1[1],...student1[q]]: an array of student integer ID's
   - student2 [student2[1],...student2[q]]: an array of student integer ID's
 
### Constraints

   -   1 <= n <= 10 pow 5
   -   1 <= q <= 10 pow 5
   -   1 <= students1[i] <= n
   -   1 <= students2[i] <= n
   -   queryType[i] is a member of {Friend, Total}
 
### Input Format

Input from stdin will be processed as follows and passed to the function.
 
   - The first line contains an integer n, the number of students.
   - The next line contains an integer q, the number of queries.
   - Each of the next q lines contains a string queryType[i] where 1 <= i <= q.
   - The next line contains an integer q, the number of students.
   - Each of the next q lines contains a string students1[i] where 1 <= i <= q.
   - The next line contains an integer q, the number of students.
   - Each of the next q lines contains a string students2[i] where 1 <= i <= q.
     
### Sample Input
 
      3            - the number of students
      2            - the number of queries
      Friend       - queryType[1]
      Total        - queryType[2]
      2            - the number of queries
      1            - student1[1]
      2            - student1[2]
      2            - then number of queries
      2            - student2[1] 
      3            - student2[2]    

### Sample Output 
 
      3
     
### Explanation
 
      There are n = 3 students labelled with IDs {1,2,3}.
      We perform q = 2 queries:
      Query 1 - "Friend 1 2" - Students 1 and 2 become friends
      Query 2 - "Total 2 3" - Find the total number of students in students 2 and 3's collective groups.
                              Student 2 is in a group with two friends (i.e. {1,2}).
                              Student 3 is in a group with one friend (i.e. {3})
                              So store 2 + 1 = 3 in index 0 of the return array.
      After performing all the queries, we return the array [3] as our answer.
