# System Analysis And Design Notes

## Definition
* The word _"System"_ is derived from the greek word _"Systema"_.
* It means an organized relationship among functioning units or components.
* We can define system as a combination of resources or functioning units working together to accomplish a central objective.

* A system is a set of related components that produce specific results.

* A system is an organized collection of components that work together to achieve a specific goal or set of goals.
* Systems can be found in various domains, including natural, social, and technological environments.
* In the context of information systems, a system typically refers to a set of interrelated components that _collect, process, store, and distribute information_ to support _decision making, coordination, control, analysis, and visualization_ within an organization.

## Characteristics
`OIIIC`
### Organization:
* It implies the **structure and order** in the arrangement of the components that help to achieve the objectives.
* It defines a hierarchial structure and order ranging from the president to workers.

### Interaction
* It refers to the manner in which a component interacts with another component in the system
* In an organization, for example, purchasing must interact with production, advertising with sales, etc.
* "Sharing problems only help to get solutions"

### Interdependence
* It means that the parts of a system depend on each other.
* They are coordinated and linked according to a plan
* One subsystem depends on output of another subsystem for functioning.
* The output of one subsystem acts as an input to another subsystem.
* No subsystem could function in isolation as it recieves data from other subsystems to perform required tasks.

### Integration
* It refers to completeness of a system.
* Refers to how the systems are combined and coordinated to act as a single unit (tied together).
* It is more than sharing the same physical location or part, it means that the _parts of a system work together within the system despite they perform unique tasks_.
* Functions in a program are logically tied together.
* It ensures data flow between modules is smooth and without any conflicts or redundancy, when they run together.
* Succesful integration produces greater total impact than each component working separately.

### Central Objective
* It is the goal or set of goals towards which the system is determined to work together, interdependently, overall.
* Objectives might be real (towards earning profit), or stated (formal).
* If there is no clear objective, the system would be just a pile of modules. 
 
## Elements
### Outputs and Inputs:
* A major objective of a system is to produce an output which is valuable to its user.
* Whatever is the nature of the output, it must be in alignment with the intentions of the user.
* Inputs are the element which **enter the system for processing**.
* The Output is the **Outcome of processing**.

### Processors:
* The processor is an element of the system which involves the actual transformation of input to the output.
* **It is the operational component of the system**.
* Processors modify the input totally or partially.

### Control:
* The control element guides the system.
* It is a decision making subsystem which controls the activities governing input, processing and output.

### Feedback:
* Control in a dynamic system is achieved by feedback.
* Feedback measures output against a standard in some form that includes communication and control
* Feedback may be positive or negative, routine or informational. 

### Environment:
* It is the source of input and external elements which impinge on the system.
* It determines how a system must function.
* It is everything that lies outside the boundary of the system.

### Boundaries:
* The line (limit) that demarcates (separates) the system from the environment is called a boundary.
* It can be defined as a limit that differentiates one system from other systems in an environment.
* Components inside the boundary could only be changed by the system.

### Interfaces:
* The points at which the system meets its environment or where the subsystems meet one another is called an interface.
* The users / environment interacts with a system through its interface.
* Input / output is sent / recieved from the interface of a system from environment.

### Components:
* A component is an irreducible part or an aggregation of parts in a system which contribute in the functioning of a system.
* A component has all the characteristics of a system, hance called a **subsystem**.
* We need not to worry about the changes occuring in the **internal complexity of a system** while working with a  subsystem, for example in a damaged automobile, we can repair it by exchanging some components without thinking about all the nuts and bolts.

## Types of system
Classification of systems can be done in three ways.

### Physical or  Abstract System
#### Physical Systems
* Physical systems are tangible entites we could feel and touch.
* These could be static or dynamic in nature.
* In an office, desks and chairs are static part where as a programmed computer is a dynamic part.

#### Abstract Systems
* Abstract systems are conceptual.
* These are not physcial entities.
* They may be formulae, representation of the model or a system.
  
### Open or Close Systems
Systems interact with their environment to achieve their targets. Things that are not part of the system are environmental elements for the system. Depending upon the interaction with the environment, systems can be divided into two categories, open and closed.

#### Open Systems:
* Systems that interact with their environment.
* Practically most of the systems are open systems.
* An open system has many interfaces with its environment.
* It can also adapt to changing environmental factors.
* It recieves inputs from, and sends outputs to the environment.
* An Information System is an example of this system.

