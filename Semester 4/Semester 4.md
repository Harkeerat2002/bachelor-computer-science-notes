#semester 
# Subjects Dashboard
```dataview
TABLE
	string("Semester: " + semester) AS "Semester",
	string("Year: ") + year AS "Year",
	string("ECT: ") + ect AS "ECT",
	string("Completed: ") + completed as "Completed"
FROM "Semester 4"
WHERE file.name = "Computer Networking" OR file.name = "Data Management" OR file.name = "Operating System" OR file.name = "Software Atelier 4" OR file.name = "Introduction to Computational Science"
```









