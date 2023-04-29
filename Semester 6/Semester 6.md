#semester
# Subjects Dashboard
```dataview
TABLE
	string("Semester: " + semester) AS "Semester",
	string("Year: ") + year AS "Year",
	string("ECT: ") + ect as "ECT",
	string("Completed: ") + completed as "Completed"
FROM "Semester 6"
WHERE file.name = "Introducton to Machine Learning" OR file.name =  "Autonomous Mobile Robots" OR file.name =  "Information Technology in Practice" OR file.name =  "Visualization, Simulation and Interaction - Virtual Reality I"
```