#### Closed Systems:
* Systems that don't interact with their envitronment.
* They are conceptual (abstract).
* They imply that either the environment does not exist or they exist in an isolation to the environment.
* All inputs and outputs are contained within the system.

### Man-Made Information Systems

Man-Made Information Systems are fundamentally categorized into Formal, Informal, and Computer-Based systems.

#### 1. Formal Information Systems

These systems represent the official, documented, and structured communication and reporting channels within an organization.

* **Definition**: They are based on the organization's official structure, as represented by the organizational chart, and are concerned with the pattern of authority, communication, and work flow.
* **Direction of Flow**:
    * **Downward Communication**: Information primarily flows from **top management to lower management** (e.g., policies, orders, and instructions).
    * **Upward Communication**: Feedback, reports, and suggestions flow from subordinate levels up to management.
* **Characteristics**:
    * **Documented**: Procedures and policies are written and auditable.
    * **Scheduled**: Communication is often planned (e.g., official meetings, scheduled reports).
    * **Reliable**: They are considered the most reliable form of communication as there is a paper/digital trail.
* **Examples**: Organization charts, written procedures, official financial statements, company intranets, and official meeting structures.

#### 2. Informal Information Systems

These systems are non-official, spontaneous, and relationship-based, existing alongside the formal structure.

* **Definition**: They are **employee-based** systems that develop organically through social connections and shared interests, designed to meet personal and vocational needs and help solve day-to-day work-related problems.
* **Direction of Flow**: Communication is **multi-dimensional**—it moves laterally (across departments) and upward through unofficial channels. It often bypasses hierarchical lines.
* **Characteristics**:
    * **Undocumented/Unauditable**: Based on verbal exchanges, opinions, and rumors (often called the 'grapevine').
    * **Ad hoc/Spontaneous**: Occurs instantly, such as during water cooler conversations or informal instant messaging.
    * **Speed**: Information transmission is generally much quicker than formal channels.
    * **Flexibility**: They can quickly form ad-hoc teams for rapid problem-solving.
* **Examples**: Lunch groups, instant messaging chats among coworkers, hallway conversations, and unofficial social media groups.

#### 3. Computer-Based Information Systems (CBIS)

This is the most critical and varied category, where the system depends mainly on a computer to process data for managing business applications. CBIS are further classified by the **organizational level** they support (operational, managerial, or strategic) and their **function**.

##### A. Operational Level Systems (Day-to-Day Activities / Lower Level)

| System Type | Purpose | Characteristics | Examples |
| :--- | :--- | :--- | :--- |
| **Transaction Processing Systems (TPS)** | To record and process the routine, day-to-day business transactions. They are the foundation of many other systems. | Focus on speed, accuracy, and high volume processing. They collect, store, modify, and retrieve transaction data. | Point-of-Sale (POS) systems, ATM systems, Payroll processing, Order entry/billing systems, Inventory management. |
| **Process Control Systems (PCS)** | To monitor and control physical industrial processes. | Input data comes from sensors (not human transactions) to monitor variables and automatically adjust equipment. | Petroleum refinery controls, assembly line monitoring, temperature and pressure testing in manufacturing. |

##### B. Knowledge Level Systems (Productivity and Expertise)

| System Type | Purpose | Characteristics | Examples |
| :--- | :--- | :--- | :--- |
| **Office Automation Systems (OAS)** | To improve the productivity of **data workers** and clerical staff by automating routine office tasks. | Focus on communication, scheduling, and document handling. They are applied at all levels of the organization. | Microsoft Office Suite (Word, Excel), Email and calendaring systems, Desktop publishing, Video conferencing tools. |
| **Knowledge Work Systems (KWS)** | To aid **knowledge workers** (professionals like engineers, doctors, or researchers) in creating new knowledge and technical skills. | Highly specialized, require powerful analytical tools, graphics, access to external databases, and complex modeling capabilities. | Computer-Aided Design (CAD) systems, Financial modeling workstations, Medical diagnostic systems. |

##### C. Management Level Systems (Monitoring and Decision Making / mid level)

