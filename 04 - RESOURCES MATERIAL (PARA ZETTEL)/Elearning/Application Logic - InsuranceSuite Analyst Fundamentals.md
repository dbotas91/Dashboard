---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--outline%201.png)

# Application Logic - InsuranceSuite Analyst Fundamentals

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201257.svg)Date Created|@January 24, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20934.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20676.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20495.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20127.svg)Last Edited|@January 26, 2022 4:20 PM|

[Application Logic](#577c2a5c-c3e8-4a73-8ef7-38efee390187)

[1. Logic](#cf81d2dc-677e-42cb-b580-5e78db813254)

[2. Two types of Rules](#8a3fd748-5e98-4981-8319-499d7138e012)

[Configuring Gosu Rules](#854b57c4-193f-4679-a24f-81bd52a0eb56)

[Business rule components](#59927afb-3ad5-4d27-84f8-0b3f9045263c)

[Business Rules Basic Info](#2be5c780-9fe9-4221-af23-c018714fb46e)

[3. Configuring PCF’s](#54e2cdea-451e-4481-a61f-2e4d06c70677)

[4. Configuring Classes](#32730593-a56e-49fb-8441-d0549db0f676)

[5. Configuring Entity Names](#de2831cf-85aa-40b4-a9b9-d2f2a76f8c2f)

[6. Determining application logic changes](#23e254e5-710f-4d25-94e4-d4121332da64)

[7. Questions](#fa3c49f0-579c-4b05-a698-547c4295f357)

# Application Logic

Application logic is the code that determines the functionality and behavior of all InsuranceSuite products. This code is written in Gosu, Guidewire’s programming language. Most projects require some changes to InsuranceSuite Functionality to satisfy the Insurance Carrier’s business needs. BAs and users of the application need to understand the base product application logic so they can identify and document new business requirements for the User Interface, rules and processing flow of the application that are compatible with the base product.

When identifying new business logic requirements, non-developers should focus on changes that add value to their company’s implementation. Examples of requirements that add value are changes that ensure compliance with federal or state regulations, help the insurer maintain a competitive advantage or improve business processes.

---

# 1. Logic

Gosu, Guidewire’s programming language, is used for the development of all InsuranceSuite Application logic. Gosu is similar to java and javascript.

Gosu is used in these five major areas of InsuranceSuite applications:

- Gosu Rules

- Business Rules

- The User Interface

- Classes

- Entity Names

[![](Dashboard/Attachments/Untitled%2030.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled.png)

---

# 2. Two types of Rules

There are two types of rules:

1. Gosu rules: which are creates in Guidewire Studio by developers;

2. Business rules, which are created in the Business Rules administration screens by non-developers

Gosu rules cover a wider variety of business processes and objects than Business rules do and can handle much more complex scenarios.

1. Gosu Rules - developers

Gosu rules are organized into categories with a specific business purpose. Examples: include Approval, Assignment and Validation, among others.

Rules are triggered or executed in response to an event which is either the creation of or an update to the business object the rule is associated with.

- Approval rules are triggered by the creation or update of a financial transaction;

- Assignment rules are triggered by business objects that can be assigned (claim, activities, exposures);

- Validation rules are triggered by an even variety of business objects.

- Creating Gosu rules requires a developer’s technical expertise as well as domain knowledge of claims handling.

Each Gosu rule works in a specific business object or entity, such as a claim, exposure or contact.

Each rule has condition that evaluates to either true or false. If the condition evaluated to true, then the action is executed. If the condition evaluates to false, nothing happens.

## Configuring Gosu Rules

Gosu Rules are provided for business pruposes not abailable for Business rules and can handle more complex logic.

For example, Assignment rules often need multiple decision points to correctly determine who should own a specific claim, exposure and so on. The same is true of the Approval rules that determine when financial transactions need to be approved.  
There are many other business purposes that can be handled with Gosu rules as well.

Even though developers create and maintain Gosu rules, non-developers often identify business requirements that are best handled using Gosu rules. There requirements should be documented in terms of conditions and actions that can be easily communicated to developers. The developer will then determine the correct category or business purpose for the rule and will write the code for the rule and test it.

[![](Dashboard/Attachments/Untitled%201%2010.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%201.png)

1. Business rules - non-developers

Business rules are created by users in the business rules administration screens. Currently in CC, Business rules are used to create activities, Exposures and Reserves.

These rules are triggered by an action on a business object. For example, the Reserve Rules shown here are triggered by the creation of a new exposure.

## Business rule components

Here is an overview ot the Business Rule screen using a rule that creates a new exposure.

- Basic Information are containts the name, description and triggering entity and action for this rule;

- Applicability criteria area contains conditions to filter out the trigger entities this rule does not apply to;

- Rule conditions area contains one or more conditions which must be true in order to execute this rule’s action;

- Action are contains the action to be performed if this rule’s conditions are true;

[![](Dashboard/Attachments/Untitled%202%207.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%202.png)

## Business Rules Basic Info

The Basic Information section identifies what the rule is for. Every new rule must have a name, and thought optional, a descritption of what the rule does is helpful as this displays in the list of the existing rules so that users can get a basic idea of what the rule does.

Next, the entity (the business object) and the action that trigger the rule to execute are identified. Finally, the rule can be marked disabled if it should not be run for some reason.

[![](Dashboard/Attachments/Untitled%203%206.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%203.png)

The Applicability Criteria section of the Rule screen allows you to limit the trigger entities or business objects the rule will execute against to just those that match the selections made here.

[![](Dashboard/Attachments/Untitled%204%205.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%204.png)

[![](Dashboard/Attachments/Untitled%205%205.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%205.png)

[![](Dashboard/Attachments/Untitled%206%205.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%206.png)

---

# 3. Configuring PCF’s

Simple logic can be used in configuring PCF files used in developing the User Interface of IS products.

For example, when adding a new contact to an Account in PolicyCenter, the Contact Detail card for a Person includes a single field Primary Phone. When a value is entered in the field Mobile Phones, the Primary Phone field is automatically set to Mobile.

This is configurable behavior and provides a mechanism for automatically setting the value of the Primary Phone field based on the phone number provided. This eliminates the need for the user to set this field unless more than one phone number is entered an the user chooses to explicitly identify which phone number is the primary phone number.

Application logic is also used in PCF’s to control the behavior of the User Interface.

In this example taken from PC, the Account File Contacts screen includes a button menu for adding contacts to an account. When a New Person is selected from the Claims Info Contact item of the menu, the New Claims Info Contact screen is displayed with the fields for a Person contact. Menu items are used in other contexts in the User Interface to navigate to another location in the application.

- The ‘Actions’ button provides menu options to open additional screens for creating notes, activities, and document, copying submission and for navigating to accounts and policies.

- The menu links in the left pane support navigation to other parts of the application, such as displaying the workplan of history for a policy.

[![](Dashboard/Attachments/Untitled%207%206.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%207.png)

---

# 4. Configuring Classes

While gathering business requirments the need for new computed valued or business logic may be identified. For example, in reviewing the User Interface screen that displays contact details for a person, it may be determined that a field is needed to display the current age of the person provided the date of birth field is populated.

The example shown here user the current date to calculate the age, but he nosiness need may actually be to calculate the age based on the date of loss. This information could be used to determine if the driver of a vehicle involved in an accident was a minor at the time of the accident, Another business requirement might be to return the month portion of the date as the name of the month instead of the numeric value. This more generic requirment may have multiple uses such as for display in the UI and also in reports.

The non developer’s responsability is to document these requirements in simple language that a developer can convert into code. It is up to the developer to determine if the code applies to a single business object or if it is reusable, as well as where the code will be created and how it will be accessed by the application.

[](https://www.notion.soundefined)

---

# 5. Configuring Entity Names

Entity names are often created by concatenating two or more fields into a string to display meaningful information about a business object in the UI. For example, the entity name for an exposure is created by joining several pieces of information together.

- A number representing the order in which the exposure was added to the claim;

- The loss party for the exposure;

- The claimant’s name (this is also an entity name for a contact)

The entity names provided in the base product can be modified if the Insurance Carrier would like to include different information. Note that only developers can create or modify entity names.

[![](Dashboard/Attachments/Untitled%208%205.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%208.png)

---

# 6. Determining application logic changes

Changes to the application logi are identified by walking through the base product and reviewing the functionality with end users, business analysts and developers.

Areas to focus include:

1. Review the fields on each screen an identify any fields to be added or removed. Are there fields that should be visible only when other fields are set, or to specific user roles?

2. Look to how the user navigates through the screens - are any changes needed?

3. Consider what validations are required when entering data - when should the user be warned about missing or possibly incorrect data, and when should they be prevented from saving their changes? What messages should display for validation errors?

4. Review options for assigning work to users and document the requirements. Consider how your current assignment process could be simplified or improved;

5. When claims and exposures are created, are there specific activities (diary entries) that should be created automatically?

6. Are there any exposures that could be created automatically when details of a loss are captured?

7. Does sufficient historical data exist to create the initial reserves for new exposures?

[![](Dashboard/Attachments/Untitled%209%204.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%209.png)

---

# 7. Questions

[![](Dashboard/Attachments/Untitled%2010%204.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%2010.png)

[![](Dashboard/Attachments/Untitled%2011%204.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%2011.png)

[![](Dashboard/Attachments/Untitled%2012%204.png)](Application%20Logic%20-%20InsuranceSuite%20Analyst%20Fundame/Untitled%2012.png)