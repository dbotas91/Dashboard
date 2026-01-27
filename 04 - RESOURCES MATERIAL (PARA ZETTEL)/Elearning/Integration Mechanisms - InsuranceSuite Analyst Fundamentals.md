---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%207.png)

# Integration Mechanisms - InsuranceSuite Analyst Fundamentals

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201263.svg)Date Created|@January 24, 2022|
|![](Dashboard/Attachments/arrow-circle-down_gray%20940.svg)Status|In Progress|
|![](Dashboard/Attachments/checkmark-square_gray%20685.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20504.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20136.svg)Last Edited|@January 26, 2022 4:20 PM|

[Integration Mechanisms](#91224e9b-59b8-4b1d-9302-2c315f68b220)

[1. InsuranceSuite integration](#bd08a610-6b52-4044-8d1a-0208acbfed47)

[2. Understanding Integration](#5b8411a5-35b9-4db6-8c18-3418c78ab6f8)

[3. InsuranceSuite Integration Mechanisms](#abc341a9-b9e9-4b6e-b5f8-fe9ab4fec7bf)

[4. Identify data requirements for integration](#4dd5c66a-e84e-4e78-a6c4-bdb1f1b9ce1c)

[5. Identify UI changes for integration](#ebef7f05-21e4-41c6-ba46-428c390d34de)

[6. Questions](#43e3355c-0e94-4fc8-987e-6e8eb1dd478a)

# Integration Mechanisms

Integration refers to the development work that connects two systems to support the exchange of data and to perform work.

Guidewire supports the integration of InsuranceSuite products with a wide variety of external systems.

Insurance companies integrate InsuranceSuite products with external systems to access services not performed by InsuranceSuite products, such as document production and management. Integration allows insurers to continue using services used with their legacy systems with Insurance Suite products. For example, an external system can be used to verify addresses or VIN numbers, or to review medical or legal bills. Integration also adds new capabilities to InsuranceSuite products, such as EFT payment processing.

Integration is valuable because it helps the insurer to benefit from external applications that are maintained by industry specialists, such as systems that handle roadside assistance or emergency services to secure damaged property. Integration can also be used to outsource common tasks like check printing. Integration saves time and money by eliminating the need to build special processes within InsuranceSuite products.

---

# 1. InsuranceSuite integration

Guidewire InsuranceSuite applications can integrate with many applications and services. Every implementation involves multiple integration points that make use of a variety of technologies and technical mechanisms.

[![](Dashboard/Attachments/Untitled%2036.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled.png)

Common integration points:

- Authentication systems: these systems take a username and either a token or a password and verifies whether the credential are authentic;

- Document management systems: applications such as FileNet or [Box.net](http://Box.net) that consist of document production and storage. Document production merges templates and data and it may also store the document templates. Document storage manages documents that end users download, create, edit and upload.

- Address book application systems: an example is Guidewire Contact Manager.

---

# 2. Understanding Integration

Non-developers need to understand the basics of integration to assist with documenting requirements and communicating them to developers.

Integration work involves the exchange of data between systems. The data requirements of the external system must be mapped to InsuranceSuite data, UI changes to support the data must be designed, and error codes must be handled.

The requirements must be documented appropriately using data mapping, screen mocups, an so on to be able to communicate requirements with integration and application developers.

---

# 3. InsuranceSuite Integration Mechanisms

Integration mechanisms are used by developers to send and receive information. For example:

1. Predefined plugins are Gosu classes that a Guidewire application invokes to perform an action or calculate a result at a specific time in its business logic.

2. Web Services define request-and-response APIs that let you call an API on a remote computer or get information from a remote computer.

3. Messaging enables a Guidewire application to send a message to an external system after something changes in the application, such as a changed exposure or an added check. The change triggers an event that executes Gosu code. The code sends a message to the external system. For example if you create a cheque in CC, your messaging code notifies a corporate financials system.

4. A startable plugin is custom code that begins executing during server startup. Unlike a predefined plugin, which executes only when it is invoked by other code a startable plugin can be started and stopped as required.

5. A batch process runs in the background and performs important tasks independent of an administrator. All batch processes execute on the batch server. A batch process runs to completion and then reports its result to a log or to a user interface.

1. Predefined plugins
    
    Some predefined plugins must interact with external systems, such as an authentication plugin in BC, CC and PC or a geocoding plugin that is used in CC and PC.
    
    [![](Dashboard/Attachments/Untitled%201%2016.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled%201.png)
    

2. Webservices
    
    Webservices are XML-based information exchange systems that use the Internet for direct application-to-application interaction. One system will publish the web service by making it available for other systems to call that service. Other systems will consume web services by calling published services.
    
    Guidewire InsuranceSuite applications can both publish and consume web services. In this example, and InsuranceSuite application publishes a webservice called UserAPI that provides methods for exchanging user information. The external system send a request to a method in UserAPI to verify that account 1733 exists. The account is not found, so the method returns the result false.
    

3. Messaging
    
    Guidewire InsuranceSuite supports sending messages to external systems in a transaction-safe way. Example: a message is created and sent to a cheque printing system. The message is sent only if cheque creation is successful and no exceptions occur. In response, the cheque and acknowledges receipt of the cheque information by returning the cheque number to ClaimCenter.
    
    Messaging is used to notify an external system of an important event. The external system does not need to call anything in InsuranceSuite. It only receives messages for successful events and sends an acknowledgement that the message was received in response.
    

4. Startable Plugins
    
    A startable plugin listens for requests from an external system that communicates with InsuranceSuite by means of mechanisms such as messaging via Java Message Service (JMS Messaging).
    
    For example: BC accepts payment information from an external payment system via a startable plugin running in BC.
    
    [![](Dashboard/Attachments/Untitled%202%2013.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled%202.png)
    

5. Batch Processes
    
    A batch process completes background work that must be done on a periodic basis without user input. Typically, a batch processes runs according to a schedule and is not triggered by a specific business event.
    

---

# 4. Identify data requirements for integration

The Business Analyst or other non-developer works with the integration developer to find out what information must be sent to the Address Verification system, and what data is returned. Next, the Business Analyst or other non-developer checks the Data Dictionary to determine if all of the required information already exists. The final step is to prepare a data mapping to match the InsuranceSuite data to the Address Verification system data. Any missing fields are identified so a developer can add them to the InsuranceSuite data model.

---

# 5. Identify UI changes for integration

The BA or other non-developer reviews the existing UI screens to identify any changes needed. This can include mocking up a copy of the existing screen to indicate where new fields should be added, and anny buttons or other controls needed to call integration if this will not happen automatically when the data is processed.

---

# 6. Questions

[![](Dashboard/Attachments/Untitled%203%2011.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled%203.png)

[![](Dashboard/Attachments/Untitled%204%208.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled%204.png)

[![](Dashboard/Attachments/Untitled%205%208.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled%205.png)

[![](Dashboard/Attachments/Untitled%206%208.png)](Integration%20Mechanisms%20-%20InsuranceSuite%20Analyst%20Fu/Untitled%206.png)