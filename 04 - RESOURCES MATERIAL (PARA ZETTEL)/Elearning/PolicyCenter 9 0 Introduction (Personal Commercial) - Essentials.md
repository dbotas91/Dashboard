---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%2013.png)

# PolicyCenter 9.0 Introduction (Personal/Commercial) - Essentials

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201268.svg)Date Created|@July 13, 2021|
|![](Dashboard/Attachments/description_gray%20340.svg)Description|This course explains the features and processes of PolicyCenter, giving learners the basic skills needed to define business requirements for a PolicyCenter project. It teaches students how to create, modify, and manage policies and accounts in PolicyCenter.|
|![](Dashboard/Attachments/arrow-circle-down_gray%20945.svg)Status|Complete|
|![](Dashboard/Attachments/checkmark-square_gray%20691.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20510.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20142.svg)Last Edited|@January 26, 2022 4:31 PM|

[1. Documents](#c6ffb94d-c955-4180-a5d1-bc55123e85aa)

[2. Notes](#98388643-fc57-4faa-90b0-bfd3c51b81e4)

[3. Roles and Permissions](#08583488-896c-4d75-ba71-fee1173565ed)

[4. Validation](#b20be4a9-62d7-4c01-90b8-eac3d3081dbc)

[5. Premium Audits](#f73481f5-584e-44d6-ba21-9f414d316a63)

[6. Rating Basics](#ea8e688f-31c8-492f-b418-5bfff55a1665)

[7. Product Designer and PolicyCenter Overview](#e2a7779b-54ea-4d40-8bbe-0562d967954d)

[8. Product Designer: Navigation](#eecc7c2e-0a62-4afd-9804-a497e988aea9)

[9. Product Designer: Products and Policy Lines](#76b58239-0688-4d0f-a732-54031a6a71e5)

[10. Product Designer: Availability](#426ad63e-29d0-4db3-b9a2-a00e864fb26d)

[11. Product Designer: Coverages and Coverage Term Patterns](#8dac1433-4f0d-42b1-a697-4de7fae4199f)

[12. Product Designer: Question Sets and Offerings](#9acb5591-594c-4a28-9c69-b720922f863f)

[13. Product Designer: Modifier](#e0d5b3c0-d20e-4711-9186-5f8adba841b6)

# 1. Documents

1. Learner story
    1. As a business analyst or configuration developer, i want to know how documents are stored and managed using PolicyCenter so that I can incorporate documents into my business processes.

2. Subtopic
    1. What exactly is a document, how can it be generated and where do i find it?

3. Documents: definition
    
    1. Examples of an electronic file include a PDF, a Word document or an email document.
    
    2. **Froms** are contractual components of a policy, not documents. Forms are discussed in a different module.
    
    3. Documents can be user to:
        
        1. Track information on physical pieces of paper that document the assets covered by the policy (such as photographs of jewelry or diagrams of the floor plan for a workplace)
        
        2. Track information on physical pieces of paper that are used to rate the policy (such as assessments from property inspectors)
        
        3. Record correspondences with the insured
        
        [![](Dashboard/Attachments/Untitled%20140.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled.png)
        

4. Documents: where to store
    1. There are four "systems" where information about documents can exist:
        
        1. The user's computer
        
        2. PolicyCenter
        
        3. A document production system, which stores templates used to generate documents
        
        4. A document storage system, which stores electronic documents
        
        [![](Dashboard/Attachments/Untitled%201%2019.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%201.png)
        

5. Subtopic
    1. How does document production work?

6. Document production
    
    1. Document production is the act of creating a draft document by merging: A template Set of business data values
    
    2. A document template is a PolicyCenter template used to generate commonly needed documents.
    
    3. Document templates often include information drawn from the account, transaction, or policy and its related records.
    
    4. The document which results from the merge is typically considered a draft document because the underwriter has the oportunity to modify ir before it becomes final and/or gets sent to the relevant party. Document metadata is stored apart from the document.
    
    [![](Dashboard/Attachments/Untitled%202%2016.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%202.png)
    

7. Document architecture
    
    1. Document templates may be stored on a **seperate document production system.**  
        When a document needs to be produced, the field values and the name of the template are passed to the document production system. The document production system merges the information and returns a draft, which in turn is made available to the user. Nothing happens on the server hosting PolicyCenter.
        
        [![](Dashboard/Attachments/Untitled%203%2014.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%203.png)
        
    
    2. **Document templates are stored on the application server that hosts PolicyCenter.** PolicyCenter merges the document itself and makes the resulting draft available to the user. (This approach may be less typical for documents authored in a Microsoft product like Word and may be more typical for open-source fromats such as PDF.)
        
        [![](Dashboard/Attachments/Untitled%204%2011.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%204.png)
        
    
    3. Other times, document production **takes places on the user's computer.** For example, the template and the field values are passed to the user's computer, and the user's local copy of the document production application (typically a word processing application) merges the information and creates the draft.
    
    [![](Dashboard/Attachments/Untitled%205%2011.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%205.png)
    

8. Document production integration
    
    1. Every instance of PolicyCenter has an integration point to document production application. The application merges tamplates and data, and may also store document templates.
    
    2. Nearly every PolicyCenter implementation has documents created using applications (such as Microsoft Word) on the user computer. ImageRight is an example of an application that the insurance industry uses.
    
    3. Information exchange:
        
        1. PolicyCenter sends the name of the template and any information to be merged into the template.
        
        2. PolicyCenter receives a draft of the document based on the template with the relevant data merged into it.
    
    4. Information to mergeinto a document could include things like:
        
        1. The current date
        
        2. The recipient's name and address
        
        3. The relevant claim number
    
    5. This integration point is typically not the one requiring the greatest amount of effort to plan and configure, but the effort involved is significant enough that it also cannot usually be considered minimal.
    
    6. A given instance of PolicyCenter may be integrated with one or more document production applications.
    
    7. For example, some documents may be created using applications on the user's computer whereas other documents are produced by an application elsewhere in the carrier's network. This can occur if the carrier has a legacy documents, but it makes more sense for general or newer documents to be produced from the user computers.
    
    [![](Dashboard/Attachments/Untitled%206%2011.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%206.png)
    

9. Document storage integration
    
    1. Every instance of PolicyCenter has an integration point to document storage application. The application stores master copies of documents.
    
    2. Information exchange:
        
        1. PolicyCenter can send a new document to be stored as well as edited version of documents.
        
        2. PolicyCenter receives the "master" version of stored documents upon request.
    
    3. The ImageRight document management system was written by Advanced Solutions, Inc. specifically for the insurance industry.
    
    4. According to Advanced Solutions, "each feature was developed at the request of a business or IT executive, an adjuster, a calaims manager, or an underwriter."
    
    5. This integration point is typically not the one requiring the greatest amount of effort to plan and configure, but the effort involved is significant.
    
    6. A given instance of PolicyCenter is typically integrated with a single document storage application.
    
    [![](Dashboard/Attachments/Untitled%207%2011.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%207.png)
    

10. Two ways to create documents
    
    1. There are two ways to create a document. You can:
        
        1. Upload an existing electronic file from your computer to the document management system.
            
            [![](Dashboard/Attachments/Untitled%208%2010.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%208.png)
            
        
        2. Create a new document using a PolicyCenter document template, which creates a local copy on your computer which is ultimately uploaded to the document management system.
        
        [![](Dashboard/Attachments/Untitled%209%207.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%209.png)
        
    
    2. There are two ways to create a document. You can:
        
        1. Upload an existing electronic file from your computer to the document management system.
        
        2. Create a new document using a PolicyCenter document template, which creates a local copy on your computer which is ultimately uploaded to the document management system.

11. Subtopic
    1. What are some attributes of documents I should know about?

12. Document management architecture: storage
    
    1. each electronic document has a MIME type. This is used by the user's local computer to determine what application to use to view a document (such as using Adobe Acrobat for PDF files). For each electronic document, the document management system stores two sets of information. One set of information is the document itself (Word icon). The order set of information is a meta-file which stores information about the document (such as who the author is).
    
    2. Each document has security type. Sensitive documents are visible only to you, your supervisors, and people with permission to view sensitive documents.  
        Documents in the base application have additional attributes, but there is no significant functionality tied to these attributes. These attributes can be configured and additional attributes could be added.
    
    [![](Dashboard/Attachments/Untitled%2010%206.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2010.png)
    

13. Document mailing
    
    1. When a new document gets created, the carrier may want to send a physical copy of the document to the relevant party. (There may be some electronic communication with relevant parties via email, but because of the legal issues surrounding insurance, most if not all important documents are delivered to the relevant party via postal mail.)
    
    2. There are typically two ways in which the document gets mailed:
        
        1. A PolicyCenter user prints the document and mails it to the recipient. This could be the claims adjuster or a customer service representative, and it typically means the user prints the copy using a printer on the office network and then inserts the document into an envelope himself/herself.
        
        2. The document storage system takes responsibility for mailing the document. This typically involves some sort of flag that can be set on the document (such as a checkbox labeled "Mail copy to recipient") and an integration between the document storage system and a printing and mailing system.

14. Subtopic
    1. How do I view, create, update and delete documents associated with an account or policy?

15. Demo: Create documents
    
    1. Demo guidelines Documents that exist
        
        1. Determine whether you are working with documents related to **Account** or **Policy.**
        
        2. Go to Account or Policy
        
        3. To create new document, navigate to parent and select **Actions → New Document**
        
        4. Select the "Link to an exisiting document" menu item.
        
        5. Navigate to the document by clicking the Browse button.
        
        6. Specify the informaton about the document.
        
        7. Click Update
    
    2. Create documents using a template
        
        1. Select the template (in he New Document screen, click the search icon, search for and select template)
        
        2. Generate the document (specify object values)
        
        3. Modify the document text
        
        4. Specify any additional values
        
        5. Save the documents
    
    3. Demo guidelines additional points:
        
        1. Documents Screen (Policy or Account)
        
        2. Document Details in the Document Screen
        
        3. Specifically, Edit Local Copy, Upload and Discard options:
    
    4. Assuming you have sufficient permissions, you can edit electronic documents. To edit a document, click the Edit button. When you do this, PolicyCenter downloads a local copy of the document to your computer and opens it in the appropriate application (such as opening a Word document in Word). It also replaces the View and Edit buttons in the Actons cell with three new buttons:
        
        1. Edit Local Copy - This button opens the local copy of the local copy of the document in the appropriate application. This is useful if you inadvertently close the application window that PolicyCenter automatically opens for you.
        
        2. Upload - This replaces the "master" copy of the document in the ocument management system with your local copy.  
            You would use this button after you make edits to the local copy and want those edits to be in the master copy.
        
        3. Discard - This severs the link between your local copy of the document and the master copy of the document, and this reverts the Action buttons to View and Edit.

16. Questão de revisão #1
    
    Questão - Give at least two examples of how documents might be used in a policy file.
    
    Resposta:
    
    - Resposta correta
        
        Track information on physical pieces of paper that document the assets covered by the policy (such as photographs of jewelry or diagrams of the floor plan for a workplace), Track information on physical pieces of paper that are used to rate the policy (such as assessments from property inspaectors), Record correspondences with the insured
        

17. Questão de revisão #2
    
    Questão - What are the two ways that electronic documents can be added to PolicyCenter?
    
    Resposta:
    
    - Resposta correta
        
        Documents can be added by:
        
        Uploading linking to an existing document
        
        Creating a new document from a template
        

18. Questão de revisão #3
    
    Questão - When a document already exists in PolicyCenter and you choose to edit it, where is the edited copy stored while it is being edited? What must you do to have the edited copy replace the master copy?
    
    Resposta:
    
    - Resposta correta
        
        The edited copy is stored on your computer. To have it replace the master copy, you must click the Upload button on the Documents screen.
        

---

# 2. Notes

1. Subtopic
    1. AS a business analyst or configuration developer, I want to know to view, add, edit and delete Notes in PolicyCener so that i can enhance the information available for a policy, account or contingency.

2. Subtopic
    1. What are notes and how can i use them in PolicyCenter?

3. Notes
    
    1. The common business case for a note is that an end user enters a detailed record of actions related to a policy, account or contingency (contingencies are covered in detail in a different module. This module focused on accounts and policies).  
        Notes can also be created in business rules, and in some cases it may make sense for a given business rule to create and attach a note to a job or account after some automatic action has been taken.
    
    2. Notes and documents can have distinct functions in PolicyCenter. Notes are written in plain text, created by a user or through Gosu, and stored only in the PolicyCenter database. Documents are more complex, and might have different MIME types such as PDF, Word or Excel. Documents can be created and stored in the PolicyCenter database OR the document management system (third-party system). Both may use a template.
        
        [![](Dashboard/Attachments/Untitled%2011%206.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2011.png)
        

4. Note fields
    
    1. The fields in the note are the note Topic, the note Subject, the note Security LEvel and the note Text.
    
    2. **Security Level Details:** Is note visible to everyone (unrestricted), internal users only (internal only) or only you, your supervisors, and people with permission to view sensitive notes (sensitive note).
        
        [![](Dashboard/Attachments/Untitled%2012%206.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2012.png)
        

5. Questão de revisão #1
    
    Questão - Now that you know about both Documents and Notes, identify for the following descriptions whether or not it applies to Documents, Notes or both Documents and Notes.
    
    1. Involves integration with a third-party system
    
    2. Create within an account, policy or contingency
    
    3. Has a MIME type
    
    4. Can use template to create it
    
    Resposta:
    
    - Resposta correta
        
        1. Documents
        
        2. Documents and Notes
        
        3. Documents
        
        4. Documents and Notes
        

---

# 3. Roles and Permissions

1. Learner story
    
    1. This lesson will focus on the basic concepts of roles and permission and how to configure it in the user interfacte. For configuration of extendind system permissions and applying permissions in the Gosu code and PCF files, please refer to the more advanced topic introduction to permission configuration and the Guidewire PolicyCenter Configuration Guide.
    
    2. As a business analyst or configuration developer, i want to grant access using permissions and assign roles in PolicyCenter in order to control user access to the UI components and functionalities.

2. Subtopic
    1. What are roles and permission?

3. Security in PolicyCenter
    
    1. Security in PolicyCenter makes the application flexible, robust, and keeps your information protected. The PolicyCenter default application contains a set of roles that perform the policy tasks in most organizations. In order to perform these tasks, a user must be assigned a role with the appropriate permissions. Typically in the base configuration, the Superuser role is granted all permissions and is responsible for granting permissions to other roles.
    
    2. Once the roles are configured, then each Policycenter user is assigned a specific role that relates to the tasks to be performed.
    
    3. Note: Although in the base configuration, Superuser has all permissions, but that could change if a customer adds custom permissions. Also, Superuser is configured in the base product as the role that would grant permissions to other roles, but a customer could configure any role to do that.
    
    [![](Dashboard/Attachments/Untitled%2013%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2013.png)
    

4. Access
    
    1. PolicyCenter has a rich set of access functionality that is managed through a set of permissions.
    
    [![](Dashboard/Attachments/Untitled%2014%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2014.png)
    

5. System permissions
    
    1. In the example above, the system permissions have been arranged in columns based on the thing the permission pertains to. the second column has only two permissions because you cannot own a group. The third column has only one permission because it pertains to an aspect of the PolicyCenter user interface. The team tab cannot be edited or owned.
    
    2. System permissions are often referred to simply as "permissions".
    
    3. The entire list of system permissions can be seen in the Security Dictionary.
    
    [![](Dashboard/Attachments/Untitled%2015%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2015.png)
    

6. Permissions can influence access
    
    1. The list of abilities in the slide above is meant as a general way of viewing of permissions and not an official categorization. There are some permissions which map directly to one of the words listed above. For example, there are some permissions which map directly to one of the words listed above. For example, there are "view accounts" and "view audit" permissions.
    
    2. Other permissions map less directly to the words listed above. for example, there is a "bind policy change" permission and a "bind submission" permission, both of which can be thought of as "act on" permissions.
    
    3. All permissions change the user experience in one of two ways:
        
        1. A permission could control whether an aspect of the user interface is visible or not. (For example, users who do not have the View Team permission simply don't see the Team tab, whereas users who do have this permission do see the tab.)
        
        2. A permission could control whether or not a user succeeds or fails at a given task. (For example, if a user attempts to bind a submission or bind a policy change, the binding fails. The user can save a draft at that point, and a user with the bind submission or bind policy change permission respectively can perform those task successfully.)
        
        [![](Dashboard/Attachments/Untitled%2016%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2016.png)
        

7. Permissions can influence access
    1. In the example above:
        
        1. Alice Applegate is an underwriter without the View Team permission. When Alice logs on, she cannot see the Team tab.
        
        2. Right Ralston is an underwriting supervisor with the View Team permission. when Rick logs on, he can see the Team tabs.
        
        [![](Dashboard/Attachments/Untitled%2017%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2017.png)
        

8. Create object permissions
    
    1. PolicyCenter typically prevents the user from taking an action they are not allowed to do by not displaying the particular button or menu item for the permission. There may be cases where a permission is not applied to a menu item for the permission. There may be cases where a permission is not applied to a menu item or a button, but to a function call in the back end. In such cases, PolicyCenter may display an error message with the permission restriction.
    
    2. (For example, some UI components do not have permission restrictions, so a user without any assigned role may see those UI components, but he/she cannot proceed a lot further due to permission restrictions applied at the function call level.)
    
    3. In the example above:
        
        1. Alice Applegate is an underwriter with the Create documents and Create a New Submission permissions. When she wants to create a document she clicks on the Actions menu and can create one using the New Document menu item. She also gets a further submenu with options to choose from to create a new document by Linking to an existing document or Create a new document or Create a new document from a template.
        
        2. Adam Auditor is an auditor and does not have Create a New Submission permission, so when he clicks on the actions menu he does not get the menu item New Submission.
    
    4. (The behavior of how you want the permission restriction to work in PolicyCenter application can be configured.)
    
    5. Note: Some of the examples in this lesson have been created for training purposes and may not be available in sample data.
    
    [![](Dashboard/Attachments/Untitled%2018%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2018.png)
    

9. Own object permissions
    1. In the example above:
        
        1. Bruce Baker is an underwriter with the Own Activity permission. When someone attempts to assign an activity to Bruce, he becomes the owner of the activity.
        
        2. Brian Malouin is a user admin without the Own Activity permission. When someone attempts to assign an activity to Brian, the system prevents the assignment and informs the user that Bruce lacks the permission needed to own an activity.
        
        [![](Dashboard/Attachments/Untitled%2019%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2019.png)
        

10. A user's permissions are determined during login
    
    1. When an end user attempts to log on to an application, the followin occurs:
        
        1. The user supplies their user name and password to PolicyCenter via the login page.
        
        2. PolicyCenter queries its database to authenticate the user and determine which permissions are assigned to the user and what the user's start page is. In the base product, authentication is managed through the PolicyCenter database. There is a table in the database which stores user names and password. (The system can also be configured to authenticate against an existing user domain structure.) Permissions determine which screens the user can navigate to and which actions the user can perform. The startup view is the first page rendered after log in.
        
        3. PolicyCenter authenticates the user.
        
        4. PolicyCenter renders the appropriate startup view with permissions appropriate for that user.
    
    2. Note that there is one login, "su" (for Super User), which is exempt from permission checks. This user is set as a power user in config.xml, and inherently can do pretty much anything in the application.  
        Generally, you would not give this login to any real user in a production environment of PolicyCenter; but it can be very useful during development.  
        A user's permissions are determined during log-in.
    
    3. However, if an administrator changes a user's permissions while that user is logged in, the new permissions are applied immediately.
    
    [![](Dashboard/Attachments/Untitled%2020%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2020.png)
    

11. Roles
    
    1. There are no absolute rules regarding how the permission/role structure must be built to accommodate users with varying levels of access. For example, if underwriters should be able to do everything an underwriter assistant can do as well as some underwriter-only tasks, then:
        
        1. You could create the an Underwriter role so it has all the permissions of the Uderwriter Assistant role plus the additional permissions.  
            Underwriter Assistant users get just the Underwriter assistant role. Underwriter users get just the Underwriter role.
        
        2. You could create the Underwriter role so it has only the additional permissions that Underwriter Assistants do not get. Underwriter Assistants users get just the Underwriter Assistant role. Underwriter gets both the Underwriter Assistant and the Underwriter role.
    
    2. Role have permissions that map to a job function. For example, the producer role contains the set of permissions appropriate for someone who is a producer.  
        This role might have the create submissions or edit accounts permissions, but it would not have the create users or even issue submissions permissions.  
        Similarly, a producer clerical role might have only create submissions and not edit accounts. You can have one or more roles (you must have at least one). You are granted all of the permissions that are contained in any of the roles that are assigned. Roles provide the basic security that governs which actions you can take within PolicyCenter.
    
    [![](Dashboard/Attachments/Untitled%2021%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2021.png)
    

12. Mapping roles to users
    
    1. In the example above:
        
        1. Dennis Right is an underwriter assistant, and therefore has all the permissions of an underwriter assistant through the underwriter assistant role.
        
        2. Bruce Baker is an underwriter, and therefore has all the permissions of an underwriter assistant through the underwriter assistant role.
        
        3. Rick Ralston is an underwriting supervisor, and therefore has all the permissions of a underwriting supervisor.  
            To accomplish this, he has both the Underwriter role and the Supervisor role. (Presumably, the Supervisor role does not contain all permissions normally associated to an underwriter.)
    
    2. PolicyCenter permissions only give you the ability to do something. Unlike the permission structure of some other systems, PolicyCenter does not have any permissions that specifically deny a person the ability to do something. The only way to prevent someone from having a given permission is to not assign them any roles that have that permission. Roles are cumulative which means that a user gets all of the permissions associated with one or more roles in which they have been assigned.
    
    [![](Dashboard/Attachments/Untitled%2022%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2022.png)
    

13. Role Types
    
    [![](Dashboard/Attachments/Untitled%2023%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2023.png)
    

14. Creating producer code roles
    
    [![](Dashboard/Attachments/Untitled%2024%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2024.png)
    

15. Subtopic
    1. How to grant permission to roles and assign roles to users?

16. Managing roles
    
    1. The screenshot above is taken from a superuser login. New role can be created via the Administration tab by superusers. Alternately users with specific manageroles permission can edit or create new roles. The manageroles permission is not linked specifically to superusers. But this can be configured using Guidewire Studio.  
        Roles displayed in this list view can be filtered based on role type using the filter drop-down at the top to display all roles, producer code roles or user roles.  
        A new role can be added or deleted through this screen.
    
    [![](Dashboard/Attachments/Untitled%2025%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2025.png)
    

17. Creating a new role
    
    1. Every user belongs to an organization. This can be the carrier's organization or an external organization, such as an agency. Internal users and groups, as well as external, can have producer codes assigned to them. External users may only have producer codes from their organization assigned to them, but internal users may have any external producer codes assigned to them, but internal users may have any external producer codes assigned explicitly to them.  
        The user has to specify whether this role is internal or external since the permissions and what a user can access or see depends on what type of organization the user belongs to. The users and producer codes that can be added to this role will be decided based on this.  
        As show in the screenshot above, the user tries to add Alan Kim as a user to this role. But Alan Kim is an external user and user selected the option above (in the Basics tab) that this is an internal role only, so PolicyCenter displays an error message explaining this. On the other hand Alice Applegate is successfully added as a user, since she belongs to the Enigma Fire & Casualty organization for which this role is being created.  
        Similarly, producer codes that belong to this organization can only be added for this role.
    
    [![](Dashboard/Attachments/Untitled%2026%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2026.png)
    

18. Modifying permissions in a role
    
    1. To add a permission to a role:
        
        1. Navigate to the role.
        
        2. Click the Edit button in the screen toolbar.
        
        3. Click the Add button in the permissions list view toolbar.
        
        4. In the new row, select the desired permission from the drop-down.
        
        5. Click Update.
    
    2. To remove a permission from a role:
        
        1. Navigate to the role.
        
        2. Click the Edit button in the screen toolbar.
        
        3. Select the permission row to delete.
        
        4. Click the Remove button in the permissions list view toolbar.
        
        5. Click Update.
    
    3. When adding new permissions to a role, the drop down list of permissions include only the permissions that the role currently does not have meaning that it is filtered.
    
    [![](Dashboard/Attachments/Untitled%2027%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2027.png)
    

19. Modifying roles for a user
    
    1. To grant a role to a user:
        
        1. Navigate to the user
        
        2. Click the Edit button in the screen toolbar.
        
        3. Click the Add button in the roles list view toolbar.
        
        4. In the new row, select the desired role from the drop-down (this drop-down lists roles that this user does not already have only).
        
        5. Click Update.
    
    2. To revoke a role from a user:
        
        1. Navigate to the user.
        
        2. Click the Edit button in the screen toolar.
        
        3. Select the role row to delete
        
        4. Click the Remove button in the role list view toolbar
        
        5. Click Update.
    
    3. Modifying a user's roles requires the "Grant roles to user" permission, which is typically given to managers.
    
    [![](Dashboard/Attachments/Untitled%2028%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2028.png)
    

20. Security dictionary
    
    1. The security dictionary is located at: <server directory>\build\dictionary\sec\urity\index.html
    
    2. The security dictionary lists four types of information:
        
        1. Application Permission Keys
        
        2. Pages (in the user interface)
        
        3. System Permissions
        
        4. Roles
    
    3. The security dictionary is a very useful tool to both the business and technical users.
    
    4. For example, they can use the security dictionary to check where the permission is applied, on which page and UI element, or what permissions a role contains.
        
        [![](Dashboard/Attachments/Untitled%2029%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2029.png)
        
    
    5. An application permission key is a set of one or more system permissions. PolicyCenter defines application permission keys internally as a method for improving system performance. For example, the accountedit permission key represents the system permissions for editing an account, and account reopen to reopen a withdrawn account. Application permission keys appear in the files used to specify the user interface, so it is important for users to know what they are.
    
    6. However,you cannot create or modify application permission keys. The Application Permission Keys section of the security dictionary lists each application permission key, the set of system permissions it contains, and the pages and elements in the user interface that reference the application permission key. The Pages section of the security dictionary lists each page in the user interface and the permissions needed to view or edit that page (if any).
    
    7. You can click on any of the permissions listed in the right pane and it takes you to the list of pages that have that particular permission set.
        1. The System permissions are permissions defined in the SystemPermissionType typelist. Permissions that appear grayed are internal and cannot be modified.
    
    8. The System permission section of the security dictionary lists each system permission and the roles that contains the system permission, and the pages and elements in the user interface that reference the system permission.
    
    9. The Roles section of the security dictionary lists each role and the permissions it contains.
    
    10. Keep in mind that the security dictionary is a series of static HTML pages. If changes are made to the permissions in a give role, the security dictionary must be regenerated to reflect those changes. Users can update the security dictionary through a command-line utility tool called "regen-dictionary" which is covered in detail in the Configuration Fundamentals course.
    
    [![](Dashboard/Attachments/Untitled%2030%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2030.png)
    

21. Questão de revisão #1
    
    Questão - Name some of the user roles in PolicyCenter.
    
    Resposta:
    
    - Resposta correta
        
        Underwriter, Producer, Auditor, Underwriter Assistant...
        

22. Questão de revisão #2
    
    Questão - When does PolicyCenter determine which permissions a given user has?
    
    Resposta:
    
    - Resposta correta
        
        PolicyCenter determines the permissions for a given user when that user logs in.
        

23. Questão de revisão #3
    
    Questão - How many permissions can a give role have?
    
    Resposta:
    
    - Resposta correta
        
        A role can have any number of permissions. PolicyCenter has certain zero-permission roles in the base product to essentially show as placeholders.
        

24. Questão de revisão #4
    
    Questão - How many roles can a give user have?
    
    Resposta:
    
    - Resposta correta
        
        A user can theoretically have any number of roles from zero to many. A user must have at least one role in order to be able to do something in PolicyCenter. A user who has boader responsibility than another user can be given additional roles so that they are able to accomplish these responsibilities.
        

25. Questão de revisão #5
    
    Questão - How could you easily determine which roles enable users to create accounts?
    
    Resposta:
    
    - Resposta correta
        
        You could view the create accounts permission in the security dictionary to see which roles the permission has been added to.
        

---

# 4. Validation

1. Learner story
    1. As business analyst or configuration developer, I want to describe the validation behavior so that i can ensue the business data is valid.

2. Validation basics
    
    [![](Dashboard/Attachments/Untitled%2031%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2031.png)
    

3. Validation with field validators
    
    1. A **field validator** is a pattern that is tied to one or more fields in the data model. If field value does not match pattern, data cannot be saved and error message is displayed. Field validators are useful when the validation logic involves simple pattern matching and the pattern holds true every time the field is used.
    
    2. **Input-masks** can be specified at the data model level or in a UI widget's property so that certai information ets stored in a certain format. For example, the digits in zip code or postal codes are separated by "-", and SSN numbers or official IDs are also separated by "-" after certain number of digits.
    
    3. An input mask does NOT restrict user input. It appears as a watermark in field. It is for information only and not part of the data input. It disappears when user enters data in field. A tooltip is displayed when user mouse-overs field.
    
    [![](Dashboard/Attachments/Untitled%2032%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2032.png)
    

4. Validation when data is saved
    
    1. A field marked as required must contain a value. The user cannot go to the next page without entering a value in the required field. There is a required property on the field in PCF that can be configured to make a field required.
    
    2. The validatable entities are those marked at the data model level and it will trigger validation before data is committed to the database.
    
    [![](Dashboard/Attachments/Untitled%2033%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2033.png)
    

5. Validation at some level during a job
    
    1. The same condition during a job (a policy transaction) may return a warning or an error depending on the level of the point in the job. This can be configured to have the desired validation results. Some validation levels are _Load and Save, Default, Quick Quotable, Quotable, Bindable and Ready for issue._
    
    2. For example, in the base application, if a Personal Auto submission does not have any vehicle defined and the user tries to navigate away from the Vehicles page, the UI will display a warning message, so that the user can enter other policy data and come back to the Vehicles page later. But it will display an error message when the Quote button is clicked so that a vehicle must be entered in order to get a valid quote.
    
    [![](Dashboard/Attachments/Untitled%2034%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2034.png)
    

6. Warning and errors
    
    1. Once PolicyCenter detects a validation issue, it displays a message for showing errors and warnings.
    
    2. Clearing a validation **warning** does not remove or correct the issue. However, you will be able to continue, if you desire.
    
    3. Fields in the user interface can be validated. Situations causing the **error** must be rectified before the user can take the same action again.
    
    4. For example, they might have hit the "Quote" button and gotten an error. In order to "Quote" successfully, they must fix the error. But they can "continue" taking other actions (including but not limited to the ones required to fix the error.
    
    [![](Dashboard/Attachments/Untitled%2035%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2035.png)
    

7. Warning and error appearance
    
    1. The first screenshot shows that if the error or warning is on the current page then it gets displayed on the top of that page itself. This behavior can vary across PolicyCenter.
    
    2. The second screenshot shows that the user is on the Policy Review page and the error is on the Vehicles page, so PolicyCenter usually displays a link to Vehicles page in the worksheet at the bottom where the error gets displayed.
    
    3. The errors or warning may appear at the bottom on an worksheet during save, if it calls the validation methods.
    
    4. Otherwise, they will appear on the top of the page.
    
    [![](Dashboard/Attachments/Untitled%2036%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2036.png)
    

8. Questão de revisão #1
    
    Questão - What are the three types of PolicyCenter validation?
    
    Resposta:
    
    - Resposta correta
        
        Validation with field validators, validation during save and validation on demand which can be run in a job wizard step or at a certain time in a job.
        

9. Questão de revisão #2
    
    Questão - What is the difference between an error and a warning?
    
    Resposta:
    
    - Resposta correta
        
        Errors are blocking which means that they block the action that the user was taking.
        
        Warning are non-blocking which means that they allow a user to go to the next step and perform the actions they were doing.
        

---

# 5. Premium Audits

1. Learner story
    1. As a business analyst or developer, I want to know what premium audits are, and how to initiate a final audit using PolicyCenter.

2. Subtopic
    1. What is a premium audit and what types are available in PolicyCenter?

3. Premium audits
    1. What distinguishes audits from other transactions in PolicyCenter
        
        1. Audits use the Policy information and are tied to the policy periods but they cannot alter the policy contract.
        
        2. Audits do not have an edit effective date associated with them.
        
        3. Audits are not bound to the policy, after they are complete, PolicyCenter closes them and renders them not editable.
        
        4. They are initiated and are viewable in a separate place in the Policycenter interface.
        
        [![](Dashboard/Attachments/Untitled%2037%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2037.png)
        

4. Audit types
    
    1. A **final audit** is a type of premium audit. There is only one final audit and it happens at the end. A second type of audit - **premium reports**, may occur at regular intervals during the policy term depending on the user's configuration of audit schedules.
    
    [![](Dashboard/Attachments/Untitled%2038%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2038.png)
    

5. Premium audit methods
    
    1. Physical: A representative (such as a premium auditor) makes an in person visit to the policyholder to review the business records and to verify and obtain all required audit information
    
    2. Phone: The auditor contacts the policyholder by phone to obtain all audit information.
    
    3. Estimated: This method is used only when the other methods are not available. For example, the policyholder went out of business, and the records were lost.
    
    4. Voluntary: The carrir sends a form to the policyholder requesting the required information. The policyholder completes the form and returns it to the carrier for processing.
    
    [![](Dashboard/Attachments/Untitled%2039%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2039.png)
    

6. Premium audit roles - insurer can tailor roles
    
    1. **Premium Auditor example**: The auditor may be allowed to edit the audit summary and audit details. However, the auditor may not be allowed to complete the audit because an audit examiner needs to check it for accuracy.
    
    2. Note: In the default configuration when the audit method is physical, PolicyCenter assigns the audit to a user with the premium auditor role.
    
    3. **Audit examiner**: The audit examiner also checks physical audits for accuracy, calculates the premiums, and completes the audit.
    
    4. If the final audit method is:
        
        1. Physical - The audit examiner receives the physical audit from the premium auditor and checks it for completeness and accuracy. The examiner also checks it of adherence to manual rules and guidelines of the insurance company. For example, does it include all the locations and entities? Does it split exposures for the anniversary rating date (ARD)?
        
        2. Voluntary - The audit examiner receives a completed report from the policyholder. The examiner review the form prior to billing to ensure that the policyholder has completed it properly. If necessary, the audit examiner calls the policyholder to clarify or amend the totals recieved.
        
        3. By phone - The audit examiner calls the policyholder to obtain audit exposures and ask questions appropriate to the audit or renewal.
    
    5. **Audit Supervisor:** In addiction, the supervisor has access to team screens where outstanding audits and audit activities can be tracked.
    
    [![](Dashboard/Attachments/Untitled%2040%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2040.png)
    

7. Premium audit process
    
    1. When the policy is issued, PolicyCenter adds adit scheduled items to the policy.
    
    2. You can see these audits by clicking the Audit Schedule link of the policy file. Initially these are not audit jobs, rather they area list of all the audit jobs anticipated but not yet initialized for the policy period.
    
    3. They are listed according to their start and end dates and their status is _Scheduled_.
    
    4. When a policy is canceled or reinstated, PolicyCenter revises the number of audits scheduled according to the coverage dates.
    
    5. Each of the scheduled items includes a process start date, an audit method and a due date. Users with the proper permissions can edit these fields before the audit job is initialized.
    
    [![](Dashboard/Attachments/Untitled%2041%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2041.png)
    

8. Audit task batch process
    
    1. A regularly scheduled batch process called **Audit Task** starts the audit jobs on their process start date.
    
    2. The **Process Start Date** is set according to the audit schedule(s) configured in Studio.
    
    3. The **Audit Method** will dictate how many days in advance of the End Date each audit should be started. (Note that physical audits start about a month before the period end.)
    
    4. With correct permission a user may _Start_ an audit prior to the _Process Start Date_ using the _Start_ button on the audit schedule item.
    
    5. Once the process is started the audit status changes from _Scheduled_ to _In Progress_. The audit becomes a draft policy transaction and the scheduled item becomes a link to the audit wizard. User can begin entering the audit information.
    
    6. After receiving the audit details, you can enter them into the Audit Summary and Audit Details screens.
    
    7. Premiums are determined by selecting the Calculate Premiums button. Finalize the calculations by selecting the Submit button. At that time, the audit becomes uneditable, the status becomes Completed, and the audit schedule displays the resulting premiums. User can change completed audits.
    
    [![](Dashboard/Attachments/Untitled%2042%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2042.png)
    

9. Subtopic
    1. What is a final audit and how can i schedule and work with final audits in PolicyCenter?

10. Final audit
    
    1. Final audits:
    
    2. Cover the entire policy term Only one final audit for each policy term.
    
    3. Starts on policy effective date and ends on policy expiration or cancellation date.
    
    4. Available in PolicyCenter base configuration for workers' compensation and general liability.
    
    5. A final audit contains the verified and ultimate cost for a variable basis policy. Final audits are important to determining actual policy premium. When the policy is issued, the estimated annual premium (EAP) is based on the policyholder's best guess at the basis, such as payroll, for the entire policy year. The final audit is conducted at expiration or cancellation. An auditor reviews the policyholder's records, or the policyholder officially reports the actual payroll amounts for the past policy term. The cost of the policy is recalculated using this actual basis amount, and the policyholder is billed or returned the difference.
    
    6. The insurer must also report final audit information to regulatory agencies. For example, worker's compensation unit statistical reports (unit stat reports) are sent to state bureaus or a council that handles multiple states (NCCI, for example).
    
    7. Unit stat reports are used by the state to calculate policyholder experience modifications and to calculate suggested or mandatory rates obtained by the insurer.
    
    8. PolicyCenter to export final audit data for statistical reporting. This data can be imported to another system such as the unit stat software application used by a particular state.
    
    [![](Dashboard/Attachments/Untitled%2043%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2043.png)
    

11. Final audit general steps
    
    1. PolicyCenter initially schedules a final audit when a submissions, rewrite, or renewal job is issued. The line of business and choices on the Payment page determine whether a final audit is required and the choice of audit schedules. Other jobs, such as policy change, reinstatement, or cancellation can amend the audit.
    
    2. The batch process _audit task_ uses the process start date to determine when to start the audit.
    
    3. If the user selects to audit the policy, the audit process is started by one of the audit methods (physical, phone, voluntary or estimation).
    
    4. If the user chose to waive the audit then the audit process status changes to complete.
    
    5. However, an audit can be manually re-added to the schedule.
    
    6. The above diagram shows the main steps that are necessary to conduct a final audit. These steps are for the defaults configuration of PolicyCenter.
    
    7. Carriers business requirements can alter the process.
    
    [![](Dashboard/Attachments/Untitled%2044%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2044.png)
    

12. Reverse a final audit job
    
    1. If you need to make changes to a final audit you can reverse or revise it.
    
    2. Reverse a Final Audit: The goal of a reversal is to undo the original audit so that a new audit can incorporate changes made by another job. In addition, PolicyCenter notifies the billing system that the first audit is reversed and will likely be replaced by an entirely new audit. Reversal occurs as a result of another job becoming effective within the final audit period after the final audit has been completed. There is no explicit user action.
    
    3. After the audit task initiates the new scheduled audit, users can begin processing the new audit.
    
    [![](Dashboard/Attachments/Untitled%2045%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2045.png)
    

13. Subtopic
    1. What is a premium report and how can i schedule and work with premium reports in PolicyCenter?

14. Premium reports: worker's compensation policies
    
    1. **Premium Reports:**
    
    2. Premium report:
        
        1. is sent by the premium audit department of a carrier
        
        2. has default audit method as Voluntary
    
    3. Premium reports may be used when the insured:
        
        1. is not able to accurately predict payroll in advance
        
        2. has variable basis, such as seasonal variations
    
    4. Premium reports are a type for audit that are created for interim periods within a policy period. Premium reporting audits adjust estimated data, such as payroll, inventory, and course of construction reports.
    
    5. The primary distinction between the two type is one is an optional way to bill premiums through out the policy term and the other has the purpose of verifying and billing an accurate premium for the entire policy term.
    
    6. Premium Reports are configured for the worker's compensation line of businesses in the base application but can be configured for other lines of business using Guidewire Studio.
    
    7. Premium reports bill attempt to ensure that the premium billed is close to the final audit amount. In most cases, the bills are more accurate than an estimate. For direct bill policies, the insured sends payment along with the report. If a report is not submitted in a timely fashion, the carrier can cancel the policy.
    
    8. The insured may choose premium reports because they are not able to accurately predict their payroll in advance or they have variable bases, such as seasonal variations in their payroll.  
        Others may choose premium reports because they end up paying only for the premiums that they actually owe. They may prefer this to paying for everything up front or agreeing to an estimated amount.
    
    [![](Dashboard/Attachments/Untitled%2046%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2046.png)
    

15. Premium reports general steps
    
    1. If the payment type is premium reporting, then PolicyCenter schedules premium reports when a workers' compensation rewrite, submission, or renewal job is issued. Other jobs, such as policy change, reinstatement, or cancellation can amend the reporting schedule. The batch process uses the process start date to determine when to start each premium report.
    
    2. The selected premium report is waived. However, a new premium report may be scheduled manually fr the waived period.
    
    3. The above diagram shows the main steps are for the default configuration of PolicyCenter.
    
    4. Carriers business requirements can alter the process.
    
    [![](Dashboard/Attachments/Untitled%2047%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2047.png)
    

1. Questão de revisão #1
    
    Questão - What are the two types of premium audit?
    
    Resposta:
    
    - Resposta correta
        
        The two types of premium audit are: final audits and premium reports.
        
        A **final audit** contains the verified and ultimate cost for a variable basis policy and usually occurs at the end of the policy term. A premium report term.
        
        A **premium report** is a bill with the premium at regular intervals throughout policy term based on reported values.
        

2. Questão de revisão #2
    
    Questão - What are the different audit roles available in PolicyCenter?
    
    Resposta:
    
    - Resposta correta
        
        The different roles in PolicyCenter are premium auditor, audit examiner and audit supervisor
        

3. Questão de revisão #3
    
    Questão - What are the different premium audit methods?
    
    Resposta:
    
    - Resposta correta
        
        The different audit methods are physically, by phone, voluntary or estimated
        

4. Questão de revisão #4
    
    Questão - What does the premium report trend analysis display?
    
    Resposta:
    
    - Resposta correta
        
        The reporting trend analysis display the ratio between the total estimated premium and total reported premium.
        

[![](Dashboard/Attachments/Untitled%2048%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2048.png)

---

# 6. Rating Basics

1. Learner story
    1. As a business analyst, actuary or rating specialist, I want to know how to manage standard rating business tasks in PolicyCenter so that i can move my existing rating set up to PolicyCenter.

2. Subtopic
    1. What should I expect to do in preparation for rating implementation?

3. Business overview
    
    1. By moving to PolicyCenter, you are implementing a Policy Administration system. Your existing rating content is most likely not ready for the system. While the rating manual stays the same, you need to focus early efforts on adjusting the rating content format so that it works for PolicyCenter.
    
    [![](Dashboard/Attachments/Untitled%2049%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2049.png)
    

4. The actuary's (or rating analyst's) role
    
    1. Before you can rate using PolicyCenter, actuaries or rating analysts will need to examine the rating content and the format so it makes sense to PolicyCenter. The rating manual remains the same.
    
    2. Start at the coverage level, then look at the various aspects that influence the rating.
    
    3. Auto model
    
    4. Rating Engine Story card:
    
    5. Actuary algorithm is what they are used to looking at Rating Algorithm Rate Flow Sample
    
    [![](Dashboard/Attachments/Untitled%2050%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2050.png)
    

5. Prepare Content
    
    1. The goal of the rating content "translation" is to arrive at the following components: Cost, Rate Flow, Rate Routines*, Rate Tables*
    
    2. The existing 'state' of rating determines the work required to 'transform' rating content. Rating content may already exist, but its exact state varies.
    
    3. Any of the following could be true:
        
        1. The rates are available in a spreadsheet for calculation or the rates can be automatically rated using a predetermined formula
        
        2. A spreadsheet model is available for rate calculation
        
        3. The rating content exists in a PDF or manual
    
    4. **Rate flow** is the logic in the rating engine. It orchestrates the premium calculation for a policy line. **Rate Routines and Rate Tables** are of particular interest to the actuaries because this is the data with which they have the most familiarity. **Rate books** are group of rate tables and rate routines, and the rate flow logic selects the rate book that will be used to access rate tables and rate routines.
    
    [![](Dashboard/Attachments/Untitled%2051%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2051.png)
    

6. Rating user stories: examples of implementation stories
    
    1. The rate book 'locks' in the rates and routines that insurers have to file with each state.
    
    [![](Dashboard/Attachments/Untitled%2052%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2052.png)
    

7. Is your rating content PolicyCenter "ready"?
    
    1. Each rating implementation starts from a different place. For example, a rating analyst may have a spreadsheet with existing rating data, or it may be contained in the existing rating data, or it may be contained in the existing system in another format.  
        In this example, the actuary or rating specialist must organize the information into a PolicyCenter-ready format for rating configuration and premium validation.
    
    [![](Dashboard/Attachments/Untitled%2053%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2053.png)
    

8. PolicyCenter-ready content may look like...
    
    1. Organize your rating information in way that defines the logical flower for each coverage, and focus on the algorithm needed to arrive at a calculation for cost. In this example, the needed data for each rate routine has come from the rate tables.
    
    2. This table shows what you need to do to organize the rating content by _**coverable and by coverage.**_
    
    [![](Dashboard/Attachments/Untitled%2054%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2054.png)
    

9. Subtopic
    1. What are the main components in PolicyCenter rating management?

10. Rating process diagram
    
    [![](Dashboard/Attachments/Untitled%2055%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2055.png)
    

11. PolicyCenter rating overview
    
    1. Costs in PolicyCenter determine are where we persist the premium and tax breakdown of a policy.  
        Your goal is to capture cost per risk, cost per policy LOB, and cost per policy.
    
    2. Examples: costs rated by vehicle, costs rated by line and cost such as taxes and surcharges
    
    [![](Dashboard/Attachments/Untitled%2056%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2056.png)
    

12. Rating components
    
    1. Rate books, rate table definitions, rate routines and parameter sets are all components in PolicyCenter rating Management.
    
    [![](Dashboard/Attachments/Untitled%2057%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2057.png)
    

13. Rating engine and rate flow
    
    [![](Dashboard/Attachments/Untitled%2058%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2058.png)
    

14. Rate tables and rate table definitions
    
    1. In PolicyCenter, your rate table implementations may be significantly different from the legacy environments and exported format. If necessary, plan on implementing a conversion between the Rating Management import/export format and the format managed by business users.
    
    2. For those used to Excel, Rate Tables use the concept of a VLOOKUP in Excel to access the rate factors.
    
    [![](Dashboard/Attachments/Untitled%2059%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2059.png)
    

15. Rate routines
    1. You can use a rate routine:
        
        1. To calculate properties on cost for coverages, taxes, an other costs on a policy
        
        2. To set up rating information for use by another rate routine
        
        [![](Dashboard/Attachments/Untitled%2060%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2060.png)
        

16. Rate books
    
    1. A **rate book** can have an implied rate order or rate steps and rate flow can be included in the rate book.
    
    [![](Dashboard/Attachments/Untitled%2061%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2061.png)
    

17. Questão de revisão #1
    
    Questão - Describe, generally, the "translation" that an actuary or rating specialist must do in order to prepare usable rating content for the configuration developer.
    
    Resposta:
    
    - Resposta correta
        
        Each rating implementation starts from a different place. For example, a rating analyst may have a spreadsheet with existing rating data, or it may be contained in the existing system in another format. Actuaries and rating specialists need to create content that is PolicyCenter ready.
        

18. Questão de revisão #2
    
    Questão - List the three main components in PolicyCenter Rating Management.
    
    Resposta:
    
    - Resposta correta
        
        For an efficient implementation, rating specialists and actuaries should identify **rate flow, rate tables, rate routines.** Note: rate routines use parameter sets.
        

---

# 7. Product Designer and PolicyCenter Overview

1. Learner story
    1. As a business analyst or developer, i want to know how to represent products in PolicyCenter.

2. Review: What is in the product model?
    
    1. Product Designer is a tool to help you view and modify the product model. The product model is what determines which policy products appear in PolicyCenter.
    
    2. In addition to lines of business and coverage details, the product model contains question sets, availability options and modifiers.
    
    [![](Dashboard/Attachments/Untitled%2062%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2062.png)
    

3. Examples of policy file information
    
    [![](Dashboard/Attachments/Untitled%2063%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2063.png)
    

4. Rating-relevant information in the product model
    
    [![](Dashboard/Attachments/Untitled%2064%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2064.png)
    

5. Patterns
    
    [![](Dashboard/Attachments/Untitled%2065%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2065.png)
    

6. Main patterns in the product model
    
    [![](Dashboard/Attachments/Untitled%2066%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2066.png)
    

7. Product and PolicyLine pattern relationship
    
    [![](Dashboard/Attachments/Untitled%2067%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2067.png)
    

8. Coverage pattern
    
    [![](Dashboard/Attachments/Untitled%2068%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2068.png)
    

9. Policy line pattern
    
    1. Patterns in the hierarchy include coverages and coverage terms, modifiers, forms, and others.
    
    [![](Dashboard/Attachments/Untitled%2069%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2069.png)
    

10. Coverage term pattern
    
    [![](Dashboard/Attachments/Untitled%2070%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2070.png)
    

11. Additional patterns
    
    1. Question sets
    
    2. Modifiers
    
    3. Exclusions
    
    4. Conditions

12. Questão de revisão #1
    
    Questão - What is the purpose of the product model?
    
    Resposta:
    
    - Resposta correta
        
        the **product model** identifies different policies, or products, that any instance of PolicyCenter offers.
        

13. Questão de revisão #2
    
    Questão - Describe one pattern type and relate it to the PolicyCenter user interface.
    
    Resposta:
    
    - Resposta correta
        
        Product, PolicyLine pattern, Coverage pattern, CoverageTerm pattern.
        

---

# 8. Product Designer: Navigation

1. Lesson objectives
    
    [![](Dashboard/Attachments/Untitled%2071%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2071.png)
    

2. Learner story
    1. As a business analyst or developer, I want to know how to use **Produce Designer** to configure the product model so that I can set up products for a line of business in PolicyCenter.

3. Product Designer
    
    1. **Product Designer** is a web-based tool for business users and developers that provides a wat to edit the product model information visually.
    
    [![](Dashboard/Attachments/Untitled%2072%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2072.png)
    

4. Product model nodes
    
    1. In this module, you will learn more about where to configure the product, policy line and question set nodes. You will also see where you add new audit Schedules to the product model using Product Designer. The data model configuration requiring creating new tables for the product model is out of scope of this course and will not be discussed in this course.
    
    [![](Dashboard/Attachments/Untitled%2073%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2073.png)
    

5. Product
    
    1. A _product_ is a collection of one or more policy lines. I the base configuration, PolicyCenter comes with several preloaded products. In the examples, the Commercial package product contains three lines of business.
    
    2. When you configure a product pattern in Product Designer, you create a policy type available to an applicant in the **Submission Manager** screen in PolicyCenter. PolicyCenter lists each product on a separate row of the **New Submissions** screen.
    
    [![](Dashboard/Attachments/Untitled%2074%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2074.png)
    

6. Subtopic
    1. How do I log on to Product Designer?

7. Product Designer modes
    
    1. In the single-user mode too, the admin can create multiple user accounts and they all can log on to the same instance of Product Designer. A user with administrative privileges can create other users and manipulate changes made by users. When the admin creates the account they decide whether they want to give administrator privileges to that user.
    
    2. Users perform all operations within a web browser. For training purpose, we will be using single-user mode and everyone will be logging in as su in Product Designer as well as in PolicyCenter.
    
    [![](Dashboard/Attachments/Untitled%2075%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2075.png)
    

8. Running a single user instance of PD
    
    1. When running in single-user mode, the following parameters can be used in the startup script, launchPD or launchPD.bat: -port=nnnn - TCP port number to assign to the build-in application server.  
        Default: 8780.  
        -openPageInWebBrowser - Automatically starts your default web browser and opens the Log In page of Product Designer after startup completes. Remove this parameter if you do not want your web browser to start up automatically.
    
    2. Refer to the Product Designer Guide to see instructions on installing a multi-user instance of Product Designer.
    
    [![](Dashboard/Attachments/Untitled%2076%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2076.png)
    

9. Login screen
    
    1. Guidewire recommends for security reasons that you create a new administrative user and delete the default user.
    
    2. **Note:** Your Product Designer session automatically terminates after 120 minutes of inactivity. This timeout is not configurable. However, because Product Designer continually maintains all your changes in the active change list until you commit them, after logging in again, none of your work is lost.
    
    [![](Dashboard/Attachments/Untitled%2077%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2077.png)
    

10. Subtopic
    1. What is a Workspace in Product Designer?

11. Workspaces
    
    1. Users select a workspace when creating a change list to identify the PolicyCenter instance to which their changes are to be committed.
    
    2. When running as single-user instance, Product Designer has a preconfigured workspaces named **Default workspace** that uses the PolicyCenter instance in which it resides. If needed, you can define additional workspaces that point to other PolicyCenter instances.
    
    3. When installed as a multi-user instance, you must define at least one workspace before anyone can use Product Designer. You define this initial workspace by running Product Designer. You are prompted to define a workspace as soon as you log in. as with a single-user instance, you also can define additional workspaces as needed.
    
    4. Only users who are designated as Administrators can edit workspaces.
    
    5. **Version Control System** column Name of version control system, one of: **None** - No version control system is configured. **Perforce** - Perforce version control is configured. **Note** - Product Designer interacts directly with Perforce version management software to check out product configuration files, which you then must check in manually. You can use a different version control system by manually checking out files as needed prior to changing them. For details on using a version control system such as Perforce with Product Designer refer to the _Product Designer Guide._
    
    [![](Dashboard/Attachments/Untitled%2078%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2078.png)
    

12. In-class demo
    
    1. **NOTES ONLY**
    
    2. **Toolbar**
    
    3. The toolbar stretches across the top of every Product Designer page.
    
    4. **Breadcrumbs**
    
    5. Breadcrumbs appear below the toolbar. Product Designer uses hierarchical breadcrumbs. Hierarchical breadcrumbs represent the location of the current page in the tree hierarchy.
    
    6. **Navigation Panel**
    
    7. On the left side of each page, the Navigation Panel displays a hierarchical tree view. The tree contains all of the nodes of the objects that can be edited, with the selected node highlighted.
    
    8. **[Object] page**
    
    9. Typical Product Designer page, in the example above BusinessOwners product page.
    
    10. Toolbar and Navigation Panel are always displayed.
    
    11. The [Object] page and breadcrumbs update depending upon the element selected in the Navigation Panel on the left side.
    
    12. **Go to** links
    
    13. For convenience, click to navigate directly to the associated page. Some of the links under **Go to** are also available in the navigation tree.
    
    14. **User menu**
        
        1. User Settings - Displays the User Settings page where you can change your user name, full name, user interface language, and regional format.
        
        2. My Change list - Displays the My change Lists page where you can add and delete change lists see which of your change lists is active, and reassign change lists to other users.
        
        3. Log Out - Logs you out of Product Designer and displays the login screen.
    
    15. **Options menu**
    
    16. Users - Display the Users page where you can add or delete users and designate one or more users as administrators.
    
    17. Change Lists - Displays the Change Lists page where you can add or delete change lists, see which of your change lists is active, and reassign change lists to users. Available only to administrators.
    
    18. Synchronize Product Model - Displays the Synchronize Product Model dialog box, enabling you to deploy your committed product model changes to a PolicyCenter server that is running in development mode.
    
    19. Synchronize System Tables - Displays the Synchronize System Tables dialog box, enabling you to deploy your committed system table changes to a Policycenter server that is running in development mode.
    
    20. About Product Designer - Displays the About Product Designer dialog box, which includes the Product Designer version number.
    
    21. **Sequence**
    
    22. Sequences are relative numberings. You can drag and drop or change the sequence number to change the ordr listed. The Sequence column in the screenshot above decides order in which products appear in UI.
    
    23. **Common operations for all pages**
    
    24. Sort - Click any column header to sort by that column.  
        Click again to reverse the sort order.
    
    25. Change order - If the table is sorted by Sequence, drag a single row to a new position to change the order in which it appears in PolicyCenter.
    
    26. Alternatively, edit the sequence number to establish the required order. You can change the order of only one row at a time.
    
    27. Edit - Click the blue item name to open a page where you can edit the item.
    
    28. Show/hide columns - Click the triangle next to each column name that appears when you mouse over the column header. This displays sort options and columns sub-menu. check-uncheck a column to show or hide it. By default all columns appear.
    
    29. Reverting a change removes you edits on the object.  
        Validating a change displays a validation message. Validation errors appear at the top of the page on a red background.  
        When no validation errors exist, clicking Validate displays the message No validation errors marked with a check mark on a green background as shown in the screenshot.  
        Deleting a page gives highlights what got deleted and gives you the options to Cancel Deletion. You can click on Cancel Deletion to retrieve your page.
    
    30. **Localization:** You can edit the text of name and description directly in the field using the current language.  
        You can set the current language in the User Settings page.
    
    31. Click Translate icon to display the Display Key Values by Language dialog box, where you can enter or edit the text in any supported language.
    
    32. On the left side of each page, the **Navigation Panel** displays a hierarchical tree view. The tree contains all of the nodes of the objects that can be edited, with the selected node highlighted.  
        Click the triangle icon to expand a node. Continue expanding nodes until you locate the node you want to select. Click a node label to select it. The corresponding page appears to the right of Navigation Panel.
    
    33. **Filter box** - Type the beginning characters of a node name. As you type, the filter hides every node in the tree except the nodes whose names or codes begin with the characters you typed. The code is the portion at the end of the label enclosed in square brackets. Note that the filtered tree also shows the parent nodes of each matching item, to help identify its location in the product model. click the adjacent **X** to clear the filter and restore all nodes to the tree.

13. Demo: Workspaces, change lists and users
    
    1. **Define workspace** - a named reference to root folder of a PolicyCenter instance.
    
    2. Shown the workspace.  
        Mention: When running as single-user instance, Product Designer has a preconfigured workspace named **Default workspace** that uses the PolicyCenter instance in which it resides. If needed, you can define additional workspaces that point to other Policycenter instances.  
        Only users who are designated as Administrators can edit workspaces.
    
    3. **Add a Changelist**
        
        1. **Define change lists** - a named collection of changes held in Product Designer until you decide either to commit or revert the changes.  
            Before you can make any changes in Product Designer, you must create a change list. You can add any number of change lists. The changes in each change list are independent from each other. For example, a Business Analyst might be adding a new line of business in the Crime LOB change list. Another change might be in the BOP Platinum Offering change list, where they were told to make changes to this offering for a certain class of customers.  
            Or Modify PA Qual Questions, where the company wants to change the qualification questions that they ask new personal auto customers.
        
        2. You can create **multiple change lists**, and then select the active change list from among them. **The active change list** is the one you are using now. All changes you make become part of the active change list. Using multiple change lists enables you to group your changes into separate sets and independently commit each change list at the appropriate time.
        
        3. Unless you assign it to another user, each change list and the changes it contains belong to you. Other users have their own change lists. A change list remains under your control unless you reassign it to another Product Designer user.
    
    4. Product Designer validates changes as you move from one page to other. Errors appear in red. Show an example.
    
    5. **Show** the **Users** An administrator user can create workspaces too in addition to adding or deleting change lists. In case of a single user system, the user is essentially the administrator. You can click on user name to edit the user settings such as user name, full name, user interface language, and region format. Users cannot add other users, but administrators can.  
        Users can edit their own user settings, administrators can edit everyone's. **Note**: This setting affects Product Designer administration only. It has no effect on PolicyCenter administration.

14. Subtopic
    1. How do i synchronize the product model with PolicyCenter?

15. Synchronizing product model
    
    1. When you click on Synchronize Product Modelit displays the Synchronize Product Model dialog box, enabling you to deploy your committed product model changes to a PolicyCenter server that is running in development mode.
    
    2. The Synchronize Product Model dialog boxprompts you for a user name and password. You must supply the PolicyCenter user name and password of a usr who belongs to a role with appropriate permission.
    
    3. A "Synchronization Successful" message is displayed if the synchronization is successful.  
        During this process, it also performs all of the verification checks. If there is an error, Product Designer displays these at the bottom of the screen.
    
    4. A user must have administration privileges in PolicyCenter to perform this task.
    
    5. Alternatively, you can set PolicyCenter login information under Workspaces → PolicyCenter page. If you set the login information there, then the above dialog to enter login information will not appear. And then you will see the Synchronization Successful or error message at the end.
    
    [![](Dashboard/Attachments/Untitled%2079%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2079.png)
    

16. Synchronizing product model with PolicyCenter
    
    1. To synchronize the Product Model from Product Designer, select Options menu → Synchronize Product Model. Synchronize the Product Model temporarily puts the server in maintenance mode and syncs the Product Designer data to the app-server data. During this process, it also performs all of the validations. If there s an error, Product Designer displays these in the top of the page you are working in or in the changes Panel. during this time, users cannot access the server. User must be connected to the server to synchronize the product model.
    
    [![](Dashboard/Attachments/Untitled%2080%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2080.png)
    

17. Commit or revert changes on Changes page
    
    1. Finally, when you select Commit, Product Designer performs validation of all changes in your active change list and proceeds only if it does not detect any validation errors. Your commit operation is blocked until you resolve all errors in the change list.
    
    2. Commit your changes means copying them to the application's configuration files on the PolicyCenter server. Because your changes are in a change list, you can safely make changes and then later choose to commit or not commit some or all of those changes.
    
    3. You can commit, revert, or validate all change list. It is a good practice to validate all change lists before committing.
    
    4. The only way you can rollback a commit is to use source control, which is not managed within Product Designer.
    
    5. **Column Description Location**
    
    6. Location of the changed object. Click this name to jump to the object so that you can examine the change.
    
    7. **Context**
    
    8. Description or type of change object.
    
    9. **Change**
    
    10. Type of change, for example, edit, added, deleted.
    
    11. **When**
    
    12. Date and time of the change.
    
    13. **Revert**
    
    14. Click Revert icon to revert the single change described in this row. Reverting a change removes it from the change list.
    
    15. **Note:** Product Designer commits changes in a logical order determined by the software. It does not commit changes in change list order, nor is it possible to influence the commit order of a single change list. If you need to control the order of changes, make your changes in separate change lists and commit the change lists in the required order.
    
    [![](Dashboard/Attachments/Untitled%2081%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2081.png)
    

18. Managing change lists
    
    [![](Dashboard/Attachments/Untitled%2082%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2082.png)
    

19. Subtopic
    1. How do i use system tables and manage audits?

20. System tables
    
    1. System tables are used when there are cases that required additional metadata that a typelist cannot support. They are not really considered as one of the core entities for PolicyCenter.
    
    2. Access system tables in Studio if you are configuring new system tables. Access system tables in Studio if you are configuring new system tables. Access system tables in Product Designer, if you are adding removing, or changing data in an existing system table.
    
    [![](Dashboard/Attachments/Untitled%2083%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2083.png)
    

21. Configuring system tables
    1. Configuration users must add new system table XML file to the systables folder **and** include the name of the new system table XML file in systables.xml in conformance with the schema defined in systables.xsd. If they do not:
        
        1. Studio does not consider the file to be a resource.
        
        2. Studio does not load it into the database
        
        3. Studio does not display the system table in the PolicyCenter interface.
        
        [![](Dashboard/Attachments/Untitled%2084%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2084.png)
        

22. Attributes: Priority and ExternallyManaged
    
    1. Specify the order in which to load the systable files using the FileDefinition Priority attribute. _As PolicyCenter loads the product model, it loads lower priority files before higher priority files before higher priority files_. (PolicyCenter loads files with the same priority concurrently.) This is critical if there are dependencies between the system tables.
    
    2. For example, the line-specific class code system tables must be loaded prior to the industry codes system table.
    
    3. Therefore, Guidewire sets the priority for the class code files _lower_ than priority value for the industry code file. For example, _class codes for gl_, the priority is 1 and industrycodes the priority is 2.
    
    4. **ExternallyManaged:**
    
    5. Possible values of the ExternallyManaged attribute and their meanings are:
        
        1. true - You cannot view of edit the system table in Product Designer. You must use an external editor to view or make changes to the system table.
        
        2. false (or not-specified) - You can edit and manage the system table values in Product Designer.
    
    6. A typical use case for setting ExernallyManaged to true is when dealing with very large system tables. Very large system tables are not to efficient to edit in Product Designer due to its page-at-a-time view of system table data.
    
    7. Territory codes provide an example use case. Territory codes are a way of encoding a given geographical location for the purpose of rating. Therefore, the territory code system table, territory_codes.xml, can become very large, contining as many as a million entities.
    
    8. If you find that editing this system table is not pratical using Product Designer, set the ExternallyManaged attribute for the territory code system table to true, as follows: <FileDefinitionName="territory_codes.xml" Priority="0" **ExternallyManaged="true"**>
    
    9. <EntityType="DB_Territory"/></FileDefinition>Setting ExternallyManaged to true affects only the ability of Product Designer to load the system table for viewing and editing. It does not affect the way in which PolicyCenter loads the system table during system startup.
    
    [![](Dashboard/Attachments/Untitled%2085%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2085.png)
    

23. Steps to add a new system table
    
    1. Refer to the _Product Model Guide_ for more details on system table configuration.
    
    [![](Dashboard/Attachments/Untitled%2086%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2086.png)
    

24. System tables
    
    1. System tables are displayed in the Navigation Panl.
    
    2. Choose the table you want to edit. The table page displays all rows in the table. You can add, delete, revert or validate rows. Select row by clicking on it.
    
    3. You can edit rows in a system table in their own page or in the table page also by directly editing contents of row in that page.
    
    [![](Dashboard/Attachments/Untitled%2087%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2087.png)
    

25. System table changes are added to change list
    
    1. The logic of committing and deploying changes to system tables is the same as deploying product model changes using the synchronize Product Model command.
    
    [![](Dashboard/Attachments/Untitled%2088%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2088.png)
    

26. Audit schedules
    
    1. Changes made to audit schedules are also added to the Changes Panel along with other changes in the change list. These changes are also committed and deployed to Policycenter in the same way as other changes to the product model.
    
    [![](Dashboard/Attachments/Untitled%2089%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2089.png)
    

27. Lesson Objectives review
    
    [![](Dashboard/Attachments/Untitled%2090%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2090.png)
    

---

# 9. Product Designer: Products and Policy Lines

1. Products and Policy lines
    
    1. Earlier in the course, you learned about the relationship between Product Designer and PolicyCenter, and some of the basics of pattern entities. Now you will see more details about how you can use Product Designer to view and configure the patterns that are used in PolicyCenter.
    
    [![](Dashboard/Attachments/Untitled%2091%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2091.png)
    

2. Product
    
    1. Most of the pattern entities in the product model have a name which ends in "Pattern".
    
    2. Product is an exception to this rule. If it had followed this rule, then the entity would be named "PolicyPattern", as it is the pattern used to create policy objects. The reason Products are not called PolicyPatterns is that "Product" is a know term to describe this concept in the product model hierarchy are _products_. Carriers or agents sell these products (such as personal auto or worker's compensation policies) to customers. Each individual policy is an instance of a product.
    
    [![](Dashboard/Attachments/Untitled%2092%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2092.png)
    

3. High level steps to create a new product
    
    1. The PolicyCenter Configuration Guide outlines specific examples of LOB configuration.
    
    [![](Dashboard/Attachments/Untitled%2093%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2093.png)
    

4. Subtopic
    1. How do i set up a policy line pattern using Product Designer?

5. PolicyLine patterns
    
    1. If the product has no policy line pattern associated to it, product synchronization will fail. Also, attempting to create a Quick Quote or Full Application generates a PCF error.
    
    2. Each policy line pattern specifies set of:
        
        1. Coverage patterns
        
        2. Categories for Coverages Conditions and Exclusions
        
        3. Modifiers
        
        [![](Dashboard/Attachments/Untitled%2094%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2094.png)
        

6. Product and PolicyLine pattern relationship
    
    1. A single product (such as Commercial Package) can have multiple policy line patterns. For example, CPP typically has General Liability and Commercial Property (required by most carriers usually), and Inland Marine.
    
    2. A single pattern (such as General Liability) can be used by multiple products.  
        For example, A General Liability policy line pattern can be used by both a General Liability product as well as to a Commercial Package product.
    
    [![](Dashboard/Attachments/Untitled%2095%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2095.png)
    

7. PolicyLine Subtypes
    
    1. Every policy line pattern is associated with one or more subtypes
    
    2. Before you can create a new policy line pattern, you must create a new subtype of PolicyLine
    
    [![](Dashboard/Attachments/Untitled%2096%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2096.png)
    

8. Demo: Products and PolicyLine Patterns
    1. Demonstrate the steps needed to access and view the Product and PolicyLine pattern configuration within Product Designer.
        
        1. Log into Product Designer and access the Changelist
        
        2. Select a product (product name) relevant to the audience
        
        3. Explain that the product appearance in the ProductDesigner
        
        4. Point out the Account Type field and explan that this selection controls who will be able to see this particular product
        
        5. Optionally - go through the other fields and explain that sections of submissions or other transactions can be customized using ProductDesigner.
        
        6. Describe Policy line patterns and explain how they are associated to products via "Policy Lines" section on Businessowners page. The policy line pattern must already exist before it can be added to the product.
        
        7. Mention Availability (next module) and that it determines if PolicyCenter exposes the pattern in the user interface.
        
        8. PolicyLine pattern configuration - show where users can find the policy line business entities in the Product Designer user interface, and describe how to "go to" each page (coverages, coverage terms, exclusions, conditions, categories, modifiers).
        
        9. Show the advanced properties - Integration → Reference code, Advanced → Policy Line Type, Territory Code, Scripts

9. Questão de revisão #1
    
    Questão - The first level of the product model hierarchy are what?
    
    Resposta:
    
    - Resposta correta
        
        Products
        

10. Questão de revisão #2
    
    Questão - A set of "legal and binding" information about the product is described in what entity?
    
    Resposta:
    
    - Resposta correta
        
        The PolicyLine pattern entity.
        

11. Questão de revisão #3
    
    Questão - Can a single product having multiple policy line patterns exist? Give an example.
    
    Resposta:
    
    - Resposta correta
        
        A package can have a single product having multiple policy line patterns.  
        The Commercial Package example is one example.
        

---

# 10. Product Designer: Availability

1. Availability
    1. As a configuration developer or business analyst, I want to know how use availability, edit and synchronize product model availability and reload availability data on a production server.

2. Subotpic
    1. What is availability?

3. Availability in the product model
    
    1. Availability in the user interface means that a coverage (or any other pattern on which the availability is set), either shows up in the application.
    
    2. Availability lookups are available on products, coverage patterns, coverage term patterns, and question sets.
    
    3. If a pattern is unavailable, PolicyCenter does not expose that pattern and does not permit you to create instances from the pattern.
    
    [![](Dashboard/Attachments/Untitled%2097%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2097.png)
    

4. Configuring availability in product model
    
    1. A product model pattern may be grandfathered, meaning that it is available if it already exists on a policy, even if it is unavailable according to both its availability table and script.
    
    2. This permits product model entities to remain on a policy even past their "normal" expiration dates, but once the entity is removed from the policy it cannot be added back. Grandfathering may be restricted to a certain set of states. Grandfathering is discussed later in this lesson.
    
    [![](Dashboard/Attachments/Untitled%2098%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2098.png)
    

5. Patterns with availability logic
    
    1. All of the product model patterns have availability logic, except for policy line patterns.
    
    2. There is no availability for policy line patterns because policy line patterns are so closely tied to products that availability logic would almost always be stored at the product level. If a product is available then it will always have an underlying policy line pattern. Note that Modifier patterns provide additional information for the rating engine to use to adjust the policy premium (or some portion of the premium).
    
    3. The availability for product level patterns can be set through lookup table only.
    
    [![](Dashboard/Attachments/Untitled%2099%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%2099.png)
    

6. Subtopic
    
    1. There are three options for availability. Note for DEMO: Show Availability Table, Availability Script and Grandfather States. Focus on the Availability Table (preferred way to deploy feature).
    
    [![](Dashboard/Attachments/Untitled%20100%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20100.png)
    

7. Determining availability of an entity
    
    [![](Dashboard/Attachments/Untitled%20101%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20101.png)
    

8. Demo: Availability
    
    1. Log in to Product Designer, go to a demo changelist, and an existing policy line (commercial property is a good one because it does not have too many coverages).  
        Go to Commercial Property Line → Coverages → Building Coverage Select Availability
    
    2. Advantages of an Availability Table: can be extended, performance is better than scripts, table is a set of 1 to many rows. Each row defines a criteria that can be based on a date, state and in some cases industry and product. True or false values of rows determine whether a pattern is available.
    
    3. Additional details: Availability lookup tables permit only relatively simple equality comparsions, so product model patterns can also specify an availability script to handle more complex conditions. For example, a script would be necessary if a coverage pattern is available only for vehicles manufactured after 1986, since this is not a straight equality check. A script may only further restrict table-based availability results; if a pattern is unavailable according to the lookup table then the script will not even execute.
    
    4. The columns in a availability table, such as start effective date, end effective date, and job type, are called dimensions. In addition, a column called Availability designates whether a pattern that matches the row is Available or Unavailable.  
        When evaluating a pattern, PolicyCenter finds the row in the availability table that matches best, and then uses the state of the Availability cell in that row. The best matching row is the row that matches the most dimensions. If multiple rows match the same number of dimensions, the precedence of the dimensions determines availability. Omitted dimensions are wildcards that match any defined dimension, the pattern is made unavailable.
    
    5. Show State and Jurisdiction list and mention it is configurable. In some countries, the state is not the regulatory jurisdiction. display keys are used for State column header in Product Designer tables.

9. Availability scripts - example
    
    1. Scripts must return true/false value  
        Scripts are in Gosu but complicated scripts can degrade performance Product Designer does not validate or compile scripts.  
        Use Studio.
    
    [![](Dashboard/Attachments/Untitled%20102%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20102.png)
    

10. Subtopic
    1. What is grandfahering

11. Grandfathering when discounting a coverage
    
    1. A product model pattern may be grandfathered, meaning that it is available if it already exists on a policy, even if it is unavailable according to both its availability table and script.  
        This means that product model entities stay on a policy past their "normal" expiration date. After the entity is removed from the policy, it cannot be added back to the policy. grandfathering may be restricted to certain states or set of states.
    
    2. **Grandfathering use cases:  
        Unavailable for all use together**
    
    3. No tall discontinued patterns will be grandfathered. In some situations, the existing pattern can no longer be supported by the carrier and so must be discontinued from all use. The pattern should not be available at the next renewal period for existing business or to any new business, but should be available to policy changes on the existing period for existing business. (The existing reference date lookup logic is taking care of this appropriately already).
    
    4. **Unavailable for new business, grandfathered if already in use**
    
    5. In the case of grandfathering, whether or not an existing coverage can continue to be used could be filed with language indicating that the coverage will be allowed to continue where it is already in use, but there will be no new usages. In this scenario, the decision of whether the pattern is available is make on a policy-by-policy basis, strictly depending upon whether the coverage is already present on the policy.
    
    [![](Dashboard/Attachments/Untitled%20103%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20103.png)
    

12. Patterns with grandfathering availability
    
    [![](Dashboard/Attachments/Untitled%20104%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20104.png)
    

13. Example: Grandfathering a coverage
    
    1. Consider the example here, where the availability table makes the medical payments coverage available until 8/7/13. After that it is unavailable to any jobs. But the coverage is made available **through Grandfathering in California only until 3/1/14.**
    
    [![](Dashboard/Attachments/Untitled%20105%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20105.png)
    

14. Renewal effective for California customer (grandfathered)
    
    1. In PolicyCenter. The coverage is available for renewals since the policy is effective on 02/01/2014 and the coverage is made available since it was Grandfathered.
    
    [![](Dashboard/Attachments/Untitled%20106%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20106.png)
    

15. Subtopic
    1. What steps should I follow to reload availability data I have added or altered?

16. Availability data: reloading
    
    1. Availability lookup tables, availability scripts, and grandfathering define the criteria for product model pattern availability on a policy entity. They are maintained in Product Designer and written to XML files in the configuration module and reloaded against a running server in production. A specific example for dynamically reloading in the product documentation (search "Reloading Availability Example").
    
    2. Reloading the availability data performs a sync between the lookup XML files and the lookup entities in the database. New lookups in XML files will be added to the database, changes to existing lookups will be applied to the database, and existing lookups which no longer appear in the XML files will be removed from the database.  
        This implies that the external lookup directory must contain a complete set of lookups for the entire product model, for instance it is not possible to update lookups for a single coverage by including a single XML file in the external directory.
    
    3. Invalid lookups can corrupt the database but this will not occur in practice if configuration users use Product Designer to manage and verify the lookup tables.  
        Press Alt + Shift + T to go to Internal tools / Server tools page.
    
    [![](Dashboard/Attachments/Untitled%20107%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20107.png)
    

17. Questão de revisão #1
    
    Questão - What is availability?
    
    Resposta:
    
    - Resposta correta
        
        Availability in the user interface means that a coverage(or any other pattern on which the availability is set), either shows up or does not show up in the application.
        

18. Questão de revisão #2
    
    Questão - List at least two factors that influences the availability of a coverage pattern.
    
    Resposta:
    
    - Resposta correta
        
        In PolicyCenter, the availability of a coverage pattern or any other pattern is based on different factors including:
        
        Start and end effective dates
        
        Industry code
        
        Underwriting company
        
        Policy transaction type
        

19. Questão de revisão #3
    
    Questão - All of the product model patterns have availability logic, except for?
    
    Resposta:
    
    - Resposta correta
        
        Policy line patterns.
        

20. Questão de revisão #4
    
    Questão - What is grandfathering?
    
    Resposta:
    
    - Resposta correta
        
        **Grandfathering** lets insurers continue to offer coverage patterns (or other patterns) even though they may not. be available to new customers.
        

21. Questão de revisão #5
    
    Questão - Which patterns have grandfathering availability?
    
    Resposta:
    
    - Resposta correta
        
        Product, PolicyLine pattern, Exclusions, Conditions pattern.
        

---

# 11. Product Designer: Coverages and Coverage Term Patterns

1. Learner story
    1. As a business analyst or configuration developer, I want to know how to set up coverage patterns and coverage terms using Product Designer.

2. Subtopic
    1. What is a coverage pattern?

3. Coverable
    
    [![](Dashboard/Attachments/Untitled%20108%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20108.png)
    

4. Coverables and coverages
    
    1. Guidewire makes the policy line a coverable to represent the named insureds.  
        Configuration users can further sub-divide coverables into Property coverables and Liability coverables.
        
        1. Property coverables are things with physical attributes (height, weight, value, construction type, age, and similar attributes, for example).
        
        2. Liability coverables are operations represented typically by class codes (coal mining, personal auto operation, for example).
    
    2. Configuration developers should see the student workbook for specific tips related to configuring the coverable.
    
    3. More information: The term coverable refers to any covered object. For example, insurance terminology refers to a covered object, such as a house, as a coverble
        
        1. For liability, the insured is the coverable.
        
        2. For liability coverages, PolicyCenter designates the policy line as the coverable to represent the insured.
        
        3. For coverages that attach at a location, the location is a coverable. Do not use PolicyLocations as the coverable, but instead, create a separate coverable entity.
    
    4. Additional specifics:
        
        1. The Coverable entity implements **CoverableDelegate** interface
        
        2. A coverable delegate encapsulates coverage behavior
        
        3. All other coverable-related configuration occurs at coverage level
        
        [![](Dashboard/Attachments/Untitled%20109%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20109.png)
        

5. Coverage patterns
    
    1. The Product Model defines Coverage patterns.
    
    2. Information for each pattern is stored in a separate xml file.
    
    3. Each CoveragePattern defines the Coverable where the coverage is attached, the coverage name (used in the UI), the Coverage Category (used for UI grouping), coverage availability, and the coverage "requiredness" - whether it is required, suggested, or electable. The pattern also defines the coverage table where the coverage will be stored when it is created. These settings are enforced when the coverages are synchronized. There is one Coverage Pattern for each coverage offered by the insurer.
    
    4. In this example, there are three coverage patterns defined for a Commercial Auto policy
        
        1. Collision (which is required for every Commercial Auto policy)
        
        2. Comprehensive (which is optional or "electable")
        
        3. Hired Auto (which is electable but which is available for cars in California only)
        
        [![](Dashboard/Attachments/Untitled%20110%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20110.png)
        

6. Coverage patterns and instances
    
    1. There are in total six coverage instances. The first policy has three instances - one electable only in California (Hired Auto). The second policy has only one instance (one not elected). The third policy has two instances (one required, one elected, and another either not available OR not elected).
    
    [![](Dashboard/Attachments/Untitled%20111%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20111.png)
    

7. Coverage pattern attributes
    
    1. Ar a high level, the CoveragePattern attributes determine whether or not each relevant coverage is offered on a given policy, and whether the user can accept (elect) the coverage or decline it.
    
    [![](Dashboard/Attachments/Untitled%20112%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20112.png)
    

8. Covered object
    
    [![](Dashboard/Attachments/Untitled%20113%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20113.png)
    

9. Coverage tables and coverables
    
    1. It is possible to associate more than one coverage table with a coverable. For example, this might be appropriate if some coverage patterns have unusual characteristics from all other coverages.  
        Typically, you define one coverage table for each coverable. However, you can associate more than one coverage table with a coverable. For example, if some coverage patterns have characteristics that are different from all other coverages, you can define a second coverage table. Be sure to include in the definition of the coverage table any values needed for all coverage patterns that can be used for the coverable.
    
    2. **Note:** In general, Guidewire recommends that you use one coverage table for each coverable, unless there is a clear use case for a second coverage table.
    
    [![](Dashboard/Attachments/Untitled%20114%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20114.png)
    

10. Coverage lookup tables
    
    1. Each coverage is associated with a coverage lookup table
        
        1. Table stores availability criteria for coverages
        
        2. Typically, each coverage lookup table is referenced by multiple coverages
    
    2. Each coverage table defines the individual criteria that can be used for an availability criteria expression. In the example above, personal auto coverages associated with the PACov table can have criteria based on state and underwriting company. (Start date, end date, and availability are columns common to all availability tables).
    
    [![](Dashboard/Attachments/Untitled%20115%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20115.png)
    

11. PolicyCenter and coverage pattern outcome
    
    [![](Dashboard/Attachments/Untitled%20116%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20116.png)
    

12. Subtopic
    1. What is a coverage category?

13. Creating coverage categories
    
    [![](Dashboard/Attachments/Untitled%20117%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20117.png)
    

14. Coverage Category
    
    1. The Personal Auto Physical Damage Group has four CoveragePatterns. The entire coverage category is associated with the Personal Auto PolicyLinePattern.
    
    2. While CoveragePatterns can be included individually in the used interface (PolicyCenter), coverages are usually added through a coverage category.  
        A policy either has all the available coverages in the group or non of them. In addition to the example in the slide, another example is in the Business Owner's policy line. The "Location Coverages" category contains the following coverage patterns:
        
        1. Outdoor signs
        
        2. Windstorm/Hail
        
        3. Outdoor Property
        
        4. Personal Effects
        
        5. Personal Property Off Premises
        
        [![](Dashboard/Attachments/Untitled%20118%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20118.png)
        

15. Coverage Availability and Existence
    
    [![](Dashboard/Attachments/Untitled%20119%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20119.png)
    

16. Demo: Create Coverage Patterns
    1. Demo:
        
        1. Show where to find the coverage patterns in Product Designer
        
        2. Click on coverage pattern Name to open its page - show details, and that it can be modified
        
        3. Show an example of the filter box to show how to filter for coverage patterns beginning with a specific string
        
        4. Show how to add a coverage (Add), and describe each field in Add Coverage
        
        5. Coverage patterns and Availability - Availability determines whether or not a coverage appears on a policy. Availability can be based on any combination of:
            
            1. Whether the effective date is within a given date range
            
            2. Whether the exposure is in a given state
            
            3. The results of a Gosu expression
        
        6. Coverage patterns - Existence field
            
            1. Required: Cannot be declined, may have a choice of term (e.g. deductible)
            
            2. Electable: Initially appear unselected in the PolicyCenter user interface (user must select)
            
            3. Suggested: Initially appear selected in the PolicyCenter user interface (user can deselect)
            
            4. Define by script: opens Advanced section where you can specify an existence script that determines whether to add the coverage
        
        7. Add a new coverage (example in instructor guide), and then explain and show:
        
        8. Changes Panel, Validate and commit the changes in Product Designer, then synchronize the model. In PolicyCenter, the changes should be visible.
        
        9. Additional details are available in the student guide for configuration developers under Configuration Tips.

17. Recommended practices: coverage patterns
    
    [![](Dashboard/Attachments/Untitled%20120%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20120.png)
    

18. Subtopic
    
    1. Coverage term patterns create instances of a coverage term to measure or further define a specific coverage.
    
    2. How do I configure a coverage term pattern?

19. Coverage term patterns
    
    1. A _coverage term pattern_ holds all configuration information for the terms of a coverage.
    
    2. Each coverage pattern has an associated coverage term pattern. PolicyCenter uses the coverage term pattern to create coverage term instances for coverage instances.
    
    3. Examples of coverage patterns for the zero, one or many terms attached:
        
        1. Loss of Use coverage in the base **commercial auto line** is an example of a coverage, the extent of the coverage, the extent of the coverage is the same for all policies.
        
        2. Hired Auto Colission coverage in the base **commercial auto line** is an example of a coverage pattern with **one term pattern**. It has a deductible term, but no other terms, such as a limit.
        
        3. The Employee Dishonesty coverage in the base **businessowners line** is an example of a coverage pattern with **multiple coverage term patterns.** It has terms for limit, number of covered employees, and number of covered locations.
        
        [![](Dashboard/Attachments/Untitled%20121%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20121.png)
        

20. Coverage term attributes
    
    1. Note that:
        
        1. You set the coverage term type in the New Coverage Term dialog as you create the coverage term.
        
        2. You set the coverage term model type in the coverage term's Basics tab, after you create the coverage term.
    
    2. To create coverage term, you must specify:
        
        1. Its type (direct, option, package, and so on)
        
        2. If type has drop-down, then the legal values for the drop-down
        
        3. Its model type (deductible, limit, coinsurance, other)
    
    3. From a configuration standpoint, the choices for type and options (when relevant) are immediate and apparent. These options control the look of the widget on the user interface as well as the options in the drop-down list.
    
    4. From a configuration standpoint, the choice of model type is neither immediate nor apparent. A coverage term's behavior on the user interface is the same regardless of the value for model type. However, this value does have implications when the value is passed to the rating engine as well as when a policy is imported into PolicyCenter. So even though it has no impact on configuration behavior, it is as important a value as the type.
    
    [![](Dashboard/Attachments/Untitled%20122%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20122.png)
    

21. Coverage tables and coverage terms
    
    1. For better performance, coverage terms are not stored in separate table. They are stored as columns in each coverage table.
    
    2. The coverage table defines the data entity that contains the coverages. Each type of coverage is applied to a coverable and coverage table.
    
    [![](Dashboard/Attachments/Untitled%20123%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20123.png)
    

22. Coverage term columns
    
    1. For configuration developers:  
        There are several different types of coverage terms, each with a different datatype. (For example, direct coverage terms are stored as decimal). Choice coverage terms (which includes option, package, and typekey) are stored as patternscodes and generics are stored based on their data type.
    
    2. Every coverage table has a set number of columns for each type of coverage term. (For example, the CP Building coverage table CPBuildingCov.eti) has three columns for direct coverage terms. When you create a coverage term pattern for a given coverage pattern, you must specify the column where the cov term value will be stored. (For example, when you create a direct coverage term pattern for a CP Building coverage pattern, you must specify if the value for the coverage term (not the pattern) will be stored in the first direct coverage term column or the second direct coverage term column).
    
    3. In addition, it also gets some of the standard columns that you can see in the data dictionary such as Branch.
    
    4. For a single coverage, if the number of coverage terms of a given type is greater than the number of table columns devoted to that type of coverage term, then you must extend the coverage table by adding an additional column to it. (For example, if a given CP building coverage needs four direct coverage terms, there is no existing column for the values of the fourth coverage term. Therefore, you must extend the table and add a new column for the fourth direct coverage term).
    
    5. Configuration Tip: Generic covTerms must go into an appropriately type column. For example, the date and Boolean columns on CPBuildingCov, are designed to take the values from generic coverage terms.
    
    [![](Dashboard/Attachments/Untitled%20124%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20124.png)
    

23. Mapping coverage terms to columns
    
    1. To map the coverage terms to the columns, you must specify the column of the coverage table in Product Designer, so that the coverage term values are stored in PolicyCenter database in the specified column of the coverage table.
    
    [![](Dashboard/Attachments/Untitled%20125%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20125.png)
    

24. Demo: Coverage Term Pattern Navigation
    
    1. To map the coverage terms to the columns, you must specify the column of the coverage table in Product Designer, so that the coverage term values are stored in PolicyCenter database in the specified column of the coverage table.
    
    2. When creating a coverage term pattern, configuration users must first specify its type (option, package, direct, typekey, or generic). Then, depending on your selection, they are given a set of choices for the column. The value of Code, Term Type, and Column fields cannot be changed after they are entered in the Add Term dialog.
    
    3. Terms appears in the Go to links on a coverage page. Click on Terms to navigate to the coverage terms page for that coverage.
    
    4. Coverage term pattern properties (All model types)
        
        1. Code - The coverage term pattern code.
        
        2. Name - The coverage term name.  
            PolicyCenter displays this value in the UI. This value is localizable.
        
        3. Description - The coverage term description.
        
        4. Sequence - Order in which to display the coverage term in the UI.
        
        5. Default Value - The default value for the term instance.
        
        6. Required - Whether the coverage term is required.
    
    5. Coverage term pattern properties (Direct and Option Only)
        
        1. Column - Table column to use to store the data. (This is set during coverage term creation).
        
        2. Value Type - The type of the value of the coverage term (percent or money, for example).
    
    6. Specify properties, options (four steps), packages (Content), availability and offerings pages.

25. Questão de revisão #1
    
    Questão - What is a coverable?
    
    Resposta:
    
    - Resposta correta
        
        A **coverable** is an exposure to risk and is not a pattern in product model.
        

26. Questão de revisão #2
    
    Questão - What is a coverage?
    
    Resposta:
    
    - Resposta correta
        
        Coverages are patterns in the product model where each coverage pattern is associated with a relevant entity.
        

27. Questão de revisão #3
    
    Questão - Define and give an example of a **coverage category.**
    
    Resposta:
    
    - Resposta correta
        
        A **coverage category** is a group of one or more logically related coverage patterns.
        

28. Questão de revisão #4
    
    Questão - What is a coverage term?
    
    Resposta:
    
    - Resposta correta
        
        A **coverage term** is a value that measures or further defines a specific coverage.
        

---

# 12. Product Designer: Question Sets and Offerings

1. Learner story
    1. As a business analyst or configuration developer, I want to know what a question set is and how to create one **so that I can facilitate information gathering during a policy transaction.**

2. What is a question set?
    
    1. Question sets are used to determine whether a person qualifies for a particular product, either right before they enter the wizard or through accumulated information indicating an unacceptably large level of risk that isn't tied to any one single issue. Question sets are linked to the Product entity in the product model. The question set gives you a way to collect underwriting information that is not pertinent to the rating process.
    
    [![](Dashboard/Attachments/Untitled%20126%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20126.png)
    

3. Question sets
    
    1. When a submission job is initiated, PolicyCenter creates a list of questions based on the Product Model definition (in XML). However, the answers to the questions for that particular job are stored as rows in the Answer table in the database. An answer points back to its question through the answer's QuestionCode, which, in Product Designer, is the Code value of the question.
    
    2. Questions are not reusable across question sets. If you want the same question asked in two different questions sets, you need to create the questions two times.  
        However, question sets can be associated with multiple products. If there were several questions you wanted to ask in more than one product, you could put those questions in a single question set and then associate that question set with each product.
    
    [![](Dashboard/Attachments/Untitled%20127%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20127.png)
    

4. Question sets for configuration developers
    
    1. Configuration Developers:
    
    2. The diagram shows the objects that store answers.
    
    3. Every PeriodAnswer object has a set of five attributes used to store the answer.
    
    4. These attributes are named Boolean Answer, IntegerAnswer, and ChoiceAnswer. The attribute used depends on the datatype of the answer. (For example, if the answer has a Choice datatype, then it is stored in the ChoiceAnswer attribute.
    
    5. For that answer, the other four attributes are NULL). Every answer object also has a QuestionCode that identifies the corresponding question.
    
    6. Every question object identifies the text to use for the question itself (such as "How many hours per day are vehicles in use?") and the datatype of the answer (such as Choice).
    
    [![](Dashboard/Attachments/Untitled%20128%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20128.png)
    

5. Learner story
    1. As a business analyst or configuration developer, I want to know what an **offering** is so that i can **define different product types** based on existing base product definitions.

6. Offerings
    
    1. Insurer want to be able to create offerings quickly, often based on a similar pre-existing product. PolicyCenter provides the tools to quickly and easily create offerings based on an existing product definition. You start with the base product definition, and then tailor it to define a specific offering. The offerings allow customers to modify default values for coverages, coverage terms. It is possible to switch between different offerings within a given product, between different products is not possible.
    
    2. In the base configuration, the following products provide offerings:
        
        1. Businessowners
        
        2. Commercial Auto
        
        3. Commercial Package
        
        4. General Liability
        
        5. Personal Auto
        
        [![](Dashboard/Attachments/Untitled%20129%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20129.png)
        

7. Subotpic
    1. When should i use offerings?

8. Offering
    
    1. An offering is the first step in the submission process in PolicyCenter. The process of creating a policy will begin with the user selecting an offering. If the user selects another offering, he will see any associated prequalification questions on the Qualification screen.
    
    2. These work the same way as questions sets at the product level — they might disqualify him from a particular offering, and/or influence rating.
    
    3. Offerings can change what appears for a coverage and other pages within the submission. If you do not define a specific Offering in the product model, then the offering is set to the PolicyLine-specific setting.
    
    [![](Dashboard/Attachments/Untitled%20130%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20130.png)
    

9. When to use offerings
    
    1. An example of marketing program could be a version of BOP might be pre-defined for a franchise. Another example might be a targeted commercial auto product offering only a limited number of options for local delivery companies. The appropriate program might to be used might be dependent upon information collected during the submission process itself.
    
    2. In the US, regulatory bodies are often oblivious to marketing programs, as long as there is no evidence that discriminatory practices are being used to assign programs to insureds.  
        Regulatory bodies are interested in the filed rates, forms, and underwriting rules, but these are not typically unique to a particular program.
    
    3. In Canada, programs might be referred to as "packaged policies" or as "programs".  
        The distinction is that packages policies are targeting a particular risk profile, while a program would be intended for a particular broker or for policies within a large corporate account. In Canada, there is a greater possibility that rating and forms might be unique to the program used, such as a discount being applied for a particular program. It remains true, however, that regulators are typically not interested in programs or packaged policies.
    
    [![](Dashboard/Attachments/Untitled%20131%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20131.png)
    

10. Availability of offerings
    
    1. Because offerings are built on top of the product model, they inherit all the capabilities of the product model. In particular, you apply the availability of all product model. In particular, you apply the availability of all product model entities _before_ you calculate the contents of the offering. Whether a given coverage appears to the user depends both on the availability of the coverage as defined by the product model, as well as by the inclusion of the coverage in the offering.
    
    2. An offering can be made available based on the above factors. Users can use offerings for the following use cases too:
        
        1. **Business-specific products:** An insurer offers a _business program_ that consists of a set of common coverages. The insurer offers specialized products based on this business program. These specialized products are offered to retailers, auto shops, and the hospitality industry, among others.  
            These specialized products offer coverage levels appropriate for each business type.
        
        2. **Affinity groups:** Some insurers write policies that are based on a group membership of the insured.  
            These affinity group policies offer a subset of the available coverages, group-specific default values, and possibly group-specific value choices for the coverage terms. Often the policy is subject to a special rate agreement, and so must obey various restrictions on the coverages and terms offered.
        
        3. **Programs or tiers of coverages:** This is similar in concept to the affinity group. The classic example is Bronze, Silver, and Gold programs where the user can choose increasing levels of coverage at increasing cost. Programs can also offer different coverages. An analogous case in commercial insurance is the creation of products for a particular industry, business profile, or franchisee.
        
        [![](Dashboard/Attachments/Untitled%20132%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20132.png)
        

11. Subtopic
    1. How do i create questions and a question set?

12. Demo: Creating Questions and Question Sets
    
    1. Demo
    
    2. The two steps to creating questions are 1) Creating the question set, 2) associating the question set with a product.
    
    3. Question sets
        
        1. In Product Designer, open the Questions Sets node.
        
        2. Click on Add. Enter the Code, Name, question Set Type, and Answer Container Type for the new question set. (PolicyCenter uses the code value internally to identify the question set.)
            
            1. Code - The code of the question set
            
            2. Name - The name of the question set (by conventon, it is used on the UI to label the question set)
            
            3. Question Set Type - Drop-down list of question set types from QuestionSetType typelist.
            
            4. Answer Container Type - Answer Container type that the new Question Set will be associated with. The drop-down list shows all Answer Container types currently defined in the system. The answer container type field is not editable after the Question has been created. Choose a type of answer (PolicyLocation, PolicyLine or PolicyPeriod).
            
            5. Available Date - Date when this question set will be available.
        
        3. Click Ok. At this point the questions set exists, but no questions exist in the question set and it does not link to a product.
        
        4. After you create a question set, you can select it in the navigation panel and then use the links under **Go to** to visit any of the following related pages:
            
            1. Questions - Define the individual questions within the question set, explained later in this lesson.
            
            2. Availability - Define the conditions that control whether the entire question set is available. Availability functionality for question sets is similar to that of the other patterns.
            
            3. Offerings - Add or remove the entire question set from offerings.
        
        5. In the Product Designer naviagion panel, expand Porducts and select the product to which to add the question set.
        
        6. In the product's home page, under Go to, click Question Sets.
        
        7. At the top of the Question Sets page, click Add and select the question set from the list of choices. The list shows only question sets that have not already been added to the product.
    
    4. To add QUESTIONS
        
        1. In the Product Designer **navigation panel, expand the Question Sets node** and then select the question set to which to add questions.
        
        2. At the top of the Questions page, click the icon that represents the type of question set to add.
        
        3. Clicking a question set type icon opens the Add Question dialog box. Specify the followin properties:
            
            1. Code - QuestionCode that answer use to point back to their questions.
            
            2. Label - Text of the question as it appears in PolcyCenter.
            
            3. Format - Listed in the table on previous slide.  
                Determines how the question is presented in PolicyCenter.
            
            4. Available Date - Date when the question will be available.
        
        4. Click OK to add the new question to the list of question to the list of questions for this question set.
        
        5. After you add a question, you can select in the navigation panel and then use the links under **Go to** to visit any of the following related pages:
            
            1. Dependent On - Create dependencies that determine whether specific questions are visible in PolicyCenter.
            
            2. Incorrect Answer - Specify a correct answer, failure message, blocking action, underwriting issue type, and risk points to add.
            
            3. Availability - Define the conditions that control whether an individual question is available. Availability functionality for questions is similar to that of the other patterns.
        
        6. You can arrange the order of questions in the Questions page by dragging them yp or down. The order of questions in the Questions page determines the order of questions in PolicyCenter.
        
        7. Additional Topics: The **Dependent On Page** enables you to display follow up questions that appear only when specific answers have been entered.
            
            1. Define both questions on Questions page
            
            2. Select dependent question
            
            3. On Dependent On page, Click Add and select initial question code
        
        8. Mention and show **Incorrect Answer Page** and Blocking Action (Blocking Quote/Bind): If the correct answer is not provided, a policy underwriting issue is created with an issue type.
        
        9. Mention and show **Choices** page.

13. Questão de revisão #1
    
    Questão - What is a **question set** and what is its purpose?
    
    Resposta:
    
    - Resposta correta
        
        A **question set** is a **set of questions** designed to facilitate the collection of information at different points in the policy transaction process. Question sets are used to determine whether a person qualifies for a particular product, either right before they enter the wizard or through accumulated information indicating an unacceptably large level of risk that isn't tied to any one single issue.
        

14. Questão de revisão #2
    
    Questão - What is as **offering** and what is its purpose?
    
    Resposta:
    
    - Resposta correta
        
        An **offering** lets insurers define different product types based on existing base product definitions. The primary use case of offerings is to define specific product types.
        

15. Questão de revisão #3
    
    Questão - List two possible factors that make an offering available.
    
    Resposta:
    
    - Resposta correta
        
        Start and end date, Job type, State, Industry, Offerings question set answers.
        

---

# 13. Product Designer: Modifier

1. Learner story
    1. As a business analyst or configuration developer, I want to know how to use modifiers in Product Designer.

2. Subtopic
    1. What is a modifier?

3. Quote modifiers
    
    1. Modifiers added to the product affect rating for all lines in that product.
    
    2. Modifiers added to a policy line affect only that line.
    
    3. They are called ProductModifier patterns.
    
    4. The individual modifiers on the policylines still exist as they were.
    
    5. Example: Modifiers are added to GL Line within CPP product
    
    [![](Dashboard/Attachments/Untitled%20133%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20133.png)
    

4. Modifier patterns
    
    1. Product level modifiers are called ProductModifiers. They are applied to product only for multi-line policies such as CPP (Commercial Package). They apply to all policy lines on a policy. An example is the "CPPIRPM" (Commercial Package Policy Individual Risk Premium Modification) which affects rating of coverage for all lines within CPP.
    
    2. **CPPIRPM:** (CPP Individual Risk Premium Modification) This is a specific example of a scheduled rate modifier. It is used primarily in property and liability policies. The rating and quoting engine takes factors into account in determining the premium. These factors can include the following (among others):
        
        1. Size of premium
        
        2. spread of risk
        
        3. superior building construction
        
        4. quality of management
        
        [![](Dashboard/Attachments/Untitled%20134%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20134.png)
        

5. Modifiers in the user interface
    
    1. Relevant for configuration developers.
    
    [![](Dashboard/Attachments/Untitled%20135%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20135.png)
    

6. Demo Creating Basic Modifier Patterns
    
    1. In Product Designer, go to the modifier section for Commercial Package to show that modifier will effect all the LOBs.
    
    2. Show policy line relationship by selecting a modifier for the line.
    
    3. Modifiers.
    
    4. When users create a modifier, they must provide a Code, a Name (which will be displayed on the user interface), a Modifier Type (the subtype for the modifier), a Data Type, and a Schedule Rate checkbox if the data type is rate.
    
    5. For most lines of business, the modifier is associated with the entire policy (the policy line). Therefore, there is usually only one possible value for modifier type, "<CodeForLine>Modifier" such as BOPModifier. For personal auto, a modifier could be associated wither with the entire policy or with a specific vehicle.  
        Therefore, for Personal Auto and Commercial Auto only, users must select the appropriate
    
    6. Click on the Add button on Product → Modifiers page.
    
    7. Enter Code, Name, Select Modifier Type as ProductModifier, Data Type, and specify if this is Schedule Rate modifier.

7. Subtopic
    1. What is schedule rate modifier and how do i create one?

8. Schedule rate modifier
    1. **Schedule Rate:** A specific type of modifier that provides credits or debits within established value ranges. Use them for factors such as management, property, and other intangibles that you cannot quantify as part of the submission.
        
        [![](Dashboard/Attachments/Untitled%20136%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20136.png)
        

9. RateFactor typelist
    
    1. A rating input modifier consists of one or more rate factors. Rate factors must be listed in the **RateFactorType typelist** before they can be added to a schedule rate.
    
    2. The first step in creating a schedule rate modifier is to create any needed rate factor in the **RateFactorType**.
    
    3. Studio automatically knows about new typecodes, so configuration users can create the schedule rate modifier without restarting the server. However, because changes to typelists are considered data model changes, configuration users must restart the server before they can test the schedule rate modifier in the user interface.
    
    4. CONFIG TIP: A rating input modifier consists of one or more rate factors. Rate factors must be listed in the RateFactorType typelist before they can be added to a schedule rate.  
        Therefore, the first step in creating a schedule rate modifier is typically to create the necessary rate factors in RateFactorType. Studio automatically knows about new typecodes, so configuration users can create the schedule rate modifier without restarting the server. However, because changes to typelists are considered data model changes, configuration users must restart the server before they can test the schedule rate modifier.
    
    5. During modifier creation, Product Designer adds a Rate Factors link under Go to links when you set the data tpe to rate and you select the Schedule Rate check box. Go to Rate Factors page to add one or more rate factors that combine to give the value of the schedule credit.
    
    [![](Dashboard/Attachments/Untitled%20137%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial/Untitled%20137.png)
    

10. Questão de revisão #1
    
    Questão - For the Personal Auto policy line, why are there two possible values for a modifier's "modifier type"?
    
    Resposta:
    
    - Resposta correta
        
        In Personal Auto, a modifier can be associated to the entire policy or to a specific vehicle. When creating the modifier, you specify a modifier type to denote if it is policy-level or vehicle-level.
        

11. Questão de revisão #2
    
    Questão - When do you need to add values to the RateFactorType typelist?
    
    Resposta:
    
    - Resposta correta
        
        You need to add typecodes to the RateFactorType typelist when you create schedule rate modifier and the desired rate factors don't already exist.
        

---

![](Dashboard/Attachments/icons_questions%2029.png)

==The Outlining Method is traditional note-taking template with an outline format. The outlining method helps show relationships in your topic hierarchy.==