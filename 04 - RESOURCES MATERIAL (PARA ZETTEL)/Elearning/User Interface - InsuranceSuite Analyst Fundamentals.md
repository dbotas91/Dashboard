---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%2017.png)

# User Interface - InsuranceSuite Analyst Fundamentals

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201272.svg)Date Created|@January 24, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20949.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20696.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20515.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20147.svg)Last Edited|@January 26, 2022 4:20 PM|

[User Interface](#eb0fb01c-3b10-4bac-9db2-eeaaca4cab12)

[1. The User Interface for all InsuranceSuite products.](#7c83b18a-0c95-4b7a-894c-20e4c39b1e5f)

[Screen Area](#ad1b8585-f9fd-412b-9144-68a6b16b7a3c)

[Sidebar](#3060a8bc-8a54-4deb-b993-a4ed26b5e1e7)

[Tab bar](#1830b1ab-bf5b-42e6-9f0e-9e78bf2a6f8a)

[Info bar](#d171ae8d-0c2f-4c4c-99b5-52e45217643d)

[Workspace](#5d5f5289-d544-4330-a406-ddb7f26af1b3)

[2. User Interface Components](#3b5e8f3c-878a-462e-b077-c18696be5e1a)

[3. Widget Examples](#73bc58d1-818d-49c9-a54c-481945f71854)

[4. How to interrogate location information](#803f77a9-9c54-44cf-9bc8-8c079e98f992)

[5. Developer’s Role in configuration](#a90d8251-d78d-4929-8a31-78f65d9734ef)

[Guidewire Studio](#ebce5545-d056-4eae-9fee-033c19517176)

[6. Questions](#3c1895a3-bc45-4261-b9e5-6884223e9e71)

# User Interface

Even though BAs and QAs will not configure InsuranceSuite (IS) products, it is still useful for these users to understand the User Interface (UI) architecture. This is true because most if not all implementations of IS products will require some UI changes, and understanding the architecture helps non-developers to request changes that are consistent with the architecture and to communicate these requirements to developers.

Changes to the UI should be consistent with the base product UI architecture for many reasons, including reduced development and training time, simpler upgrades and a reduced chance of performance impacts.

---

# 1. The User Interface for all InsuranceSuite products.

The User Interface for all InsuranceSuite products include five common areas:

- Screen Area

- Sidebar

- Tab bar

- Info bar

- Workspace

This common UI architecture ensures that all InsuranceSuite products have a similar look and feel, which makes it easier for users to learn the products.

## Screen Area

The first and most dominant area is the Screen Area. The Screen Area displays most of the business information. This is where users interact with the product.

## Sidebar

The second major are is the Sidebar. The Sidebar provides menu links used to navigate to other pages within the current claim object. In this case, navigation is to other pages of information within a claim. The menu links change depending on the context of the screen. For ex. , different menu links are provided when viewing objects accessed from the Desktop, Search, Address Book and Team tabs.

## Tab bar

The third common are is the Tab Bar. The Tab Bar contains a set of tabs that vary based on a user’s permission. For example, an Adjuster usually sees the Desktop, Claim and Search tabs. If the adjuster has the necessary permission, he or she also sees the Address Book tab. If the Adjuster is designated as the backup for a team  
member, the Vacation tab is also visible. A Supervisor sees the Team tab, which an Adjuster does not have permission to see.

The Quick Jump box that displays ‘Go to (Alt-/)’ provides a fast way to navigate within InsuranceSuite or to search for information in specific categories. Users can type a command and press Enter key to jump to that location in the application. The ser’s permissions are checked and any unpermitted jumps are blocked. A number of predefined commands can also be entered here.

The Unsaved Work menu provides access to any work started from a tab but not completed when the user navigates to another location. Use this menu to return to unsaved work to complete it, or to discard work in progress.

The Options Menu contains global links including International, Help, About, Preferences and Log Out.

## Info bar

The fourth common area is the Info Bar. The Info Bar contains information that pertains to the main Screen Area. A combination of text and icons provide a quick reference to the information displayed below.

## Workspace

The last common area is the Workspace, which is used to display additional information such as an activity or note while keeping the Screen Area visible to display claim information.

---

# 2. User Interface Components

The User Interface is built out of elements called ‘widgets’. Widgets display application information to the user, support data entry, and organize data into logical groups of related information. Widgets are also specialized:

- Some support data entry, like input fields, check boxes, and radio buttons, among other;

- Some act on data, like buttons, menus and links;

- Some organize related data, such as lists or cards;

- Some are containers – every screen in ClaimCenter is actually a container widget made up of other widgets

[![](Dashboard/Attachments/Untitled%20144.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled.png)

---

# 3. Widget Examples

- Buttons: buttons are used to perform actions on a list or screen, such as adding or removing rows from a list, or putting a screen in edit mode or updating the screen to accept the edits.

- Text Input: used to enter text data for a specific fields, such as a contact name;

- Radio Buttons: used to answer a true/false or yes/no question;

- Date input: used to select and set a date field. The main input sows the required date format and allows the date to be typed in manually. The small calendar icon displays a calendar allowing the date to be selected.

- Typekey Input: allows the user to select the value of the field from a predefined list of options;

- Contact Picker – this specialized widget has multiple parts. The main field provides a dropdown list of existing contacts on the claim to select from. The arrow at the right end provides a menu of options to the user – create a new contact, search for an existing contact, or view the details for the selected contact.

[![](Dashboard/Attachments/Untitled%201%2023.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%201.png)

---

# 4. How to interrogate location information

When you are viewing a screen in any IS product, you can use the keyboard shortcut ALT+SHIFT+I to display the Location info window. This window shows you information about the construction of the screen you are viewing, which includes the location name, screen names, and high-level widgets defined in the screen, and the names of the PCF files in which they are all defined.

Each line in the window identifies a component of the screen that is stored in a separate file, such as screens, list views and so on. This information is typically used by a developer to identify the file they need to make changes to in order to satisfy business requirements.

[![](Dashboard/Attachments/Untitled%202%2019.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%202.png)

You can also get more detail by interrogating widget information for the screen you are currently viewing. Use the Keyboard shorcut ALT+SHIFT+W to display the Widget Inspector window.

The first part of the window show the page structure in a format similar to the Location Info Window.

Notice that the variables and other data defined in the page are also listed for each PCF.

After the page structure information, all of the widgets on the page are listed in alphabetical order in sections that can be expanded. This information is primarily of interest to developers as a debugging aid.

[![](Dashboard/Attachments/Untitled%203%2017.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%203.png)

---

# 5. Developer’s Role in configuration

The role of the developers on a project implementation team is to configure IS products to sastify the customer’s requirements. Developers use the Guidewire Studio development tool to modify the UI.

## Guidewire Studio

Guidewire Studio provides a graphical view of the User Interface that makes it easy for the developer to visualize what the finished screen will look lilke.

[![](Dashboard/Attachments/Untitled%204%2014.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%204.png)

---

# 6. Questions

[![](Dashboard/Attachments/Untitled%205%2014.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%205.png)

[![](Dashboard/Attachments/Untitled%206%2014.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%206.png)

[![](Dashboard/Attachments/Untitled%207%2013.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%207.png)

[![](Dashboard/Attachments/Untitled%208%2012.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%208.png)

[![](Dashboard/Attachments/Untitled%209%209.png)](User%20Interface%20-%20InsuranceSuite%20Analyst%20Fundamenta/Untitled%209.png)