| System Type | Purpose | Characteristics | Examples |
| :--- | :--- | :--- | :--- |
| **Management Information Systems (MIS)** | To provide mid-level managers with pre-specified, summarized reports on the organization's current and past performance. | Uses data *aggregated* from TPS. Reports are typically scheduled (daily, weekly, monthly) and have little analytical capability, focusing on control and monitoring. | Sales analysis reports (broken down by region/product), Inventory level reports, Budgeting and expense tracking systems. |
| **Decision Support Systems (DSS)** | To help managers make non-routine, complex decisions by modeling data and assessing different scenarios. | Interactive and flexible. They use analytical and modeling capabilities to project potential future effects of decisions, often combining internal data with external information. | Logistics systems finding the most cost-effective delivery route, Financial planning systems, Market trend analysis systems. |

##### D. Strategic/Enterprise Level Systems (Long-Term Planning and Integration / high level)

| System Type | Purpose | Characteristics | Examples |
| :--- | :--- | :--- | :--- |
| **Executive Information Systems (EIS) / Executive Support Systems (ESS)** | To support the **strategic-level decisions** of senior executives. | Provide a highly summarized view of organizational performance and market conditions (often via a digital dashboard). They rely heavily on data from MIS/DSS and external sources (economic forecasts, competitors). | Corporate dashboards tracking key performance indicators (KPIs), Strategic planning and forecasting tools. |
| **Enterprise Resource Planning (ERP)** | A single, integrated software system that manages and integrates all the core business processes across the entire organization. | Centralizes data into a single database, enabling coordination across finance, HR, manufacturing, and supply chain functions. | SAP, Oracle, and Microsoft Dynamics used for managing all departments. |
| **Customer Relationship Management (CRM)** | Focuses on managing and analyzing customer interactions and data throughout the customer lifecycle. | Designed to improve business relationships with customers, assist in customer retention, and drive sales growth. | Salesforce, HubSpot, and other systems used to track leads, customer interactions, and sales history. |
| **Supply Chain Management (SCM)** | Manages the flow of goods, data, and finances from the procurement of raw materials to the delivery of the final product. | Helps organizations coordinate with vendors, manage inventory, handle logistics, and optimize the overall supply chain. | Systems for warehouse management, demand planning, and vendor relationship management. |

***

## Software Development Life Cycle (SDLC) – Phases & Best Practices

The **Software Development Life Cycle (SDLC)** is a structured methodology for designing, developing, testing, and deploying software. It breaks a project into clearly defined stages (e.g., planning, requirements, design, implementation, testing, deployment, maintenance), each with specific goals. A well-defined SDLC improves project management and quality by forcing detailed requirements and designs up front, which helps align stakeholders and avoid costly rework later.

* **Purpose:** Provides a clear roadmap for each phase of development, so teams know what to accomplish at every step.

* **Benefits:** Enhances resource planning, risk management, and end-product quality by setting clear goals early. It also catches defects early (during testing), reducing expensive fixes after release.

* **Scope:** SDLC is flexible (e.g., Waterfall, Agile, DevOps models) but every process typically includes planning, analysis, design, coding, testing, deployment, and maintenance.

***

## Phase 1: Preliminary System Study 🕵️‍♂️

* **Focus:** Understand the current system and define the project scope. Identify _what_ problem needs solving and who will use the new software.

* **Activities:** Interview users and study the existing process to pinpoint pain points and goals.

* **Output:** A **System Proposal** document (often called a project initiation report) listing the problem definition, objectives, constraints (budget, time, etc.), and expected benefits. This document helps management decide whether to proceed.

> 💡 **Memory Hook:** This is the **pitch** phase—figuring out the problem and if it's worth a further look.

***

## Phase 2: Feasibility Study 💡

* **Focus:** Determine whether the project is practical and worth pursuing. Assess technical, economic, and operational feasibility.

* **Activities:** Analyze whether available technology and skills can meet requirements; estimate costs versus benefits; check if the organization can support the change.

* **Output:** A **Feasibility Report** with a go/no-go recommendation. If approved, this report includes a rough project plan and budget estimates for the rest of the SDLC.

> 💡 **Memory Hook:** This is the **reality check**—can we actually build this? (Tech, Money, Support).

***

## Phase 3: Detailed System Study 📘

* **Focus:** Conduct an in-depth analysis of the current system and detailed requirements. Map out how data and processes flow now, and define what the new system must do.

* **Activities:** Gather detailed information on existing data, user roles, workflows, and decision points. Draw context diagrams and data flow diagrams to clarify system boundaries.

* **Output:** Documentation of system requirements (often as detailed data flow diagrams, data dictionaries, and process descriptions) defining exactly _what_ the new system must accomplish. This lays a clear foundation before actual development begins.

