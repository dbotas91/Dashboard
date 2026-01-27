---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%2019.png)

# User Story and User Story Cards - InsuranceSuite Implementation Tools

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201196.svg)Subject|[![](Dashboard/Attachments/icons_graduate%2025.png)InsuranceSuite Implementation Tools/Curriculum for InsuranceSuite 9.0 Analysts/PMs](../Subjects/InsuranceSuite%20Implementation%20Tools%20Curriculum%20for%206d35ed61e4a9476880379373e4727236.html)|
|![](Dashboard/Attachments/calendar_gray%201274.svg)Date Created|@July 13, 2021|
|![](Dashboard/Attachments/arrow-circle-down_gray%20951.svg)Status|Complete|
|![](Dashboard/Attachments/formula_gray%20517.svg)Next Review|@January 24, 2022|
|![](Dashboard/Attachments/calendar_gray%201274.svg)Last Review|@January 24, 2022|
|![](Dashboard/Attachments/checkmark-square_gray%20698.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20517.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20149.svg)Last Edited|@January 26, 2022 4:20 PM|

[User Story and User Story Cards](#cecf57bf-1f57-4dce-b100-5a4e53ba0844)

[1. Guidewire Project Lifecycle - Phases](#3287a8e1-1d93-4d15-bac4-8727400b87ad)

[2. Planning Delivery Sprints with User Stories](#d6b1c9b7-3a82-4dc1-9406-16f95c1d313c)

[Estimate Release “Planner” tool](#d1e893e2-e17e-4f0e-a038-9966367414c2)

[3. Documenting User Story Cards](#802951b5-427d-43c0-beb8-502a53786577)

[Customizing User Story Cards](#4c7e6bd6-09b6-4ae1-84f0-15ad44d60817)

[4. Questions](#8d7da074-a92f-43d1-8e91-ac5f29d89bf4)

# User Story and User Story Cards

One of the most integral tools of a Guidewire InsuranceSuite IMplementation is the User Story Card. From Pre-Inception through Development, essentially all team members refer to user sotires in various ways at some point in the project lifecycle.  
Guidewire has over 5000 User story cards on the standard features of InsuranceSuite products to leveraged if needed.

What is a user story?

A user story describes a high-level requirement for a needed system feature from a user’s perpective. It includes a role, an action, and a reason formulated as one or more sentences in the business langugae of the end user. User stories are part of an agile approach that helps shift the focus from writing detailed requirements to talking about the desired functionality. Often, they are captured on index cards or sticky notes during the project to reflect customer’s specific business requirements.

Guidewire has documented all standard feature of the InsuranceSuite base configuration in individual User Stories. Each User Story has a User Story description, a baseline estimate and a User Story Card. With customer decisions about features stories are included or excluded from scope.

Story elaboration

User stories are created via story elaboration. Elaboration refers to conversations that occur between the users and the project team during Inception to ensure that all requirements are understood. After these conversations, the high-level requirments that emerge from these discussions are documented.

What is a User Story Card?

It is a tool build by Guidewire Delivery Services to support Implementation Projects in the capturing of functional requirements. Guidewire provides user story cards for each standard User Story for the Guidewire product. Each story card represents a Guidewire User Story or a Customer Gap Story. However, a single User Story can drive changes to multiple story cards and, inversely, a single user story card can be edited to meet the needs of multiple stories.

Initially, a story card describes the standard behaviors of the base application. Then story cards are refined, or new story cards are created to reflect the customer’s specific business requirements. Ultimately, each story card becomes a detailed specification of what has been implemented to support the customer’s business requirements. They include details describing the user interface, business rules, acceptance criteria and other requirements.

Story Cards are used as the major point of communication between the business community and the software delivery team. They are intended to be easily understandable by virtually any member of the business community, and yet contain enough information for software developers to estimate the work effort and identify delivery risks.

---

# 1. Guidewire Project Lifecycle - Phases

User Story Cards play an important role during the early phases of the Guidewire Project Lifecycle through Development.

- During Pre-Inception, user stories are referenced for preliminary estimates and scooping efforts

- During inception, user stories are identified and then elaborated at a high level. This is done to understand the nature of the user story so that estimates can be created

- During Sprint 0 and Development sprint planning sessions, user stories and requirements are further refined to a detailed level and then used to build the solution

- During Stabilization requirements defects identified during testing may need Story Card updates

image

1. User Story - Pre-Inception
    
    User story cards are first used in the Pre-Inception phase. Guidewire provides a Preliminary Estimate before or during Pre-Inception based on a “Bottom-Up” estimate of every In-Scope User Story Card. Abottom-up estimate is an estimate where all the details are estimated. The socpe and estimate are based on customer answers to high-level questions.
    
    User Story Cards are identified for the project at the conclusion of Pre-Inception. This includes all the standard Guidewire Story Cards and Gap Story cards which will used to drive Inception elaboration and scope confirmation discussions.
    
    When naming the user story cards for the project, Guidewire recommends the following naming convention: Xcenter - Theme - Sub-theme - ID Number
    
    image
    

2. User Story Card - Development
    
    The User Stories that were commited by the team during Inception are now completed in Development sprints. This may be all part of a User Story Card feature.
    
    There are different types of story cards for different types of stories. For example: There are specific story for capturing requirements for changes to the User Interface, for Policy Froms, Activities and products or the product model.
    
    User Story Cards are filled out during Elaboration meetings or workshops. Each card is an Excel spreadsheet that has tabs for organizing the information such as:
    
    - Functional requirements
    
    - Action Items
    
    - Key Decisions
    
    - Validation and Busienss Rules
    
    - Design elements (UI Mockup / Fiel information)
    
    - Tpelists
    
    - Business Acceptance
    
    - Custom Details
    

3. User Story card - Stabilization

User Story Cards have reduced emphasis in Stabilization as the focus shifts to E2E, Performance and Stabilization Testing. This phase is driven by Test Strategy, Test Plans and Test Scripts specific for those purposes. Defects are categorized as Process or Requirements Defects. Requirements defects need Story CArd updates to correct the requirement in the User Story Card along with the correction in the configuration.

---

# 2. Planning Delivery Sprints with User Stories

## Estimate Release “Planner” tool

Guidewire has an estimation tool or “Planner” which includes complex logic to quickly estimate User Stories based on multiple criteria unique to an organization and their project stategy.

This estimation tool is used as a starting point to estimate the project. Each User Story must be further broken down to validate the estimate. The backlog of User Stories, as defined by the scope selections in the release planner, are imported into a conceptual sprint planning tool, to assist with planning the inception sprints, before being imported into a project management tool such as Jira.

1. Themes
    
    When planning an implementation project, Guidewire has a detailed planning and priorization approach, called Themes, to break down the work into smaller buckets.  
    Then each theme is further broken down into features, User Stories and eventually tasks.
    
    Displayed here you can see a set of themes that are common processes Guidewire has identified within the product. Guidewire provides a list of over 5000 standard User stories grouped by these themes for all base products to help customers jump-start the project and avoid re-creating the wheel.
    
    [![](Dashboard/Attachments/Untitled%20146.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled.png)
    

2. Features, User Stories and Tasks
    
    Here you can see an example of how a theme for ClaimCenter is broken down into features (also known as subthemes). Each feature contains multiple User Stories.  
    Then, each User Story is broken down into taks, which are captured and estimated during sprint palnning sessions. Team members maintain their tasks and User Stories daily to track and show process.
    
    [![](Dashboard/Attachments/Untitled%201%2025.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%201.png)
    

3. Planning
    
    We do not know everything at the beginning of the project, so we plan based on what we do know. Plan to the horizon and then re-evaluate preiodically as needed.
    
    Planning an implementation is much like peeling an onion. It is done in layers:
    
    - Start by planning the program
    
    - Next plan the project
    
    - Thirdly, plan each Release
    
    - Then plan the iteration or sprints whithin the Release
    
    - Finally, plan the Daily Scrum
    
    [![](Dashboard/Attachments/Untitled%202%2021.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%202.png)
    

4. Steps to plan a delivery sprint

Here you can see how User Stories play are integral role in planning out development work. These are the recommended stpes to follow when planning a Deliveru Sprint:

- Determine team capacity

- Define sprint backlog

- Validate estimate for each

- User Story

- Define tasks for each User Story in the sprint
    
    - Assign a resource to each task
    
    - Estimate each task
    
    - Add new User Stories and tasks as needed
    
    - Repeat Steps 1-5 until sprint capacity is full

[![](Dashboard/Attachments/Untitled%203%2018.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%203.png)

Planning best practices:

- Standardize sizing guidelines to improve predictability across the program

- Standardize the task list before loading the Product Backlog

- Prioritize the Release Backlog to facilitate planning

- Move stories to sprints according to the Conceptual Sprint Plan, and enter capacity for each sprint to see how loaded the sprint is

- Dedicate the team to sprint planning at the start of each sprint. Validate estimates during sprint planning and build time into the project plan for this activity

- Add all tasks to in-scope stories during sprint planning, not in the middle of the sprint

- Only estimates tasks and hours of stories in the current sprint

- Refine the plan each sprint based on new information regardind priorities, business value, risks, dependencies and defects.

---

# 3. Documenting User Story Cards

When writing User Stories, keep in mind the INVEST model for well written user stories.

[![](Dashboard/Attachments/Untitled%204%2015.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%204.png)

Good stories should be self-contained with no inherent dependencies. When writing stories, try to avoid inter-story dependencies because it is hard to demonstrate a story that requires features from a future sprint.

When you have a story with a dependency, try to break down the story down the story further so that it can stand alone. However, if the dependency is unavoidable, consider the “cost” of doing it later in the project.

[![](Dashboard/Attachments/Untitled%205%2015.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%205.png)

## Customizing User Story Cards

During a project, the story cards can be customized in many ways. These are some of the mostcommon customizations.

Often, you may need to Enhance and modify this tool to meet your project needs, such as adding columns to existing tabs to support the requirements.

For example:

- A requirement number column can be added to each tab with a unique numbering system for traceability, or column indicating follow-on releases.

- During development, QA engineers may document testing results in the user story by adding columns such as Test by, Date tested, Pass or Fail, Submission Number, Policy Number and comments.

You can also create additional tabs for requirements that are not readily captured in other tabs such as adding tabs for data mapping, integration triggers or integration failover.

To make mass updates to all the user story cards for a project, make your modifications to the base user story card template before they are generated.

---

# 4. Questions

[![](Dashboard/Attachments/Untitled%206%2015.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%206.png)

[![](Dashboard/Attachments/Untitled%207%2014.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%207.png)

[![](Dashboard/Attachments/Untitled%208%2013.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%208.png)

[![](Dashboard/Attachments/Untitled%209%2010.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%209.png)

[![](Dashboard/Attachments/Untitled%2010%208.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%2010.png)

[![](Dashboard/Attachments/Untitled%2011%208.png)](User%20Story%20and%20User%20Story%20Cards%20-%20InsuranceSuite%20I/Untitled%2011.png)

---