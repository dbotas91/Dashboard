---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---

![](Dashboard/Attachments/icons_notes--outline%203.png)

# Data Model - InsuranceSuite Analyst Fundamentals

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201259.svg)Date Created|@January 23, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20936.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20680.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20499.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20131.svg)Last Edited|@January 26, 2022 4:20 PM|

[Data Model](#3212be4a-3d25-4ecb-8054-ace3eb0b3071)

[1. Data Model Components](#8d88bdbe-e2b4-4d25-b03c-cb9ab1a3064d)

[2. Entity Basics](#4deb5f23-0fa2-468d-9f44-61ecab13c84f)

[3. Data Field](#9f1534d5-0d9b-437d-92e5-1e382e47f87d)

[4. Foreign key field](#be78f7d2-51d7-4a3f-8384-dd0067fec32c)

[5. Array](#f7727d2a-349f-45a4-9351-d0ce7cd6bde8)

[6. Data Dictionary](#fd90d534-581c-49d1-b13f-33a1ac8d7b81)

[7. Typelist Basics](#1569934f-92b6-4bc1-bd18-921408faa8be)

[8. Questions](#a4e2669d-eb61-4c53-92c2-9e4f8e6da050)

# Data Model

The data model for InsuranceSuite organizes and stores data in entities. It used typelists to restrict the list of valid choices for data in a field. Every field that a user sees in the UI is based in some way on the underlying data model.

Changes to the UI are usually based on underlying data stored in the Data Model. Understanding the data stored, allows a non-developer to make better decisions about configuration changes.

---

# 1. Data Model Components

The Guidewire data model consists of entities and typelists.

- An Entity defines a set of fields, or attributes, related to an object. Ex. A claim entity contains attributes related directly to a claim, like claim description and loss date.

- Typelist defines a set of code/value pairs, called typecodes. These are used to restrict or define values that are valid for a field. Ex. LossType defines a specific set of valid types of a loss.

Together these two components make up the data model.

[![](Dashboard/Attachments/Untitled%2032.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled.png)

---

# 2. Entity Basics

Entities define a set of attributes related to a specific object, as a claim, an exposure or a contact. Entities not only define those attributes but are used to store and retrieve that data. There are several types of data stored in an entity. Using CC as an example:

- Fields: there store atomic data about the entity. For example, a claim report data or if the claim is weather related.

- Type Keys: references a single value typelist, which is restricted to acceptable values. As accident type, claim source, loss type.

- Array keys: reference multiple rows in a related entity. For example, all addresses, secondary address, incidents.

- Foreign keys: reference a single row in a related entity. It is related to an id of another entity. For example catastrophe, assigned group.

---

# 3. Data Field

A data field is where a single value is stored. For example, the Claim entity has fields for Id, description, closed date, fault and so on. These fields are physical data fields that will be stored and retrieved from the database.

[![](Dashboard/Attachments/Untitled%201%2012.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%201.png)

---

# 4. Foreign key field

A foreign key field stores a reference to a related object in the data model. It defines a unidirectional relationship.

[![](Dashboard/Attachments/Untitled%202%209.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%202.png)

---

# 5. Array

An array defines a set of additional related rows in another entity.

[![](Dashboard/Attachments/Untitled%203%207.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%203.png)

---

# 6. Data Dictionary

The Data Dictionary documents the entities and typelists in a Guidewire application. The dictionary includes information for both the base application entities and customer extensions. Whenever changes are made to the data model, the implementation team should regenerate the data dictionary so it will include the changes.

[![](Dashboard/Attachments/Untitled%204%206.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%204.png)

---

# 7. Typelist Basics

InsuranceSuite displays many fields in the interface as drop-down lists of possible values. The list of available values for a drop-down field is called a typelist. Typelists limit the acceptable values. Wherever there is a dop-down list in the UI, it is usually a reference to a typelist.

The typelist can be reference by typekey fields on multiple entities.

The typelist represents a predefined set of possible values, with each separate value defined as a typecode.

A typekey field is an entity field that is associated with a specific typelist. It can pont to exactly one typecode in the typelist.

[![](Dashboard/Attachments/Untitled%205%206.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%205.png)

The typelists are the basis for almost all dropdowns lists in the InsuranceSuite. The values available in a typelist can be restricted by applying a type filter which is designed to reduce the list of available values based on some other data element.

---

# 8. Questions

[![](Dashboard/Attachments/Untitled%206%206.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%206.png)

[![](Dashboard/Attachments/Untitled%207%207.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%207.png)

[![](Dashboard/Attachments/Untitled%208%206.png)](Data%20Model%20-%20InsuranceSuite%20Analyst%20Fundamentals/Untitled%208.png)