#semester
# Subjects Dashboard
```dataview
TABLE
	string("Semester: " + semester) AS "Semester",
	string("Year: ") + year AS "Year",
	string("ECT: ") + ect as "ECT",
	string("Completed: ") + completed as "Completed"
FROM "Semester 5"
WHERE file.name = "Algorithms & Data Structures 2" OR file.name = "Artificial Intelligence" OR file.name = "Computer Graphics" OR file.name = "Experimentation & Evaluation" OR file.name = "Information Retrieval"
```


