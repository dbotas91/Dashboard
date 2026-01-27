---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
![](Dashboard/Attachments/icons_notes--outline%2012.png)

# PolicyCenter 9.0 Introduction (Personal/Commercial) - Kickstart

|   |   |
|---|---|
|![](Dashboard/Attachments/calendar_gray%201267.svg)Date Created|@July 13, 2021|
|![](Dashboard/Attachments/description_gray%20339.svg)Description|This course explains the features and processes of PolicyCenter, giving learners the basic skills needed to define business requirements for a PolicyCenter project. It teaches students how to create, modify, and manage policies and accounts in PolicyCenter.|
|![](Dashboard/Attachments/arrow-circle-down_gray%20944.svg)Status|Complete|
|![](Dashboard/Attachments/checkmark-square_gray%20690.svg)To Review?||
|![](Dashboard/Attachments/formula_gray%20509.svg)Review Due||
|![](Dashboard/Attachments/clock_gray%20141.svg)Last Edited|@January 26, 2022 4:31 PM|

[1. The Policy File](#55de6a1e-2b93-4707-9812-4c2b97628944)

[2. Policy Transactions](#afd6e8d4-c837-4407-9349-c121b1576045)

[3. Accounts](#e1f54378-68b3-4a7f-8edc-ae90f33bcdde)

[4. Full Application Submission](#f86bd92f-6882-431e-a54f-172f361d94a1)

[5. Policy Tools](#cba2532a-390b-4ddf-8f9d-ad67824e5d41)

[6. Policy Changes and Pre-emption](#4dfb238b-cf3e-4312-b63a-a4a90e71e0cf)

[7. Renewals](#21e464d6-baac-4b26-918a-f960b2b8e31e)

[8. Cancellation Transaction Set](#c8670227-7ced-477b-9a07-9811cdd96ff2)

[9. Out-of-Sequence Transactions](#fd4d27b7-ab5e-49ea-a7fd-b014f7279c4f)

[10. Users, Groups and Organizations](#da5bcb29-304e-40bd-81ca-c252935ed93f)

[11. Activities](#06ed9822-7557-4cba-80c6-4b621e8293f8)

[12. Contingencies](#67304c78-374e-4811-98ce-b081202195bc)

[13. Forms](#2196a123-6e1a-42d3-aaf0-0466a642d19a)

[14. Underwriting Authority](#ce6085b7-b414-4f42-a3c7-b31516c66d75)

# 1. The Policy File

1. Quero saber o que é um _Policy file_ e a relação entre _policy file_, _account e_ _coverages_ e procurar por uma _policy_.
    
    1. _Entity_
        
        Um _entity_ é um tipo de objeto que o PolicyCenter precisa criar, modificar ou gerir
        
        Exemplos de entity: Policy, Account, Coverage, User
        
        Apenas algumas entities são essenciais para as funções de negócio do PolicyCenter.
        
        As entities são difinidos em ficheiros XML que são acessíveis através do PolicyCenter Studio
        
        Cada entity do PolicyCenter guarda dados numa da tabela da base de dados.
        
    
    2. _Policy Terminology_
        
        Hierarquia das relações
        
        [![](Dashboard/Attachments/Untitled%2038.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled.png)
        
    
    3. _Policies_
        
        É um ficheiro onde o PolicyCenter guarda informação que faz parte do contrato legal com a seguradora. Uma policy está associado a uma _Account_.
        
        _Accounts_ serão abordados num módulo diferente. No entanto é preciso entender que policies estão associadas às accounts.
        
    
    4. _Contacts and Locations_
        
        Um _contact_ é uma pessoa ou organização que inclui (mas não está limitado) o nome do segurado(s).
        
        Uma _location_ é um local físico que pode ser referido numa policy.
        
        _Contacts_ e _locations_ podem ser criados inicialmente numa _account_ e reutilizados numa policy ou criados numa policy.
        
    
    5. _Coverages_ (Coberturas)
        
        Uma _coverable_ é uma exposição ao risco que pode ser protegido pela policy.
        
        Tais como:
        
        - Uma propriedade tangível como um edifício;
        
        - Veículos
        
        - Jurisdição
        
        - A própria policy
        
        Tipos de cobertura de nível de linha da policy:
        
        - Property
        
        - Liability (responsabilidade)
        
        [![](Dashboard/Attachments/Untitled%201%2018.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%201.png)
        
    
    6. _Coverages Terms_ (Termos da cobertura)
        
        Um _coverage term_ é um valor que limita ou define a coverage.
        
        [![](Dashboard/Attachments/Untitled%202%2015.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%202.png)
        
        [![](Dashboard/Attachments/Untitled%203%2013.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%203.png)
        
        [![](Dashboard/Attachments/Untitled%204%2010.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%204.png)
        
    
    7. _Core concept: Forms_ (Formulários)
        
        Um _form_ é um documento físico que detalha algum aspeto da _policy_.
        
        [![](Dashboard/Attachments/Untitled%205%2010.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%205.png)
        
    
    8. _Core concept: Premium_ (Prémio)
        
        Um _premium_ é o dinheiro que o segurado paga pela _policy_.
        
        [![](Dashboard/Attachments/Untitled%206%2010.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%206.png)
        

2. Questão de Revisão #1
    
    Questão - Where do PolicyCenter entities store data?
    
    Resposta:
    
    - Resposta correta
        
        - A data table in the database.
        
    

3. Questão de revisão #2
    
    Questão - How many files can be associated with an account?
    
    Resposta:
    
    - Resposta correta
        
        - Zero, um ou mais.
        

4. Questão de revisão #3
    
    Questão - Of the primary entities discussed in this lesson (other than policy), wich entity:
    
    1. Is the money the insured (account) pays for the policy?
    
    2. Is an exposure to risk that can be protected by the policy?
    
    3. Is a physical document detailing some aspect of policy?
    
    4. Can either be created on the policy or created on the account and reused on the policy? (two possible answers)
    
    5. Is a value that further limits or defines the coverage?
    
    Resposta:
    
    - Resposta correta
        
        1. Premium (prémio)
        
        2. Coverable (coberto)
        
        3. Form
        
        4. Contact or Location
        
        5. Coverage Term
        

5. Questão de revisão #3
    
    Questão - Of the primary entities discussed in this lesson (other than policy), wich entity:
    
    1. Is the money the insured (account) pays for the policy?
    
    2. Is an exposure to risk that can be protected by the policy?
    
    3. Is a physical document detailing some aspect of policy?
    
    4. Can either be created on the policy or created on the account and reused on the policy? (two possible answers)
    
    5. Is a value that further limits or defines the coverage?
    
    Resposta:
    
    - Resposta correta
        
        1. Premium (prémio)
        
        2. Coverable (coberto)
        
        3. Form
        
        4. Contact or Location
        
        5. Coverage Term
        

---

# 2. Policy Transactions

1. Como business analyst or developer, quero descrever os tipos de policy transactions (transações numa apólice) e interpretar o policy graph para que consiga e explicar o ciclo de vida duma policy no PolicyCenter
    
    1. Policy lifecycle transaction  
        O core (coração) do PolicyCenter está na policy.  
        Exemplos de _policy changes_ são: criação de uma nova _policy_, _renewal of a policy for e new term_ (renovações da apólice para um novo termo/período), ou cancelamento da policy. A única transação que não está incluída é _Audit_. _Audits_ podem ocorrer a qualquer altura durante o termo da policy. Uma _audit_ (auditoria) final pode ocorrer no final de cada termo da policy.
        
        Cada transação vai ser descrita nos pontos seguintes.
        
        [![](Dashboard/Attachments/Untitled%207%2010.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%207.png)
        
    
    2. Life span of a policy  
        Policy transaction graphs are useful for depicting the nature and behavior of complex transaction interactions including reistatements, rewrites, preemptions and out-of-sequence transaction.  
          
        The question "When does a policy end?" does not have a universal answer in the insurance industry. Personal lines insurers are more likely to view successive policy terms as a single policy; and Commercial lines insurers are likely to view each term as a "policy".
        
        If you assume that a policy has one-year term, and at renewal time a new policy number is not generated. (This is often the case, but not always the case with every insurance company.) At the end of that year, the policy has the samen policy number. Did the original policy end?
        
        Some would say yes, that when the expiration date is reached, the policy ends. A new policy with the same number is created, but it is a different policy.  
        Others would say no, if the two time periods are governed by a document with the same policy number, then it is in fact the same policy.  
        
        [![](Dashboard/Attachments/Untitled%208%209.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%208.png)
        
    
    3. Policy period
        
        In PolicyCenter, a **policy period** is a copy of the entire policy after a job taks place, wich can be within a Policy Term (job = policy change, renewal, etc.). The copy of the policy includes policy information that was in place prior to the job executing and also reflects the _new_ changes.  
        There can be multiple periods within a term. For instance, each time there is a policy change, a new period begins on that effective date.
        
        [![](Dashboard/Attachments/Untitled%209%206.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%209.png)
        
    
    4. Submissions
        
        All transactions (including submissions) have a create date, an effective date and close date.
        
        - The create date is the date that the transaction was initiated.
        
        - Transaction close date or close date - the date the job was completed.
        
        - Effective date - the date that the information in the job becomes legal and biding. The effective date is the date that the transaction becomes effective. For example, you could create and complete a submission today for an auto policy that will not take effect until Monday of next week. Today would be the written date, but Monday of the next week is the effective date.
        
        [![](Dashboard/Attachments/Untitled%2010%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2010.png)
        
        In some cases, the transaction close date comes before the effective date. For example, a submission job is typically completed before the policy goes into effect.  
        In other cases, the transaction close date comes **after** the effective date. For example, a rewrite job that corrects a clerical error may be run several weeks after the policy has become effective, but the rewrite is effective at the start of the policy.  
        **Issuance job:** An issuance job always occurs with a submission job if necessary. There are times that a user may choose to bind a submission without issuing it. Perhaps you need to collect additional information that binding does not require, such as verification of eligibility for discounts in an auto policy. To start an issuance job, the policy must already be bound (submission), but not issued.  
        In addition, there must be no other open jobs on the policy.
        
    
    5. Policy Change
        
        A change transaction is also referred to as a "policy change". A "material change" is a change to a policy that affects what is covered. Policy changes typically involve material changes. Policy changes almost always involve a change to the policy's premium.
        
        [![](Dashboard/Attachments/Untitled%2011%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2011.png)
        
    
    6. Renewals  
        An insured might choose to not renew a policy because the or she found a better-priced policy elsewhere, or because the policy premium has changed (perhaps because of changes in the industry or because of claims made against the original policy) and the insured does not wish to pay the premium.  
        An insurer might choose to not renew a policy because the policy is considered financially unfavorable (perhaps because too many claims were filed against the policy).  
        Renewals can be highly regulated from state to state.  
        There are restrictions in some states relating to rate increases on renewals in excess of given percent.  
        And, there are restrictions in essentially all states relating ot the insurer non-renewaing without providing a specified amount of prior notice.  
        Renewal regulation at a state level is largely a consumer protection issue. It is focused principally on personal lines (homeowners, personal auto) and harder to place on commercial lines.
        
        [![](Dashboard/Attachments/Untitled%2012%205.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2012.png)
        
    
    7. Cancellations  
        Cancellations are more easily executed by the insured than they are by the insurer. In many cases, the insurer can choose to discontinue a policy and not need to have any reason for it. However, an insurer cannot discontinue a policy unless they can demonstrate some just cause, such as non payment of premiums, purposefully inaccurate information provided at the time of submission, or fraud.
        
        [![](Dashboard/Attachments/Untitled%2013%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2013.png)
        
    
    8. Reinstatements
        
        [![](Dashboard/Attachments/Untitled%2014%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2014.png)
        
    
    9. Rewrites  
        A rewrite involves a change to a policy that is significant enough that it cannot be captured with a policy change.  
        Although there is not absolute rule in the insurance industry that dictates when something must be done as a rewrite versus as a policy change, there is at least one common use case for this type of transaction:  
        People who work for the insurer may make clerical errors when entering policy information. For example, during a discussion with an applicant, the underwriter might have agreed to provide a certain type of coverage but forget to enter it into the policy system. The forms issued from the submission job are wrong, and the insurer may prefer to have a new set of forms drafted so that they have physical proof of exactly what was covered. In this case, a rewrite is required because the customer wanst a full set of policy forms showing the correct information. If the requirement was to just make the change have handled this. This rewrite must have an effective date as of the start of the policy.  
        Rewrite feature allows you to do the following:  
        Full-term Rewrite: a full term rewrite replaces the original policy for the complete policy term.
        
        [![](Dashboard/Attachments/Untitled%2015%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2015.png)
        
    
    10. Mid-term rewrites  
        Mid-Term Rewrite: A mid-term rewrite replaces a portion of the original term and allows you to rewrite the policy to the original policy end date or to a new end date.  
        Every transaction has two different dates:
        
        - **transaction close date** or **close date -** the date the job was compleetd.
        
        - **effective date -** the date that the information in the job becomes legal and binding.
        
        In some cases, the transaction close date comes _**before**_ the effective date. For example, a submission job is typically completed before the policy goes into effect. In other cases, the transaction close date comes _**after**_ the effective date. For example, a rewrite job that corrects a clerical error may be run several weeks after the policy has become effective, but the rewrite is effective at the start of the policy.
        
        [![](Dashboard/Attachments/Untitled%2016%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2016.png)
        
    
    11. Rewrite new account  
        Rewriting a policy to another account means moving the policy going forward to another account, but the policy history including earlier policy terms stay with its current account. For example, a young adult has a policy in his parent's personal auto account. He graduates from college, and wants to move his policy to his own account.  
        The insurer cancels his policy and rewrites it to his new account.  
        When the user chooses to rewrite a policy to a new account, a rewrite new account job is created on the new account. This job takes data from an existing policy and creates a new policy with a new policy number in the new account. The policies on the new and old accounts cannot overlap. Because of this, no policy transaction can be created on the source policy for a date later than the rewrite date (effective date of the rewritten policy). The policy does not exist on the source account after that date.  
        Unlike a rewrite job can have qualification questions.  
        Qualification questions are discussed later in this course.
        
        [![](Dashboard/Attachments/Untitled%2017%204.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2017.png)
        
    
    12. Policy lifecycle transactions  
        The core of PolicyCenter revolves around the policy.  
        Examples of policy changes are: creation of a new policy, renewal of a policy for a new term, or cancellation of a policy. The only transaction **not** included in the slide is Audit. Audits can occur at any time during a policy term. A final audit can happen at the end of each policy term.
        
        [![](Dashboard/Attachments/Untitled%2018%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2018.png)
        
    
    13. Audits/Final audits  
        Audits are unlike the other transactions for the following reasons:
        
        - Audits utilize the policy information and are tied to the policy periods but they cannot alter the policy contract.
        
        - Audits don't have an edit effective date associated with them and do not get "issued".
        
        - They can be executed at any time within the policy term. (The only other job wich typically executes on a recurring basis is a renewal, and even that technically occurs only once per term.)
        
        - They are initiated and are viewable in a separate place in the PolicyCenter interface.
        
        In case of workers compensation line of business the premium is typically based on the payroll of the insured workers. One usually cannot say for certain how many workers will be employed during the policy term or what their salaries will be.  
        Consequently, the payroll is estimated. Hence an audit is required to convert these estimated amounts to actual data wich in turn is reflected on the policy premium.  
        Sometimes, an LOB wich does not appear to be based on estimates may be subject for a Final Autid (for example Business Auto). Final Audits or other audit 'reporting' can be applied to several lines of businesses.  
        Premium Reports are available for workers' compensation line of business. Final Audits are available for worker's compensation and general liability LOBs.  
        **Premium Reports:** Premium reports are subtype for audit that are created for interim periods within a policy period.  
        Premium reporting audits adjust estimate data, such as payroll, inventory, and course of construction reports. The primary distinction between the two types of activities is that an "audit" is executed by the insurer whereas a "premium report" is prepared exclusively by the policyholder (or their representative) and are not typically verified by the insurer. A premium report or a final audit is created using any of the available audit methods (voluntary, phone, physical or estimate).
        
        [![](Dashboard/Attachments/Untitled%2019%203.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2019.png)
        

2. What is the relationship between transactions and jobs?
    
    1. Jobs  
        The term "policy transaction" is more typical in the industry and is used in the user interface. The term "job" is used in the data model, in user interface configuration, and in business rules.  
        All jobs have an issue date and an effective date. For example, you could create a submission job today and issue it tomorrow, that will not take effect until Monday of next week is the effective date. Tomorrow would be the issue date, but Monday of the next week is the effective date. Also referred to as the "Transaction Close Date" in the Transactions list.  
        A policy transaction is used to execute a transaction. Once it completes, it becomes a transaction on the policy but has an associated policy transaction number.
        
        [![](Dashboard/Attachments/Untitled%2020%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2020.png)
        
    
    2. Things that define job logic
        
        Job Processes control the job flow and may use workflows.  
        Workflows can be invoked by a job process class as appropriate for asynchronous processes. User actions in the user interface directly invoke methods on the job process.
        
        The other places where logic could be defined that could impact how a job is executed, include functions called by business rules and/or changes to the Guidewire's default Java class model. But the majority of the configuration works occurs in the above listed six categories. With the exception of the product model, none of the features are unique to PolicyCenter.
        
        They are platform-level features that are also used in ClaimCenter and BillingCenter. Because policy processing involves more complex business processes than claims processing, PolicyCenter makes more extensive use of wizards and workflow.
        
        [![](Dashboard/Attachments/Untitled%2021%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2021.png)
        
    
    3. Job processes
        
        PolicyCenter uses both workflows and job process Job processes are editable.
        
        The [JobProcess.gs](http://jobprocess.gs) Gosu class contains methods that are common to all jobs and can be viewed in Studio. For example, consider the above job process steps involved in a submission job process. The [SubmissionProcess.gs](http://submissionprocess.gs) class exists in Guidwire Studio and has the actions taken within a submission job.
        
        [![](Dashboard/Attachments/Untitled%2022%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2022.png)
        
    
    4. Workflows
        
        Workflows is recommended for automation and coordination of activities (including manual activities) between PolicyCenter and external systems. Workflows are used for asynchronous steps and for automated processes. The workflow is called by the job code and by rules in the rule sets. In some cases, the wizard calls the workflow and sends control back to the wizard
        
        In the default installation, only renewal and cancellation jobs have workfloes. Cancellation has a workflow that handles the potential waiting period between the time the cancellation is scheduled or issued and completed.
        
        [![](Dashboard/Attachments/Untitled%2023%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2023.png)
        
    
    5. Wizards
        
        [![](Dashboard/Attachments/Untitled%2024%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2024.png)
        
    
    6. Business rules
        
        The job code and workflows access the rule sets. Simple business rules are configurable withn the user interface and will be discussed later in another module. Complex business rules are often implemented and executed within Gosu classes. Inserting logic in the job code allows for a more centralized job flow and is easier to debug. In the base application, most of the business logic is in the Gosu job process code.
        
        Rules can be used to check for a simple set of conditions and then follow with a set of simple actions. Rules are grouped by function for the purpose of customizing a process, such as a submission, to follow established business procedures.
        
        [![](Dashboard/Attachments/Untitled%2025%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2025.png)
        
    
    7. External systems
        
        External systems are not discussed in detail in this course. For further information, refer to the PolicyCenter Documentation.
        
        [![](Dashboard/Attachments/Untitled%2026%202.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2026.png)
        
    
    8. Initiating jobs
        
        The jobs that can be executed depend on the state of the policy. For example, you cannot initiate a reinstatement job against a policy that hasn't been cancelled.
        
        Submission, policy change, cancellation, reinstatement, rewrite, and audit jobs are typically initiated by the end user through menu actions.
        
        Renewal jobs are typically initiated automatically by a PolicyCenter batch process.
        
        Cancellation jobs might be initiated automatically by a billing application due to non-payment.
        
        [![](Dashboard/Attachments/Untitled%2027%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2027.png)
        

3. Como é que as policies são representadas no PolicyCenter?
    
    1. Histórico duma policy
        
        If a policy is created, not modified, and then either canceled before the renewal date or not renewed at the expiration date, then the policy never changed over time. In all other circumstances, the policy changes over time.
        
        [![](Dashboard/Attachments/Untitled%2028%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2028.png)
        
    
    2. Períodos da policy
        
        **The PolicyPeriod entity contains information about all effectiv dates within a single PolicyTerm or period.**
        
        Thus, every change in policy is represented by a PolicyPeriod entity at the root of a complex graph of sub-objects such as policy lines, vehicles, coverages, and many others. This entire hierarchy of entities is cloned in the database into new rows during policy changes, renewals, or other jobs. The cloned branch is updated with the changes. The changes made to this branch will be visible only when a user views policy from that branch's effective date. This cloned branch becomes the base for future changes and so forth.
        
        (In contrast, a submission job's branch is not cloned from another branch.)
        
        **PolicyPeriod**  
        The PolicyPeriod entity stores information for a specific revision of the contractual period of a policy. A revision occurs when a job occurs on a policy. Submission creates the first revision. Each additional transaction on the policy creates a new revision.  
        Therefore, a policy usually has multiple revisions, with one PolicyPeriod entity for each revision. During the contractual period, only one PolicyPeriod entity is in effect at a time. A new revision is created when you process a policy change that adds a car to the policy. The EffectiveDate for the car is several months into contractual period, and the ExpirationDate extends to the end of the period.
        
        PolicyCenter clones a new PolicyPeriod entity and its sub-entties and adds an entity for the new car. The contractual period now has two PolicyPeriods. The new PolicyPeriod entity is in effect.
        
        The old PolicyPeriod entity is preserved as a historical record of the policy.
        
        [![](Dashboard/Attachments/Untitled%2029%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2029.png)
        
        **PolicyTerm**
        
        A new Policyterm is created whenever the policy contract is completely recreated. This occurs with a new policy (submission), a renewal, or a rewrite of an existing contract.
        
        A new PolicyTerm is not created when you amend a policy contract with a policy change job.
        
        The terms "policy period" and "policy term" are used synonymously throughout the industry. The PolicyPeriod entity represents one historical version of a particular "policy period" or "policy period" or "policy term", all representing what the policy looked like at different points in model time. Thus "PolicyPeriod" is somewhat different than "policy period".
        
        In order to avoid confusion about wich we are talking about at any given time, throughout this course we will use the term "policy term" to refer to a "policy period" or "policy term", and use "PolicyPeriod" only to refer to entity, that is, a specific version of a "policy term".
        
        Transaction effective dates
        
        Every transaction has effective date that identifies when it goes into effect, not the date the job was actually run and could be different from the policy term effective date.
        
        For example, a renewal job often takes several weeks (or even months) to run.
        
        Therefore, it must be executed well in advance of the expiration date. The "renewal" label shown above indicates when the job became effective. The date the job was started would be well in advance of the date indicated by the "renewal" arrow. The data model uses the term "Edit Effective Date" for job policy periods so that it is not confused with the policy term dates. Although they both show up as Effective Date on the user interface.
        
        For the example above, the policy term has the following dates effective date 4/20/08 and an expiration date of 4/20/09. But the renewal job has an edit effective date of 4/20/10. The policy term dates are different from the job dates.
        
    
    3. Applying jobs to policies
        
        Every transaction has two dates relevant to these graphs
        
        - **Bind Date** - when was transaction processing completed
        
        - **Effective date** - when do transaction results come into effect
        
        Note that the effective date can come before, on, or after the bind date. Transaction effective date is no the date the job was run. Every transacation within a policy term supersedes the transaction effective before it.
        
        In a simple world, only one job would be run against a policy at a given time, and every job would be executed in the order in wich it was supposed to take effect. In practice, this is not always the case.
        
        "Preemtion" is a policy transaction phenomenon that occurs when two or more jobs are running on a policy at a given time. This can cause a problem because both jobs are based off of the same version of the policy, When one job finishes, the state of the policy changes, and this could cause conflits for the other job.
        
        (For example, an auto policy could have one car on it. Then, a change job is executed to add a motorcycle to it, and a second change job is executed to add a truck to it. If the motorcycle job finishes first, then the car policy becomes a car + motorcycle policy. However, the truck job was started on a poklicy that had just a car on it. When that job finishes, the motorcycle cannot be discarded. Somehow, the result of the motorcycle change job must be reconciled.)
        
        An "out of sequence" (also referred to in the industry as an "out of sequence endorsement") is a policy transaction wich is executed after some other policy transaction wich is executed after some other policy transaction but becomes effective before that policy transaction. The second job changes the state of the policy wich could impact how the first job should be executed.
        
        (For example, in January, an auto policy could have one car on it. Then, a change job is executed to add a motorcycle to the policy as of June. After that, change job is executed to add a truck to the policy as of March. The second job must be treated in two pieces: March to June (in wich only a truck is being added) and June forward (in wich a car and a truck are being added).
        
        Preemptions and out-of-sequence transactions are discussed later in this course in th Out-Of-Sequence Transactions lesson under Policy Transactions.
        
        [![](Dashboard/Attachments/Untitled%2030%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2030.png)
        

4. Questão de revisão #1
    
    Questão - Is a transaction job? Explain.
    
    Resposta:
    
    - Resposta correta
        
        The term "policy transaction" is more typical in the industry and is used in the user interface. The term "job" is used in the data model, in user interface configuration, and in business rules.
        

5. Questão de revisão #2
    
    Questão - A customer calls and wants a new policy for another term, at the end of policy term.  
    What transaction is the customer asking for?
    
    Resposta:
    
    - Resposta correta
        
        The customer wants a renewal.
        

6. Questão de revisão #3
    
    Questão - A customer wants a new coverage on an existing policy. What transaction will best suit this need?
    
    Resposta:
    
    - Resposta correta
        
        A policy change is the most obvious transaction for this. However, a rewrited may also be needed depending on the coverage details.
        

---

# 3. Accounts

1. Learner story
    1. As a business analyst or developer, I want to know what an **account** is and how to create it so that I can keep account information separate from policy details.

2. Accounts
    1. What is an account?  
        An account gives PolicyCenter users the flexibility to create and manage a customer's account independent of policies with wich the account may be associated. The ability to manage an account separately from a policy can be useful when assigning visibility into both policies and accounts to different type of users.
        
        [![](Dashboard/Attachments/Untitled%2031%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2031.png)
        
        A person or an organization might be the account holder.
        
        [![](Dashboard/Attachments/Untitled%2032%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2032.png)
        

3. Accounts - People
    1. Different accounts have different purposes. A single person may hold multiple accounts.
        
        [![](Dashboard/Attachments/Untitled%2033%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2033.png)
        

4. Accounts - Creating
    
    1. When you try to create a new account in PolicyCenter, it always searches for the account first, checking the name against one or more producer or account databases. PolicyCenter is going through "**name clearance**" to ensure that a person or company is not an existing account and that another producer does not represent them for the given policy type.
    
    2. Name clearance is a relevant issue when the same account requests quotes or policies at different times and may not provide exactly the same name (such as company known as "Demo Deliveries", Demo Deliveries Inc.", and "Demo Delivers").  
        PolicyCenter executes name clearance to see if the named account exists. Based on the customer's business need, the end user can choose an existing account (if bound) or create a new account.
    
    [![](Dashboard/Attachments/Untitled%2034%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2034.png)
    

5. Accounts and Policies
    
    1. An account can have zero, one or many associated policies. An account having at least one policy is often referred to as "the insured".  
        An account may have many separate and distinct "insureds" aggregated within or below it as a related account. For example, General Motors could be an account with separate insureds (including Chevy, Buik, GMC, and Pontiac) and separate policies for each.
    
    [![](Dashboard/Attachments/Untitled%2035%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2035.png)
    

6. Accounts - Producers
    
    1. When you create an account in PolicyCenter, you will need to provide an **organization** and a **producer**. A **producer** is a generic term for third party who brings business to the insurer. An **organization** is what PolicyCenter users to refer to a insurer or a producer. The producer code identifies the sales agent who sold the policy. By including it during account creation, the insurer can track the agent or agency who originally opened the account. Sometimes, producers can pre-qualify an applicant. In PolicyCenter, you specify producers in the account information using a producer code, wich you enter when you create the account. A **producer code** is a unique identifier assigned by the insuere to track the agent or agency responsible for a policy or account.
    
    2. You can learn more about **organizations and producers** in the context of the PolicyCenter Community Model education offering.
    
    [![](Dashboard/Attachments/Untitled%2036%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2036.png)
    

7. Supporting Information
    
    1. PolicyCenter provides a wide range of supporting information about the Account.  
        This graphic shows several, but not all, of the types of supporting Account information. More details will be shared in the second video, Supporting Account Information. First, show how to create an account.
    
    [![](Dashboard/Attachments/Untitled%2037%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2037.png)
    

8. Questão de revisão #1
    
    Questão - What is the purpose of an account?
    
    Resposta:
    
    - Resposta correta
        
        An account gives PolicyCenter users the flexibility to create and manage a customer's account independent of policies with wich the account may be associated. The ability to manage an account separately from a policy can be useful when assigning visibility into both policies and accounts to different types of users. In addition, PolicyCenter is going through "**name clearance**" to ensure that a person or company is not an existing account and that another producer does not represent them for the given policy type.
        

9. Questão de revisão #2
    
    Questão - How many policies can fall under an account?
    
    Resposta:
    
    - Resposta correta
        
        An account to policy is a 1-0 (one account with zero policies) or 1-to-many (one account with one or more policies) relationship. (One account can have many policies).
        

10. Questão de revisão #3
    
    Questão - How many accounts can a policy bee attached to?
    
    Resposta:
    
    - Resposta correta
        
        A policy can belong to only one account.
        

---

# 4. Full Application Submission

1. Full Applications
    1. As a business analyst or configuration developer, i want to see how the PolicyCenter submission process works so that I can determine my organization's best aproach to configuration.

2. Submissions
    
    1. In a project, the user story for a typical submission is: "As a PolicyCenter user with the role of Agent, CSR, Underwriter, or Manager, I want to be able to create a new submission or quote from an account in PolicyCenter."
    
    2. In order to create a new submission, you need an account. If you are not sure how to do that, see the Accounts module.
    
    3. After you create an account and a start the new submission process, you can enter relevant information via the PolicyCenter submission wizard in order to present a policyholder with a quote. You can move forward from a quote to the binding and issuing of a policy. In this lesson, you will learn how each step looks in the PolicyCenter application, and what deatils are required to get to a quote or fully bound policy.
    
    4. There are two submission wizards: the Full Application Wizard and the Quick Quote Wizard. We focus on the Full Application Wizard in this lesson. For information about the Quick Quote Wizard, see the supplemental lessons or the PolicyCenter 9.0 documentation.
    
    [![](Dashboard/Attachments/Untitled%2038%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2038.png)
    

3. Policy submission: full application
    
    1. Before moving into the details of each step, let's take a look at the workflow for the submission process.
    
    2. A full application is the complete set of information needed to issue a policy. The "complete" set includes the product selection, the specific offering, basic policy information, coverages and modifiers for the specific line of business and finally, underwriting details related to risk analysis. After the user enters the complete set of information, they cangenerate a quote for the policyholder. If the quote is acceptable, the policy can be issued and bound. When a policy is bound, it becomes a legal contract. To reach the Bind and Issue step in this diagram, the quote must first exist.  
        Each of these steps will be covered in the demo. Any time prior to the Quote, you can edit and change details about the policy ("Modify quote" bracket).
    
    3. Multiple submissions are permitted. In the default application, you can create up to a maximum of five per line of business.
        
        [![](Dashboard/Attachments/Untitled%2039.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2039.png)
        
    

4. Questão de revisão #1
    
    Questão - Based only on the submission workflow, what is the main screen that will likely trigger an underwriting issue?
    
    Resposta:
    
    - Resposta correta
        
        Pre-Qualification is the likely screen where underwriting issues first appear. Other issues appear later in the Risk Analysis Screen (Underwriting Issues tab).
        

5. Questão de revisão #2
    
    Questão - Are multiple submissions permitted? What is the base application limit?
    
    Resposta:
    
    - Resposta correta
        
        Yes, multiple submissions are permitted. In the default application, you can create up to a maximum of five per line of business.
        

6. Questão de revisão #3
    
    Questão - Where do you configure modifier specifications?
    
    Resposta:
    
    - Resposta correta
        
        In the LOB-specifica section, there is a section dedicated to adjusting modifier specifications.
        

7. Questão de revisão #4
    
    Questão - In wich screen does an underwriter review issues raised during the submission process?
    
    Resposta:
    
    - Resposta correta
        
        Underwriters review the issues in the Risk Analysis screen, Underwriting Issues tab.
        

---

# 5. Policy Tools

1. Policy Tools
    1. "As a business analyst or configuration developer, I want to know how Policy Tools can enable my users to find out details about a policy."

2. Tools
    
    1. A **Summary** option provides concise information about the entire Policy file.
    
    2. **Billing** allows you to view overall balance and balances for individual policy periods.
    
    3. A **Contract** is a person whom the insurer may need to contact but who is not part of the policy contract (such as a billing manager for a company which has a business owner's policy).
    
    4. **Participant** is the user that manages the policy and has a role such as underwriter or producer.
    
    5. **Policy transaction** displays summary information about all policy transactions that have occured on the policy. This list includes jobs that are in-progress, withdrawn, not taken, or non-renewed.
    
    6. **Note** is a record of a user of PolicyCenter thinking or strategy when working on a policy.
    
    7. **Document** is an electronic or physical file associated to a policy (other than a form).
    
    8. **Risk Analysis** displays issues that may affect the policy. It includes underwriting issues which is a note of an issue which is relevant to the creation or renewal of a policy and may cause the carrier to deny the policy or raise the premium. It also displays claims, prior policies, or prior losses. A claim is an event in which a potentialy covered loss occurred.
    
    9. **Reinsurance** is insurance risk transferred to another insurance company for all or part of an assumed liability.
        
        [![](Dashboard/Attachments/Untitled%2040.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2040.png)
        

3. Questão de revisão #1
    
    Questão - What is the main purpose of "Tools" in PolicyCenter?
    
    Resposta:
    
    - Resposta correta
        
        The Tools menu provides an easy way to get to several important pieces of supporting information for a policy file.
        

4. Questão de revisão #2
    
    Questão - Where in the Tools would you be able to access a record of a user of PolicyCenter thinking or strategy when working on a policy?
    
    Resposta:
    
    - Resposta correta
        
        Notes.
        

5. Questão de revisão #3
    
    Questão - Which Tools option provides a way to access electronic or physical files that are associated with a policy, and not necessarily part of the contract??
    
    Resposta:
    
    - Resposta correta
        
        Documents. Note that documents are not the same as Forms.
        

---

# 6. Policy Changes and Pre-emption

1. Subtopic
    
    1. Each line of business (LOB) has its own set of user stories for working with policy changes.
    
    2. "As a business analyst or developer, I want to know how **policies changes** and **preemption** work for a specific line of business in PolicyCenter."

2. Policy Change
    1. A change transaction is also referred to as a "policy change". A "material change" is a change to a policy that affects what is covered. Policy changes involve material changes. Policy changes almost always involve a change to the policy's premium.
        
        [![](Dashboard/Attachments/Untitled%2041.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2041.png)
        

3. Edit the effective date of an unbound policy change
    
    1. It is often the case that a customer will call wanting to make a policy change and all the initial data for the change gets captured but then the effective date of the policy change needs to be modified.
    
    2. A common use case for this is changing the date on which a coverage starts for a newly acquired vehicle:  
        A customer is buying a new vehicle, and calls the insurance company to determine how much coverage for the new vehicle will cost; a policy change is started but not completed.
    
    3. They initially expect to recieve the vehicle on a certain date (for example, October 1st as shown in the creenshot bellow), so the Policy change begun for that date.  
        However, the vehicle is delayed and is not received, until next month (for example, November 1st).
    
    4. The agent would just like so simply change the effective date of the already in progress change to November 1st (01-11-yyyy).  
        Most of the time the new effective date of the policy change will be quite close to the old effective date of the policy change.
    
    [![](Dashboard/Attachments/Untitled%2042.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2042.png)
    

4. The effective date is edited on the policy change
    
    1. A user cannot change the effective date across transaction boundaries. That is, the new effective date must not cross over the effective date of any other transactions.  
        It must also be within the same policy term. For example, if the current effective date of an unbound policy change is 11-01-2016 and there was another bound policy change on this policy with and effective date of 15-11-2013, you can't change the effective date of the unbound policy change to 16-11-2013 (but you can change it to 14-11-2013).
    
    [![](Dashboard/Attachments/Untitled%2043.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2043.png)
    

5. Subtopic
    
    1. How does a preemption occur during policy changes?
    

6. Simple scenarios
    
    [![](Dashboard/Attachments/Untitled%2044.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2044.png)
    

7. Based periods
    
    [![](Dashboard/Attachments/Untitled%2045.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2045.png)
    

8. Preemptions
    
    1. In the example bellow, the submission creates a personal auto policy with car 1. Later, a change transaction adds a second car to the policy.
    
    2. However, before the transaction is bound, a second change is started which adds a truck to the policy. The "truck" change job must be based on the latest bound version. Because the "car 2" change job has not completed, the latest bound version is version A, the same version that the "car 2" job was based off of.
    
    [![](Dashboard/Attachments/Untitled%2046.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2046.png)
    

9. Preempting job
    
    [![](Dashboard/Attachments/Untitled%2047.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2047.png)
    

10. Preemption warning: Policy change
    1. When you initiate a change and another change is in progress, you are warned before the change wizard is initiated.
        
        [![](Dashboard/Attachments/Untitled%2048%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2048.png)
        

11. Preempting change
    
    1. When a change job preempts other transactions, the Policy Change Bound screen provides links to preempted transactions.
        
        [![](Dashboard/Attachments/Untitled%2049%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2049.png)
        
    
    2. When a change job is preempted, the user is alerted to this when trying to complete the preempted job.
    
    [![](Dashboard/Attachments/Untitled%2050%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2050.png)
    

12. Handling preemptions
    
    1. The comparisons are shown in a tree format for the preempted changes The "Decide Later" button makes no changes to the policy or the preempted transaction. It has the effect of simply closing the screen. In the screenshot bellow the differences are shown as a tree format comparing the Policy and the Policy Change that was bound earlier.
    
    [![](Dashboard/Attachments/Untitled%2051%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2051.png)
    

13. Applying all changes from preempting job
    
    [![](Dashboard/Attachments/Untitled%2052%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2052.png)
    

14. Questão de revisão #1
    
    Questão - For each of the following, identify whether the statement applies to submission jobs, change jobs, or both.
    
    1. It can be started manually.
    
    2. It can only be executed off of an existing policy.
    
    3. It requires you to identify the producer of record.
    
    4. It can be withdrawn.
    
    5. It can be declined.
    
    6. It requires a new quote to be generated.
    
    Resposta:
    
    - Resposta correta
        
        1. both
        
        2. change
        
        3. submission
        
        4. both
        
        5. both
        
        6. both
        

---

# 7. Renewals

1. Learner story
    1. "As a business analyst or configuration developer, I want to know how to know how to renew a policy so that I can effectively design and configure PolicyCenter's renewal process to my client's specifications."

2. Subtopic
    1. How does renewal work in PolicyCenter=

3. Renewals
    1. The discussion here covers renewals in the base application
        
        1. Creates new policy period
        
        2. May include change in coverages
        
        3. May include change in premium due to change in rates
        
        [![](Dashboard/Attachments/Untitled%2053%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2053.png)
        

4. Starting renewals
    
    1. Automatic start  
        Typically starts X days before expiration date "X" can vary based on nature of policy
    
    2. Manual Start  
        Could be because of desire to start policy earlier than X days  
        Could be because policy must change at time of renewal
    
    [![](Dashboard/Attachments/Untitled%2054%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2054.png)
    

5. Processin renewals
    
    [![](Dashboard/Attachments/Untitled%2055%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2055.png)
    

6. End results of a renewal job
    1. Definitions:
        
        1. Non-renewed: An insurer might choose to not renew a policy because the policy is considered financially unfavorable (E.G. too many claims were filed against the policy). Reneals can be highly regulated from jurisdiction to jurisdiction. There are restricions in some jurisdictions relating to non-renewal because of losses. There are also restrictions in many jurisdictions relating to rate increases on renewals in excess of a given percent. And, there are restrictions in essentially all jurisdictions relating to the insurer non-renewing without providing a specified amount of prior notice. Renewal regulation at a jurisdiction level is largely a consumer protection issue. It is focused principally on personal lines (homeowners, personal auto) and harder to place on commercial lines.
        
        2. Non taken: An insured might choose to not renew a policy because he or she found a better-priced policy elsewhere, or because the policy premium has changed (perhaps becuase of changes in the industry or because of claims made against the original policy) and the insured does not wish to pay the new premium.
        
        3. Short-term renewal (not shown): In some cases, a policy may be renewed "short term". This means that the policy is renewed but it is **not renewed for the full term** (and typically for only a small fraction of the full term).  
            One common situation where this is done involves cancellation. When a insurer cancels a policy, jurisdiction laws may stipulate that the insurer must provide a certain amount of advanced notice (say, for example, 60 days) prior to the policy being cancelled. If the insurer wants to cancel the policy but the policy is due to be renewed within the advanced notice period (say, for example, the policy is due to be renewed in 45 days), then the insurer may renew the policy for a short period of time simply to provide the appropriate amount of advanced notice (for example, 15 days).
        
        [![](Dashboard/Attachments/Untitled%2056%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2056.png)
        

7. Renewal wizard
    
    1. The renewal wizard is how users gather and display renewal information in the PolicyCenter user interface. The wizard is relevant only for renewals which are started **manually** or renewals which are **referred** to end users.
    
    [![](Dashboard/Attachments/Untitled%2057%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2057.png)
    

8. Subtopic
    1. "What is pre-renewal direction?"

9. Pre-renewal directions
    
    1. If a policy has a pre-renewal direction, you can either delete it or change it. (For example, you could delete a non-renew direction, which would mean the policy would in fact renew. Or, you could change a non-renew direction to a not taken direction.) But, you could never have two or more pre-renewal directions for a single policy.
    
    2. You cannot create pre-renewal directions for a policy period which has already been renewed.
    
    [![](Dashboard/Attachments/Untitled%2058%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2058.png)
    

10. Demo: Pre-renewal and Renewal
    
    1. Demo:
        
        1. Open a policy that you can renew Actions → Renew Policy
        
        2. You can click the Edit Policy Transaction button which makes the policy editable.
        
        3. The renewal is automatically quoted by the renewal workflow; if there are no issues blocking bind or quote then the user will be able to issue the policy and the appropriate buttons are displayed.
        
        4. Bind options for manual renewal completion (Renew, Issue Now)
        
        5. Completed renewal: If the renewal job is listed in the "Policy Terms" list, it has been completed and the status is "Renewed" or "Renewing" if the completion was Bind → Renew. If it is listed in the "Pending Policy Transactions" list, it is still in progress and the status is Renewing.
    
    2. When you choose Renew as a Bind Option, you will have to additionally choose a renewal code based on the renewal requirements. If you choose Issue Now, a dialog box will ask to confirm issuance of the policy (shown).

11. Demo: Renewal and Policy Change (optional)
    
    1. Note: This demo is not available as a self-study video in version 9.0
    
    2. If a user starts a renewal, then changes the original policy and issues it, what happens to the renewal that the user initially started? The goalin this demo is to show students that there is a later unbound renewal and that the policy change can be applied to the renewal.

12. Questão de revisão #1
    
    Questão - What are the three ways that a renewal can end?
    
    Resposta:
    
    - Resposta correta
        
        Renewed, non-renewal (when the insurer chooses not to renew the policy), not taken (when the insured chooses not to renew the policy).
        

13. Questão de revisão #2
    
    Questão - Under what two circumstances does the renewal wizard typically get used?
    
    Resposta:
    
    - Resposta correta
        
        The renewal wizard typically gets when the renewal is started manually or when the policy must be changed at renewal time.
        

14. Questão de revisão #3
    
    Questão - How many pre-renewal directions can a policy have?
    
    Resposta:
    
    - Resposta correta
        
        A policy have any number of pre-renewal directios, but there is always only one active pre-renewal renewal direction.
        

15. Questão de revisão #4
    
    Questão - When should you not create a pre-renewal diraction?
    
    Resposta:
    
    - Resposta correta
        
        You should not create a pre-renewal direction if you want to renew the policy and do not need any human review of the job while it's being executed.
        

---

# 8. Cancellation Transaction Set

1. Learner story
    1. "As a business analyst or configuration developer, I want to know how to start and process a policy cancellation, how to issue rewrites and how to reinstate a canceled policy so that I can effectivelly design and configure PolicyCenter to my client's specifications."

2. Subtopic
    1. How do I cancel a policy, and what are the consequences of cancelling a policy in PolicyCenter?

3. Cancellation transactions
    
    [![](Dashboard/Attachments/Untitled%2059%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2059.png)
    

4. Cancellations
    
    1. It is easier for the insured to cancel a policy than it is for an insurer to cancel a policy. The insurer can choose to discontinue a policy without reason. However, an insurer cannot discontinue a policy unless it can demonstrate some juts cause, such as non-payment of premiums, purposefully inaccurate information provided at the time of submission, or fraud.
    
    2. Common Business cases:  
        Insured finds a better price elsewhere.  
        Insured has not paid premium insurer cancels the policy.
    
    [![](Dashboard/Attachments/Untitled%2060%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2060.png)
    

5. Subtopic
    1. What is a reinstatement and how do I reinstate a policy using PolicyCenter?

6. Reinstatement
    
    1. Common business case: if the insurer misses a premium payment, a cancellation may occur. After the insured makes a payment, the reinstatement occurs.
    
    [![](Dashboard/Attachments/Untitled%2061%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2061.png)
    

7. Subtopic
    1. What is a rewrite and how do I rewrite a policy using PolicyCenter?

8. Rewrites
    
    1. A rewrite involves a change to a policy that is significant enough that it cannot be captured with a policy change.  
        When a mid-term rewrite is done it is generally either done for the remainder of the term or for a full new term.  
        With a full-term rewrite, the policy is flat canceled.  
        In most cases, the rewrite effective date is the same as the cancellation effective date. This is typically done when:
        1. The original policy was issued with a significant error, and the policy essentially needs to be reissued.
    
    2. In some cases, the rewrite effective date is after the cancellation effective dates. This is typically done when:
        
        1. The original policy was in force and then cancelled. It now needs to be reinstated, but the reinstatement is to be effective some time after the cancellation, indicating that there is a gap in coverage. (This type of scenario cannot be done with a reinstatement transaction because an reinstatement transaction must have the same effective date as the cancellation.)
        
        2. The original policy was in force under producer A and is now being transferred to producer B. (A policy's producer is somewhat inherent to a policy and cannot be changed through a change transaction.)
        
        [![](Dashboard/Attachments/Untitled%2062%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2062.png)
        

9. Full-term rewrite
    
    1. Cancellation must be effective on the start date of the original policy term in a situation when the policy is **flat canceled**). In case of a flat cancel, followed by a full-term rewrite, one can have the rewrite start on different effective date than the cancellation.
    
    2. A full term rewrite results in the original policy term being completely wiped out. A mid-term rewrite behaves differently.
    
    3. Find: The application Guid's "Rewrite Key Features" section discusses the differences between the two in detail.
    
    [![](Dashboard/Attachments/Untitled%2063%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2063.png)
    

10. Mid-term rewrites
    
    [![](Dashboard/Attachments/Untitled%2064%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2064.png)
    

11. Demo: Cancellation
    
    1. Demo  
        The "Cancel Policy" menu action is available only for policies that do not already have completed cancellation jobs.  
        Cancellation jobs are not always initiated manually.  
        They could be initiated automatically by a billing system. To start a cancellation job, provide 1) the cancellation source (insured or insurer), 2) The cancellation reason (drop-down), 3) The refund method (describe), 4) The effective date for the cancellation.
        
        1. Locate a policy you created to cancel.
        
        2. Actions → Cancel Policy
        
        3. Enter source and select a reason. Describe each
        
        4. The learners that the reason you select will determine the **Refund Method**, and show it change with different reasons (e.g. Criminal Conduct vs. Policy not-taken). The refund methods are outlined in the student workbook for review.  
            "**Flat**": refund all money - typically used if the policy has not yet become effective, "**pro rata**": prorate, or "**short rate**": prorate the refund and subtract processing fee.
    
    2. After you enter the required information, select **Start Cancellation**.  
        This is step 2 in two-step wizard process. You can either Schedule Cancellation or Cancel Now. The "Schedule Cancellation" option will schedule the job to be completed on the cancellation effective date. The "Cancel Now" option completes the job immediately, but the policy is still in force until the Cancellation Effective date.

12. Questão de revisão #1
    
    Questão - Cancellations and reinstatements always have the same effective date. T/F?
    
    Resposta:
    
    - Resposta correta
        
        Cancellation and reinstatement always have the same effective date.
        

13. Questão de revisão #2
    
    Questão - Can you describe a situation where why you might use a rewrite rather than a policy change?
    
    Resposta:
    
    - Resposta correta
        
        Answers vary by student knowledge. A rewrite includes such an extreme change that it is not covered by a simple policy change transaction. This might include a change the effective date of the policy or to the producer of record.
        

14. Questão de revisão #3
    
    Questão - Describe the effective date for a rewrite.
    
    Resposta:
    
    - Resposta correta
        
        The effective date for a rewrite may coincide with the cancellation date or it may be after the cancellation date.
        

---

# 9. Out-of-Sequence Transactions

1. Learner story
    1. As a p«business analyst or developer, I want to know what an out-of-sequence transaction is so that I can manage out-of-sequence conflicts in PolicyCenter.

2. Subtopic
    1. What is an out-of-sequence transaction and how does it appear in PolicyCenter?

3. Review: Policy transaction graph
    
    [![](Dashboard/Attachments/Untitled%2065%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2065.png)
    

4. Out-of-sequence transaction
    
    1. OOS transactions can introduce complexity in a policy's history because the "past" job (C in the example above) may change the policy in ways which impact the "future" jobs (such as B in the example above).
    
    [![](Dashboard/Attachments/Untitled%2066%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2066.png)
    

5. What can be out-of-sequence
    
    1. A **submission transaction** cannot be out-of-sequence because the submission creates the policy. The policy has to exist before an out-of-sequence transaction can occur.
    
    2. A renewal cannot be an out-of-sequence transaction for a similar reason. The renewal extends the policy for another term. If a renewal has not yet completed, there is no new term, and so other transactions such as changes, could only affect the current term.
    
    3. Audits cannot be done out-of-sequence because out-of-sequence because out-of-sequence audits do not have an edit effective date and do not result in modifying the policy's structure.
    
    4. While a premium report or check audit can technically be out-of-sequence to a future bound change, cancellation, reinstatement, rewrite or renewal, it is never created as an out-of-sequence transaction because it never modifies the policy's structure and no changes need to be merged. If a change is made after a final audit, the final audit is reversed.
    
    [![](Dashboard/Attachments/Untitled%2067%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2067.png)
    

6. What can be out-of-sequence transactions preced?
    
    1. A change, cancellation, reinstatement, or rewrite cannot come before a submission because there is no effective policy prior to a submission  
        A change, cancellation, reinstatement, or rewrite could come before a premium report or check audit, but it is never created as an out-of-sequence transaction because it never modifies the policy's structure and no changes need to be merged. If a change is made after a final audit, the final audit is reversed.
    
    [![](Dashboard/Attachments/Untitled%2068%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2068.png)
    

7. Preemptions vs. out-of-sequence transactions
    
    1. Preemptions and out-of-sequence transactions are similar in that they both involve two or more transactions which, in some way, are being processed in a non-serial fashion. However, it is importante to be clear on the differences.
    
    2. A **preemption** occurs when a transaction is created and, **before it is bound**, a second transaction is started. The critical issue here is that two transactions have been started from the same base period. Only one of those transactions can be bound, and when one of them is bound (when one "wins"), it will force additional work for the other transaction (the "lossing transaction"), because the base period has been changed. (For preemptions, the effective date of the second transaction is not significant. The fact that the second transaction has been started before the first transaction was bound is what is significant.)
    
    3. An out-of-sequence transaction occurs when a transaction is created and, **after it is bound**, a second transaction is started with **an earlier effective date**. The critical issue here is that the second transaction changes the nature of the policy at a point prior to the effective date of the first transaction must take into account both what the policy looks like when it becomes effective and the impact of jobs which become effective at a later date.
    
    [![](Dashboard/Attachments/Untitled%2069%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2069.png)
    

8. Subtopic
    1. What is a conflict, and how do I resolve conflits due to out-of-sequence transactions=

9. What is a conflict?
    
    [![](Dashboard/Attachments/Untitled%2070%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2070.png)
    

10. PolicyCenter merges data when no conflits are present
    
    1. If there is no single field which was changed in both transactions to different values, then there are no conflicts to resolve.  
        Changes from "effective earlier" transaction are automatically merged into "effective later" transaction.
    
    [![](Dashboard/Attachments/Untitled%2071%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2071.png)
    

11. If a conflict exists, the user decides how to proceed
    
    [![](Dashboard/Attachments/Untitled%2072%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2072.png)
    

12. Demo: Out-of-sequence transactions
    
    1. Preparation: Give an example of what makes transactions out of sequence.
    
    2. On January 1, a customer adds a new auto policy effective all year for a **redcar**. The effective date is January 1.
    
    3. Change 1: On March 1, the customer increases a specific coverage on the car to $20,000 effective to the year end. _The effective date for the cahnge is March 1._
    
    4. Change 2: On March 2, the customer calls to say that he had the car painted **blue** on February 1. _The effective date of this change is February 1._ The effective date is earlier than the effective date of the previous change. The las change in this example is out-of-sequence. Change 2 has an effective date occuring before Cahnge 1. A transaction (job) is out of sequence if its effective date is earlier than other transactions (jobs) bound on the policy for that contractual period.
    
    5. Before you begin: Go to any account and create or copy a personal auto policy for Erica Billings for one vehicle.
    
    6. Notes: In order to raise a conflict that requires resolution, you need to attempt to change the same fiel at two different points in time.
    
    7. Preparation: Using the same policy, try to change the Medical Limit liability coverage on the personal auto policy at two different points in time.

13. Questão de revisão #1
    
    Questão - What makes a transaction out-of-sequence?
    
    Resposta:
    
    - Resposta correta
        
        A transaction is out-of-sequence if it is entered after some other bound transaction bu has an effective date earlier than the effective date of that bound transaction.
        

14. Questão de revisão #2
    
    Questão - Can a submissiont be out-of-sequence? Why or why not?
    
    Resposta:
    
    - Resposta correta
        
        No, a submission can never be out-of-sequence. A submission creates a policy and therefore mus be the first transaction that can be issued against a policy. You cannot have transactions effective earlier than when the policy was created.
        

15. Questão de revisão #3
    
    Questão - Can a change be out-of-sequence? When you start an out-of-sequence transaction, how do you know that it's an out-of-sequence transaction?
    
    Resposta:
    
    - Resposta correta
        
        Yes, a change can be out-of-sequence. PolicyCenter displays an "out-of-sequence" dialog box prior to starting the wizard, and it displays a warning label at the top of the wizard screens.
        

16. Questão de revisão #4
    
    Questão - What criteria does PolicyCenter use to determine if an out-of-sequence transaction conflits with a later effective" transaction?
    
    Resposta:
    
    - Resposta correta
        
        If each transaction changes a given single field to a different value, then the two transactions are in conflict.
        

17. Questão de revisão #5
    
    Questão - If there are no conflicts, what additional work must the end user do?
    
    Resposta:
    
    - Resposta correta
        
        When there are conflicts, there is no additional work. PolicyCenter automatically merges the data from the two transactions.
        

18. Questão de revisão #6
    
    Questão - If there is at least one conflitct, what additional work must the end user do?
    
    Resposta:
    
    - Resposta correta
        
        For each conflict, the end user must identify whether or not the earlierd effective-dated value overrides the future effective-dated value in the future slice of the policy.
        

---

# 10. Users, Groups and Organizations

1. Learner story
    1. As a business analyst or configuration developer, I want to describe the **producer code security** so that I can create and manage producer codes to control data access.

2. Producers
    
    1. A producer is a person or organization that has one or more agreements to sell business on behalf of the carrier. A producer could be responsible for many, one, or zero policies.  
        In the insurance industry, producers are typically referred to as agents, brokers, or internal sales force. The carrier may hold the account directly (the insurer contacts the account directly), in which case there is no producer.  
        In some cases, a producer agency has only one code associated with it. In other cases, a carrier may want to separately track two or more different categories of policies assigned to a single producer agency will have multiple codes, and the user must select the appropriate code.
    
    [![](Dashboard/Attachments/Untitled%2073%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2073.png)
    

3. Internal and external producers
    
    [![](Dashboard/Attachments/Untitled%2074%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2074.png)
    

4. Producer types
    
    1. **Producer of record** is the one that created the policy. The producer of record may or may not service the account and have limited permissions on the policy and account. For a new policy, producer of record is the same as producer of service as shown in the example above.  
        If for some reason user decides they don't like the agent and want a new one, then the producer of service changes. Producer that provides this new service is the **producer of service.** The old agent continues to get commission for the policy because he was the producer of record, the one that brought the business initially.  
        This can be reviewed on the Policy Info page by typing the effective date in any policy.  
        A producer of service has permissions to edit policies for renewal and then becomes producer of record and can receive commissions.
    
    [![](Dashboard/Attachments/Untitled%2075%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2075.png)
    

5. Producer code
    
    1. Producer code is used to be able to accurately track which agent or agency is responsible for which policies and accounts. In some cases, a producer agency has only one code associated with it. In other cases, a carrier may want to separately track two or more different categories of policies assigned to a single producer. In this case, the producer agency will have multiple codes, and the user must select the appropriate code. Carriers may think of producer codes as fallowing their organization or group hierarchy, so assigning product codes to groups eases administration duties.
    
    [![](Dashboard/Attachments/Untitled%2076%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2076.png)
    

6. Subtopic
    1. What is producer code security?

7. Securirty in PolicyCenter
    
    1. Security in PolicyCenter makes the application flexible, robust, and keeps your information protected. The PolicyCenter default application contains a set of roles that perform the policy tasks in most organizations. In order to perform these tasks, a user must be assigned a role with the appropriate permissions. Typically in the base configuration, the Superuser role is granted all permissions and is responsible for granting permissions to other roles. Once the roles are configured, then each PolicyCenter user is assigned a specific role that relates to the tasks to be performed.  
        Note: Although in the base configuration, Superuser has all permissions, but that could change if a customer adds custom permissions. Also, Superuser is configured in the base product as the role that would grant permissions to other roles, but a customer could configure any role to do that.
    
    [![](Dashboard/Attachments/Untitled%2077%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2077.png)
    

8. Types of Security
    
    1. Security in PolicyCenter makes the application flexible, robust, and keeps your information protected.  
        Please refer to the Roles and Permissions lesson for more details for Role-Based security.
    
    [![](Dashboard/Attachments/Untitled%2078%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2078.png)
    

9. Producer code Security
    
    1. Restrictions can be placed upon access through producer code security beyond just the permissions associated with the matching producer code.  
        For a producer, the producer code security would typically be turned on, but for underwriters or auditors it may be off, thus allowing them to work on any policy. You can think of producer codes as an agreement between the producer and the carrier determining exactly what a producer can do. Attaching permissions to producer codes and attaching producer codes to users allows a carrier to:
        
        1. Further customize what a producer can do
        
        2. Track the performance of a producer
        
        3. Tie the producer to a specific organization or region
    
    2. Users inherit the producer codes through their group, and do not need to have producer codes assigned explicitly.
    
    [![](Dashboard/Attachments/Untitled%2079%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2079.png)
    

10. Prevent producer code misuse - Status field
    
    1. Both the status of the matching producer code and the status of the user's organization must be checked before allowing access through producer code security. Both statuses must either be **Active** or on the list of allowed statuses in the permission handler. Without any configuration to the security handlers, full permissions are granted when the status is **Active**. No permissions are allowed when the status is anything else, except for Renewals, which allow for **Limited** status.  
        Producer codes are used for the account security checks in the absence of any policies or submissions.
    
    2. To configure which permissions are allowed when the status of the producer code or agency is other than **Active**, refer to the Permissions lesson set in the further study modules or the PolicyCenter Configuration Guide.
    
    [![](Dashboard/Attachments/Untitled%2080%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2080.png)
    

11. Subtopic
    1. As a business analyst or configuration developer, I want to describe the **users, groups and organizations** so that I can manage them efficiently in PolicyCenter.

12. Users
    
    1. Each policy is usually managed by several users.
    
    2. Every user assigned to a policy has a role on that policy, such as underwriter, customer service representative, or producer.
    
    3. a user can:
        
        1. perform policy transactions or look up the status of a policy
        
        2. manage activities, assignment rules, notes, attached documents, history, team views and more
        
        3. belong to one or more groups
        
        [![](Dashboard/Attachments/Untitled%2081%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2081.png)
        

13. User categories
    
    1. Typically, the user belongs to at least one group that represents the actual reporting relationship found in the company's organizational chart. This is the main group that the user works in and the supervisor that the user normally reports to. User can belong to an unlimited number of groups or need not belong to any group.
    
    2. Captive agents are sometimes internal but they will often be external users because they are often not actually employees of the carrier, they just have an exclusive contract to do business with that carrier. So they'll often get modeled as external users. In other cases, they will, in fact, be employees and so would get modeled as internal users. You can also have internal users who are CSRs or something equivalent who are not agents, but are selling policies through a call center and might be using producer codes.
    
    [![](Dashboard/Attachments/Untitled%2082%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2082.png)
    

14. Groups
    
    1. Administrators create groups based on:
        
        1. geographical regions
        
        2. divisions and
        
        3. departments
    
    2. Each group can also contain sub-groups which have their own users and producer codes etc.
    
    3. Users can belong to one or more groups.
    
    4. Group membership influences several PolicyCenter aspects of functionality. For example, once a policy is assigned to a group, the assignment engine can automatically assign it to one of the users in the group using the round robin selection.
    
    [![](Dashboard/Attachments/Untitled%2083%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2083.png)
    

15. Organization / Community model
    
    1. PolicyCenter needs to maintain information about how you organize people and their work. In many cases, you can edit this information within the PolicyCenter administration screens.  
        Users, groups and producer codes all belong to one organization. Organization can be the organization of the carrier or an external organization, such as an agency. Organization has groups within it. A users can be assinged to any number of these groups. Producer codes can be assigned to groups or directly to users in an organization.
    
    2. Users have a list of producer codes that have been allowed for them, either explicitly, or through on of the groups to which the user is assigned.
    
    3. Internal users, groups, organizations, and permissions, as well as external, can have producer codes assigned to them.
    
    4. External users may only have producer codes from their organization assigned to them, but internal users may have any external producer codes assigned explicitly to them.
    
    [![](Dashboard/Attachments/Untitled%2084%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2084.png)
    

16. Subtopic
    1. How to work with users, groups, organization and producer codes?

17. Managing producer code
    
    1. One should have superuser or seradmin privileges to manage producer codes, users, groups and organizations.
    
    2. **Search:**
        1. To search for a user, group or an organization click on similar links. After searching the results are displayed as links so the user can view the entity details by clicking on it.
    
    3. View or edit producer code:
        
        1. The Basics tab lists the code, description, organization, status and other info related to the producer code.
        
        2. The Groups tab lists the groups that have this producer code security. This defines what the users within these groups can access and what actions they can perform.
        
        3. The Users tab lists the users that have access to this producer code. These users belong to one of the groups listed under the Groups tab. Carriers may thinkof producer codes as following their organization or group hierarchy, so assigning product codes to groups eases administration duties.
        
        4. The Roles tab lists the roles assigned to the producer code.  
            The producer code can be added to users and groups using the Edits Users or Edit Groups administration screens respectively. The producer codes details get updated.
    
    4. Create new producer codes:
        
        1. Enter basic details of the producer code such as code, description, organization and parent code, etc. The Search icon when available provides a list to choose from, for example, the Organization takes user to the Organization Search page to search for organizations.
        
        [![](Dashboard/Attachments/Untitled%2085%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2085.png)
        

18. Managing users
    
    1. Administrators define users, giving them membership in groups, roles, credentials, etc...  
        Both the Team tab and the Administration tab contain User Profile screens that allow administrators to define and edit these characteristics.  
        User information can be viewed and managed in the Administration Tab. Users can use the left sidebar links to search or edit users, groups, organizations, regions, or producer codes.  
        They can view, edit or create roles (this is discussed in detail in Permissions lesson). They can also define attributes that the system can use for making assignment decisions.
    
    2. When you create an external user, the fields and available values in the **User** sub-tabs change. External users must be associated with an **Organization**. The tree browser (as seen on the **Administration** tab) will always show the home organization of the user (either internal or external).
    
    3. Typically, the user belongs to at least on group that represents the actual reporting relationship found in the company's organizational chart. This is the main group that the user works in and the supervisor that the user normally reports to. Users can belong to an unlimited number of groups or need not belong to any group.
    
    4. An external user cannot view or edit internal user or their organization details.  
        Access is controlled through roles and producer codes.
    
    [![](Dashboard/Attachments/Untitled%2086%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2086.png)
    

19. User details - Access (for producers)
    
    1. **Groups:  
        **The Groups lists which groups the user belongs to, if the user is a member, whether the user is a Manager, load factor permissions and the load factor within that group. This is useful for activity assignment using assignment rules. One can click on a group name which is a link and open the Groups screen. Groups can be configured through that screen. Groups are discussed in detail later in this lesson.
    
    2. **Producer Codes from Groups:**
        
        1. The users automatically get all the producer codes assigned to their groups.
        
        2. A user can create collections of permissions as roles and attach them to producer codes. The producer codes can then be assigned to users, to policies, or to accounts.
        
        3. Users for whom Producer Code Security is set to Yes can only use their role permissions against policies that have a producer code matching one of their own producer codes. Only the permissions assigned to the producer code that matches can be used against that policy, even if the user has a larger set of permissions available through user roles.
        
        4. Both producer code role permissions and user role permissions must match in order for the user to gain access.
        
        5. **Additional Producer Codes:**
        
        6. Users can add producer codes through this option.
        
        7. External producer users can have producer codes from their own organization/groups added to them only. But internal users who have their producer code security turned on can have producer codes from any organization added to them.
        
        8. In insurance companies, a lot of different policies exist, each with different producers to see information on different policies. Similarly, in an agency, one group does not need to see policies in other groups within the organization.  
            For example, an agent in San Francisco should not be able to look at the policies of an agent in San Diego.
        
        [![](Dashboard/Attachments/Untitled%2087%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2087.png)
        

20. Managin groups
    
    1. User should have admin privileges to view the groups using **Administration** tab.
    
    2. The bellow image shows the producer codes in the group Eastern Mid-West Region.
    
    3. The producer codes tab shows all producer codes available to the parent group, which can be made available to the current group. All users in this group can use the producer codes available to the group. This is not implicit, a user has to be granted access to producer codes and groups through the Access tab on the user.
    
    [![](Dashboard/Attachments/Untitled%2088%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2088.png)
    

21. Managing organizations
    
    1. An organization can be the carrier's organization or an external organization, such as an agency. The tree structure of organization and the groups within it are displayed in the left sidebar.
    
    2. The _**Basics**_ card displays the Organization info like its name, type, address, supervisor and so on. The load factor used by assignment rules to assign an activity to a user or group within this organization is also displayed here.
    
    3. The _**Users**_ card on the screen lists users under that organization.
    
    4. The _**Producer Codes**_ card displays the producer codes and a list view of description, status, branch, and the preferred underwriter for each code.
    
    [![](Dashboard/Attachments/Untitled%2089%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2089.png)
    

22. Delegate management using User Admin role
    
    1. Because managing both the internal company and the external company can become quite complex, you can delegate management of external producer companies to a designated external **User Admin**. This can be done by assigning the **User Admin** role to a user within that external organization. That user will have permission to administer Users, Groups, Organizations, and Permissions within the user's organization, but will not have access to other organizations.
    
    2. Delegating allows a **User Admin** to build the set of Users, Groups, Organizations, and Permissions that represent an external company. Even though you can delegate administration of these external companies, you still have access and complete administrative rights from the **Administration** tab.
    
    3. The difference between a Supervisor and a User Admin is that a Supervisor has access to the Team screen related to a group whereas the User Admin has the ability to manage Users, Groups, Organizations, and Permissions. Alsothere is no limit on the number of User Admins in a Organization. Roles are discussed later in this lesson.
    
    [![](Dashboard/Attachments/Untitled%2090%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2090.png)
    

23. Learner story
    1. As a business analyst or configuration developer, I want to describe the team tab so that I can view details within a group when logged in as a supervisor or manager.

24. Team tab
    
    1. Supervisor and managers can manage their teams, obtain status information, monitor caseloads, identify backlogs, and reassign activities on the Team tab. In some respects, team management is a reporting tool, where you can see summaries of a group's workload. You can then can drill down to view and manage the workload of a team member. The reporting categories for workloads are: **Activities, Submissions, Renewals,** and **Other Policy Transactions.**
    
    2. The **Team** screens show the job workload for groups or individual users.
    
    3. The **Team** screen determines whether a user has work to do on a job depending upon the role of the user or whether an activity is assigned to the user.  
        All the tabs display statistics for the current week in base configuration. Batch processes are run at scheduled time intervals based on configurations set in config.xml. The parameters that set the time window used to calculate user statistics are also set in config.xml.  
        Configuration users can configure config.xml using Guidewire Studio.
    
    4. The **Misassigned** category contains jobs and ativities assigned to the group under which the node appears, but it was assigned to an invalid user. An invalid user is someone who is no longer a member of the group. Perhaps the user switched groups or retired. Misassigned jobs or activities can appear when a user leaves the group or company and his or her activities/jobs need to be reassigned.
    
    5. Activities and jobs can be mass reassigned. For example, an underwriter is leaving and all his jobs can be reassigned to someone else.
    
    [![](Dashboard/Attachments/Untitled%2091%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2091.png)
    

25. User categories
    
    1. **By Role -** These users work on jobs when they have a participating role. A customer service representative (CSR) is an example of a by role user.  
        The CSR makes sure that the job progresses. The CSR may not have any activities associated with the job. So when the By Role button is clicked, the **Team** screen displays jobs on which the user is a participant.
    
    2. **By Activity** - These users work on jobs when they are assigned to an activity on the job. An underwriter is an example of a _by activity_ user. For example, one underwriter may be assigned on the large number of policies generated by a group of CSRs. In this sense, an underwriter may participate in thousands of jobs but they do not have to take action on each policy. Only when an activity is explicitly assgined to them do they have to perform a task.  
        Similarly, for a personal lines which renew every six months, a third renew every six months, a third or more of the policies may have an active renewal in process at any time. Each renewal is assigned an underwriter even if the renewal is expected to complete automatically without intervention. These renewal jobs do not represent work for the underwriter unless a job requires some action. An activity makes the underwriter aware that work is required on the job. So when the By Activity button is clicked, the **Team** screen displays jobs on which the user has an activity.
    
    3. The addition of user categories of activity or role allows users to better focus on the jobs for which they need to take action. For example, underwriter, just the ones for which they have an activity.  
        Renewal jobs are an exception. The **Team** screen displays renewal jobs _by_ _activity_ for both categories of users.  
        On **Summary** screen, you can view jobs **By Role** or **By Activity**. The default viw is **By Role.**
    
    [![](Dashboard/Attachments/Untitled%2092%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2092.png)
    

26. Reporting icons and their meanings
    
    [![](Dashboard/Attachments/Untitled%2093%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2093.png)
    

27. Questão de revisão #1
    
    Questão - What is a producer code? What does it identify?
    
    Resposta:
    
    - Resposta correta
        
        A producer code is a unique ID (alphanumeric) assigned by the carrier to determine what a producer can do. Producer code and its description identify the sales office that sold the policy.
        

28. Questão de revisão #2
    
    Questão - What is an organization?
    
    Resposta:
    
    - Resposta correta
        
        An organization is a business entity which represents either the Carrier itself or an external company for any set of PC users, typically producers.
        

29. Questão de revisão #3
    
    Questão - State true or false:
    
    An internal user could be assigned any producer code for any organization.
    
    Resposta:
    
    - Resposta correta
        
        True
        

---

# 11. Activities

1. Learner Story
    1. As a business analyst or configuration developer, I want to know what activities are and how to add an activity in PolicyCenter.

2. Subtopic
    
    1. What is an activity, who uses them and how do they work?
    
    2. PolicyCenter allows users to create new activity patterns of type General only. There are a few activities of type Underwriter Review in the base configuration.
    
    3. Underwriter Review type of activities can be created by clicking the Request Approval button when a CSR or person creating the policy feels that an underwriter should review this UW issue raised on the Risk Analysis page and the policy is locked. Once the issue is reviewed by an underwriter the activity is completed and another activity is sent back to the original requestor and the lock is released and the job can progress.

3. Activities
    
    1. An Activity represents a task that someone to which someone must attend or an issue about which someone should be aware. Activities are associated with accounts.  
        They can also be associated with a transaction, or a policy. Both transactions and policies are associated with accounts.
    
    2. Activities can:
        
        1. Let processes and users assign work to users
        
        2. Alert users to certain events
        
        3. Manage how policy jobs are completed
        
        [![](Dashboard/Attachments/Untitled%2094%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2094.png)
        

4. Activities: Applications
    
    1. In manual assignments, the user (or code) that creates activity explicitly chooses owner.
    
    2. In automatic assignments, assignment logic evaluates acivity and selects owner
    
    [![](Dashboard/Attachments/Untitled%2095%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2095.png)
    

5. Subtopic
    1. How can i view activities from the Desktop tab?

6. View activities in the Desktop
    1. Clicking activity subject:
        
        1. Displays associated parent in screen area Opens activity in workspace frame
        
        [![](Dashboard/Attachments/Untitled%2096%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2096.png)
        

7. Subtopic
    1. What is an activity pattern and how does it influence activities in PolicyCenter?

8. Activity patterns
    
    1. An Activity pattern is a template that standardizes the way PolicyCenter creates activities. The activity pattern specifies details about an activity.
    
    2. The details include:  
        Subject, priority, number of days until due, among others. Activities follow the specified activity pattern.
    
    3. Managers have the ability to create and modify activity patterns on the Administration tab in the PolicyCenter user interface.
    
    4. Configuration users can configure the data model to add fields to the activity pattern entity. When a field is added to the activity pattern entity, it is available on all activity patterns. For example, a given carrier might want to add a "Required Role" field which is used to identify the role a person must have in order to have this type of activity assigned to them.
    
    [![](Dashboard/Attachments/Untitled%2097%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2097.png)
    

9. Activity lifecycle
    
    1. After PolicyCenter creates an activity, the activity goes through as many as five stages.
    
    2. Initially, the activity is in progress and it is "new or updated". Any activity which has been newly assigned to you (or which has been modified by another user since the last time you viewed it) has a star icon in the first column.
        
        [![](Dashboard/Attachments/Untitled%2098%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2098.png)
        
    
    3. After you view an activity assigned to you, it is in progress as any normal activity. Viewing a "new or updated" activity causes the star to disappear. An activity which is in progress (and is "normal") has no special visual designation.
        
        [![](Dashboard/Attachments/Untitled%2099%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%2099.png)
        
    
    4. Every activity has a due date and an escalation date. When the due date passes, the activity is overdue. The due date now appears in red.
        
        [![](Dashboard/Attachments/Untitled%20100%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20100.png)
        
    
    5. When the escalation date passes, the activity is escalated. An escalated activity appears with the escalation icon (an activity with an exclamation symbol in the upper left corner) in the second column.
        
        [![](Dashboard/Attachments/Untitled%20101%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20101.png)
        
    
    6. At any point, an activity can be closed. There are two ways you can close an activity. You can complete it (which means the work is done), or you can skip it (which means the work has not been done but is now irrelevant). When an activity is closed, it no longer appears in any activities list unless the filtering criteria specifically includes closed activities.
    
    [![](Dashboard/Attachments/Untitled%20102%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20102.png)
    

10. Types of activities in PolicyCenter
    
    1. PolicyCenter allows users to create new activity patterns of type General only. There are a few activities of type Underwriter Review in the base configuration.
        
        [![](Dashboard/Attachments/Untitled%20103%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20103.png)
        
    
    2. Underwriter Review type of activities can be created by clicking the Request Approval button when a CSR or person creating the policy feels that an underwriter should review this UW issue raised on the Risk Analysis page and the policy is locked. Once the issue is reviewed by an underwriter the activity is completed and another activity is sent back to the original requestor and the lock is released and the job can progress.
    
    [![](Dashboard/Attachments/Untitled%20104%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20104.png)
    

11. Activity ownership: explicit and implicit
    
    1. An activity can be assigned to a user explicitly or implicitly.
    
    2. When an activity is explicitly assigned to a user, that user is either chosen bu the user who created the activity or by the routing rules. Changes to any job or account will not affect the ownership of the activity.
    
    3. When an activity is implicitly assigned to a user, it is actually assigned to a specific role on a job or account (such as the underwriter for Big Lake Bakery). The activity is "owned" by the user who has that role (which, in the example above, is Alice Applegate). But, if that role is later reassigned to another user, then all activities which were assigned via roles will be reassigned to that user. (So in the example abose, if the role of underwriter for Big Lake Bakery is later reassigned to Bob Baker, then the second activity will also be reassigned to Bob Baker. Alice owned the second activity only be virtue of being the underwriter for the Big Lake Bakery account.)
    
    [![](Dashboard/Attachments/Untitled%20105%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20105.png)
    

12. Subtopic
    1. What is an activity queue?

13. Queues
    
    1. A **queue** is a repository associated to a group which contains activities assigned to the group but not to any user in that group. Users in group can take ownership of activities in queue.
    
    2. From the Desktop, navigate to **My Queue**. To assign an activity to yoursefl, click **Assign Next to Me**.  
        The user must have the **Get next activity from queue** (actquenext) permission. In the base donfiguration, the underwriter role has this permission.
    
    [![](Dashboard/Attachments/Untitled%20106%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20106.png)
    

14. What can you do with activities
    
    1. Activities can be skipped only if they are not mandatory.
    
    [![](Dashboard/Attachments/Untitled%20107%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20107.png)
    

15. Demo: Activity Patterns and Creating and Working with Activities
    
    1. Navigate to parent object: **account, transaction or policy**
    
    2. Select appropriate **activity pattern**
    
    3. Specify additional information:
        1. Enter values for Subject, Description, Due Date, and so on Assign the activity (a queue might be a good example)
    
    4. Show learners where to find queued activities, and how to assign activities from a queue
    
    5. When complete, show learners where you find the activities (Summary)
    
    6. Show learners where to find Activity Details
    
    7. Also, demonstrate Activity Patterns

16. Questão de revisão #1
    
    Questão - Give one example of how an activity can help users manage their work.
    
    Resposta:
    
    - Resposta correta
        
        Assign work to a user, alert users to certain events, manage how policy jobs are completed.
        

17. Questão de revisão #2
    
    Questão - What business objects can have an associated activity?
    
    Resposta:
    
    - Resposta correta
        
        Accounts, policies and transactions (jobs).
        

18. Questão de revisão #3
    
    Questão - What is an activity pattern?
    
    Resposta:
    
    - Resposta correta
        
        An activity pattern is a description of how to create a specific activity.
        

19. Questão de revisão #4
    
    Questão - Is an activity always assigned to a group? A user?
    
    Resposta:
    
    - Resposta correta
        
        Activities can be assigned to users, groups or queues. Also, a user is assigned to a group, and a queue also contains activities assigned to a group.
        

20. Questão de revisão #5
    
    Questão - Who can modify an activity?
    
    Resposta:
    
    - Resposta correta
        
        The **activity owner** and anyone with **manager permissions**.
        

---

# 12. Contingencies

1. Learner story
    1. As a business analyst or configuration developer, I want to know **what a contigency is so that I can apply it accordingly to policies that are both issued or not yet issued.**

2. Subtopic
    1. What is a contigency and how do I add it to a policy?

3. Contingencies
    1. There are times when a policy is issued, but the issuance is dependent on the delivery of another piece of information. For example, even if you issue a policy with a good driver discount, you still need to get a copy of the student's report card. PolicyCenter has an option called "Contigencies" which give the user a chance to attach documents related to contigent issuance.  
        Contigency-related documents can be added to policies that are issued or not yet issued.  
        Contigencies are part of the policy, but provide a specific place where you can attach contigency-related information.
        
        [![](Dashboard/Attachments/Untitled%20108%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20108.png)
        

4. Subtopic
    1. How do I associate information with a contigency?

5. Demo: Add a Contingency and include Notes, Documents and Activities
    
    1. Demo: Add a contigency
        
        1. Go to a policy that is not yet issued (you may have to create one).
        
        2. In the Risk Analysis section, you can add a contigency-related document under the tab **Contigencies**
        
        3. Select **Add Contigency** and add a contigency for the policy. The specific contigency depends on the LOB.
    
    2. **OTHER:**
        
        1. In the **New Contigency** screen, give the Contingency a meaningful name and description.
        
        2. After that, you can choose a specific action to take on the Due Date (which you also need to enter). the Actions start a transaction that ranges from changing the policy in some way, cancelling and rewriting the policy. These actions are configurable.
        
        3. For the base configuration, the Actions have pre-configured action start dates and effective dates.  
            after you create the contigency throughout each screen of the submission. To access the newly created contigency, select the contigency. This takes you to a contigency page.
        
        4. Show students the options for contigencies that exist (notes, document additions and acitivties). In addition to being able to resolve or waive the contigency in this screen, there are several options that give you the ability to add details about the contigency to the submission. If configured in PolicyCenter, these notes, documents, and activities may be related to other entities.
            
            1. Notes: You can add a note to the contigency just as you would add a Note to a policy or account.
            
            2. Documents: You can add a document to the contigency just as you would add a note to a policy or account.
            
            3. Activities: You can add an activity to the contigency.
    
    3. Describe the process of **Resolving** a contigency. After resolving the contigency, you can see the status, resolved, on the contigency screen, along with the completion date, due date and potential action, The details also include the user who first added the contigency.

6. Questão de revisão #1
    
    Questão - Describe a business situation that calls for a contigency. Draw upon your industry experience as you come up with ideas.
    
    Resposta:
    
    - Resposta correta
        
        Answers vary by audience, but the most common answer is getting a student report card to offer a discount on a personal auto policy.
        

7. Questão de revisão #2
    
    Questão - Can you add extra information to a Contigency? Give one or more examples.
    
    Resposta:
    
    - Resposta correta
        
        Yes. You can add Notes, Documents and Activities to a Contigency.
        

8. Questão de revisão #3
    
    Questão - Give one or more examples of appropriate actions related to a contigency.
    
    Resposta:
    
    - Resposta correta
        
        Changing the policy in some way, cancelling the policy, or canceling and rewriting the policy.
        

---

# 13. Forms

1. Learner story
    1. As a business analyst or configuration developer, I want to know what forms and form patterns are so that I can set up PolicyCenter to add forms to policies.

2. Subtopic
    1. What is a form and how do you add it to a policy?

3. What is a form?
    1. Examples of forms:
        
        1. **Declaration sheets** - A declaration sheet is an index or summary of all exposures, coverages, and in some cases forms.
        
        2. **Base forms** - These forms get attached regardless of what coverages or exposure units are selected. They have language defining, from a legal perspective, who is the insured, who is the insurer and so on.  
            They typically have a set of standard coverages which additional forms will either amend or remove.
        
        3. **Additional coverage forms** - These forms add additional coverage. (For example, a "Hired Auto Coverage Form" might add hired auto coverage to a base form that didn't originally specify this.)
        
        4. **Exclusion forms** - These forms limit coverages. (For example, a "Mold and Fungues Exclusion Form" might limit coverage on a homeowner's policy such that damage due to mold and gfungus was not covered or covered only to a certain amount.)
        
        5. **Manuscript forms** - These forms are blank forms with space for free form text where the carrier can type one off legal terms for the policy.
        
        [![](Dashboard/Attachments/Untitled%20109%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20109.png)
        

4. Adding forms to policy transactions
    
    1. When PolicyCenter issues a policy, it sends information to the **document management system** about forms to be created. Forms document the policy and they could be electronic, not printed. Sometimes document management system create electronic forms, such as PDFs, and email them, rather than always physically priting the forms.
    
    [![](Dashboard/Attachments/Untitled%20110%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20110.png)
    

5. When can a form appear on a policy?
    
    1. Examples of transactions when a form might be incorporated in a policy include, but are not limited to, submissions, policy changes or renewals. These are three examples.
    
    2. Note: during audit transactions, the forms are not added to the policy file.
    
    3. The **Forms** appear on the policy after the policy is quoted or bound. The Forms option is grayed out unless the policy has been quoted or quoted and bound.
    
    [![](Dashboard/Attachments/Untitled%20111%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20111.png)
    

6. Forms inference
    
    1. PolicyCenter generates forms based on details that the user has entered. Users specify coverages, exclusions and other details that give PolicyCenter the information it needs to run **forms inference logic.**
    
    2. Some insurers manually add forms by configuring coverages, exclusions or conditions in the product model or by adding entities to the period (e.g. drivers or insurers). After the policy is bound, the list of forms may be different from the preview that you see before the policy is bound.
        
        [![](Dashboard/Attachments/Untitled%20112%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20112.png)
        
    
    3. The list may be different because the information to accurately infer some forms is available only at binding time. When the policy is issued, your integration code sends a form description to an external system, which prints the forms on paper or in an electronic format.
        
        [![](Dashboard/Attachments/Untitled%20113%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20113.png)
        
    
    4. The basic definition for forms is in the Administration section.
    
    5. Custom inference logic can be added in Studio, and configuration developers can find details about which classes to customize in the PolicyCenter documentation.
    
    [![](Dashboard/Attachments/Untitled%20114%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20114.png)
    

7. When are forms inferred (generic form inference*)?
    
    - Common inference conditions can be defined directly in the Inference tab. Generic form inference means the definitions for form inference are located in the class:  
        gw.forms.FormInferenceEngine
    
    1. The user has control over the conditions for initially including the form and updating the form mid-term.  
        If a policy changes, then new forms are generated, and the previous forms are invalidated.
    
    2. Configuration users can define complicated inference behavior in custom inference classes using Guidewire Studio. If there's a custom inference class specified for a form pattern code, then generic inference cannot be used for that form pattern.
    
    [![](Dashboard/Attachments/Untitled%20115%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20115.png)
    

8. Subtopic
    1. How is a form different from a document?

9. Document / Form
    
    1. A document in PolicyCenter is any electronic file (such as a PDF, Word or Email document) which contains information relevant to a policy or account. A form is part of the policy, electronic (though printable), and contains **legal information** about the policy. PolicyCenter automatically "infers" the necessary forms needed on the policy when you click Quote or Bind.
    
    2. Forms are published with a bound policy. Forms are **automatically added** using the **inference engine**. The inference engine "decides" if the form is needed for the policy. Policy Center **does not store** the form's content.
    
    3. PolicyCenter adds a form automatically to the policy by using special "inference" business logic.  
        PolicyCenter will publish the form with the final bound policy.  
        PolicyCenter generated the form using a **form pattern** (a form "template").
    
    [![](Dashboard/Attachments/Untitled%20116%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20116.png)
    

10. Document creation using forms and document templates
    1. Outside of a transaction:
        
        1. Both **forms and document template** can initiate the creation of a _document_ within the document management system. The document management system can upload the document to PolicyCenter, or PolicyCenter can contain a reference to that document.
        
        [![](Dashboard/Attachments/Untitled%20117%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20117.png)
        

11. Subtopic
    1. What is a form pattern?

12. Form pattern
    
    1. Users can define form patterns using the Add button if they have the appropriate permissions.  
        As PolicyCenter creates an instance of a policy, it conditionally adds forms defined by form patterns for that product.
    
    [![](Dashboard/Attachments/Untitled%20118%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20118.png)
    

13. Form pattern definition
    1. Business users can configure forms in the user interface.  
        In order to access the form administration user interface, users must log in as a user with the appropriate permissions are required to work with form configuration:
        
        1. **formpatcreate:  
            **permission to create new form patterns
        
        2. **formpatview:  
            **permission to access the forms editor and view existing form patterns
        
        3. **formpatedit:  
            **permission to edit existing form patterns
        
        4. **formpatdelete:  
            **permission to delete existing form patterns
        
        [![](Dashboard/Attachments/Untitled%20119%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20119.png)
        

14. Subtopic
    1. What is an endorsement and how do I represent it with a form in PolicyCenter?

15. Endorsements
    1. An **endorsement** refers to a form that is added to the policy contract in addition to the base forms. Endorsements are commonly characterized in PolicyCenter as _additional coverage forms_. An endorsement form does not have to be associated with a coverage pattern, and can be added without a coverage pattern. You can identify an endorsement using an endorsement number, which is defined in the form pattern.
        
        [![](Dashboard/Attachments/Untitled%20120%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20120.png)
        

16. Endorsement number
    
    1. Endorsement numbers provide a way to keep forms distinguishable.
    
    2. Endorsement numbering starts at 1 for the first contract form on the policy.  
        The endorsement numbers apply within a policy period and are reset to start at 1 on a renewal or a rewrite. Each additional contract form is numbered sequentially after the first form.
    
    [![](Dashboard/Attachments/Untitled%20121%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20121.png)
    

17. Demo: Forms and Form Patterns
    
    1. Users can define form patterns using the Add button if they have the appropriate permissions.  
        As PolicyCenter creates an instance of a policy, it conditionally adds forms defined by form patterns for that product.
    
    2. Users can search for a form that exists by entering the form number, form name or Group Code in the respective fields. Then click on Search button. This returns the forms that match the search criteria.
    
    3. Duplicate and Delete buttons are available when users select a form to delete or create a copy of the form. The product filter is available to filter the form patterns by product.  
        The from administration PCFs use permissions to control the availability of various parts of the forms UI. For example, if a user does not have the formpatdelete permission, the buttons for deleting a FormPatten will be hidden and they won't be able to delete anything.

18. Subtopic
    1. How do coverages trigger endorsements in PolicyCenter?

19. Triggering from coverages
    
    1. Forms that are applicable to a single state or set of states typically can be added only for policies where the account's base state is in one of the given states, or where a location-based exposure unit is in one of the given states. For example, an account in Kentucky with a covered warehouse in Tennessee would have access to the "Privacy Policy - Kentucky" form, but not to a "Privacy Policy - Illinois" form.
    
    2. Some forms are applicable for all lines of business and/or for all states. For example, a "Hired Auto Exclusions" form might be appropriate for all business auto policies, regardless of the states involved.
    
    [![](Dashboard/Attachments/Untitled%20122%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20122.png)
    

20. Subtopic
    1. What is a multi-form and when do I use it?

21. Triggering from coverages
    
    1. How to represent where a Coverage triggers an Endorsement but only under certain circumstances
        1. Example: Different States have different requirements to handle coverages some states will endorse a policy others don't.
    
    2. How to represent cases where a Coverage term triggers an Endorsement
        1. Example: when endorsement allows extended coverage - there are a couple of ways we can implement this specific limits trigger an Endorsement (higher limits)
    
    3. Forms that are applicable to a single line of business can be added only for policies created from the applicable product. For example, a business owners submission would have access to the "Limitation of Coverages for Properties on Landfill"form, but a business auto submission would not.
    
    [![](Dashboard/Attachments/Untitled%20123%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20123.png)
    

22. Form multiplicity
    
    1. Some business cases may require multiple instances of the same form. For example, a personal auto policy with multiple vehicles may require multiple instances of a single form for each vehicle. PolicyCenter supports **form multiplicity**, but it does require configuration, wich is documented in the PolicyCenter documentation in the Integration Guide.
    
    [![](Dashboard/Attachments/Untitled%20124%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20124.png)
    

23. Subtopic
    1. What do I do if I have a new edition of a form?

24. New editions and expiring forms
    
    1. There are times when a new edition of a form must be added.
        
        1. New jobs expire the old form and replace with a new edition
        
        2. Date changes require a new edition
    
    2. During a policy change, PolicyCenter must determine wether a version of the reissued form is already present. If it is, it must determine whether the data on the old version of the form is the same as the new version of the form.
    
    3. If a previous version of a form exists and the form pattern is no longer inferred by the current date, then PolicyCenter will **set the removal data** on the previous version (ignores during processing) and will add a new form if it is inferred to be added (according to the form pattern).
    
    4. If a previous version of a form exists and PolicyCenter infers a form with different data from the previous form version then PolicyCenter will **set the removal date** on the previous version, adds the new version and marks the new version a superceding the previous version.
    
    5. More details about new editions are available in the PolicyCenter documentation. Search "Policy Change Tab for Form Patterns".
    
    [![](Dashboard/Attachments/Untitled%20125%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20125.png)
    

25. Questão de revisão #1
    
    Questão - What role does the document management system play in terms of form generation?.
    
    Resposta:
    
    - Resposta correta
        
        The document management system is responsible for both managing form contents (or linking to another system that manages the form content) and for priting the appropriate forms for a give policy.
        

26. Questão de revisão #2
    
    Questão - When can PolicyCenter add forms to the policy?
    
    Resposta:
    
    - Resposta correta
        
        Policycenter can add forms to a policy at quote and at bind.
        

27. Questão de revisão #3
    
    Questão - Describe form inference.
    
    Resposta:
    
    - Resposta correta
        
        Forms inference is how PolicyCenter determines what forms to add to a policy.
        
        PolicyCenter generates froms based on details that the user has entered. Users specify coverages, exclusions and other details that give PolicyCenter the information it needs to run **forms inference logic.** This is form inference.
        

---

# 14. Underwriting Authority

1. Learner story
    
    1. Users can modify the underwriting infrastructure such as they can define underwriting issues or determine the types of underwriting issues that a user can approve. The underwriting rules specify things such as the state or jurisdiction of coverage and minimum or maximum amounts. For example, when an agent creates a new policy, certain terms of that policy may need to be reviewed by underwriting rules of the carrier require that an underwriter approve any vehicle valued at over $100,000. If an agent adds a car valued at $200,000 in a personal auto policy, an underwriter must give approval for that car.
    
    2. PolicyCenter creates an issue for the underwriter which prevents the agent from binding the policy until the underwriter approves the issue.
    
    3. "As a business analyst or configuration developer, I want to describe the concepts of Underwriting Authority so that I can understand the lifecycle of the underwriting issues."

2. Underwriting process
    
    1. An agent or a producer is creating a policy using the submssion transaction. If the policy has an issue that blocks quoting, the agent cannot view the quote until the underwriter approves the blocking issue then the agent can view the quote and then bind and issue the policy, potentially raising new issues. The new issues will again have to go through the underwriting process.
    
    [![](Dashboard/Attachments/Untitled%20126%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20126.png)
    

3. Underwriting authority
    
    1. The details on how to configure the underwriting authority will be covered in the _Configuring Underwriting_ _Authority_ module in the course _PolicyCenter Configuration Core._
    
    [![](Dashboard/Attachments/Untitled%20127%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20127.png)
    

4. Underwriting issues
    
    1. The UWIssue entity refers to the underwriting issues in the data model. There are certain issues that can be approved by agents themselves, but certain other need special approval from underwriters.
    
    2. For example, if the driver or applicant has a suspended/revoke license then the agent cannot quote the policy and an underwriting issue is raised and sent to the underwriter for approval as shown in the screenshot bellow. Alternetl, if a driver is driving a vehicle garaged in CA but has a valid driving license in MA, then agents can verify the license and underwriting issue will not ba raised.
    
    3. PolicyCenter raises issues automatically based on policy choices such as the types of vehicles on a policy or coverage amounts.
    
    [![](Dashboard/Attachments/Untitled%20128%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20128.png)
    

5. Creating underwriting issues
    
    [![](Dashboard/Attachments/Untitled%20129%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20129.png)
    

6. Underwriting rules
    
    1. An underwriting issue type is specified in the UWIssueType entity, which is a property of UWRule. PolicyCenter uses the UW Rule to define the UW Issue Type and specify the conditions to raise the issue. Configuration users should create and manage the set of underwriting rules and their characteristics very carefully. Guidewire recommends that you do not remove underwriting rules once they have been deployed in a production system.
    
    2. The Underwriting Rule Screen can be divided into several categories.
        
        1. Fields related to defining the UW Rule (mostly on the Rule Details tab). It includes Name, Code, Description, Checking Set, Blocking Point, Enabled, Start and End Date.
        
        2. Fields related to evaluating the UW Issue. It includes the Applicability section, Rule Context, Rule Condition and UW Issue Details.
        
        3. Fields related to approving the UW Issue (mostly on the Advanced tab). It includes Auto-approvable, Default Edit Before Bind, Default Approval Blocking Point, Default Duration (Rule Details tab), Value Comparator, Value Formatter Type, Default Value Assignment Type and Default Value Offset Amount
    
    3. PolicyCenter uses underwriting rule values:
        
        1. to check the condition and raise UW issue
        
        2. for determining availability of the Approve button, indicating that you can approve a specific issue to the default level
        
        3. to initially set the user interface for approvals that do not already have an approval present
        
        4. as automated approvals for auto-approvalbe issues and issues in automated processes
        
        [![](Dashboard/Attachments/Untitled%20130%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20130.png)
        

7. Checking set
    
    [![](Dashboard/Attachments/Untitled%20131%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20131.png)
    

8. Blocking point
    
    1. User defines a blocking point for each issue type. For example, PolicyCenter prevents a user from binding a policy until high-value vehicle underwriting issue is approved. Blocking points can be set at quote step to non-blocking so that issue does not stop the job at the quote step, but shows up as an informational issue on the Risk Analysis page as shown in the screenshot above. When the underwriting issue is informational, the agent can progress further in the job and quote, bind and issue the policy. Informational issues do not need approval from underwriters.
    
    2. Note that you can detect issues early, but then block at a much later point.
    
    3. For example, you can detect fire-breathing clowns before _quoting_ a policy, but have the issue block _binding_.
        
        1. By doing this, you can provide added visibility to PolicyCenter users, and improve their ability to plan their work.
        
        2. _In general, detect issues as early as possible, and think carefully about where they will block progress._
        
        3. Some problem that could occur, for example, if a field were to be only available on a quote screen (e.g., manual pricing adjustment factor), but its value blocked quote - meaning you could never get back to the screen to change it.
        
        [![](Dashboard/Attachments/Untitled%20132%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20132.png)
        

9. Authority grants and authority profiles
    
    1. Authority grants are similar to physical letters of authority.
    
    2. Each authority grant is based on an issue type defined in the UWIssueType table. The authority grant can specify the values which need additional approval.
    
    3. Users can have zero or more Authority Profiles assigned to them. Authority Profiles assigned to them. Authority profiles is different than a role. In the examples above, Job-level is the job grade a customer might have. In the base application the job-levels are Underwriter 1, Underwriter 2 and so on.
    
    4. When an underwriter has a specific expertise such as knowledge about Farm Equipement one can assign authority grants related to specific class codes and create a profile with those grants.
    
    5. Incremental, "Joe's Special" - bumps Joe's authority up a bit, since he isn't quite ready for a promotion to "Underwriter 2", meaning that the person has all the grants for "Underwriter 1" and some additional grants but not all the grants that he needs to be at Underwriter 2" level.
    
    [![](Dashboard/Attachments/Untitled%20133%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20133.png)
    

10. Learner story
    1. As a business analyst or configuration developer, I want to describe the policy Hold so that I can apply them in circumstances, such as a natural disaster, to avoid incorrect rates and forms.

11. Policy hold overview
    
    1. When a natural disaster is impending or in progress, a carrier may decide not to bind any new policy transactions in that area before or after the natural disaster. The carrier does not wish to write new policies until the natural disaster has passed and the losses have been accessed.
    
    2. For example, a gurricane is predicted to hit Florida.
    
    3. Customer start calling in to add flood coverage to their policy. The carrier puts a policy hold in place so that agents cannot add that coverage.
    
    4. For a business, coverage forms and rates are constantly changing. Changes are generally made at the state level by line ofbusiness.
    
    5. Although changes generally pertain to one state, sometimes there are changes that occur on a countrywide level when numerous states adopt the same change at the same time. Generally, work is put on hold for a few number of days prior to the effective date of the change to help ensure that work is not started with incorrect rates or forms.
    
    [![](Dashboard/Attachments/Untitled%20134%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20134.png)
    

12. Hold and release a transaction in PolicyCenter
    
    1. If a policy hold applies, then the policy transaction is blocked. When a policy hold applies, PolicyCenter creates an underwriting issue of the policy hold type. An underwriter with proper authority can approve the policy hold UW issue.
    
    2. Otherwise until the issue is approved a batch process Policy Hold Job Evaluation runs at scheduled times and keeps comparing the period values with the hold values and reevaluates whether the hold can be removed. An issue can be approved when the hold end date has passed or the hold is modified by the superuser. The _PolicyHoldJobEvalPlugin_ keeps track of transactions that are currently held by a policy hold and the last time the transaction was evaluated against the policy hold. Once a hold can be removed an activity is sent to the producer and they can process the transaction.
    
    [![](Dashboard/Attachments/Untitled%20135%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20135.png)
    

13. Working with Policy Holds
    
    1. Hold Details Tab Hold Type: Regulatory or Underwriting
    
    2. A regulatory hold is created for regulatory hold is created for regulatory reasons when the rates or forms have not been approved yet by the regulatory body and Carrier needs to hold off on writing certain business in certain jurisdictions.
    
    3. An underwriting hold is created for underwriting reasons when there's risk in an area and Carrier wants to avoid or use caution with, such as an impending hurricane.
    
    4. The value chosen from Hold Type drop-down list changes the availability of the UW Issue Type and the Long Description fields in the UW Issue Info.
    
    5. **UW Issue Info**
    
    6. The underwriting rule user interface defines the regulatory and underwriting holds issues in the case configuration of PolicyCenter.
    
    7. **Hold Rules**
    
    8. The hold rules scetion describes the rules that can be entered for each policy hold. The hold rules specify the line of business, transaction, date type, and coverage that will be used to determind whether or not a transaction process should be held.
    
    9. The transaction Date Type lists the options Effective Date and Written Date for Underwriting Hold, and Reference Date for a Regulatory Hold.
    
    10. **Hold Regions Tab**
    
    11. The hold regions that are undergoing a natural disaster or a regulatory modification.
    
    12. The hold regions will be compared against the policy locations when a transaction is being processed.
    
    13. Users can use the **import/export** functionality to test the behavior of policy holds in a staging environment before deploying them to your production environment. Set up the proposed policy hold in the staging environment, test its behavior, then export the policy holds. In the production environment, import that file. Only policy holds existing production data will be updated.
    
    [![](Dashboard/Attachments/Untitled%20136%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20136.png)
    

14. Learner story
    1. As a business analyst or configuration developer, I want to describe the Underwriting Referral Reasons so that I can record issues outside of a policy transaction.

15. Underwriting referral reasons
    
    1. The UWReferralReason entity is used for marking a policy issue outside of a transaction. It identifies the details of a corresponding UWIssue that will be generated the next time the application checks for UWIssues.
    
    2. You can use referral reasons to record underwriting issues for a policy outside of the context of a transaction.
    
    3. Because you add referral reasons ot the policy, you can create referral reasons at any time, even when there is no policy transaction.
    
    4. Policy Center creates underwriting issues for these referral reasons the next time a user processes a transaction on the policy. It also checks for referral reasons at various point in the transaction progress. Referral reasons can block progress of transactions on the policy. In the default application, the renewal transaction checks to see if there are any open referral reasons in the prior term.
    
    5. Referral reasons affect all transactions that handle underwriter issues.
    
    6. Consider the following example for creation of a referral reason. An external claim system stores the loss claims for a policy. The external system notes that loss claims are unacceptably high. The external system sends a message to PolicyCenter to add an underwriting referral reason on the policy. So the next time a transaction runs on the policy, an issue is created that correspons to this referral reason. The referral reason remains on the poliy.
    
    7. An underwriter cannot approve an underwriting referral reason, but he/she can removee it. For example, a visit to the customer site revealednumberous safety violations, and an underwriting referral reason was added to the policy. On a subsequent visit, the safety violations have been addressed. The underwriting referral reasosn is removed from the policy. The next time a transaction is run or reaches a checking set, the corresponding issue is deactivated.
    
    [![](Dashboard/Attachments/Untitled%20137%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20137.png)
    

16. Referral reasons in the user interface
    
    1. The UWReferralReason entity is similar to the UWIssue entity but is based on the policy rather than the policy period. Because of the close relationship between a UW referral reason and the associated UW issue, the default user interface displays them in a similar way.
    
    2. Steps to work with a referral reason:
        
        1. Go to an account and select a policy.
        
        2. Click Risk Analysis in the left sidebar. The UW Referral Reasons tab displays all underwriting referral reasons on the policy.
        
        3. Click the Add UW Referral Reason button.
        
        4. Enter an issue type, and short and long description.
    
    3. You can close an underwriting referral reason, opne a closed one, or view details.
    
    [![](Dashboard/Attachments/Untitled%20138%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20138.png)
    

17. UW referral reasons vs. UW issues
    
    [![](Dashboard/Attachments/Untitled%20139%201.png)](PolicyCenter%209%200%20Introduction%20\(Personal%20Commercial%201c64e0b5/Untitled%20139.png)
    

18. Questão de revisão #1
    
    Questão - When is an underwriting issue raised?
    
    Resposta:
    
    - Resposta correta
        
        Underwriting rules generate underwriting issues automatically. Or in certain situations underwriters can add issues manually depending on their permissions.
        

19. Questão de revisão #2
    
    Questão - What decides when an underwriting issues is raised?
    
    Resposta:
    
    - Resposta correta
        
        Blocking points defined in the issue types system table decide at which point an underwriting issue should be raised. For example, whether an issue should be raised at quote, bind or issue or if the issue is non-blocking.
        

20. Questão de revisão #3
    
    Questão - Who can approve or reject underwriting issues? How is this decided?
    
    Resposta:
    
    - Resposta correta
        
        An underwriter or an agent can approve or reject underwriting issues depending on their authority grants.
        

21. Questão de revisão #4
    
    Questão - Where are the underwriting issues displayed?
    
    Resposta:
    
    - Resposta correta
        
        The underwritingissues are displayed on the Risk Analisys page under the tab - UW Issues.
        

22. Questão de revisão #5
    
    Questão - State true or false:
    
    1. An approved UW issue cannot be reopened?
    
    2. An agent can reject an UW issue?
    
    3. UW referral reason is the same as an UW issue?
    
    Resposta:
    
    - Resposta correta
        
        1. False
        
        2. True
        
        3. False
        

---

![](Dashboard/Attachments/icons_questions%2028.png)

==The Outlining Method is traditional note-taking template with an outline format. The outlining method helps show relationships in your topic hierarchy.==