> 💡 **Memory Hook:** This is the **deep dive**—mapping every existing detail to inform the new system.

***

## Phase 4: System Analysis 🔬

* **Focus:** Convert the requirements into a precise specification of software behavior. Answer critical "who/what/when/why" questions about the system.

* **Activities:** Work with stakeholders to finalize user and system requirements. Analyze user needs, business rules, and data constraints. Consider alternatives or process changes.

* **Output:** A **Software Requirements Specification (SRS)** – a formal document that lists all functional and non-functional requirements in detail. This acts as a "contract" for what the software must do.

> 💡 **Memory Hook:** Writing the SRS is like making a Santa Claus wishlist🎅 – if you don't specify what you want, you might end up with the wrong gift!

***

## Phase 5: Design 🏗️

* **Focus:** Translate the SRS "what" into a "how" – i.e., a system design. Decide on the architecture, technologies, database schemas, and user interface layouts.

* **High-Level Design (HLD):** Define the overall system architecture. Specify major components or modules and how they interact (e.g., client-server layout, APIs, data flow between modules).

* **Detailed (Low-Level) Design (LLD):** Flesh out the internal logic of each component. Detail data schemas, algorithms, input/output formats, and module interfaces. This includes choosing programming languages and frameworks.

* **Output:** A set of design documents – block diagrams, flowcharts, class diagrams, data models, etc. – that fully describe the planned solution. This should make it clear to developers exactly how to build each part.

* **Tools:** Common artifacts include **flowcharts**, **Data Flow Diagrams (DFDs)**, **entity-relationship diagrams (ERDs)**, data dictionaries, and decision tables. These provide blueprints for coding.

> 💡 **Memory Hook:** An architect draws blueprints🏠 before construction. Similarly, designers create detailed design docs before any code is written.

***

## Phase 6: Development (Coding) 💻

* **Focus:** Write and compile the actual code according to the design specifications. Developers implement the functionality module by module, following the chosen architecture and coding standards.

* **Activities:** Convert each piece of the design into code. Use version control (e.g., Git) to track changes. Follow coding best practices (consistent naming, style, comments) and keep functions/modules small and manageable. Perform developer testing (unit tests) as you go.

* **Output:** The complete source code, along with generated binaries or executables. By the end of this phase, all modules should be developed and integrated into a working (if untested) system.

> 💡 **Memory Hook:** This is the **actual construction**—translating the blueprints into a physical structure (code).

***

## Phase 7: Testing 🧪

* **Focus:** Verify the software works correctly and meets all requirements. Thoroughly test each part and the system as a whole to find and fix defects.

* **Unit Testing:** Test individual modules or classes to ensure each function works as intended (catching logic bugs, interface errors, etc.).

* **Integration/System Testing:** Test the combined system end-to-end using real or simulated data. Check that different modules interact properly. Perform functional tests (each requirement works) and non-functional tests (performance, security, usability).

* **User Acceptance Testing (UAT):** Have actual end-users try the system in realistic scenarios to confirm it meets their needs.

* **Output:** A tested, bug-free system. Defects found during testing are fixed, and test reports are produced. After this phase, the software should be ready for deployment.

> 💡 **Memory Hook:** Like a final house inspection🔧 before moving in, we check plumbing, electricity, and structure. Testing verifies every "pipe and wire" of the software is sound.

***

## Phase 8: Deployment (Implementation) 🚀

* **Focus:** Release the finished software into the production environment and hand it over to users. Also includes training users and setting up support.

* **Activities:** Install the software on user machines or servers, migrate any needed data from the old system, and train users. Update documentation. Provide technical support and troubleshoot any immediate issues.

* **Output:** The software is now live. Deployment may use one of several strategies:

  * _Direct Cutover:_ Switch off the old system and turn on the new one all at once (fast but risky).

  * _Parallel:_ Run old and new systems together for a time, ensuring the new works before retiring the old (safer but resource-heavy).

  * _Pilot:_ Roll out the new system to a small user group first, then expand if successful (controlled approach).

> 💡 **Memory Hook:** It’s like finally getting the keys to your new house🔑. You can **move in completely (Direct)**, **rent the new house while still keeping the old as backup (Parallel)**, or **try out just one room first (Pilot)**.

***

## Phase 9: Maintenance 🔄

* **Focus:** Keep the software useful and efficient over time. Fix bugs that are discovered in production, update the system for new requirements, and improve performance.

