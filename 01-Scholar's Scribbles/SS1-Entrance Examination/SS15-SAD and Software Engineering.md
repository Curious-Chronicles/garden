---
index: SS15
marks: 5
tags: entrance, SAD, software-enginnering
related: [[]]
status: Completed
created: [[2023-05-06]]
---

## 1. Software development life cycle (SDLC) 

1. Overview of SDLC:
- The Software Development Life Cycle (SDLC) is a structured approach to software development that defines a set of phases, activities, and deliverables to guide the development process from inception to deployment and maintenance.
- SDLC provides a framework for teams to plan, design, develop, test, deploy, and maintain software systems in a systematic and efficient manner.

2. Phases of SDLC:
- Requirements Gathering: In this phase, the software requirements are identified, analyzed, and documented based on stakeholder input and business needs.
- System Design: The system architecture and high-level design are developed, specifying how the software components will interact and fulfill the requirements.
- Implementation: The software is developed, coding the system according to the design specifications and using appropriate programming languages and tools.
- Testing: The developed software is thoroughly tested to ensure that it meets the specified requirements and functions correctly under different scenarios.
- Deployment: The software is deployed to the target environment, including installation, configuration, and data migration if necessary.
- Maintenance: After deployment, the software is maintained, which includes bug fixes, enhancements, and updates throughout its lifecycle.

3. Methodologies and Models:
- Waterfall Model: A sequential approach where each phase is completed before moving to the next. It is rigid and linear, suitable for projects with stable requirements.
- Agile Methodology: Iterative and incremental development approach that emphasizes collaboration, flexibility, and adaptability to changes in requirements. Examples include Scrum, Kanban, and Extreme Programming (XP).
- Spiral Model: Combines elements of the waterfall model and prototyping, involving iterative cycles of risk analysis, prototyping, development, and testing.
- DevOps: A combination of software development (Dev) and IT operations (Ops), emphasizing collaboration, continuous integration, and continuous delivery to streamline the software development and deployment process.

4. Examples:
- Waterfall Model: In a software project following the waterfall model, the development team completes the requirements gathering phase, then moves on to system design, implementation, testing, deployment, and maintenance in a sequential manner.

- Agile Methodology: In an agile development project using the Scrum framework, the development team works in short iterations called sprints, delivering incremental software functionality at the end of each sprint. The requirements are continuously refined and adjusted based on stakeholder feedback.

- DevOps: A software development team adopts DevOps practices, which include using automated build and deployment tools, continuous integration and delivery pipelines, and collaboration between development and operations teams to ensure a seamless and efficient software development and deployment process.

## 2. Requirement gathering techniques and tools 

1. Requirement Gathering:
- Requirement gathering is the process of capturing and documenting the needs and expectations of stakeholders to define the scope and objectives of a software project.
- Effective requirement gathering ensures that the software solution meets the desired functionality, usability, and performance.

2. Requirement Gathering Techniques:
- Interviews: Conducting one-on-one or group interviews with stakeholders to gather their perspectives, insights, and requirements for the software system.
- Workshops: Organizing interactive sessions with stakeholders to facilitate discussions, brainstorming, and collaboration in defining and refining requirements.
- Surveys and Questionnaires: Collecting feedback and information from a larger group of stakeholders using predefined sets of questions to gather their requirements and opinions.
- Prototyping: Creating mock-ups or interactive prototypes of the software system to gather feedback and refine requirements based on user interactions.
- Observation: Directly observing users and stakeholders in their working environment to understand their needs, workflows, and pain points.
- Document Analysis: Reviewing existing documents such as business process documents, user manuals, and technical specifications to extract relevant requirements.

3. Requirement Gathering Tools:
- Requirements Management Tools: Software tools that facilitate the collection, organization, and tracking of requirements throughout the software development lifecycle. Examples include IBM Rational DOORS, JIRA, and Trello.
- Collaboration Tools: Online platforms that enable real-time collaboration and communication between stakeholders, such as Microsoft Teams, Slack, and Google Docs.
- Prototyping Tools: Software tools that allow for the creation of interactive prototypes to visually represent the software's user interface and functionality. Examples include Balsamiq, Axure RP, and Adobe XD.
- Survey Tools: Online platforms for creating and conducting surveys and questionnaires, such as SurveyMonkey, Google Forms, and Qualtrics.
- Visualization Tools: Tools that help visualize and model requirements, such as flowcharts, UML diagrams, mind mapping software, and wireframing tools.

