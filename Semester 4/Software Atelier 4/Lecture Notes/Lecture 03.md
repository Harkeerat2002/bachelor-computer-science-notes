# Software Development Life Cycle (1)
- A **reference scheme** according to which all activities related to software production are organized, their goals are defined, their expected outputs are specified
## Waterfall Model:
- A **family** of models:
	- Identify **phases and activities** forcing linear progression from a phase to the next
	- **No returns are** considered harmful

>The waterfall model is a breakdown of project activities into linear sequential phases, where each phase depends on the deliverables of the previous one and corresponds to a specialization of tasks.

### Royce's Waterfall Model:
![[https---s3-us-west-2.amazonaws.com-secure.notion-static.com-a7ee6031-85db-4e46-a16b-15173d060896-Untitled.png]]
- Feasibility Study
- Requirement Analysis & Spec
- Design
- Coding & Unit Test
- Integration & System Test
- Deployment
- Maintenance
    - Corrective Maintenance:
        - Diagnosing and fixing errors, possibly ones found by users.
    - Adaptive Maintenance:
    - Perfective Maintenance:

### Cost of late correction:
- Eliminating errors from large and mature systems **costs more (4-10 times)** than in the case of small and new systems.
- Error removal causes the introduction of **new errors**

### Software Evolution:
- Software must be designed to **accommodate future changes** reliably and cheaply

### Waterfall can be Harmful:
- Requires / Imposes perfect understanding of requirements (that must not change)
- The waterfall by design states that the project has a fixed size and a fix-scoped. However, that is wrong since it never happens like that.

## Spiral Model:
### Boehm's Spiral Model:
![[https---s3-us-west-2.amazonaws.com-secure.notion-static.com-aa37b5cf-b70c-44c4-9d6b-44d21343d059-Untitled.png|450]]
- **Determine Goals, and Alternatives Constraints**
    - Budget
    - Alternatives
    - Constraint
- **Evaluate Alternatives & Risks**:
    - Risks
    - Prototypes
        - **Throw-away:** Little to no reuse of the components of the prototype
        - **Evolutionary:** Reuse components even in the final product.
- **Develop & Test**
    - Detailed usage / Concept of Operation
    - Requirements / Validated Requirements
    - Design & Specs
    - Integration
    - Test
    - Implementation
- **Plan**
    - Requirements & Life-cycle Plan.
    - Planning the next iteration
    - Release

Each phase is its own **quarter**, meaning that it would go always be in a **loop**. Hence, typically going through all of them once is **one** iteration. Hence, usually it's gone through 4 iterations. Also, each tasks under the phase may be executed in a different phase.

## Synchronize & Stabilize:
### **Phases**:
- **Planning Phase**
    - Vision Statement
    - Specification Document
    - Schedule & Team Formation
- **Development Phase**  
    All teams go throughout a complete cycle of development:
    - Development
    - Integration
    - Testing
        - Continuous testing and building
    - Fixing
-   **Stabilization Phase**
    - Perform final debugging
    - Recreate and isolate errors