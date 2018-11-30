# SFDX  App
Career coach contains 2 apps, Resume Builder and Certification tracker. 

## Dev, Build and Test


## Resources


## Description of Files and Directories


## Issues


## Data Management
sfdx force:data:tree:export -u OldHub -q "SELECT Id, Name, BillingStreet, BillingCity, BillingState, BillingPostalCode, BillingCountry, Phone, Website, Industry, Ownership, (SELECT LastName, FirstName, Salutation, MailingStreet, MailingCity, MailingState, MailingPostalCode, MailingCountry, Phone, MobilePhone, Email, Title, LinkedIn_Profile__c, Trailhead_Profile__c, Personal_Website__c FROM Contacts) FROM Account" --prefix jax --outputdir JaxData2 --plan

sfdx force:data:tree:export -u OldHub -q "SELECT Name, Summary__c, Active__c, (SELECT Job_Title__c, Degree_Earned__c, Completion_Date__c, Start_Date__c, End_Date__c, Current_Position__c, Resume__c, Description__c, Location__c, Course_Name__c FROM Experiences__r),(SELECT Name, Completion_Date__c, Sort_Order__c, Subtitle__c FROM Achievements__r),(SELECT Name, Sort_Order__c, Skills_List__c FROM Technical_Skills__r),(SELECT IsPrivate, Name, Description, StageName, Amount, Probability, CloseDate, Type, NextStep FROM Opportunities__r) FROM Resume__c" --prefix jax --outputdir JaxData2 --plan

sfdx force:data:tree:export -u OldHub -q "SELECT Name, Certification_Id__c, Completed_Date__c, Contact__c, Credential_Issuer__c, Description__c, Exam_Registration_URL__c, Renewal_Date__c, Resources_URL__c, Status__c, Version__c,(SELECT Completed_Date__c, Status__c, Version__c FROM Exams__r) FROM Certification__c" --prefix jax --outputdir JaxData2 --plan

### Orphan QUERY

sfdx force:data:tree:export -u OldHub -q "SELECT Name, Certification_Id__c, Completed_Date__c, Description__c, Exam_Registration_URL__c, Renewal_Date__c, Resources_URL__c, Status__c, Version__c,(SELECT Completed_Date__c, Status__c, Version__c FROM Exams__r) FROM Certification__c" --prefix jax --outputdir JaxData2 --plan