4. Examples:
- During the requirement gathering phase of a software project, the development team conducts interviews with key stakeholders, asking open-ended questions to gather their requirements and expectations.

- In a workshop, the development team and stakeholders collaborate to define and prioritize the software requirements using interactive activities, such as brainstorming and group discussions.

- To gather feedback on a software prototype, the development team creates a clickable mock-up using a prototyping tool like Balsamiq. Users can interact with the prototype and provide feedback on the proposed functionality and user interface.

- A survey is sent to a wide range of users and stakeholders to gather their opinions and preferences regarding the features and usability of the software.

## 3. Unified Modeling Language (UML)             

1. Unified Modeling Language (UML):
- UML is a standardized visual modeling language used in software engineering to design, visualize, and document software systems.
- It provides a set of graphical notations for representing different aspects of a system, including its structure, behavior, and interactions.

2. UML Diagrams:
- UML diagrams are graphical representations that capture different perspectives of a system. They help in understanding, communicating, and documenting the system's architecture and design.

3. Common UML Diagram Types:
- Class Diagram: Represents the static structure of a system, including classes, attributes, methods, relationships, and inheritance.
- Use Case Diagram: Illustrates the interaction between actors (users or external systems) and the system, focusing on functional requirements and user goals.
- Sequence Diagram: Depicts the interactions and message exchanges among objects in a specific scenario, showing the dynamic behavior of the system over time.
- Activity Diagram: Models the workflow or business processes within a system, representing the flow of activities and decisions.
- State Machine Diagram: Describes the different states of an object and its transitions based on events and conditions.
- Component Diagram: Illustrates the high-level components of a system and their dependencies.
- Deployment Diagram: Shows the physical deployment of software components on hardware devices or nodes.

4. Examples:
- A class diagram for a banking system may include classes such as Account, Customer, and Transaction, along with their attributes and relationships.
  
- A use case diagram for an e-commerce website may show actors like Customer, Admin, and Payment Gateway, along with their interactions and the system's functionalities.
  
- A sequence diagram can depict the steps involved in a user making a hotel reservation, showing the interactions between the user, the website, and the hotel booking system.
  
- An activity diagram can illustrate the steps involved in processing an online order, including activities like selecting items, adding to the cart, and making the payment.
  
- A state machine diagram can represent the different states of a user session in a web application, such as logged in, browsing, and logged out.

## 4. Object-oriented design principles                

1. Object-Oriented Programming (OOP):
- Object-oriented programming is a programming paradigm that organizes code around objects, which are instances of classes. It emphasizes encapsulation, inheritance, and polymorphism.

2. Object-Oriented Design Principles:
- SOLID Principles: A set of five design principles that promote software design that is modular, maintainable, and extensible.
  - Single Responsibility Principle (SRP): A class should have only one reason to change, meaning it should have a single responsibility.
  - Open-Closed Principle (OCP): Software entities (classes, modules, functions) should be open for extension but closed for modification.
  - Liskov Substitution Principle (LSP): Subtypes must be substitutable for their base types without altering the correctness of the program.
  - Interface Segregation Principle (ISP): Clients should not be forced to depend on interfaces they do not use. It promotes smaller, focused interfaces.
  - Dependency Inversion Principle (DIP): High-level modules should not depend on low-level modules. Both should depend on abstractions.

3. Design Patterns:
- Design patterns are reusable solutions to common software design problems. They provide proven approaches for solving recurring design challenges.
- Examples of design patterns:
  - Factory Method: Provides an interface for creating objects, but allows subclasses to decide which class to instantiate.
  - Observer: Defines a one-to-many dependency between objects, so that when one object changes state, all its dependents are notified and updated.
  - Strategy: Encapsulates a family of algorithms and makes them interchangeable. The client can choose the algorithm at runtime.
  - Decorator: Allows adding new behavior to an object dynamically by placing it inside wrapper objects that contain the original object.
  - Singleton: Ensures a class has only one instance, providing a global point of access to it.