* **Activities:** Provide patches and minor upgrades. Monitor the system for issues and user feedback. Optimize performance and adapt to environmental changes (e.g., new OS versions, hardware). Occasionally add new features as needed.

* **Output:** Ongoing support and updates. Software may be versioned (1.0, 1.1, 2.0, etc.) as it evolves. Periodic maintenance reports assess whether a major redesign or a new SDLC cycle is needed.

> 💡 **Memory Hook:** Think of it as regular house upkeep🧹 – you mow the lawn, replace worn-out parts, and repaint walls so your home stays in good shape. Software maintenance is the same for your "software house."

***

## Best Practices in SDLC

Successful SDLC implementation follows certain best practices:

* **Define Clear Requirements:** Invest time in a complete SRS so developers know exactly what to build. Avoid vague goals to prevent scope creep.

* **Choose the Right Model:** Pick an SDLC methodology that fits your project. Well-defined projects may suit **Waterfall**, while rapidly changing or iterative projects benefit from **Agile** methods.

* **Follow Coding Standards:** Enforce consistent style and naming conventions across the team. Conduct regular **code reviews** for quality and knowledge sharing.

* **Use Version Control:** Track all code changes with tools like **Git**. This enables safe collaboration, rollback of errors, and maintains history of the project's evolution.

* **Automate Testing & Deployment:** Implement **Continuous Integration/Continuous Delivery (CI/CD)** pipelines to automatically build, test, and deploy code. Automation catches errors early and accelerates delivery cycles.

* **Maintain Documentation:** Keep requirements, design docs, and user manuals up to date. Good documentation ensures team alignment and aids new developers or stakeholders in understanding the system.

* **Involve Stakeholders:** Keep users and business stakeholders engaged throughout SDLC. Regular feedback (not just at the start) helps catch requirement misunderstandings before it's too late.

* **Integrate Security Early:** Adopt a **"DevSecOps"** mindset by building security into every phase. For example, use automated security scans during testing and educate developers on secure coding.

> 💡 **Memory Hook:** Best Practices are the **rules for success**—use the right tools (Git, CI/CD), talk to users, and write good docs!

***

## Example: Banking Application SDLC

Developing an online banking system might follow these SDLC steps:

* **Planning & Analysis:** Gather requirements (e.g., accounts, transfers, security) from banking staff and customers. Produce a detailed SRS document and get it approved.

* **Design:** Draft the system architecture (e.g., web server, database, API) and database design. Decide on technologies (e.g., Java or Python, SQL database). Prepare high-level and low-level design diagrams.

* **Development:** Write the code for user authentication, transaction processing, account management, etc., following the design. Use version control and coding standards.

* **Testing:** Perform unit tests on each function (login, transfer money), then system tests with realistic data (simulate customers). Fix any bugs so the system meets all requirements.

* **Deployment & Maintenance:** Roll out the banking app (perhaps first to a pilot branch, then bank-wide). Train tellers and customer-support staff. After launch, monitor usage and release patches for any issues. Add new features later (e.g., mobile banking) as needed.

> 💡 **Memory Hook:** The **Banking App** example shows how a project moves logically from defining _needs_ to designing the _structure_, writing the _code_, confirming the _quality_, and finally _releasing_ and _maintaining_ it.

### Custom Mnemonic for the 9 SDLC Phases:
To fit the exact list: Preliminary, Feasibility, Detailed Study, System Analysis, Design, Development, Testing, Deployment, Maintenance.

| Initial | SDLC Phase              | Mnemonic Word |
|---------|-------------------------|---------------|
| P       | Preliminary Study       | People        |
| F       | Feasibility Study       | Finally       |
| D       | Detailed System Study   | Drew          |
| S       | System Analysis (SRS)   | Some          |
| D       | Design                  | Decent        |
| D       | Development (Coding)    | Drawings      |
| T       | Testing                 | To            |
| D       | Deployment              | Deliver       |
| M       | Maintenance             | Money         |

***

## Role of Systems Analyst 

***

### 1. Definition & Purpose

* **Who?** Bridge between **business goals ↔️ tech solutions**.
* **Why?** SAD prevents system rejection/failure.
* **Skills:** Tech 👨‍💻 + People 🤝 + Planning.
🔑 **Mnemonic:** _"Bridge People to Plan Properly"_
***

### 2. Multi-faceted Roles 🎭

