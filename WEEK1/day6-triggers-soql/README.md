# Day 6 - Triggers & SOQL

## 1. What is SOQL?

SOQL (Salesforce Object Query Language) is used in Salesforce to retrieve data from the database.

It is similar to SQL but designed specifically for Salesforce objects.

### Key Points:
- Used to fetch records from Salesforce objects like Account, Contact, Opportunity
- Always returns records (not tables like SQL joins)
- Can be used in Apex classes and triggers

### Example:
SELECT Id, Name FROM Account

---

## 2. What is an Apex Trigger?

An Apex Trigger is a piece of code that executes automatically before or after changes to Salesforce records.

### Trigger Events:
- Before Insert
- After Insert
- Before Update
- After Update
- Before Delete
- After Delete

### Example:
trigger AccountTrigger on Account (before insert) {
    for (Account acc : Trigger.new) {
        acc.Name = acc.Name + ' - Updated';
    }
}

---

## 3. Difference

### Flow vs Trigger

| Flow | Trigger |
|------|--------|
| No-code / low-code tool | Code-based (Apex) |
| Used by admins | Used by developers |
| Easier to build | More flexible and powerful |
| Visual interface | Written in code |
| Limited complex logic | Supports complex logic |

---

### Before vs After Trigger

| Before Trigger | After Trigger |
|----------------|--------------|
| Executes before record is saved | Executes after record is saved |
| Used to validate or modify data | Used to update related records |
| Cannot access record Id (in insert) | Can access record Id |
| Used to update fields | Used to create/update related records |

---

## 4. Your Trigger Use Cases (5 Examples)

- Auto-update Account rating when Industry changes  
- Prevent deletion of Accounts with open Opportunities  
- Create Contact automatically when Account is created  
- Update total Opportunity amount on Account  
- Send notification when high-value Opportunity is created  

---

## 5. Query Examples (English → SOQL)

### English Queries:
- Get all Accounts from India  
- Find Contacts with Gmail emails  
- List Opportunities above 1,00,000  
- Get Accounts created in last 30 days  
- Fetch Contacts linked to an Account  

### SOQL Examples:

SELECT Id, Name FROM Account WHERE BillingCountry = 'India'

SELECT Id, Name FROM Contact WHERE Email LIKE '%gmail.com%'

SELECT Id, Name, Amount FROM Opportunity WHERE Amount > 100000

SELECT Id, Name FROM Account WHERE CreatedDate = LAST_N_DAYS:30

SELECT Id, Name FROM Contact WHERE AccountId != null

---

## 6. Reflection

Enterprise systems like Salesforce react automatically to data changes because:

- Businesses require real-time updates
- Manual processes are slow and error-prone
- Automation improves accuracy and consistency
- Triggers enforce business rules instantly
- Data across objects must stay synchronized

Automation using SOQL and Apex Triggers makes enterprise systems efficient, scalable, and reliable.
