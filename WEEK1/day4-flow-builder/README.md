# Day 4 – Flow Builder

## 1. What is Flow Builder?

Flow Builder is a declarative automation tool in :contentReference[oaicite:0]{index=0} that allows users to automate business processes using clicks instead of code.

It helps organizations:
- Automate repetitive tasks
- Reduce manual work
- Improve productivity
- Send notifications automatically
- Update records instantly
- Build guided user screens

Flow Builder is widely used by admins and developers to create enterprise automation processes.

---

# 2. Types of Flows

## Screen Flow

Screen Flow is an interactive flow that collects input from users through screens.

### Features:
- Displays forms and input fields
- Guides users step-by-step
- Used for data entry processes
- Can show messages and validation

### Example:
Student Admission Form:
1. Enter student details
2. Select course
3. Upload documents
4. Submit application

---

## Record-Triggered Flow

Record-Triggered Flow runs automatically when a record is:
- Created
- Updated
- Deleted

### Features:
- Fully automated
- No user interaction required
- Runs in the background
- Useful for business automation

### Example:
When Admission Status becomes "Confirmed":
- Send confirmation email
- Update seat count
- Notify faculty
- Create enrollment record

---

# 3. Automation Ideas (5 Examples)

## 1. Student Admission Confirmation
When admission is approved:
- Send email notification
- Generate enrollment ID
- Update available seats

---

## 2. Attendance Warning System
If attendance drops below 75%:
- Notify student
- Notify parents
- Alert faculty advisor

---

## 3. Fee Due Reminder
If fee payment is pending:
- Send reminder email
- Send SMS notification
- Update finance dashboard

---

## 4. Course Completion Certificate
After course completion:
- Generate certificate
- Send certificate email
- Update student status

---

## 5. Faculty Leave Approval
When faculty applies for leave:
- Send request to HOD
- Approve or reject automatically
- Notify faculty member

---

# 4. Flow Diagram

## Admission Automation Flow

```text
Student Application Submitted
                ↓
      Verify Documents
                ↓
      Admission Approved?
          ↙           ↘
        No             Yes
        ↓               ↓
 Reject Application   Send Confirmation Email
                        ↓
                 Update Seat Count
                        ↓
                   Notify Faculty
