#semester 
# Subjects Dashboard
```dataview
TABLE
	string("Semester: " + semester) AS "Semester",
	string("Year: ") + year AS "Year",
	string("ECT: ") + ect AS "ECT",
	string("Completed: ") + completed as "Completed"
FROM "Semester 2"
WHERE file.name = "Algorithms and Data Structure" OR file.name = "Discreate Structures" OR file.name = "Programming Fundamentals 2"
```
