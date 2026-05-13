# Day 5 – Apex Introduction

## 1. What is Apex?

Apex is a strongly typed, object-oriented programming language developed by Salesforce.  
It is used to implement custom business logic and automation in Salesforce applications.

Apex helps developers:
- Create custom automation
- Perform complex calculations
- Integrate external systems
- Handle advanced validations
- Build enterprise-level applications

---

# 2. Difference

## Flow vs Apex

| Flow | Apex |
|---|---|
| Declarative tool | Programming language |
| Built using clicks | Built using code |
| Used for simple automation | Used for complex logic |
| Easy for admins | Used by developers |
| Limited flexibility | Highly flexible |

---

## Configuration vs Coding

| Configuration | Coding |
|---|---|
| Uses clicks and settings | Uses programming |
| Best for simple tasks | Best for advanced tasks |
| Limited customization | Full customization |
| Easy to build | Requires coding skills |
| Good for standard processes | Good for enterprise systems |

---

# 3. Real Examples Where Apex Is Needed

## 1. Complex Fee Calculation
Apex is needed to handle:
- Scholarships
- Discounts
- Late fees
- Tax calculations
- Multiple conditions

---

## 2. Integration with External Payment System
Apex is needed for:
- REST API callouts
- Payment gateway integration
- Secure authentication
- Error handling

---

## 3. Advanced Eligibility Logic
Apex is needed to check:
- Attendance percentage
- GPA requirements
- Pending fee dues
- Prerequisite subjects

---

# 4. Integrated System Design

## CRM Example
Student Admission Pipeline

```text
Lead → Inquiry → Application → Verification → Admission Confirmed
```

---

## Objects
- Student
- Course
- Faculty
- Enrollment

---

## Relationships

```text
Student ----< Enrollment >---- Course
```

Many-to-Many Relationship:
- One student can enroll in many courses
- One course can contain many students

---

## Validation Rule

### Email Required Validation

```text
IF(ISBLANK(Student_Email), TRUE, FALSE)
```

Error Message:
```text
"Email field is mandatory."
```

---

## Formula

### Remaining Seats Formula

```text
Remaining Seats = Total Seats - Filled Seats
```

---

## Flow Automation

```text
Admission Confirmed
        ↓
Send Email Notification
        ↓
Update Seat Count
        ↓
Notify Faculty
```

---

## Apex Business Rule

```java
trigger CheckSeatAvailability on Enrollment__c (before insert) {

    for(Enrollment__c e : Trigger.new) {

        Course__c c = [
            SELECT Remaining_Seats__c
            FROM Course__c
            WHERE Id = :e.Course__c
        ];

        if(c.Remaining_Seats__c <= 0) {
            e.addError('No seats available.');
        }
    }
}
```

---

# 5. Pseudocode Examples

## 1. Seat Availability Check

```text
IF remaining_seats = 0 THEN
    Block registration
ELSE
    Allow registration
END IF
```

---

## 2. Attendance Eligibility Check

```text
IF attendance_percentage < 75 THEN
    Notify student
ELSE
    Allow exam eligibility
END IF
```

# 6. Reflection

## Why enterprise systems eventually need programming

Enterprise systems cannot rely only on clicks and configuration because:
- Complex business rules require advanced logic
- External integrations need APIs and custom code
- Large-scale systems require performance optimization
- Advanced security needs custom implementation
- Enterprise applications need scalability and flexibility

Configuration tools are useful for simple automation, but programming languages like Apex are necessary for advanced enterprise-level functionality.