4. Encapsulation:
- Encapsulation is the principle of bundling data and methods that operate on that data within a class. It hides the internal details and provides a public interface to interact with the object.

5. Inheritance:
- Inheritance is a mechanism in OOP that allows a class (subclass) to inherit properties and behavior from another class (superclass). It promotes code reuse and supports the "is-a" relationship between classes.

6. Polymorphism:
- Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables methods to be invoked on different objects, resulting in different behaviors based on the object's type.

## 5. Design patterns

Design patterns are reusable solutions to common software design problems. They provide proven approaches for solving recurring design challenges, promoting code reusability, maintainability, and extensibility. Here are some commonly discussed design patterns:

1. Creational Patterns:
- Factory Method: Defines an interface for creating objects, but allows subclasses to decide which class to instantiate.
- Singleton: Ensures a class has only one instance, providing a global point of access to it.
- Builder: Separates the construction of complex objects from their representation, allowing the same construction process to create different representations.

2. Structural Patterns:
- Adapter: Converts the interface of a class into another interface that clients expect. It allows incompatible classes to work together.
- Decorator: Dynamically adds new behavior to an object by wrapping it in an object of a decorator class.
- Composite: Treats individual objects and compositions of objects uniformly, allowing clients to treat both in the same way.

3. Behavioral Patterns:
- Observer: Defines a one-to-many dependency between objects, so that when one object changes state, all its dependents are notified and updated.
- Strategy: Encapsulates a family of algorithms and makes them interchangeable. The client can choose the algorithm at runtime.
- Template Method: Defines the skeleton of an algorithm in a base class, allowing subclasses to provide specific implementations of certain steps.

4. Architectural Patterns:
- Model-View-Controller (MVC): Separates the application logic into three interconnected components: model (data), view (presentation), and controller (user input handling).
- Repository: Mediates between the data source (database, file system) and the application, providing a clean separation and hiding the details of data access.

5. Concurrency Patterns:
- Producer-Consumer: Coordinates the interaction between multiple threads, where one or more threads produce data and one or more threads consume it.
- Mutex: Provides mutual exclusion to protect shared resources from simultaneous access by multiple threads.

These design patterns, along with others, serve as valuable tools for software designers and developers to solve common design problems effectively and efficiently. It's important to understand their principles and appropriate use cases to apply them appropriately in software development.

## 6. Software testing methods

Software testing methods are techniques used to verify and validate software applications to ensure they meet the desired requirements and function correctly. Here are some commonly used software testing methods:

1. Unit Testing:
- Definition: In unit testing, individual units or components of a software system are tested independently to ensure their correctness.
- Example: Writing test cases to validate the behavior of a specific function or method in isolation.

2. Integration Testing:
- Definition: Integration testing focuses on testing the interactions between different software components or modules to ensure they work together as intended.
- Example: Testing the integration of multiple modules of an application to check if they communicate correctly and share data accurately.

3. System Testing:
- Definition: System testing involves testing the complete and integrated system to verify that it meets the specified requirements and functions as expected.
- Example: Testing the entire web application, including its user interface, database, and external dependencies, to ensure all features work together seamlessly.

4. Acceptance Testing:
- Definition: Acceptance testing is performed to determine whether a system satisfies the acceptance criteria and meets the needs of the end-users or stakeholders.
- Example: Conducting a series of tests based on user scenarios to validate that the software meets the desired business requirements.

5. Performance Testing:
- Definition: Performance testing assesses the responsiveness, scalability, and stability of a software application under various load conditions.
- Example: Running a performance test to measure the response time and throughput of a web application when subjected to a high number of concurrent users.

6. Security Testing:
- Definition: Security testing aims to identify vulnerabilities and weaknesses in the software system to ensure the protection of sensitive data and prevent unauthorized access.
- Example: Conducting penetration testing to simulate attacks and uncover any security loopholes in the application.