* Consultant → advises mgmt.
* Investigator/Monitor → checks progress.
* Architect → system blueprint.
* Psychologist → user fears.
* Salesperson → sells system idea.
* Agent of Change → drives new systems.
* Conflict Resolver → balances interests.

🔑 **Mnemonic:** _"Cool Intelligent Architects Play Smart And Clever"_

***

### 3. Main Activities (Across SDLC)

#### A. Initial Phases 🟢

* **Defining Requirements:** Fact-finding (interview, observation, forms).
* **Identifying Problems & Opportunities:** Output = **Feasibility Report**.
🔑 **Mnemonic:** _"Find → Fix → Feasibility"_

***

#### B. Analysis & Design 🔍

* **Human Info Requirements:** Understand **5Ws+H** (who, what, where, when, why, how).
* **Analyzing Needs:** Use **DFDs, activity diagrams, dictionary** → Output = **System Proposal**.
* **Designing System:** Modular, user-friendly, cost-benefit, backups. Output = **System Model**.
  
🔑 **Mnemonic:** _"People Need Diagrams & Design"_

***

#### C. Implementation & Maintenance ⚙️

* **Develop & Document Software:** Programs + Manuals.
* **Implement & Evaluate:** Train users, smooth conversion.
* **Testing & Maintenance:** Debug + updates (≈60% time).
  
🔑 **Mnemonic:** _"Develop → Deliver → Debug"_

***

## 4. Attributes & Skills

#### A. Interpersonal (Soft) 🗣️

* Translate tech ↔️ non-tech.
* Communicate, lead, motivate.

🔑 _"Talk, Teach, Team up"_

#### B. Technical 🖥️

* Tools, software, creativity, new tech.

🔑 _"Tech Tools Today"_

#### C. Analytical 🧠

* Problem-solving, trade-offs, curiosity.

🔑 _"Analyze All Alternatives"_

#### D. Management 📊

* Project scheduling, cost mgmt, risk handling.

🔑 _"Manage Money & Moments"_

***

### 5. Key Qualities 🌟

* Authority, Creativity, Communication.
* Ethics, Self-discipline, Motivation.

🔑 _"Act Confidently, Stay Ethical"_

***

### 6. Academic Needs 🎓

* Systems theory + org behavior.
* Finance, marketing, production domains.
* Programming + databases.
* Hardware/software knowledge.

🔑 _"Study Fields + Software + Systems"_

***

### 📝 Super-Mnemonic Summary

**"Bridge Cool People Find Diagrams, Develop Management And Study."**\
(= Definition, Roles, Activities, Attributes, Skills, Qualities, Academic)

## **1. System Planning and Initial Investigation**

**Systems development** is a **two-part process**:

* **Systems Analysis** – Gathering & interpreting facts, diagnosing problems, and recommending improvements.
* **Systems Design** – Implementing the solution effectively.

### **Initial Investigation**

* A **preliminary investigation** that begins when a user requests **change, improvement, or enhancement** in an existing system.
* **Objective:** Determine whether the request is **valid and feasible** before deciding to:

  * Do nothing
  * Modify/improve existing system
  * Build a new system

### **Process Steps:**

1. **Problem Definition & Project Initiation**

   * Define the problem clearly; ensure user & analyst agreement.
   * Focus on **logical requirements** (what must result) over physical details.
   * **Components:** System functions, input/output requirements, environment (weather, temperature), required skills, personnel involved, interfaces, data flows, components & purposes.

2. **Background Analysis**

   * Learn about the existing system and **physical processes** for potential revision.

3. **Fact-Finding**

   * Collect data about **inputs, outputs, and costs**.
   * **Techniques:** Review documents, on-site observation, interviews, questionnaires.

4. **Fact Analysis**

   * Analyze data using:

     * Input/Output (I/O) Analysis
     * Data Flow Diagrams (DFDs)
     * Decision Tables
     * Structure Charts

5. **Determination of Feasibility**

   * Summarize gathered information.
   * Deliverables may include:

     * Interview records
     * Updated system documentation
     * Flowcharts
     * Specifications of good/bad features of the current system

***

## **2. Information Gathering Tools**

**Essence:** Effective info gathering is both an **art and science**. Analysts need sensitivity, common sense, and proper methodology.

**Principle:** Obtain information **accurately, methodically, under the right conditions, and with minimal disruption**.

### **Main Techniques**

