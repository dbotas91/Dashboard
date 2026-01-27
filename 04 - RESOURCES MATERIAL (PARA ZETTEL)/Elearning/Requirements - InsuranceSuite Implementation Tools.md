---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%2015.png)

# Requirements - InsuranceSuite Implementation Tools

|   |   |
|---|---|
|![](Dashboard/Attachments/arrow-northeast_gray%201194.svg)Subject|[![](Dashboard/Attachments/icons_graduate%2023.png)InsuranceSuite Implementation Tools/Curriculum for InsuranceSuite 9.0 Analysts/PMs](../Subjects/InsuranceSuite%20Implementation%20Tools%20Curriculum%20for%206d35ed61e4a9476880379373e4727236.html)|
|![](Dashboard/Attachments/calendar_gray%201270.svg)Date Created|@January 23, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20947.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20693.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20512.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20144.svg)Last Edited|@January 26, 2022 4:20 PM|

[1. Requirements Gathering Process](#46874649-cefa-415d-b0bf-dcc48c34185d)

[Elaboration sessions](#e0ae8143-77e2-44db-a974-1f24ceb42afe)

[2. Elaboration Workshops](#39c9d56b-8dbb-441b-93fd-730799d67119)

[3. Acceptance Criteria](#994b5114-9ee1-421d-b603-e47ba74c3b9b)

[How different roles use acceptance criteria](#76f39942-577a-4d4c-b947-d51803d0c0f4)

[4. Questions](#ac89f9ce-7541-4638-ad1f-4a1c29802558)

# 1. Requirements Gathering Process

The requirement gathering process is different depending on the phase of the project.  
During Inception, user stories are identified and then requirments are elaborated at a high level in Elaboration Workshops. This is done to understand the nature of the user story so that estimates can be created. During inception, the functional details of the user story are not elaborated. If using Behavior-Driven Development (BDD), requirements are captured as rules and examples using an example mapping technique.

During Sprint 0, the Agile team prepares for development by setting up the development environment, completing training and conducting a Mock delivery sprint. Also, requirements for the first sprint maybe elaborated to get a head-start on Development.

The Development phase divides time into sprint pre (Sprint N-1) and the actual development sprint (Sprint N). As mentioned, Business Analysts (BAs) typically work on the requirements a sprint ahead (Sprint N-1) to allow for development to start on the first day of Sprint N. During Development, user stories are elaborated to a functional details level Requirement Refinement workshops are held to elaborate the funcitonal details of the requirments and update the story cards as needed. If using BDD, the Three Amigos meet in Story Huddles to further clarify example maps for each story, add examples, and translate examples into concrete examples. Then the Developer or Quality Engineer translates the concrete examples into Gherkin Scenarios to crearte the Feature File for Automated testing.

[![](Dashboard/Attachments/Untitled%20142.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled.png)

## Elaboration sessions

During Inception sprints, project teams will meet regularly with key stakeholders to identify and elaborate on the business requirements. These meetings are called elaboration sessions or workshops. The goal of these elaboration sessions is to identify value-drive changes to the standard User Story to support business processes. The workshops also help project teams better understand the product to be implemented and requiremens needed.

Project team typically include Subject Matter Experts, Business Analysts, Business System Analysts or Technical Business Analysts, Quality Analyst and a Scrum MAster. At the start of the project, these sessions are led by Guidewire, but eventually they are expected to be led by the customer as the project progresses. The Business Analyst typically facilitates the elaboration sessions.

Elaboration sessions help team members gain a clearer understanding of the product:

- Guidewire begins by looking at the standard user story backlog for the project based on the products purchasedd and the lines of business to be implemented;

- Then the standard process flows are reviewed and how those tie back to the product screen functionality.

- Next, the high-level requirements along with any concern and possible gaps are discussed.

- After these elaboration conversations, the user story is revisited to validate the estimate for the user story. The team may decide the user story is not required, that the estimate can be reduced or increased, or perhaps to create a new user story if there is a gap requirement to address during the implementation.

[![](Dashboard/Attachments/Untitled%201%2021.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%201.png)

[![](Dashboard/Attachments/Untitled%202%2017.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%202.png)

---

# 2. Elaboration Workshops

[![](Dashboard/Attachments/Untitled%203%2015.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%203.png)

[![](Dashboard/Attachments/Untitled%204%2012.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%204.png)

[![](Dashboard/Attachments/Untitled%205%2012.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%205.png)

[![](Dashboard/Attachments/Untitled%206%2012.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%206.png)

[![](Dashboard/Attachments/Untitled%207%2012.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%207.png)

---

# 3. Acceptance Criteria

Acceptance Criteria are used to identify when a User Story is done development. They describe the conditions that must be met before a user story can be considered complete. These are also known as conditions of satisfaction. They should be written in clear and concise statements in business terms with a clear pass or fail result.  
While acceptance criteria do provide details which are used as input for test case creation and Feature Files, they are not test cases or edge test cases themselves. Also they should not be just restatements of the requirements or a description of a solution.  
It is recommended that Acceptance Criteria be written as early as possible and at the same times as the Business Requirement. However, some of the Acceptance Criteria will be discovered in ongoing backlog refinement sessions before the sprint starts and others will be discovered right after sprint planning when the team sits down to have a conversation about the user Story.

[![](Dashboard/Attachments/Untitled%208%2011.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%208.png)

After the requirements are elaborated, the Business Analyst should update the user story cards as usual, adding functional requirements, adding Acceptance Criteria to the Business Acceptance tab, and other information gathered for all the other tabs.  
If applying the BDD approach, the Business Acceptance tab should be completed by adding the Acceptance criteria in a “Given-When-Then” format or at least by adding a draft of the acceptance criteria in common business terms. If questions arise, the BA may need to iterate back with the business stakeholders to gain additional details.  
The Business Analyst, Developer and Quality Analyst will refer to the acceptance criteria when writing acceptance tests.

## How different roles use acceptance criteria

Acceptance criteria play a crucial role during development and are referenced by virtually every member of the project team:  
• Business Analysts: capture them during requirements gathering;  
• Developers: use them to configure and code requirements;  
• Quality Testers: use them to define test cases and derive a pass or fail status  
• Product Owners: user them to confirm if a user story com be accepted.

[![](Dashboard/Attachments/Untitled%209%208.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%209.png)

[![](Dashboard/Attachments/Untitled%2010%207.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%2010.png)

---

# 4. Questions

[![](Dashboard/Attachments/Untitled%2011%207.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%2011.png)

[![](Dashboard/Attachments/Untitled%2012%207.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%2012.png)

[![](Dashboard/Attachments/Untitled%2013%206.png)](Requirements%20-%20InsuranceSuite%20Implementation%20Tools/Untitled%2013.png)

---