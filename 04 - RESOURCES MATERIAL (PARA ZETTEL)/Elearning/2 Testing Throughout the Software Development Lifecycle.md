---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--sentence%208.png)

# 2. Testing Throughout the Software Development Lifecycle

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201179.svg)Subject|[![](Dashboard/Attachments/icons_graduate%208.png)ISTQB - Certified Tester Foundation Level](../Subjects/ISTQB%20-%20Certified%20Tester%20Foundation%20Level%20116035acaece4b219ecbbed5e0181a76.html)|
|![](Dashboard/Attachments/calendar_gray%201241.svg)Date Created|@March 22, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20932.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20660.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20479.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20111.svg)Last Edited|@February 17, 2023 6:21 PM|

[Keyword](#a927b2ed-83cc-42ca-a111-0e4dff982eb1)

[2.1. Software Development Lifecycle Models](#09fb431e-b9b6-4102-b1ed-111905977f81)

[2.1.1. Software Development and Software Testing (K2)](#69644d22-c170-4d5e-a23b-b8704390be51)

[2.1.2. Software Development Lifecycle Models in Context (K1)](#d6e1218b-4b07-4442-999d-2a6924f02203)

[2.2. Test Levels](#f5c3eb98-c036-44c7-be42-1bb099fd019b)

[2.2.1. Component Testing (K2)](#fb8deebd-d4d4-4e3c-a1e6-c041d85879f2)

[2.2.2. Integration Testing (K2)](#95e1ec34-97d1-461f-a96c-fc2464e08302)

[2.2.3. System Testing (K2)](#1220ca17-de09-4df2-85c5-c4fa729b0fbf)

[2.2.4. Acceptance Testing (K2)](#ae2304fb-c56d-47ad-8349-0fbbbbbcd7de)

[2.3. Test Types](#c70b198e-d1b8-493a-91dc-542302074115)

[2.3.1. Functional Testing (K2)](#cb1440f0-1359-4795-ae18-75613fb23940)

[2.3.2. Non-functional Testing (K2)](#dd3eea7f-a5d4-4e85-a8b6-6ce3f86b51b4)

[2.3.3. White-box Testing (K2)](#ad3fa7cc-5739-482e-a365-f4ce142a3c0f)

[2.3.4. Change-related Testing (K2)](#57bbefa2-fc63-45c1-bbb5-8032d61fae6a)

[2.3.5. Test Types and Test Levels (K2)](#64f80190-f9b9-4af2-9629-4e119ea0ac97)

[2.4. Maintenance Testing](#7b40b0f1-85b8-489e-a594-5ccfa78ef783)

[2.4.1. Triggers for Maintenance (K2)](#2edba7e8-3de3-4963-a972-ff72c856e29a)

[2.4.2. Impact Analysis for Maintenance (K2)](#e80fc3b3-3aab-423b-8200-b2b0d1523e92)

[Review Questions](#eb248286-97c6-477c-854b-051fe445ae37)

Keyword

|Keyword|Description|
|---|---|
|acceptance testing|Formal testing with respect to user needs, requirements, and business processes conducted to determine whether or not a system satisfies the acceptance criteria and to enable the user, customers or other authorized entity to determine whether or not to accept the system.|
|alpha testing|Simulated or actual operational testing conducted in the developer's test environment, by roles outside the development organisation.|
|beta testing|Simulated or actual operational testing conducted at an external site, by roles outside the development organisation.|
|change-related testing|A type of testing initiated by modification to a component or system.|
|commercial off-the-shelf (COTS)|A software product that is developed for the general market, i.e. for a large number of customers, and that is delivered to many customers in identical format.|
|component testing|The testing of individual hardware or software components.|
|component integration testing|Testing performed to expose defects in the interfaces and interaction between integrated components.|
|confirmation testing|Dynamic testing conducted after fixing defects with the objective to confirm that failures caused by those defects do not occur anymore.|
|contractual acceptance testing|Acceptance testing conducted to verify whether a system satisfies its contractual requirements.|
|functional testing|Testing conducted to evaluate the compliance of a component or system with functional requirements.|
|impact analysis|The identification of all work products affected by a change, including an estimate of the resources needed to accomplish the change.|
|integration testing|Testing performed to expose defects in the interfaces and in the interactions between integrated components or systems.|
|maintenance testing|Testing the changes to an operational system or the impact of a changed environment to an operational system.|
|non-functional testing|Testing conducted to evaluate the compliance of a component or system with non-functional requirements.|
|operational acceptance testing|Operational testing in the acceptance test phase, typically performed in a (simulated) operational environment by operations and/or systems administration staff focusing on operational aspects, e.g., recoverability, resource-behavior, install-ability and technical compliance.|
|regression testing|Testing of a previously tested component or system following modification to ensure that defects have not been introduced or have been uncovered in unchanged areas of the software, as a result of the changes made.|
|regulatory acceptance testing|Acceptance testing conducted to verify whether a system conforms to relevant laws, policies and regulations.|
|system testing|Testing an integrated system to verify that it meets specified requirements.|
|system integration testing|Testing the combination and interaction of systems.|
|test basis|The body of knowledge used as the basis for test analysis and design.|
|test case|A set of preconditions, inputs, actions (where applicable), expected results and post-conditions, developed based on test conditions.|
|test environment|An environment containing hardware, instrumentation, simulators, software tools, and other support elements needed to conduct a test.|
|test level|A specific instantiation of a test process.|
|test object|The component or system to be tested.|
|test objective|A reason or purpose for designing and executing a test.|
|test type|A group of test activities based on specific test objectives aimed at specific characteristics of a component or system.|
|user acceptance testing|Acceptance testing conducted in a real or simulated operational environment by intended users focusing their needs, requirements and business processes.|
|white-box testing|Testing based on an analysis of the internal structure of the component or system.|

# 2.1. Software Development Lifecycle Models

**FL-2.1.1** _Explain the relationships between software development activities and test activities in the software development lifecycle (K2)_

**FL-2.1.2** _Identify reasons why software development lifecycle models must be adapted to the context of project and product characteristics (K1)_

A software development lifecycle model describes the types of activity performed at each stage in a software development project, and how the activities relate to one another logically and chronologically.

There are a number of different software development lifecycle models, each of which require different approaches to testing.

[ISTQB Foundation Syllabus]

The basic steps in software development are shown below:

[![](Dashboard/Attachments/Untitled%2018.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled.png)

Each phase produces deliverable required by the next phase.

2.1.1. Software Development and Software Testing (K2)

**FL-2.1.1** _Explain the relationships between software development activities and test activities in the software development lifecycle (K2)_

It is an important part of a tester's role to be familiar with the common software development lifecycle models so that appropriate testing activities can take place.

In any software development lifecycle model, there are several characteristics of good testing:

- For every development activity, there is a corresponding test activity

- Each test level has test objectives specific to that level

- Test analysis and design for a given test level begin during the corresponding development activity

- Testers participate in discussions to define and refine requirements and design, and are involved in reviewing work products (e.g., requirements, design, user stories, etc.) as soon as drafts are available

No matter which software development lifecycle model is chosen, test activities should start in the early stages of the lifecycle, adhering to the testing principle of early testing.

This syllabus categories common software development lifecycle models as follows:

- Sequential development models

- Iterative and incremental development models

Sequential development models

A sequential development model describes the software development process as a linear, sequential flow of activities.

This means that any phase in the development process should begin when the previous phase is complete.

In theory, there is no overlap of phases, but in practice, it is beneficial to have early feedback from the following phase.

_**The Waterfall model**_

In the Waterfall model, the development activities (e.g., requirements analysis, design, coding, testing) are completed one after another.

[![](Dashboard/Attachments/Untitled%201%206.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%201.png)

In this model, testing is viewed as a separate phase which takes place after development has been completed.

_**The V-model**_

Unlike the Waterfall model, the V-model integrates the testing process into the development process, implementing the principle of early testing.

[![](Dashboard/Attachments/Untitled%202%204.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%202.png)

Further, the V-model includes test levels associated with each corresponding development phase, which further supports early testing (see [section 2.2](2%20Testing%20Throughout%20the%20Software%20Development%20Life%2038645f60409f48fe9f3fe059f0d92a15.html) for a discussion of test levels).

In this model, the execution of tests associated with each test level proceeds sequentially, but in some cases overlapping occurs.

_**Sequential development models**_

Sequential development models deliver software that contains the complete set of features, but typically require months or years for delivery to stakeholders and users.

Iterative and incremental development models

[![](Dashboard/Attachments/Untitled%203%203.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%203.png)

_**Incremental development**_

Incremental development involves establishing requirements, designing, building, and testing a system in pieces, which means that the software’s features grow incrementally.

The size of these feature increments varies, with some methods having larger pieces and some smaller pieces.

The feature increments can be as small as a single change to a user interface screen or new query option.

_**Using iterations**_

Iterative development occurs when groups of features are specified, designed, built, and tested together in a series of cycles, often of a fixed duration.

Iterations may involve changes to features developed in earlier iterations, along with changes in project scope.

Each iteration delivers working software which is a growing subset of the overall set of features until the final software is delivered or development is stopped.

_**Examples of iterative development models**_

Examples include:

- Rational Unified Process: Each iteration tends to be relatively long (e.g., two to three months), and the feature increments are correspondingly large, such as two or three groups of related features

- Scrum: Each iteration tends to be relatively short (e.g., hours, days, or a few weeks), and the feature increments are correspondingly small, such as a few enhancements and/or two or three new features

- Kanban: Implemented with or without fixed-length iterations, which can deliver either a single enhancement or feature upon completion, or can group features together to release at once

- Spiral (or prototyping): Involves creating experimental increments, some of which may be heavily re-worked or even abandoned in subsequent development work

_**Overlapping and iterating test levels**_

Components or systems developed using these methods often involve overlapping and iterating test levels throughout development.

Ideally, each feature is tested at several test levels as it moves towards delivery.

In some cases, teams use continuous delivery or continuous deployment, both of which involve significant automation of multiple test levels as part of their delivery pipelines.

Many development efforts using these methods also include the concept of self-organizing teams, which can change the way testing work is organised as well as the relationship between testers and developers.

_**A growing system**_

These methods form a growing system, which may be released to end-users on a feature-by-feature basis, on an iteration-by-iteration basis, or in a more traditional major-release fashion.Regardless of whether the software increments are released to end-users, regression testing is increasingly important as the system grows.

_**Delivery**_

In contrast to sequential models, iterative and incremental models may deliver usable software in weeks or even days but may only deliver the complete set of requirements product over a period of months or even years.

For more information on software testing in the context of Agile development, see ISTQB-AT Foundation Level Agile Tester Extension Syllabus, Black 2017, Crispin 2008, and Gregory 2018.

2.1.2. Software Development Lifecycle Models in Context (K1)

**FL-2.1.2** _Identify reasons why software development lifecycle models must be adapted to the context of project and product characteristics (K1)_

_**Adapting to the project/product context**_

Software development lifecycle models must be selected and adapted to the context of project and product characteristics.

An appropriate software development lifecycle model should be selected and adapted based on the project goal, the type of product being developed, business priorities (e.g., time-to-market), and identified product and project risks.

For example, the development and testing of a minor internal administrative system should differ from the development and testing of a safety-critical system such as an automobile’s brake control system.

As another example, in some cases organisational and cultural issues may inhibit communication between team members, which can impede iterative development.

_**May need to combine test levels**_

Depending on the context of the project, it may be necessary to combine or reorganize test levels and/or test activities.

For example,

> For the integration of a Commercial Off-The-Shelf (COTS) software product into a larger system, the purchaser may perform integration testing at the system level (e.g., integration to the infrastructure and other systems, or system deployment) and at the acceptance testing level(functional and non-functional, along with user acceptance testing and operational acceptance testing).

> See section 2.2 for a discussion of test levels and section 2.3 for a discussion of test types.

_**May need to combine lifecycle models**_

In addition, software development lifecycle models themselves may be combined.For example, a V model may be used for the development and testing of the back-end systems and their integrations, while an Agile development model may be used to develop and test the front-end user interface (UI) and functionality.Prototyping may be used early in a project, with an incremental development model adopted once the experimental phase is complete.

_**The Internet of Things**_

Internet of Things (IoT) systems, which consist of many different objects, such as devices, products, and services, typically apply separate software development lifecycle models for each object.

This presents a particular challenge for the development of Internet of Things system versions.

Additionally, the software development lifecycle of such objects places stronger emphasis on the later phases of the software development lifecycle after they have been introduced to operational use (e.g., operate, update, and decommission phases).

_**Software development models must be adapted to the context**_

Reasons why software development models must be adapted to the context of project and product characteristics can be:

- Difference in product risks of systems (complex or simple project)

- Many business units can be part of a project or program (combination of sequential and agile development)

- Short time to deliver a product to the market (merge of test levels and/or integration of test types in test levels)

# 2.2. Test Levels

**FL-2.2.1** _Compare the different levels of testing from the perspective of objectives, test basis, test objects, approaches and responsibilities, and typical defects and failures (K2)_

[![](Dashboard/Attachments/Untitled%204%202.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%204.png)

Test levels are groups of test activities that are organised and managed together.

Each test level is an instance of the test process, consisting of the activities described in [section 1.4](1-%20Fundamentals%20of%20Testing%20dee706310d134005a409a3a472aba8ea.html), performed in relation to software at a given level of development, from individual units or components to complete systems or, where applicable, systems of systems.

Test levels are related to other activities within the software development lifecycle.

The test levels used in this syllabus are:

- Component testing

- Integration testing

- System testing

- Acceptance testing

Test levels are characterized by the following attributes:

- Specific objectives

- Test basis, referenced to derive test cases

- Test object (i.e., what is being tested)

- Typical defects and failures

- Specific approaches and responsibilities

For every test level, a suitable test environment is required.

In acceptance testing, for example, a production-like test environment is ideal, while in component testing the developers typically use their own development environment.

2.2.1. Component Testing (K2)

Objectives of component testing

Component testing (also known as unit, module, or program testing) focuses on components that are separately testable.

Objectives include:

- Reducing risk

- Verifying whether the functional and non-functional behaviors of the component are as designed and specified

- Building confidence in the component’s quality

- Finding defects in the component

- Preventing defects from escaping to higher levels of testing

_**May use automated regression**_

In some cases, especially in incremental and iterative development models (e.g., Agile) where code changes are ongoing, automated component regression tests play a key role in building confidence that changes have not broken existing components.

_**May be done in isolation**_

Component testing is often done in isolation from the rest of the system, depending on the software development lifecycle model and the system, which may require mock objects, service virtualization, harnesses, stubs, and drivers.

Component testing may cover:

- Functionality (e.g., correctness of calculations)

- Non-functional characteristics (e.g., searching for memory leaks)

- Structural properties(e.g., decision testing)

Test basis

Examples of work products that can be used as a test basis for component testing include:

- Detailed design

- Code

- Data model

- Component specifications

Test Objects

Typical test objects include:

- Components, units, modules, and programs

- Code and data structures

- Classes

- Database modules

Typical defects and failures

Examples of typical defects and failures for component testing include:

- Incorrect functionality (e.g., not as described in design specifications)

- Data flow problems

- Incorrect code and logic

Defects are typically fixed as soon as they are found, often with no formal defect management.

However, when developers do report defects, this provides important information for root cause analysis and process improvement.

Specific approaches and responsibilities

Component testing is usually performed by the developer who wrote the code, but it at least requires access to the code being tested.

Developers may alternate component development with finding and fixing defects.

_**Writing the tests before the code**_

Developers will often write and execute tests after having written the code for a component.

However, in Agile development especially, writing automated component test cases may precede writing application code.

For example, consider test driven development (TDD).

> Test driven development is highly iterative and is based on cycles of developing automated test cases, then building and integrating small pieces of code, then executing the component tests, correcting any issues, and re-factoring the code.

> This process continues until the component has been completely built and all component tests are passing.

> Test driven development is an example of a test-first approach.

> While test driven development originated in eXtreme Programming (XP), it has spread to other forms of Agile and also to sequential lifecycles (see ISTQB-AT Foundation Level Agile Tester Extension Syllabus).

2.2.2. Integration Testing (K2)

Objectives of integration testing

Integration testing focuses on interactions between components or systems.

Objectives include:

- Reducing risk

- Verifying whether the functional and non-functional behaviors of the interfaces are as designed and specified

- Building confidence in the quality of the interfaces

- Finding defects (which may be in the interfaces themselves or within the components or systems)

- Preventing defects from escaping to higher levels of testing

As with component testing, in some cases automated integration regression tests provide confidence that changes have not broken existing interfaces, components, or systems.

_**The levels of integration testing**_

There are two different levels of integration testing described in this syllabus, which may be carried out on test objects of varying size as follows:

_**Component integration testing**_

Component integration testing focuses on the interactions and interfaces between integrated components.

Component integration testing is performed after component testing and is generally automated.

In iterative and incremental development, component integration tests are usually part of the continuous integration process.

_**System integration testing**_

System integration testing focuses on the interactions and interfaces between systems, packages, and microservices.

System integration testing can also cover interactions with, and interfaces provided by, external organisations (e.g., web services).

In this case, the developing organisation does not control the external interfaces, which can create various challenges for testing (e.g., ensuring that test-blocking defects in the external organisation’s code are resolved, arranging for test environments, etc.).

System integration testing may be done after system testing or in parallel with ongoing system testing activities (in both sequential development and iterative and incremental development).

Test basis

Examples of work products that can be used as a test basis for integration testing include:

- Software and system design

- Sequence diagrams

- Interface and communication protocol specifications

- Use cases

- Architecture at component and system level

- Workflows

- External interface definitions

Test Objects

Typical test objects include:

- Subsystems

- Databases

- Infrastructure

- Interfaces

- APIs

- Micro-services

Typical defects and failures

Examples of typical defects and failures for component testing include:

- Incorrect data, missing data, or incorrect data encoding

- Incorrect sequencing or timing of interface calls

- Interface mismatch

- Failures in communication between components

- Unhand-led or improperly handled communication failures between components

- Incorrect assumptions about the meaning, units, or boundaries of the data being passed between components

Examples of typical defects and failures for system integration testing include:

- Inconsistent message structures between systems

- Incorrect data, missing data, or incorrect data encoding

- Interface mismatch

- Failures in communication between systems

- Unhand-led or improperly handled communication failures between systems

- Incorrect assumptions about the meaning, units, or boundaries of the data being passed between systems

- Failure to comply with mandatory security regulations

Specific approaches and responsibilities

Component integration tests and system integration tests should concentrate on the integration itself.

> For example, if integrating module A with module B, the test should focus on the communication between the modules, not the functionality of the individual modules, as that should have been covered during component testing.  
>   
> If integrating system X with system Y, the test should focus on the communication between the systems, not the functionality of the individual systems, as that should have been covered during system testing.  
>   
> Functional, non-functional, and structural test types are applicable.

_**Integration testing responsibilities**_

Component integration testing is often the responsibility of developers.

System integration testing is generally the responsibility of testers.

Ideally, testers performing system integration testing should understand the architecture, and should have influenced integration planning.

_**Systematic integration strategies**_

If integration tests and the integration strategy are planned before components or systems are built, those components or systems can be built in the order required for most efficient testing.

[![](Dashboard/Attachments/Untitled%205%202.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%205.png)

Systematic integration strategies may be based on the system architecture (e.g., top-down and bottom-up), functional tasks, transaction processing sequences, or some other aspect of the system or components.

In order to simplify defect isolation and detect defects early, integration should normally be incremental (i.e., a small number of additional components or systems at a time) rather than “big bang” (i.e., integrating all components or systems in one single step).

A risk analysis of the most complex interfaces can help to focus the integration testing.

_**Isolating defects**_

The greater the scope of integration, the more difficult it becomes to isolate defects to a specific component or system, which may lead to increased risk and additional time for troubleshooting.

This is one reason that continuous integration (which implements a functional integration strategy), where software is integrated on a component-by-component basis, has become common practice.

Such continuous integration often includes automated regression testing, ideally at multiple test levels.

2.2.3. System Testing (K2)

Objectives of system testing

System testing focuses on the behavior and capabilities of a whole system or product (e.g., an application, a hardware/software system, an operating system, etc.), often considering the end-to-end tasks the system can perform and the non-functional behaviors it exhibits while performing those tasks.

Objectives include:

- Reducing risk

- Verifying whether the functional and non-functional behaviors of the system are as designed and specified

- Validating that the system is complete and will work as expected

- Building confidence in the quality of the system as a whole

- Finding defects

- Preventing defects from escaping to acceptance testing or production

For certain systems, verifying data quality may be an objective.

As with component testing and integration testing, in some cases automated system regression tests provide confidence that changes have not broken existing features or end-to-end capabilities.

_**The information from system testing**_

System testing often produces information that is used by stakeholders to make release decisions.

System testing may also satisfy legal or regulatory requirements or standards.

_**The test environment**_

The test environment should ideally correspond to the final target or production environment.

Test basis

Examples of work products that can be used as a test basis for system testing include:

- System and software requirement specifications (functional and non-functional)

- Risk analysis reports

- Use cases

- Epics and user stories

- Models of system behavior

- State diagrams

- System and user manuals

Test Objects

Typical test objects include:

- Applications

- Hardware/software systems

- Operating systems

- System under test (SUT)

- System configuration and configuration data

Typical defects and failures

Examples of typical defects and failures for system testing include:

- Incorrect calculations

- Incorrect or unexpected system functional or non-functional behavior

- Incorrect control and/or data flows within the system

- Failure to properly and completely carry out end-to-end functional tasks

- Failure of the system to work properly in the production environment(s)

- Failure of the system to work as described in system and user manuals

Specific approaches and responsibilities

_**The focus of system testing**_

System testing should focus on the overall, end-to-end behavior of the system as a whole, both functional and non-functional.

System testing should use the most appropriate techniques (see chapter 4) for the aspect(s)of the system to be tested.

For example, a decision table may be created to verify whether functional behavior is as described in business rules.

_**Independence**_

Independent testers typically carry out system testing.

Defects in specifications (e.g., missing user stories, incorrectly stated business requirements, etc.) can lead to a lack of understanding of, or disagreements about, expected system behavior.

Such situations can cause false positives and false negatives, which waste time and reduce defect detection effectiveness, respectively.

Early involvement of testers in user story refinement, or static testing activities such as reviews, is important in part because it reduces the incidence of such situations.

2.2.4. Acceptance Testing (K2)

Objectives of acceptance testing

Acceptance testing, like system testing, typically focuses on the behavior and capabilities of a whole system or product.

Objectives of acceptance testing include:

- Establishing confidence in the quality of the system as a whole

- Validating that the system is complete and will work as expected

- Verifying that functional and non-functional behaviors of the system are as specified

Acceptance testing may produce information to assess the system’s readiness for deployment and use by the customer (end user).

Defects may be found during acceptance testing, but finding defects is often not an objective, and finding a significant number of defects during acceptance testing may in some cases be considered a major project risk.

Acceptance testing may also satisfy legal or regulatory requirements or standards.

_**Common forms of acceptance testing**_

Common forms of acceptance testing include the following:

- User acceptance testing

- Operational acceptance testing

- Contractual and regulatory acceptance testing

- Alpha and beta testing

Each is described in the following four subsections.

User acceptance testing (UAT)

[![](Dashboard/Attachments/Untitled%206%202.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%206.png)

The acceptance testing of the system by users is typically focused on validating the fitness for use of the system by intended users in a real or simulated operational environment.

The main objective is building confidence that the users can use the system to meet their needs, fulfill requirements, and perform business processes with minimum difficulty, cost, and risk.

Operational acceptance testing (OAT)

[![](Dashboard/Attachments/Untitled%207%202.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%207.png)

The acceptance testing of the system by operations or systems administration staff is usually performed in a (simulated) production environment.

The tests focus on operational aspects, and may include:

- Testing of backup and restore

- Installing, uninstalling, and upgrading

- Disaster recovery

- User management

- Maintenance tasks

- Data load and migration tasks

- Checks for security vulnerabilities

- Performance testing

_**The main objective**_

The main objective of operational acceptance testing is building confidence that the operators or system administrators can keep the system working properly for the users in the operational environment, even under exceptional or difficult conditions.

Contractual and regulatory acceptance testing

_**Contractual acceptance testing**_

[![](Dashboard/Attachments/Untitled%208%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%208.png)

Contractual acceptance testing is performed against a contract’s acceptance criteria for producing custom-developed software.

Acceptance criteria should be defined when the parties agree to the contract.

Contractual acceptance testing is often performed by users or by independent testers.

_**Regulatory acceptance testing**_

[![](Dashboard/Attachments/Untitled%209%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%209.png)

Regulatory acceptance testing is performed against any regulations that must be adhered to, such as government, legal, or safety regulations.

Regulatory acceptance testing is often performed by users or by independent testers, sometimes with the results being witnessed or audited by regulatory agencies.

_**The main objective**_

The main objective of contractual and regulatory acceptance testing is building confidence that contractual or regulatory compliance has been achieved.

Alpha and beta testing

Alpha and beta testing are typically used by developers of commercial off-the-shelf (COTS) software who want to get feedback from potential or existing users, customers, and/or operators before the software product is put on the market.

[![](Dashboard/Attachments/Untitled%2010%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2010.png)

Alpha testing is performed at the developing organisation’s site, not by the development team, but by potential or existing customers, and/or operators or an independent test team.

[![](Dashboard/Attachments/Untitled%2011%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2011.png)

Beta testing is performed by potential or existing customers, and/or operators at their own locations.

Beta testing may come after alpha testing or may occur without any preceding alpha testing having occurred.

_**The main objectives**_

One objective of alpha and beta testing is building confidence among potential or existing customers, and/or operators,that they can use the system under normal, everyday conditions, and in the operational environment(s) to achieve their objectives with minimum difficulty, cost, and risk.

Another objective may be the detection of defects related to the conditions and environment(s) in which the system will be used, especially when those conditions and environment(s) are difficult to replicate by the development team.

Test basis

Examples of work products that can be used as a test basis for any form of acceptance testing include:

- Business processes

- User or business requirements

- Regulations, legal contracts, and standards

- Use cases

- System requirements

- System or user documentation

- Installation procedures

- Risk analysis reports

In addition, as a test basis for deriving test cases for operational acceptance testing, one or more of the following work products can be used:

- Backup and restore procedures

- Disaster recovery procedures

- Non-functional requirements

- Operations documentation

- Deployment and installation instructions

- Performance targets

- Database packages

- Security standards or regulations

Test Objects

Typical test objects for any form of acceptance testing include:

- System under test

- System configuration and configuration data

- Business processes for a fully integrated system

- Recovery systems and hot sites (for business continuity and disaster recovery testing)

- Operational and maintenance processes

- Forms

- Reports

- Existing and converted production data

- Configuration data

Typical defects and failures

Examples of typical defects for any form acceptance testing include:

- System workflows do not meet business or user requirements

- Business rules are not implemented correctly

- System does not satisfy contractual or regulatory requirements

- Non-functional failures such as security vulnerabilities, inadequate performance efficiency under high loads, or improper operation on a supported platform

Specific approaches and responsibilities

Acceptance testing is often the responsibility of the customers, business users, product owners, or operators of a system, and other stakeholders may be involved as well.

Acceptance testing is often thought of as the last test level in a sequential development lifecycle, but it may also occur at other times, for example:

- Acceptance testing of a COTS software product may occur when it is installed or integrated

- Acceptance testing of a new functional enhancement may occur before system testing

_**Using various forms of acceptance testing**_

In iterative development, project teams can employ various forms of acceptance testing at the end of each iteration, such as those focused on verifying a new feature against its acceptance criteria and those focused on validating that a new feature satisfies the users’ needs.

In addition, alpha tests and beta tests may occur, either at the end of each iteration, after the completion of each iteration, or after a series of iterations.

User acceptance tests, operational acceptance tests, regulatory acceptance tests, and contractual acceptance tests also may occur, either at the close of each iteration, after the completion of each iteration, or after a series of iterations.

# 2.3. Test Types

**FL-2.3.1** _Compare functional, non-functional, and white-box testing (K2)_

**FL-2.3.2** _Recognize that functional, non-functional, and white-box tests occur at any test level (K1)_

**FL-2.3.3** _Compare the purposes of confirmation testing and regression testing (K2)_

[![](Dashboard/Attachments/Untitled%2012%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2012.png)

A test type is a group of dynamic test activities aimed at testing specific characteristics of a software system, or a part of a system, based on specific test objectives.

Such objectives may include:

- Evaluating functional quality characteristics, such as completeness, correctness, and appropriateness

- Evaluating non-functional quality characteristics, such as reliability, performance efficiency, security, and usability

- Evaluating whether the structure or architecture of the software or system is correct, complete, and as specified

- Evaluating the effects of changes, such as confirming that defects have been fixed (confirmation testing) and looking for unintended changes in behavior resulting from software or environment changes (regression testing)

2.3.1. Functional Testing (K2)

> _**functional testing**_  
> _Testing conducted to evaluate the compliance of a component or system with functional requirements.  
> ISTQB Glossary_

Functional testing of a system involves tests that evaluate functions that the system should perform.

Functional requirements may be undocumented or may be described in work products such as:

- business requirements specifications,

- epics,

- user stories,

- use cases, or

- functional specifications.

The functions are “what” the system should do.

_**Should be performed at all test levels**_

Functional tests should be performed at all test levels (e.g., tests for components may be based on a component specification), though the focus is different at each level (see [Section 2.2](2%20Testing%20Throughout%20the%20Software%20Development%20Life%2038645f60409f48fe9f3fe059f0d92a15.html)).

Functional testing considers the behavior of the software, so black-box techniques may be used to derive test conditions and test cases for the functionality of the software or system (see Chapter 4).

_**Functional coverage**_

The thoroughness of functional testing can be measured through functional coverage.

Functional coverage is the extent to which some type of functional element has been exercised by tests and is expressed as a percentage of the type(s) of element being covered.

For example, using traceability between tests and functional requirements, the percentage of requirements which are addressed by testing can be calculated, potentially identifying coverage gaps.

_**May involve special skills or knowledge**_

Functional test design and execution may involve special skills or knowledge, such as:

- knowledge of the particular business problem the software solves (e.g., geological modelling software for the oil and gas industries) or

- the particular role the software serves (e.g., computer gaming software that provides interactive entertainment).

2.3.2. Non-functional Testing (K2)

> _**non-functional testing**_  
> _Testing conducted to evaluate the compliance of a component or system with non-functional requirements.  
> ISTQB Glossary_

_**Evaluating other quality characteristics**_

Non-functional testing of a system evaluates characteristics of systems and software such as usability, performance efficiency, security, and so forth.

Refer to the international standard ISO/IEC 25010 for a classification of software product quality characteristics.

Non-functional testing is the testing of “how well” the system behaves.

In some cases, non-functional tests can be quantified; e.g., performance testing to measure the response times of a system.

_**Should be performed at all test levels**_

Contrary to common misperceptions, non-functional testing can and often should be performed at all test levels and done as early as possible.

The late discovery of non-functional defects can be extremely dangerous to the success of a project.

|   |   |   |
|---|---|---|
|**Performance**  <br>How long does it take to get from 0 to 60mph?|**Load  <br>**How does it perform with 4 passengers and their luggage?|**Stress**  <br>How fast can it go round a bend?|
|**Portability  <br>**Can it be converted to left hand drive?|🚘🚘🚘🚘🚘🚘🚘🚘🚘🚘|**Reliability  <br>**How many miles will it do before breaking down?|
|**Usability  <br>**How easy is it to drive?|**Security  <br>**Can we stop people stealing it?|**Maintainability  <br>**How easy is it to maintain and service?|

[![](Dashboard/Attachments/Untitled%2013%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2013.png)

[![](Dashboard/Attachments/Untitled%2014%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2014.png)

[![](Dashboard/Attachments/Untitled%2015%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2015.png)

_**Black-box techniques can be used to identify tests**_

[![](Dashboard/Attachments/Untitled%2016%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2016.png)

Black-box techniques (see section 4.2) may be used to derive test conditions and test cases for non-functional testing.

For example, boundary value analysis can be used to define the stress conditions for performance tests.

_**Non-functional coverage**_

The thoroughness of non-functional testing can be measured through non-functional coverage.

Non-functional coverage is the extent to which some type of non-functional element has been exercised by tests and is expressed as a percentage of the type(s) of element being covered.

For example, using traceability between tests and supported devices for a mobile application, the percentage of devices which are addressed by compatibility testing can be calculated, potentially identifying coverage gaps.

_**May involve special skills or knowledge**_

Non-functional test design and execution may involve special skills or knowledge, such as:

- knowledge of the inherent weaknesses of a design or technology (e.g., security vulnerabilities associated with particular programming languages) or

- knowledge of the particular user base (e.g., the personas of users of a healthcare facility management systems).

Refer to ISTQB-ATA Advanced Level Test Analyst Syllabus, ISTQB-ATTA Advanced Level Technical Test Analyst Syllabus, ISTQB-SEC Advanced Level Security Tester Syllabus, and other ISTQB specialist modules for more details regarding the testing of non-functional quality characteristics.

2.3.3. White-box Testing (K2)

[![](Dashboard/Attachments/Untitled%2017%201.png)](2%20Testing%20Throughout%20the%20Software%20Development%20Life/Untitled%2017.png)

_**Based on the system’s internal structure**_

White-box testing derives tests based on the system’s internal structure or implementation.

Internal structure may include code, architecture, work flows, and/or data flows within the system (see section 4.3).

_**Structural coverage**_

The thoroughness of white-box testing can be measured through structural coverage.

Structural coverage is the extent to which some type of structural element has been exercised by tests and is expressed as a percentage of the type(s) of element being covered.

_**Measuring coverage at component test level**_

At the component level, code coverage is based on the percentage of component code that has been tested and may be measured in terms of different aspects of code (coverage items) such as the percentage of executable statements tested in the component, or the percentage of decision outcomes tested.

These types of coverage are collectively called code coverage.

_**Measuring coverage at component integration test level**_

At the component integration level, white-box testing may be based on the architecture of the system, such as interfaces between components, and structural coverage may be measured in terms of the percentage of interfaces exercised by tests.

_**May involve special skills or knowledge**_

White-box test design and execution may involve special skills or knowledge, such as:

- the way the code is built (e.g., to use code coverage tools),

- how data is stored (e.g., to evaluate possible database queries), and

- how to use coverage tools and to correctly interpret their results.

2.3.4. Change-related Testing (K2)

**FL-2.3.3** _Compare the purposes of confirmation testing and regression testing (K2)_

When changes are made to a system, either to correct a defect or because of new or changing functionality, testing should be done to confirm that the changes have corrected the problem or implemented the functionality correctly and have not caused any unforeseen adverse consequences.

_**Confirmation testing:**_

> _**confirmation testing(re-testing)  
> **__Dynamic testing conducted after fixing defects with the objective to confirm that failures caused by those defects do not occur anymore._  
> ISTQB Glossary

After a defect is fixed, the software may be tested with all test cases that failed due to the defect, which should be re-executed on the new software version.

The software may also be tested with new tests if, for instance, the defect was missing functionality.

At the very least, the steps to reproduce the failure(s) caused by the defect must be re-executed on the new software version.

The purpose of a confirmation test is to confirm whether the original defect has been successfully fixed.

_**Regression testing:**_

Regression testing involves re-running tests to detect such unintended side-effects.

> _**regression testing**_  
> _Testing of a previously tested component or system following modification to ensure that defects have not been introduced or have been uncovered in unchanged areas of the software, as a result of the changes made._  
> ISTQB Glossary

It is possible that a change made in one part of the code, whether a fix or another type of change, may accidentally affect the behavior of other parts of the code, whether within the same component, in other components of the same system, or even in other systems.

Changes may include changes to the environment, such as a new version of an operating system or database management system.

Such unintended side-effects are called regressions.

Regression testing involves running tests to detect such unintended side-effects.

_**Performed at all test levels**_

Confirmation testing and regression testing are performed at all test levels.

Especially in iterative and incremental development lifecycles (e.g., Agile), new features, changes to existing features, and code refactoring result in frequent changes to the code, which also requires change-related testing.

_**They are very important**_

Due to the evolving nature of the system, confirmation and regression testing are very important.

This is particularly relevant for Internet of Things systems where individual objects (e.g., devices) are frequently updated or replaced.

_**Regression testing is a strong candidate for automation**_

Regression test suites are run many times and generally evolve slowly, so regression testing is a strong candidate for automation.

Therefore, automation of these tests should start early in the project (see Chapter 6).

2.3.5. Test Types and Test Levels (K2)

It is possible to perform any of the test types mentioned above at any test level.

To illustrate, examples of functional, non-functional, white-box, and change-related tests will be given across all test levels, for a banking application, starting with functional tests:

- During component testing, tests are designed based on how a component should calculate compound interest.

- During component integration testing, tests are designed based on how account information captured at the user interface is passed to the business logic.

- During system testing, tests are designed based on how account holders can apply for a line of credit on their checking accounts.

- During system integration testing, tests are designed based how a component uses an external microservice to check an account holder’s credit score.

- During acceptance testing, tests are designed based on how the banker handles approving or declining a credit application.

The following are examples of non-functional tests:

- For component testing, performance tests are designed to evaluate the number of CPU cycles required to perform a complex total interest calculation.

- For component integration testing, security tests are designed for buffer overflow vulnerabilities due to data passed from the user interface to the business logic.

- For system testing, portability tests are designed to check whether the presentation layer works on all supported browsers and mobile devices.

- For system integration testing, reliability tests are designed to evaluate system robustness if the credit score microservice fails to respond.

- For acceptance testing, usability tests are designed to evaluate the accessibility of the banker’s credit processing interface for people with disabilities.

The following are examples of white-box tests:

- For component testing, tests are designed to achieve complete statement and decision coverage (see section 4.3) for all components that perform financial calculations.

- For component integration testing, tests are designed to exercise how each screen in the browser interface passes data to the next screen and to the business logic.

- For system testing, tests are designed to cover all possible sequences of web pages that can occur during a credit line application.

- For system integration testing, tests are designed to exercise all possible inquiry types sent to the credit score microservice.

- For acceptance testing, tests are designed to cover all supported financial data file formats for bank-to-bank transfers.

Finally, the following are examples for change-related tests:

- For component testing, automated regression tests are built for each component and included within the continuous integration framework.

- For component integration testing, tests are designed to confirm fixes to interface-related defects as the fixes are checked into the code repository.

- For system testing, all tests for a given workflow are re-executed if any screen on that workflow changes.

- For system integration testing, tests of the application interacting with the credit scoring microservice are re-executed daily as part of continuous deployment of that microservice.

- For acceptance testing, all previously-failed tests are re-executed after a defect found in acceptance testing is fixed.

While this section provides examples of every test type across every level, it is not necessary, for all software, to have every test type represented across every level.

However, it is important to run applicable test types at each level, especially the earliest level where the test type can occur.

# 2.4. Maintenance Testing

**FL-2.4.1** _Summarise triggers for maintenance testing (K2)_

**FL-2.4.2** _Describe the role of impact analysis in maintenance testing (K2)_

> _**maintenance testing**_  
> _Testing the changes to an operational system or the impact of a changed environment to an operational system._  
> ISTQB Glossary

_**Handling changes in live environments**_

Once deployed to production environments, software and systems will need to be maintained.

Changes of various sorts are almost inevitable in delivered software and systems, either to fix defects discovered in operational use, or to add, delete, or alter already-delivered functionality.

Maintenance is also needed for assuring non-functional quality characteristics of the software or system over its lifetime, especially performance efficiency, compatibility, reliability, security, and portability.

_**When to perform maintenance testing**_

When any kind of change is made, maintenance testing should be performed, both to evaluate the success with which the changes were made and to check for possible side-effects (e.g., regressions) in parts of the system that remain unchanged (which is usually most of the system).

Maintenance testing focuses on testing the parts of the system affected by changes as well as testing the unchanged parts.

_**The scope of planned and unplanned changes**_

Maintenance can involve planned releases and unplanned releases (hot fixes).

A maintenance release may require maintenance testing at multiple test levels, using various test types, based on its scope.

The scope of maintenance testing depends on:

- The degree of risk of the change, for example, the degree to which the changed area of software communicates with other components or systems

- The size of the existing system

- The size of the change

2.4.1. Triggers for Maintenance (K2)

**FL-2.4.1** _Summarise triggers for maintenance testing (K2)_

There are several reasons why software maintenance, and thus maintenance testing, takes place, both for planned and unplanned changes.

We can classify the triggers for maintenance as follows:

### **Modification**

Modification, such as:

- planned enhancement changes (e.g., release-based),

- corrective and emergency changes,

- changes of the operational environment (such as planned operating system or database upgrades),

- upgrades of COTS software, and

- patches for defects and vulnerabilities

### Migration

Migration, such as from one platform to another, which can require:

- operational tests of the new environment

- operational tests of the changed software or tests of data conversion when data from another application will be migrated into the system being maintained

### Retirement

Retirement, such as when an application reaches the end of its life.

_**The Internet of Things**_

For Internet of Things systems, maintenance testing may be triggered by the introduction of completely new or modified things, such as hardware devices and software services, into the overall system.The maintenance testing for such systems places particular emphasis on integration testing at different levels(e.g., network level, application level) and on security aspects, in particular those relating to personal data.

2.4.2. Impact Analysis for Maintenance (K2)

**FL-2.4.2** _Describe the role of impact analysis in maintenance testing (K2)_

_**Impact analysis**_

> _**impact analysis**_  
> _The identification of all work products affected by a change, including an estimate of the resources needed to accomplish the change.  
> _ISTQB Glossary

Impact analysis evaluates the changes that were made for a maintenance release to identify the intended consequences as well as expected and possible side effects of a change, and to identify the areas in the system that will be affected by the change.

Impact analysis can also help to identify the impact of a change on existing tests.

The side effects and affected areas in the system need to be tested for regression, possibly after updating any existing tests affected by the change.

_**Can be done before the change**_

In some cases, impact analysis is done before a change is made, to help decide if the change should be made, based on the potential consequences in other areas of the system.

Impact analysis can be difficult if:

- Specifications (e.g., business requirements, user stories) are out of date or missing

- Test cases are not documented or are out of date

- Bi-directional traceability between tests and the test basis has not been maintained

- The people involved do not have domain and/or system knowledge

- Insufficient attention has been paid to the software's maintainability quality characteristics during development

Review Questions

1. **What does the software development lifecycle describe?**
    
    1. It describes the types of activities performed in software development projects
    
    2. It describes the types of test activities performed in software development projects
    
    3. It describes the functional and non-functional requirements of the project
    
    - Answer:
        
        **a. It describes the types of activities performed in software development projects**
        

2. **Which of the following is one of the characteristics of good testing?  
      
    i.Each test level has a test objective specified to that level  
    ii.Test analysis and design for a given test level should only begin at the end of the development activities of that level  
    iii.For every development activity there is a corresponding test activity  
    iv.Testers participate in discussions to define and refine requirements and design**
    
    1. i is correct, ii,iii,iv are wrong
    
    2. i,iii,iv are correct, ii is wrong
    
    3. i,iii are correct, ii,iv are wrong
    
    - Answer:
        
        **b. i,iii,iv are correct, ii is wrong**
        

3. **Which of the following is correct regarding sequential models?**
    
    1. It depends on sequential flow of activities, and there is no overlap between phases
    
    2. It divides the project into iterations or sprints
    
    - Answer:
        
        1. **It depends on sequential flow of activities, and there is no overlap between phases**
        

4. **Which of the following is correct regarding incremental models?**
    
    1. Feature increments must be a big change to a software module
    
    2. Features can be reviewed only at the end of the project
    
    3. Software features grow incrementally
    
    - Answer:
        
        **c. Software features grow incrementally**
        

5. **Which is a main difference between incremental and iterative models?**
    
    1. There is no difference between incremental and iterative models.
    
    2. Incremental models have fixed length iterations but iterative models don't
    
    3. Iterative models have fixed length iterations but incremental models don't
    
    - Answer:
        
        **c. Iterative models have fixed length iterations but incremental models don't**
        

6. **Which of the following is correct regarding the waterfall model?  
      
    i.Waterfall Model is a sequential model  
    ii.In the waterfall model, test activities begin after all development activities are finished  
    iii.Waterfall model is the best development model to choose for small organizations  
    iv. Waterfall model divides the project into small iterations**
    
    1. i, iii are correct, ii, iv are wrong
    
    2. i, iv are correct, ii, iiii are wrong
    
    3. ii, iii are correct, i, iv are wrong
    
    4. i, ii are correct, iii, iv are wrong
    
    - Answer:
        
        d. **i, ii are correct, iii, iv are wrong**
        

7. **The V-Model can be considered as a ..............**
    
    1. sequential model
    
    2. iterative model
    
    3. incremental model
    
    - Answer:
        
        1. **Sequential model**
        

8. **In the V-Model, in which stage does the client see the product and give feedback about its quality?**
    
    1. Unit Testing
    
    2. Integration Testing
    
    3. System Testing
    
    4. Acceptance Testing
    
    - Answer:
        
        **d. Acceptance testing**
        

9. **Which of the following is a main difference between the waterfall and the V-model?**
    
    1. The waterfall is a sequential model but the v-model is an iterative one
    
    2. In the v-model, the principle of early testing is applied. In waterfall model, it is not applied.
    
    3. The v-model has one type of software requirements while the waterfall model has two types
    
    - Answer:
        
        **b. In the v-model, the principle of early testing is applied. In waterfall model, it is not applied.**
        

10. **Rational unified process model divides the project into iterations with the length of .............**
    
    1. Relatively short (one to four weeks)
    
    2. Relatively long (two to three months)
    
    - Answer:
        
        **b. Relatively long (two to three months)**
        

11. **Which of the following is correct regarding scrum methodology?  
      
    1-Scrum divides the project into large iterations [two to three months]  
    2-In scrum, the tester is the person who is responsible for writing the software requirements document  
    3-At the end of each iteration, a retrospective meeting is held to review the progress**
    
    1. 1 is correct, 2 & 3 are wrong
    
    2. 1 & 2 are correct, 3 is wrong
    
    3. 1 & 3 are correct, 2 is wrong
    
    4. 3 is correct, 1 & 2 are wrong
    
    - Answer:
        
        **d. 3 is correct, 1 & 2 are wrong**
        

12. **Which of the following is correct regarding Kanban?**
    
    1. Kanban divides the project into fixed length iterations
    
    2. There is no overlap between phases in Kanban
    
    3. Kanban is implemented with or without fixed length iterations
    
    - Answer:
        
        c. **Kanban is implemented with or without fixed length iterations**
        

13. **If you have a board with stations showing the progress of the project. Each station has a name like "To do - In development - Done". We call this board a ...............**
    
    1. Kanban requirements specification
    
    2. Kanban board
    
    3. Kanban backlog
    
    - Answer:
        
        **b. Kanban board**
        

14. **In spiral model, we build a prototype which is ............**
    
    1. a customer feedback about the finished work
    
    2. wireframes and notes which may be heavily reworked or even abandoned
    
    - Answer:
        
        b. **wireframes and notes which may be heavily reworked or even abandoned**
        

15. **When should the tester start reviewing project documents?**
    
    1. When they have been baselined and approved
    
    2. After the first revision
    
    3. As soon as a draft is available
    
    4. When the developers have started coding
    
    - Answer:
        
        **c. As soon as a draft is available**
        

16. **What is important to do when working with software development models?**
    
    1. To adapt the models to the context of project and product characteristics
    
    2. To choose the waterfall model because it is the first and best proven model
    
    3. To start with the V-model and then move to either iterative or incremental models
    
    4. To only change the organization to fit the model not vice versa
    
    - Answer:
        
        1. **To adapt the models to the context of project and product characteristics**
        

17. **Which of the following characteristics of good testing apply to any software development lifecycle model?**
    
    1. Acceptance testing is always the final test level to be applied
    
    2. All test levels are planned and completed for each developed feature
    
    3. Testers are involved as soon as the first piece of code can be executed
    
    4. For every development activity there is a corresponding testing activity
    
    - Answer:
        
        **d. For every development activity there is a corresponding testing activity**
        

18. **Which iterative model consists of relatively short iterations (e.g., few weeks) and produces small features increments?**
    
    1. Rational Unified Process
    
    2. Scrum
    
    3. Kanban
    
    4. Rapid prototyping
    
    - Answer:
        
        **b. Scrum**
        

19. **Which iterative model may or may not have fixed length iterations?**
    
    1. Rational Unified Process
    
    2. Scrum
    
    3. Kanban
    
    4. Rapid prototyping
    
    - Answer:
        
        **c. Kanban**
        

20. **Which one of the following is the BEST definition of an incremental development model?**
    
    1. Defining requirements, designing software and testing are done in a series with added pieces
    
    2. A phase in the development process should begin when the previous phase is complete
    
    3. Testing is viewed as a separate phase which takes place after development has been completed
    
    4. Testing is added to development as an increment
    
    - Answer:
        
        1. **Defining requirements, designing software and testing are done in a series with added pieces**
        

21. **Which of the following is a true statement regarding the V-model lifecycle?**
    
    1. Testing involvement starts when the code is complete
    
    2. The test process is integrated with the development process
    
    3. The software is built in increments and each increment has activities for requirements, design, build and test
    
    4. All activities for development and test are completed sequentially
    
    - Answer:
        
        b. **The test process is integrated with the development process**
        

22. **In an iterative lifecycle model, which of the following is an accurate statement about testing activities?**
    
    1. For every development activity, there should be a corresponding testing activity
    
    2. For every testing activity, appropriate documentation should be produced, versioned and stored 
    
    3. For every development activity resulting in code, there should be a testing activity to document test cases
    
    4. For every testing activity, metrics should be recorded and posted to a metrics dashboard for all stakeholders
    
    - Answer:
        
        1. **For every development activity, there should be a corresponding testing activity**
        

23. **Which of the following is not a test level?**
    
    1. Component Testing
    
    2. Functional Testing
    
    3. System integration testing
    
    - Answer:
        
        **b. Functional Testing**
        

24. **Which of the following is correct regarding the test levels?  
      
    1-Each test level is an instance of the test process  
    2-The test levels are universal and used in all software companies  
    3-Test levels are groups of test activities that are organized and managed together  
    4-For every test level, a suitable test environment is required**
    
    1. 1,2,3 are correct. 4 is wrong
    
    2. 1,3,4 are correct. 2 is wrong
    
    3. 2,3,4 are correct. 1 is wrong
    
    4. 1,2,4 are correct. 3 is wrong
    
    - Answer:
        
        **b. 1,3,4 are correct. 2 is wrong**
        

25. **Which of the following is a correct definition of component testing?**
    
    1. Testing interactions between components or systems.
    
    2. Testing components that are separately testable.
    
    3. Testing the behavior and capabilities of a whole system or product
    
    - Answer:
        
        b. **Testing components that are separately testable.**
        

26. **Which of the following is an objective of component testing?**
    
    1. Building confidence in the component’s quality
    
    2. Building confidence in the quality of the interfaces
    
    3. Validating that the system is complete and will work as expected
    
    - Answer
        
        1. **Building confidence in the component’s quality**
        

27. **Which of the following are considered as test basis for component testing?**
    
    1. use cases - workflows - Sequence diagrams
    
    2. Epics and user stories - State diagrams - Risk analysis reports
    
    3. Detailed design - code - data model
    
    - Answer
        
        c. **Detailed design - code - data model**
        

28. **Which of the following is an example of defects and failures that can be found in component testing?**
    
    1. Incorrect sequencing or timing of interface calls
    
    2. Incorrect code and logic
    
    3. Incorrect control and/or data flows within the system
    
    - Answer
        
        **b.** **Incorrect code and logic**
        

29. **"A software development process relying on software requirements being converted to test cases before software is fully developed, and tracking all software development by repeatedly testing the software against all test cases"**
    
    1. This is the definition of component testing
    
    2. This is the definition of test-driven development
    
    3. This is the definition of the test levels
    
    - Answer
        
        **b.** **This is the definition of test-driven development**
        

30. **"Integration testing" focuses on:**
    
    1. Testing the code early as possible
    
    2. Interactions between components or systems
    
    3. Functionality of each component that can be tested separately
    
    - Answer
        
        b. **Interactions between components or systems**
        

31. **"Component integration testing" is mostly the responsibility of (...............) and "System integration testing" is mostly the responsibility of (.............)**
    
    1. **developer-tester**
    
    2. **tester-developer**
    
    3. **tester-tester**
    
    4. **tester-client**
    
    - Answer
        
        1. **developer-tester**
        

32. **Which of the following can be considered as test basis for integration testing?**
    
    1. use cases - workflows - Sequence diagrams
    
    2. Epics and user stories - State diagrams - Risk analysis reports
    
    3. Detailed design - code - data model
    
    - Answer
        
        1. **use cases - workflows - Sequence diagrams**
        

33. **Which of the following is an example of defects and failures that can be found in integration testing?**
    
    1. Incorrect sequencing or timing of interface calls
    
    2. Incorrect code and logic
    
    3. Incorrect control and/or data flows within the system
    
    - Answer
        
        1. **Incorrect sequencing or timing of interface calls**
        

34. **Which of the following sentences regarding scope of integration is correct?**
    
    1. The greater the scope of integration, the more difficult it becomes to isolate defects
    
    2. The greater the scope of integration, the more easy it becomes to isolate defects
    
    3. The lower the scope of integration, the more difficult it becomes isolate defects
    
    4. Isolating defects is always a difficult activity
    
    - Answer
        
        a.**The greater the scope of integration, the more difficult it becomes to isolate defects**
        

35. **Which of the following is a correct definition of System testing?**
    
    1. Testing components that are separately testable.
    
    2. Testing the behavior and capabilities of a whole system or product
    
    3. Testing interactions between components or systems.
    
    - Answer
        
        b. **Testing the behavior and capabilities of a whole system or product**
        

36. **Which of the following statements about system testing are correct?  
    1-The test environment should ideally correspond to the final production environment  
    2-System testing is typically carried out by independent testers who rely heavily on specifications  
    3-Finding defects is often not an objective of system testing**
    
    1. 1 & 2 are correct. 3 is wrong
    
    2. 1 & 3 are correct. 2 is wrong
    
    3. 2 & 3 are correct. 1 is wrong
    
    - Answer
        
        1. **1 & 2 are correct. 3 is wrong**
        

37. **Which of the following can be considered as test basis of System testing?**
    
    1. Detailed design - code - data model
    
    2. Epics and user stories - State diagrams - Risk analysis reports
    
    3. use cases - workflows - Sequence diagrams
    
    - Answer
        
        b. **Epics and user stories - State diagrams - Risk analysis reports**
        

38. **Which is a test object that can be tested in system testing?**
    
    1. Applications - Operating systems
    
    2. Reports - Forms
    
    3. APIs - Microservices
    
    - Answer
        
        1. **Applications - Operating systems**
        

39. **Which of the following is a similarity between system testing and acceptance testing?**
    
    1. They both have the same test objects
    
    2. They both have the same test basis
    
    3. They both focus on the behavior and capabilities of a whole system or product.
    
    - Answer
        
        c. **They both focus on the behavior and capabilities of a whole system or product.**
        

40. **Your project is currently in Acceptance testing phase, and your testing team is reporting too many defects, what does this situation indicate?**
    
    1. This is a good situation and it indicates that the product quality is increasing and testers are making good effort
    
    2. This is a bad situation because finding defects is often not an objective of acceptance testing, and finding a significant number of defects during acceptance testing may in some cases be considered a major project risk.
    
    - Answer
        
        b. **This is a bad situation because finding defects is often not an objective of acceptance testing, and finding a significant number of defects during acceptance testing may in some cases be considered a major project risk.**
        

41. **Which of the following can be considered as test basis of Acceptance testing?**
    
    1. Regulations, legal contracts and standards
    
    2. State diagrams
    
    3. Workflows
    
    - Answer
        
        1. **Regulations, legal contracts and standards**
        

42. **Which of the following is a defect that can be found in Acceptance testing?**
    
    1. Failure to properly and completely carry out end-to-end functional tasks
    
    2. Business rules are not implemented correctly
    
    3. Interface mismatch
    
    - Answer
        
        b. **Business rules are not implemented correctly**
        

43. **In which type of acceptance testing are we testing the system by systems administration staff in a (simulated) production environment?**
    
    1. User Acceptance Testing
    
    2. Operational Acceptance Testing
    
    3. Contractual and regulatory acceptance testing
    
    4. Alpha and beta testing
    
    - Answer
        
        b. **Operational Acceptance Testing**
        

44. **Which type of Acceptance testing is used by developers of commercial off-the-shelf (COTS) software who want to get feedback from potential or existing users, customers, and/or operators before the software product is put on the market?**
    
    1. User Acceptance Testing
    
    2. Operational Acceptance Testing
    
    3. Contractual and regulatory acceptance testing
    
    4. Alpha and beta testing
    
    - Answer
        
        d. **Alpha and beta testing**
        

45. **Which type of Acceptance testing tests the system by validating the fitness for use of the system by intended users in a real or simulated operational environment?**
    
    1. **User acceptance testing**
    
    2. **Operational acceptance testing**
    
    3. **Contractual and regulatory acceptance testing**
    
    4. **Alpha and beta testing**
    
    - Answer
        
        1. **User acceptance testing**
        

46. **Which testing level is primarily focused on building confidence rather than finding defects?**
    
    1. Unit Testing
    
    2. Integration Testing
    
    3. System Testing
    
    4. Acceptance Testing
    
    - Answer
        
        **d. Acceptance Testing**
        

47. **If you need to add system integration testing as a test level for a particular project, what testing level should it directly follow?**
    
    1. Component
    
    2. Component Integration
    
    3. System
    
    4. Acceptance
    
    - Answer
        
        **c. System**
        

48. **In which test level are the developers most heavily involved?**
    
    1. Compatibility
    
    2. Acceptance
    
    3. Component
    
    4. Conversion
    
    - Answer
        
        **c. Component**
        

49. **Which of the following is a characteristic of a well-managed test level?**
    
    1. It has a target duration of one month
    
    2. It has a corresponding test objective
    
    3. It does not overlap with another test level
    
    4. It applies a single test design technique
    
    - Answer
        
        **b. It has a corresponding test objective**
        

50. **Which of the following comparisons of component testing and system testing is true?**
    
    1. Component testing verifies the functioning of software modules, program objects, and classes that are separately testable, whereas system testing verifies interfaces between components and interactions with different parts of the system
    
    2. Test cases for component testing are usually derived from component specifications, design specifications, or data models, whereas test cases for system testing are usually derived from requirement specifications, functional specifications or use cases
    
    3. Component testing focuses on functional characteristics, whereas system testing focuses on functional and non-functional characteristics
    
    4. Component testing is the responsibility of the technical testers, whereas system testing typically is the responsibility of the users of the system
    
    - Answer
        
        **b. Test cases for component testing are usually derived from component specifications, design specifications, or data models, whereas test cases for system testing are usually derived from requirement specifications, functional specifications or use cases**
        

51. **Contract & Regulation testing is a part of...**
    
    1. System Testing
    
    2. Acceptance Testing
    
    3. Integration Testing
    
    4. Functional Testing
    
    - Answer
        
        **b. Acceptance Testing**
        

52. **Which of the following is considered as a test type?**
    
    1. Rational unified process
    
    2. Integration Testing
    
    3. Structural Testing
    
    4. Early Testing
    
    - Answer
        
        **c. Structural Testing**
        

53. **"Functional Testing" means that we evaluate functions that the system performs, which of the following is a test basis for functional testing?**
    
    1. Load, performance and security
    
    2. Agile, Scrum and Kanban
    
    3. User stories, Epics and use cases
    
    - Answer
        
        c. **User stories, Epics and use cases**
        

54. **Which of the following is correct regarding functional testing?  
    1-Functional testing is only performed in system testing  
    2-The functions in functional testing are “what” the system should do.  
    3-The thoroughness of functional testing can be measured through functional coverage  
    4-black-box techniques may be used to derive test conditions and test cases for the functionality of the component or system**
    
    1. 1,2,3 are correct. 4 is wrong
    
    2. 1,2,4 are correct. 3 is wrong
    
    3. 1, 3,4 are correct. 2 is wrong
    
    4. 2,3,4 are correct. 1 is wrong
    
    - Answer
        
        d. **2,3,4 are correct. 1 is wrong**
        

55. **Which of the following describes non-functional testing correctly?**
    
    1. Non-functional testing focuses on what the system performs
    
    2. Non-functional testing focuses on writing the test plan of the project
    
    3. Non-functional testing focuses on how well the system behaves
    
    - Answer
        
        c. **Non-functional testing focuses on how well the system behaves**
        

56. **Which of the following is correct regarding non-functional testing?  
    1-Non-functional testing can be performed at all test levels  
    2-Non-functional testing focuses on how well the system behaves, such as performance, usability and security  
    3-Non-functional testing must be performed by a dedicated tester  
    4-An example of non-functional coverage is using traceability between tests and supported devices for a mobile application, the percentage of devices which are addressed by compatibility testing can be calculated, potentially identifying coverage gaps.**
    
    1. 1,2,3 are correct. 4 is wrong
    
    2. 1,2,4 are correct. 3 is wrong
    
    3. 2,3,4 are correct. 1 is wrong
    
    4. 1,3,4 are correct. 2 is wrong
    
    - Answer
        
        b. **1,2,4 are correct. 3 is wrong**
        

57. **Which of the following is mostly true regarding structural testing?**
    
    1. Deriving tests based on requirements and user stories
    
    2. Deriving tests based on the system’s internal structure
    
    - Answer
        
        b. **Deriving tests based on the system’s internal structure**
        

58. **In white-box testing, what do we mean with the word "internal structure"?**
    
    1. Requirements, Epics and user stories
    
    2. Usability, performance and security
    
    3. Architectures, workflow and data flow
    
    - Answer
        
        c. **Architectures, workflow and data flow**
        

59. **Which of the following is a correct definition of structural coverage?**
    
    1. Tests based on the system’s internal structure or implementation
    
    2. The extent to which some type of structural element has been exercised by tests
    
    - Answer
        
        b. **The extent to which some type of structural element has been exercised by tests**
        

60. **Which of the following is a correct definition of change-related testing?**
    
    1. When changes are made to a system, testing should be done to confirm that the changes have corrected the defect or implemented the functionality correctly, and have not caused any unforeseen adverse consequences.
    
    2. tests that evaluate functions that the system should perform.
    
    - Answer
        
        1. **When changes are made to a system, testing should be done to confirm that the changes have corrected the defect or implemented the functionality correctly, and have not caused any unforeseen adverse consequences.**
        

61. **Which of the following is correct regarding confirmation testing?  
    1-After a defect is fixed, the software may be tested with all test cases that failed due to the defect, which should be re-executed on the new software version.  
    2-The steps to reproduce the failure(s) caused by the defect must be re-executed on the new software version  
    3-The purpose of a confirmation test is to confirm whether the original defect has been successfully fixed  
    4-Confirmation testing is performed in all test levels**
    
    1. 1,2,3 are correct. 4 is wrong.
    
    2. 2,3,4 are correct. 1 is wrong.
    
    3. 1,2,4 are correct. 3 is wrong.
    
    4. 1,3,4 are correct. 2 is wrong.
    
    5. All answers are correct
    
    - Answer
        
        e. **All answers are correct**
        

62. **It is possible that a change made in one part of the code, whether a fix or another type of change, may accidentally affect the behavior of other parts of the code, whether within the same component, in other components of the same system, or even in other systems. Which test type is used to find defects in those changed areas?**
    
    1. Confirmation testing
    
    2. Regression Testing
    
    3. Impact Analysis
    
    - Answer
        
        **b. Regression Testing**
        

63. **Which of the following is most correct regarding when functional tests may be executed?**
    
    1. Unit & Integration
    
    2. Integration & System
    
    3. System & Acceptance
    
    4. All Levels
    
    - Answer
        
        **d. All Levels**
        

64. **Which of the following is most correct regarding when non-functional tests may be executed?**
    
    1. Unit & Integration
    
    2. Integration & System
    
    3. System & Acceptance
    
    4. All Levels
    
    - Answer
        
        **d. All Levels**
        

65. **Usability testing is an example of which type of testing?**
    
    1. Functional
    
    2. Non-functional
    
    3. Structural
    
    4. Change-related
    
    - Answer
        
        b. **Non-functional**
        

66. **Which of the following is an important characteristic of tests used for regression testing?**
    
    1. They focus on testing the intricate and difficult-to-test aspects of the software
    
    2. They require significant maintenance effort for each release
    
    3. They are used for one release and are then discarded to keep the test set fresh
    
    4. They are reusable for multiple releases with little maintenance
    
    - Answer
        
        **d. They are reusable for multiple releases with little maintenance**
        

67. **Which statement below BEST describes non-functional testing?**
    
    1. The process of testing an integrated system to verify that it meets specified requirements
    
    2. The process of testing to determine the compliance of a system to coding standards
    
    3. Testing without reference to the internal structure of a system
    
    4. Testing system attributes, such as usability, reliability or performance
    
    - Answer
        
        **d. Testing system attributes, such as usability, reliability or performance**
        

68. **Which of the following statements are TRUE?  
    **_**A. Regression Testing & Acceptance Testing are the same  
    B. Regression tests show if all defects have been resolved  
    C. Regression tests are typically well-suited for test automation  
    D. Regression Tests are performed to find out if code changes have introduced or uncovered defects**_
    
    1. A,C & D are true; B is false
    
    2. A & C are true; B & D are false
    
    3. C & D are true; A & B are false
    
    4. B is true; A,C & D are false
    
    - Answer
        
        **c. C & D are true; A & B are false**
        

69. **Repeated Testing of an already tested program, after modification, to discover any defects introduced or uncovered as a result of the changes in the software being tested or in another related or unrelated software component:**
    
    1. Retesting
    
    2. Confirmation Testing
    
    3. Regression Testing
    
    4. Negative Testing
    
    - Answer
        
        **c. Regression Testing**
        

70. **Which of the following is a true statement regarding the process of fixing emergency changes?**
    
    1. There is no time to test the change before it goes live, so only the best developers should do this work and should not involve testers as they slow down the process
    
    2. Only retest of the defect actually fixed
    
    3. Retest the changed area and then use risk assessment to decide on a reasonable subset of the whole regression test to run in a case other parts of the system have been adversely affected
    
    4. Always run a full regression test of the whole system in case other parts of the system have been adversely affected
    
    - Answer
        
        **c. Retest the changed area and then use risk assessment to decide on a reasonable subset of the whole regression test to run in a case other parts of the system have been adversely affected**
        

71. **Which of the following is correct regarding maintenance testing?**
    
    1. Maintenance testing focuses on how will the system behaves
    
    2. Maintenance testing focuses on testing the changes to the system, and can involve planned and unplanned releases
    
    3. Maintenance testing focuses on what the system performs
    
    - Answer
        
        b. **Maintenance testing focuses on testing the changes to the system, and can involve planned and unplanned releases**
        

72. **The triggers of maintenance testing are .............**
    
    1. Requirements, Epics and User stories
    
    2. Modification, Migration and Retirement
    
    3. Retesting & Regression Testing
    
    - Answer
        
        b. **Modification, Migration and Retirement**
        

73. **If we are moving the application to a newer version of the operating system, this is .........  
    If we are going to build a new system and erase the old one, this is .............  
    If we are going to add or remove a functionality, this is .............**
    
    1. Modification, migration, retirement
    
    2. Retirement, modification, migration
    
    3. Migration, retirement, modification
    
    4. Modification, retirement, migration
    
    - Answer
        
        c. **Migration, retirement, modification**
        

74. **Impact analysis is done:**
    
    1. before the change is made
    
    2. after the change is made
    
    3. before and after the change is made
    
    4. during making the change
    
    - Answer
        
        c. **before and after the change is made**
        

75. **Which one of the following is TRUE?**
    
    1. The purpose of regression testing is to check if the correction has been successfully implemented, while the purpose of confirmation testing is to confirm that the correction has no side effects.
    
    2. The purpose of regression testing is to check if the new functionality is working, while the purpose of confirmation testing is to check if the original defect has been fixed.
    
    3. The purpose of regression testing is to detect unintended side effects, while the purpose of confirmation testing is to check if the original defect has been fixed.
    
    4. The purpose of regression testing is to detect unintended side effects, while the purpose of confirmation testing is to check if the system is still working in a new environment.
    
    - Answer
        
        **c. The purpose of regression testing is to detect unintended side effects, while the purpose of confirmation testing is to check if the original defect has been fixed.**
        
        **Correta**
        
        **Regression testing does not check successful implementation of corrections and confirmation testing does not check for side effects and Testing new functionality is not regression testing.**
        

76. **Which one of the following is the BEST definition of an incremental development model?**
    
    1. Testing is added to development as an increment.
    
    2. Defining requirements, designing software and testing are done in phases where in each phase a piece of the system is added.
    
    3. A phase in the development process should begin when the previous phase is complete.
    
    4. Testing is viewed as a separate phase which takes place after development has been completed.
    
    - Answer
        
        **b. Defining requirements, designing software and testing are done in phases where in each phase a piece of the system is added.**
        
        **Correta**
        
        **Incremental development involves establishing requirements, designing, building, and testing a system in pieces.**
        

77. **Which of the following statements comparing component testing and system testing is TRUE?**
    
    1. Component testing is the responsibility of the testers, whereas system testing typically is the responsibility of the users of the system.
    
    2. Component testing verifies the functionality of software modules, program objects, and classes that are separately testable, whereas system testing verifies interfaces between components and interactions between different parts of the system.
    
    3. Test cases for component testing are usually derived from component specifications, design specifications, or data models, whereas test cases for system testing are usually derived from requirement specifications or use cases.
    
    4. Component testing only focuses on functional characteristics, whereas system testing focuses on functional and non-functional characteristics.
    
    - Answer
        
        **c. Test cases for component testing are usually derived from component specifications, design specifications, or data models, whereas test cases for system testing are usually derived from requirement specifications or use cases.**
        
        **Correta**
        
        **Examples of work products that can be used as a test basis for component testing include detailed design, code, data model, component specifications. Examples of work products for system testing include system and software requirement specifications (functional and non-functional) use cases.**
        

78. **Which of the following should NOT be a trigger for maintenance testing?**
    
    1. decision to test after “hot fixes”
    
    2. decision to test the system after migration to a new operating platform
    
    3. decision to test if archived data is possible to be retrieved
    
    4. decision to test the maintainability of the software
    
    - Answer
        
        **d. decision to test the maintainability of the software**
        
        **Correta**
        
        **This is maintainability testing, not maintenance testing.**
        

79. **Which of the following is the correct list of the triggers for maintenance testing?**
    
    1. A component in production is modified, migrated or retired
    
    2. A fix has been received for a product that is in development
    
    3. regression has been discovered in a set of fixes just received from the developer
    
    4. A new requirement has been received for the software that is currently under test that may result in an architectural change
    
    - Answer
        
        1. **A component in production is modified, migrated or retired**
        

80. **Which of the following is a trigger for maintenance testing?**
    
    1. A new software product is being developed and defects have been found in unit testing
    
    2. A new software product is being developed and will work across multiple platforms
    
    3. A component of an existing production software product has been removed
    
    4. A component of an existing production software product has received high usage
    
    - Answer
        
        **c. A component of an existing production software product has been removed**
        

81. **Impact analysis helps to decide**
    
    1. How much regression testing should be done
    
    2. Exit criteria
    
    3. How many more test cases need to be written
    
    4. Different tools to perform regression testing
    
    - Answer
        
        a**. How much regression testing should be done**
        

82. **When should the testers start reviewing project documents?**
    
    1. When they have been baselined and approved
    
    2. After the first revision
    
    3. As soon as a draft is available
    
    4. When the developers have started coding
    
    - Answer:
        
        **c. As soon as a draft is available**
        

83. **What is important to do when working with software development models?**
    
    1. To adapt the models to the context of project and product characteristics
    
    2. To choose the waterfall model because it is the first and best proven model
    
    3. To start with the V-model and then move to either iterative or incremental models
    
    4. To only change the organization to fit the model and not vice versa
    
    - Answer
        
        1. **To adapt the models to the context of project and product characteristics**
        

84. Which of the following Software Development Lifecycle Models performs acceptance testing only one time during the project?
    
    1. Spiral Model
    
    2. Iterative Models
    
    3. Sequential Lifecycle
    
    4. Agile
    
    - Answer
        
        **c. Sequential Lifecycle**
        

85. Beta testing is
    
    1. Performed by customers at their own site
    
    2. Performed by customers at the software developer’s site
    
    3. Performed by an independent test team
    
    4. Useful to test software developed for a specific customer or user
    
    - Answer
        
        1. **Performed by customers at their own site**
        

86. **Which of these is a functional test?**
    
    1. Measuring response time on an on-line booking system?
    
    2. Checking the effect of high volumes of traffic in a call-center system
    
    3. Checking the on-line bookings screen information and the database contents against the information on the letter to the customers
    
    4. Checking how easy the system is to use
    
    - Answer
        
        **c. Checking the on-line bookings screen information and the database contents against the information on the letter to the customers**
        

87. **A regression test:**
    
    1. is only run once
    
    2. Will always be automated
    
    3. Will check unchanged areas of the software to see if they have been affected
    
    4. Will check changed areas of the software to see if they have been affected
    
    - Answer
        
        **c. Will check unchanged areas of the software to see if they have been affected**
        

88. **Consider the following statements about regression tests:  
    **_**1- They may usefully be automated if they are well designed  
    2- They are the same as confirmation tests (re-tests)  
    3- They are a way to reduce the risk of a change having an adverse affect elsewhere in the system  
    4- They are only effective if automated.**_**  
      
    Which pair of statements is true?**
    
    1. 1 & 2
    
    2. 1 & 3
    
    3. 2 & 3
    
    4. 2 & 4
    
    - Answer
        
        **b. 1 & 3**
        

89. **Which of these statements about functional testing is true?**
    
    1. Structural testing is more important than functional testing as it addresses the code
    
    2. Functional testing is useful throughout the lifecycle and can be applied by business analysts, testers, developers and users
    
    3. Functional testing is more powerful than static testing as you actually run the system and see what happens
    
    4. Inspection is a form of functional testing
    
    - Answer
        
        **b. Functional testing is useful throughout the lifecycle and can be applied by business analysts, testers, developers and users**
        

90. **You have been receiving daily builds from the developers. Even though they are documenting the fixes they are including in each build, you are finding that the fixes either aren’t in the build or are not working. What type of testing is best suited for finding these issues?**
    
    1. Unit Testing
    
    2. System Testing
    
    3. Confirmation Testing
    
    4. Regression Testing
    
    - Answer
        
        **c. Confirmation Testing**
        

91. **A defect was found during testing. When the network got disconnected while receiving data from a server, the system crashed. The defect was fixed by correcting the code that checked the network availability during data transfer. The existing test case covered 100% of all statements of the corresponding module. To verify the fix and ensure more extensive coverage, some new tests were designed and added to the test suite.  
      
    What types of testing are mentioned above?  
    a. functional testing  
    b. Structural testing  
    c. re-testing  
    d. performance testing**
    
    1. a., b. and d.
    
    2. a. and c.
    
    3. a., b. and c.
    
    4. a., c. and d.
    
    - Answer
        
        **c.- a., b. and c.**
        

92. **What is the purpose of performing regression testing when system maintenance activities have occurred?**
    
    1. To ensure the overall system has not regressed
    
    2. To ensure no unauthorized changes have been applied to the system
    
    3. To assess the scope of maintenance performed on the system
    
    4. To identify any maintainability issues with the code
    
    - Answer
        
        1. **To ensure the overall system has not regressed**
        

93. **For which of the following would maintenance testing be used?**
    
    1. Correction of defects during the development phase
    
    2. Planned enhancements to an existing operational system
    
    3. Complaints about system quality during user acceptance testing
    
    4. Integrating functions during the development of a new system
    
    - Answer
        
        **b. Planned enhancements to an existing operational system**
        

94. Which of the following uses impact analysis the most?
    
    1. Component Testing
    
    2. Non-functional System Testing
    
    3. User Acceptance Testing
    
    4. Maintenance Testing
    
    - Answer
        
        **d. Maintenance Testing**
        

95. **Consider the following statements about maintenance testing  
    1- It requires both re-test and regression test and may require additional new tests.  
    2- It is testing to show how easy it will be to maintain the system  
    3- It is difficult to scope and therefore needs careful risk and impact analysis.  
    4- It need not be done for emergency bug fixes  
    Which of the statements are true?**
    
    1. 1 and 3
    
    2. 1 and 4
    
    3. 2 and 3
    
    4. 2 and 4
    
    - Answer
        
        1. **1 and 3**
        

96. **Which of the following best describes component integration testing?**
    
    1. tests the individual components that have been developed
    
    2. tests interactions between modules or subsystems
    
    3. only uses components that form part of the live system
    
    4. tests interfaces to other systems
    
    - Answer
        
        **b. tests interactions between modules or subsystems**
        

97. **Which of the following best describes the main focus of acceptance testing?**
    
    1. finding defects in the system
    
    2. ensuring that the system is acceptable to every user
    
    3. testing the system with other systems
    
    4. testing from a business perspective
    
    - Answer
        
        **d. testing from a business perspective**
        

98. **Which one of the following statements about system testing is NOT true?**
    
    1. system testing is often performed by independent teams
    
    2. functional testing is used more than structural testing
    
    3. defects found during system tests can be very expensive to fix
    
    4. end-users must be involved in system testing
    
    - Answer
        
        **d. end-users must be involved in system testing**
        

99. **Which of the following best describes the difference between confirmation and regression testing?**
    
    1. confirmation ensures the original fault has been removed; regression testing looks for unexpected side-effects
    
    2. confirmation looks for unexpected side-effects; regression testing ensures the original fault has been removed
    
    3. confirmation is done after faults are fixed;regression testing is done earlier
    
    4. confirmation is done by developers; regression testing is done by independent testers
    
    - Answer
        
        1. **confirmation ensures the original fault has been removed; regression testing looks for unexpected side-effects**
        

100. **Which of the following statements is true?  
    Regression testing should be performed:  
    i.once a month  
    ii.when a defect has been fixed  
    iii.when the environment has been changed  
    iv.when the software has changed**
    
    1. i, ii and iv
    
    2. ii, iii and iv
    
    3. i, iii and iv
    
    4. i, ii and iii
    
    - Answer
        
        **b. ii, iii and iv**
        

101. **In which test level might you use an incremental approach?**
    
    1. component (unit)testing
    
    2. system testing
    
    3. component integration testing
    
    4. operational acceptance testing
    
    - Answer
        
        **c. component integration testing**
        

102. **The degree to which a component or system uses time, resources and capacity when accomplishing its designated functions is?**
    
    1. stress testing
    
    2. load testing
    
    3. performance testing
    
    4. reliability testing
    
    - Answer
        
        **c. performance testing**
        

---

![](Dashboard/Attachments/icons_questions%208.png)

The **Sentence Method** is a simplified way to record notes on the fly. You should revisit your note after it is complete to restructure the information for easier reviewing later.