7. Regression Testing:
- Definition: Regression testing is performed to ensure that changes or updates in the software do not introduce new bugs or break existing functionality.
- Example: Re-running a comprehensive set of test cases after making changes to the software to ensure that previously working features still function correctly.

These software testing methods help ensure the quality, reliability, and robustness of software applications. Different methods are applied at different stages of the software development life cycle to detect and resolve issues early, resulting in more reliable and user-friendly software products.

## 7. Agile software development

Agile software development is an iterative and incremental approach to software development that emphasizes flexibility, collaboration, and responsiveness to change. It promotes adaptive planning, continuous improvement, and early delivery of working software. Here are some key topics and sub-topics related to Agile software development:

1. Agile Principles:
- Definition: Agile principles are a set of guiding values and beliefs that drive the Agile software development approach.
- Examples: Customer collaboration over contract negotiation, responding to change over following a plan, delivering working software frequently, etc.

2. Scrum:
- Definition: Scrum is an Agile framework that provides a structured approach for managing and delivering software projects.
- Examples: Daily Scrum meetings, Sprint planning, Sprint review, Sprint retrospective, etc.

3. Kanban:
- Definition: Kanban is an Agile methodology that focuses on visualizing work, limiting work in progress, and optimizing flow.
- Examples: Kanban board, WIP limits, pull-based system, continuous flow, etc.

4. User Stories:
- Definition: User stories are short, simple descriptions of desired functionality from the end-user perspective.
- Examples: "As a user, I want to be able to create a new account," "As an admin, I want to be able to generate reports," etc.

5. Agile Estimation and Planning:
- Definition: Agile estimation and planning involve techniques for estimating project efforts, breaking down work into manageable tasks, and prioritizing them.
- Examples: Story points, planning poker, backlog grooming, release planning, etc.

6. Continuous Integration and Continuous Delivery (CI/CD):
- Definition: CI/CD is an Agile practice that focuses on automating the integration, testing, and deployment of software changes to ensure frequent and reliable releases.
- Examples: Automated build and test processes, version control, continuous deployment pipelines, etc.

7. Agile Roles and Responsibilities:
- Definition: Agile teams have specific roles and responsibilities that contribute to the success of the project.
- Examples: Scrum Master, Product Owner, Development Team, stakeholders, etc.

## 8. Project management techniques (PERT, CPM, Gantt chart)

Project management techniques are methodologies and tools used to plan, schedule, and control projects. They help project managers and teams effectively manage resources, activities, and timelines. Here are the key topics and sub-topics related to project management techniques:

1. PERT (Program Evaluation and Review Technique):
- Definition: PERT is a project management technique used to analyze and represent the tasks and activities involved in completing a project, considering their dependencies and uncertainties.
- Examples: PERT charts, critical path analysis, estimating task durations, identifying critical activities, etc.

2. CPM (Critical Path Method):
- Definition: CPM is a project management technique used to identify the longest sequence of dependent activities, known as the critical path, and determine the project's minimum duration.
- Examples: CPM diagrams, forward and backward pass calculations, slack time analysis, resource leveling, etc.

3. Gantt Chart:
- Definition: A Gantt chart is a visual representation of a project schedule that shows tasks, their durations, and their dependencies over time.
- Examples: Bar chart with task bars, milestones, dependencies, resource allocation, progress tracking, etc.

4. Resource Management:
- Definition: Resource management involves identifying and allocating resources needed for project activities, ensuring optimal utilization, and balancing resource availability and project requirements.
- Examples: Resource allocation charts, resource leveling techniques, resource optimization strategies, resource utilization tracking, etc.

5. Risk Management:
- Definition: Risk management involves identifying, assessing, and managing risks that may affect project objectives, and implementing strategies to mitigate or respond to them.
- Examples: Risk identification and analysis, risk mitigation planning, risk response strategies, contingency planning, etc.

6. Project Tracking and Control:
- Definition: Project tracking and control involve monitoring project progress, comparing actual progress against the planned schedule, identifying deviations, and implementing corrective actions.
- Examples: Earned value analysis, progress tracking metrics, variance analysis, change management, project performance reporting, etc.

