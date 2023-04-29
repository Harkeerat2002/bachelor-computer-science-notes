# Requirements Enginnering
## What is Requirements Enginneering?
- It is concering two concepts: **Problem World** and **Machine Solutions**.
	### Problem World
	- The context (e.g.. organizational, physical, technical) where the problem to be sovled lies. 
	### Machine Solution
	- What needs to be developed, purchaes or installed to solve the problem.
	- Hardware and Software
		- ![[Pasted image 20220601184501.png]]
### Definition: 
- Requirements Engineering is concerned with the **machine's effect** on the surrounding world and the **assumptions** we make about that world.
	- ![[Pasted image 20220601184644.png]]
- Difference between **System-as-is** and **System-to-be**
	### System-as-is
	- The system as it exits before the machine is built into it.
	- It would give:
		- Problems
		- Opportunities
		- Domain Knowledge
	### System-to-be
	- The system as it should be when the machine will be build and operated in it.
	- Understanding how to design the objectives such as:
	  - Services
	  - Constraints
	  - Assumptions
	  Then they are assigned to different fields. It's all about **Why**, **What**, **Who**
## Categories of Requirements:
- ### Domain Properties
	- A **descriptive** statement about the **problem world** that is expected to **hold regardless** of how the system will behave.
	- Area of Knowledge
	- Examples:
		- ![[Pasted image 20220601190219.png]]
- ### Assumptions
	- A statement **to be satisfied by the environment** and formulated in terms of **environmental phenomena**.
	- Examples:
		- ![[Pasted image 20220601190410.png]]
- ### System Requirements
	- A prescriptive statement to be enforced by the software-to-be, possible in cooperating with other system components, and formulated in terms of environmental phenomena.
	- Examples:
		- ![[Pasted image 20220601191118.png]]
- ### Software Requirements
	- A prescriptive statement to be enforced solely by the software-to-be and formulated only in terms of shared phenomena. 
		- ![[Pasted image 20220601191127.png]]
- ### Functional Requirements
	- Functional requirements define the functional effects that the software-to-be is required to have on its environment.
	- Functional Requirements may refer to **environmental conditions** under which such operations should be applied.
	- Functional requirements characterize units of functionality as called **features**
	- Functions may be grouped into coarsergraned functionalities that the software should support.
	- Examples:
		- ![[Pasted image 20220601191524.png]]
- ### Non-Functional Requirements
	- Non-functional requirements define constraints on the way the software-to-be should satisfy functional requirements or on the way it should be developed. 
	- Examples:
		- Standards (European Standards)
		- Accessibility
		- Should support legacy systems
	- Types of Non-functional Requirements
		- ### Quality Requirements
			- Safety
			- Security
			- Reliability
			- Performance
			- Interface
			- Accuracy
		- ### Compliance Requirements
			- Prescribe software effects on the environment to conform to standards, national and international laws, social norms, cultural or political constraints.
		- ### Architectural Requirements
			- Impose structural constraints on the architecture of the software-to-be to fit its environment.
		- ### Development Requirements
			- Constrain the way the software should be developed like development costs, delivery, maintainability, reusability, and portability.
## The Requirements Engineering Process