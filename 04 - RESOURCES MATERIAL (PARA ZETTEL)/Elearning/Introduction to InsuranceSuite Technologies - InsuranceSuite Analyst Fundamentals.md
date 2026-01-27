---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%208.png)

# Introduction to InsuranceSuite Technologies - InsuranceSuite Analyst Fundamentals

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201264.svg)Date Created|@January 23, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20941.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20686.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20505.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20137.svg)Last Edited|@May 6, 2022 3:30 PM|

[1. Configuration and the technology stack](#d2db0324-a86c-46e5-9ab7-68d681473eed)

[2. InsuranceSuite Technologies](#4f2df41d-3d4a-40c9-9611-17da337e6760)

[3. Questions](#1fcc058e-8a31-4edc-88da-eda856467094)

# 1. Configuration and the technology stack

Configuraition is modifying the base application behavior to support specific business requirements. At some level, this is a normal process during implementation of InsuranceSuite, as almost all implementations require some amount of configuration.  
This requires a coordinated effort between developers and non-developers. The developers will wirte or modify the code or system behavior, while the non developers help define and communicate the business requirements that are beyond the behavior of the base application.

Non developers need to understand the underlying technologies so they can communicate business requirements effectively with the development team. Knowing what can be configured and how the base application behaves, helps the non-developer decide what needs to be configured, without unnecessary changes.

---

# 2. InsuranceSuite Technologies

The Guidewire platform is layer of configuration technology that includes the functionality needed to define a Guidewire application. For example, it includes the technology needed to define a Guidewire application. For example, it includes the technology to define:

- The user interface;

- The data model;

- Application logic;

- Integration points.

Insurancesuite uses common technology to define its own data model, user interface, business logic and integration points. Each application is distinct but shares common features and configuration techniques with all the other applications. For example, and administrator creates, modifies and deletes users in the same way across all InsuranceSuite applications. This common approach is possible because data model entities, PCF files and the application logic to manage users are all defined in the Guidewire platform.

[![](Dashboard/Attachments/Untitled%2037.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled.png)

1. User Interface (UI)
    
    Screens in InsuranceSuite are all build using Page Configuration Format files, or PCFs.  
    This is the same across all InsuranceSuite applications. Using PCFs, developers can change text, labels, colors, fonts and images. They can also add or removed fields or even create new screens. Screens sometimes include logic that helps control specific behavior. This logic can also be modified or even added.
    
    Changing the order of fields, changing labels or regrouping fields is a fairly simple change for developers. Creating new screens or changing the screen-based logic is more complex.
    
    User Interface changes are done by developers using Guidewire Studio, which is an Integrated Development Environment specifically designed for InsuranceSuite applications.
    
    [![](Dashboard/Attachments/Untitled%201%2017.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%201.png)
    

2. Data Model
    
    The core of any application is the data it stores an uses. In InsuranceSuite, there are two types of data: Entities and Typelists. Entities store dynamic data which is data about a thing such as a person or a claim. For example, a person’s name or address or the date of loss for a claim. Typelists are lists of static data that are used to restrict values that can be stored in an entity. For example, the severity of an injury is restricted to minor, moderate, major, life-threatening and death. Those are the only valid values for severity of an injury.  
    The data used in an InsuranceSuite application can be configured by a developer. Common configurations include adding fields that are not in the base application, such as passport number, or modifying the list of valid values in a Typelist, such as adding or removing a type of phone number. Another common configuration is adding data to support regulatory requirements.  
    These data model configurations are done by developers. However, the specifications for the business requirements are gathered by and communicated to the development team by non-developers.
    
    [![](Dashboard/Attachments/Untitled%202%2014.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%202.png)
    

3. Application Logic
    
    The behavior of an InsuranceSuite application is controlled by application logic. This logic is stored and executed in program code in the InsuranceSuite application. Developers use a programming language called Gosu in all Guidewire applications. Gosu is a language similar to Java.  
    Application logic is used in a number of places. Rules are one of the objects where application logic is used. Rules are executed automatically based on rule criteria such as when a object is created or modified. There are quite a few different sets of rules such as Validation rules, Assignment rules, Approval routing and so on.  
    Gosu code is also used in classes that contain functions that return calculated values for special circumstances. For example, a class cloud be created that returns the  
    number of days a claim has been open. Gosu code could also be used to determine the assignment of a claim or object to a specific group and user.  
    These data model configurations are done by developers. However, the specifications for the business requirements are gathered by and communicated to the development team by non-developers.
    

4. Integration
    
    Integration with external systems is a common and important aspect of InsuranceSuite implementations. InsuranceSuite integrates with several systems including external policy systems, general ledger system …  
    Integrations are configured by specifying the data that is passed to the external systems as well as what data is returned. The timing of the integrations may also be configured.  
    Configuration of Integrations are done by developers using Guidewire Studio and typically involve programming code.
    

---

# 3. Questions

[![](Dashboard/Attachments/Untitled%203%2012.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%203.png)

[![](Dashboard/Attachments/Untitled%204%209.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%204.png)

[![](Dashboard/Attachments/Untitled%205%209.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%205.png)

[![](Dashboard/Attachments/Untitled%206%209.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%206.png)

[![](Dashboard/Attachments/Untitled%207%209.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%207.png)

[![](Dashboard/Attachments/Untitled%208%208.png)](Introduction%20to%20InsuranceSuite%20Technologies%20-%20Insu/Untitled%208.png)

---