1. **Review Literature, Procedures, and Forms**

   * Professional references, manuals, company studies, government publications.
   * **Advantages:** Learn system operation quickly; understand transactions; minimal intrusion.
   * **Disadvantages:** Time-consuming; outdated or expensive.

2. **On-Site Observation**

   * Analyst observes users, workflow, and physical layout.
   * **Types:**

     * Natural vs. Contrived
     * Obtrusive vs. Unobtrusive
     * Direct vs. Indirect
     * Structured vs. Unstructured
   * **Advantages:** Direct, reliable, authentic data.
   * **Challenges:** Intrusive, time-consuming, difficult to assess attitudes/motivations.

3. **Interviews**

   * Face-to-face discussions to gather qualitative insights.
   * **Types:**

     * Unstructured – open, free-flowing conversation
     * Structured – fixed questions in a set order
   * **Question types:** Open-ended, Close-ended (dichotomous, ranking scales, multiple-choice, rating scales)
   * **Advantages:** Flexible, immediate clarification, high-quality qualitative data.
   * **Disadvantages:** Time-consuming, expensive, preparation required.

4. **Questionnaires**

   * Collection of written questions distributed to many people.
   * **Advantages:** Economical, standardized, anonymous, less pressure on respondents.
   * **Disadvantages:** Low return rate, limited depth, difficult for subjective topics.

### **Kinds of Information Required**

| Type         | Details                                                                                   |
| ------------ | ----------------------------------------------------------------------------------------- |
| Organization | Policies, goals/objectives, structure (org chart), environment for computer-based systems |
| User Staff   | Roles, authority, job functions, interpersonal relations, expectations for new system     |
| Workflow     | Data movement, input/output, documented via DFDs or system flowcharts                     |

### **Sources of Information**

* **External:** Vendors, government documents, newspapers, professional journals
* **Internal:** Financial reports, personnel staff, professional staff, system documentation/manuals, reports, transactions

***

## **3. Feasibility Study**

A **feasibility study** evaluates whether a system **can and should be developed** before committing resources.

**Purpose:**

* Assess problem scope, not solve it.
* Identify whether improvements or new system development is possible.
* Produce refined estimates for further development.

**Output:**

* A **formal system proposal** for management including scope, cost, and savings of alternatives.

### **Importance**

* Evaluates costs and benefits
* Helps management decide whether to **proceed, postpone, or cancel** a project

### **Types of Feasibility**

| Type        | Focus                | Key Points                                                               |
| ----------- | -------------------- | ------------------------------------------------------------------------ |
| Economic    | Cost-benefit         | Determine net benefit, ROI, and investment risks                         |
| Technical   | Technology           | Check if existing tech supports requirements or needs upgrades           |
| Operational | System effectiveness | User acceptance, management support, resource feasibility                |
| Behavioral  | User attitudes       | Training, job changes, acceptance of new methods                         |
| Schedule    | Timeframe            | Can deadlines be met?                                                    |
| Legal       | Compliance           | Meets regulations like Data Protection Acts                              |
| Resource    | Availability         | Time, human resources, dependencies, interference with normal operations |
| Cultural    | Impact               | Check for clashes with local/organizational culture                      |

### **Feasibility Analysis Steps**

1. Form project team; appoint project leader
2. Develop system flowcharts & review DFDs
3. Identify current system deficiencies & set goals
4. Enumerate alternative solutions/candidate systems
5. Evaluate performance & cost-effectiveness
6. Weight criteria & rate alternatives (Weight × Rating → total score)
7. Rank alternatives & select best system
8. Prepare **system proposal** for management approval

### **Feasibility Report (System Proposal)**

**Characteristics:**

* Brief yet comprehensive, understandable for management.
  **Structure:**

1. Cover Letter – Summary of findings & recommendations
2. Table of Contents
3. Overview – Project purpose, scope, departments affected, team members, timeline
4. Detailed Findings – Current methods, efficiency, operating costs, new system objectives/procedures
5. Economic Justification – Costs, ROI, preliminary estimates
6. Recommendations & Conclusion – Most beneficial, cost-effective solution
7. Appendices – Supporting documents & memos

***

## **4. Cost-Benefit Analysis (CBA)**

**Purpose:** Assess **financial and operational value** of the proposed system before implementation. Compares expected **benefits and savings** against **costs**.

### **Cost Categories**