## 9. Software quality assurance (SQA)

Software Quality Assurance (SQA) refers to the systematic and planned set of activities designed to ensure that software products and processes meet specified quality standards. It involves monitoring and improving the entire software development life cycle to deliver high-quality software. Here are the key topics and sub-topics related to Software Quality Assurance:

1. Quality Planning:
- Definition: Quality planning involves defining the quality objectives and establishing the processes and activities needed to achieve those objectives.
- Examples: Defining quality standards, setting quality goals, creating quality assurance plans, identifying quality metrics, etc.

2. Quality Control:
- Definition: Quality control focuses on identifying defects or deviations from established quality standards during the software development process.
- Examples: Conducting inspections, reviews, and audits, performing testing and analysis, tracking defects, implementing corrective actions, etc.

3. Test Planning and Execution:
- Definition: Test planning involves defining the test objectives, selecting appropriate testing techniques, and creating test plans. Test execution involves running tests and analyzing the results.
- Examples: Creating test cases, test scenarios, and test scripts, conducting functional and non-functional testing, regression testing, performance testing, etc.

4. Configuration Management:
- Definition: Configuration management is the process of managing and controlling changes to software artifacts, including version control, release management, and change management.
- Examples: Version control systems, release management processes, change request tracking, configuration identification and control, etc.

5. Process Improvement:
- Definition: Process improvement focuses on continuously improving the software development processes to enhance quality, efficiency, and effectiveness.
- Examples: Conducting process assessments, implementing process improvement frameworks (e.g., CMMI), analyzing process metrics, adopting best practices, etc.

6. Defect Management:
- Definition: Defect management involves identifying, tracking, prioritizing, and resolving defects found during the development and testing phases.
- Examples: Defect tracking systems, defect triaging, root cause analysis, defect resolution processes, defect trend analysis, etc.

These topics cover the essential aspects of Software Quality Assurance (SQA). SQA ensures that software products are developed and delivered with high quality, meeting user expectations and industry standards. Understanding these topics helps in implementing effective quality assurance practices and improving overall software development processes.

## 10. Software maintenance and evolution.

Software Maintenance and Evolution refers to the process of managing, enhancing, and modifying software systems after their initial development to meet changing user requirements and address issues. Here are the key topics and sub-topics related to software maintenance and evolution:

1. Types of Maintenance:
- Corrective Maintenance: Fixing defects or errors in the software.
- Adaptive Maintenance: Modifying the software to adapt to changes in the environment or requirements.
- Perfective Maintenance: Enhancing the software to improve its performance, maintainability, or user experience.
- Preventive Maintenance: Making changes to prevent potential future issues.

2. Software Evolution:
- Definition: Software evolution refers to the long-term process of changing and improving software systems over time.
- Examples: Adding new features, optimizing performance, refactoring code, migrating to new platforms or technologies, etc.

3. Maintenance Processes:
- Problem Analysis: Identifying and analyzing issues reported by users or discovered during testing.
- Impact Analysis: Assessing the potential effects of proposed changes on the software system.
- Change Implementation: Applying modifications to the software system while ensuring its integrity and stability.
- Verification and Validation: Testing the modified software to ensure that it functions correctly and meets the desired requirements.
- Release Management: Planning and coordinating the deployment of software updates or patches.

4. Software Documentation:
- Importance of Documentation: Maintaining accurate and up-to-date documentation to aid in understanding, maintaining, and evolving the software system.
- Types of Documentation: Requirements documentation, design documentation, user manuals, change logs, etc.

5. Legacy Systems and Modernization:
- Definition: Legacy systems are older software systems that may be outdated, difficult to maintain, or incompatible with current technologies.
- Modernization Techniques: Reengineering, restructuring, or migrating legacy systems to modern platforms or architectures.

6. Configuration Management:
- Definition: Configuration management involves managing software configurations, versions, and dependencies to support maintenance and evolution.
- Examples: Version control systems, dependency management tools, configuration management plans, etc.