| Classification               | Examples                                                          |
| ---------------------------- | ----------------------------------------------------------------- |
| Development Costs (One-time) | Wages, equipment, personnel, supplies, overheads, consultant fees |
| Operating Costs (Recurring)  | Wages, supplies, maintenance, overheads                           |
| Hardware/Software Costs      | Purchase/lease of computers, peripherals, software                |
| Personnel Costs              | Salaries, insurance, allowances                                   |
| Facility Costs               | Site preparation, wiring, flooring, lighting, HVAC                |
| Supply Costs (Variable)      | Paper, ribbons, disks, consumables                                |

### **Benefit Categories**

| Type       | Characteristic             | Examples                                                           |
| ---------- | -------------------------- | ------------------------------------------------------------------ |
| Tangible   | Measurable, monetary       | Faster response time, error-free output, higher transaction volume |
| Intangible | Hard to measure            | Customer satisfaction, company reputation                          |
| Direct     | Linked directly to project | Disk costs, additional transactions handled                        |
| Indirect   | Overhead-related           | Insurance, utilities                                               |
| Fixed      | Constant                   | Hardware depreciation, insurance                                   |
| Variable   | Changes with usage         | Time saved in automated tasks                                      |

### **Procedure for CBA**

1. Identify all costs & benefits
2. Categorize costs & benefits (Tangible/Intangible, Direct/Indirect, Fixed/Variable)
3. Select evaluation method
4. Interpret results & make decision

### **Methods of Evaluation**

| Method                  | Procedure                                   | Pros                                   | Cons                                                      |
| ----------------------- | ------------------------------------------- | -------------------------------------- | --------------------------------------------------------- |
| Net Benefit Analysis    | Total benefits – total costs                | Easy to calculate & present            | Ignores time value of money                               |
| Present Value (PV)      | Cost & benefits in today’s value            | Accounts for time value                | Relative measure only                                     |
| Net Present Value (NPV) | Discounted benefits – discounted costs      | Accounts for time value, easy          | Relative measure only                                     |
| Payback Analysis        | Investment ÷ annual savings                 | Simple, quick                          | Doesn’t compare multiple alternatives, ignores time value |
| Break-Even Analysis     | Compare cost of present vs candidate system | Easy to understand                     | Ignores time/depreciation value                           |
| Cash-Flow Analysis      | Track accumulated costs & revenues          | Combines payback & break-even benefits | Ignores time value & long-term profitability              |

### **Problems with CBA**

* **Valuation Problems:** Difficult to assign monetary value to intangibles
* **Distortion Problems:** Inaccurate results from incomplete/favoritized data
* **Completeness Problems:** Costs of conducting CBA itself may limit comprehensiveness

## **1. System Planning & Initial Investigation**

**Mnemonic for Steps of Initial Investigation:**\
**“P-B-F-F-D” → Problem, Background, Fact-finding, Fact-analysis, Determination of Feasibility**

* **Problem Definition & Project Initiation** → **P**

* **Background Analysis** → **B**

* **Fact-Finding** → **F**

* **Fact Analysis** → **F**

* **Determination of Feasibility** → **D**

**Tip:** Remember it as **“Please Be Fast For Decision”** 😎

***

## **2. Information Gathering Tools**

**Mnemonic for Techniques:**\
**“L-O-I-Q” → Literature, Observation, Interview, Questionnaire**

* Literature/Forms/Procedures → **L**

* On-Site Observation → **O**

* Interviews → **I**

* Questionnaires → **Q**

**Tip:** Think **“Learn Observing Important Questions”**

**Kinds of Info Required (Organization, Staff, Workflow)** → **O-S-W** → **“Our System Works”**

***

## **3. Feasibility Study Types**

**Mnemonic for Feasibility Types:**\
**“E-T-O-B-S-L-R-C”**

* **E**conomic

* **T**echnical

* **O**perational

* **B**ehavioral

* **S**chedule

* **L**egal

* **R**esource

* **C**ultural

**Tip:** **“Every Tech Operator Builds System’s Legal Resource Culture”** (weird, but it sticks 😁)

***

## **4. Cost-Benefit Analysis (CBA)**

**Mnemonic for Cost Categories:**\
**“D-O-H-P-F-S” → Development, Operating, Hardware/Software, Personnel, Facility, Supply**

**Tip:** **“Develop Our Happy Project Fully Smartly”**

**Mnemonic for Benefit Categories:**\
**“T-I-D-I-F-V” → Tangible, Intangible, Direct, Indirect, Fixed, Variable**

**Tip:** **“The Intelligent Developer Identifies Future Value”**

***





