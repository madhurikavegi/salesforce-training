# Day 3 - Data Modeling

## 1. Difference Between App, Object, Record, and Field

| Term | Meaning | Example |
|------|----------|----------|
| App | A collection of related tools and objects used for a specific purpose | College Management App |
| Object | A table that stores similar types of data | Student Object |
| Record | A single row of data inside an object | One student’s details |
| Field | A single piece of information in a record | Student Name |

---

# 2. Standard vs Custom Objects

| Standard Objects | Custom Objects |
|------------------|----------------|
| Pre-built objects provided by the system | Objects created by users |
| Already available in the platform | Created based on business needs |
| Example: User, Task | Example: Student, Faculty |

## Examples

### Standard Objects
- User
- Task
- Account

### Custom Objects
- Student
- Faculty
- Course
- Department

---

# 3. College Data Model

## Objects

1. Student
2. Faculty
3. Course
4. Department

---

## Relationships

### Department → Student
- One department has many students
- Lookup Field: `Department_ID`

### Department → Faculty
- One department has many faculty members
- Lookup Field: `Department_ID`

### Department → Course
- One department offers many courses
- Lookup Field: `Department_ID`

### Faculty → Course
- One faculty member can teach many courses
- Lookup Field: `Faculty_ID`

### Course → Student
- One course can have many students
- Lookup Field: `Course_ID`

---

## College Data Model Diagram

```text
Department
   │
   ├── Students
   ├── Faculty
   └── Courses

Faculty
   └── Courses

Course
   └── Students
```

---

# 4. Formula Fields

## 1. Full Name

### Formula
```text
First_Name + " " + Last_Name
```

### Why should this be calculated automatically?
- Reduces manual typing
- Avoids spelling mistakes
- Updates automatically when names change

---

## 2. Remaining Seats

### Formula
```text
Total_Seats - Enrolled_Students
```

### Why should this be calculated automatically?
- Shows live seat availability
- Prevents calculation errors
- Helps students know available seats instantly

---

## 3. Percentage

### Formula
```text
(Obtained_Marks / Total_Marks) * 100
```

### Why should this be calculated automatically?
- Saves time
- Gives accurate results
- Updates instantly when marks change

---

# 5. Validation Rules

## 1. Email cannot be empty

### Validation Rule
```text
Email field must contain a value
```

### What problem does this prevent?
- Prevents missing contact information
- Ensures complete records
- Helps communication with students and faculty

---

## 2. Student age cannot be negative

### Validation Rule
```text
Age >= 0
```

### What problem does this prevent?
- Prevents invalid age entries
- Maintains accurate student records
- Avoids incorrect reports

---

## 3. Course seats cannot exceed limit

### Validation Rule
```text
Enrolled_Students <= Total_Seats
```

### What problem does this prevent?
- Prevents overbooking courses
- Helps manage classroom capacity
- Ensures seat availability remains accurate

---

# 6. Reflection: Why Structured Enterprise Data Matters

Structured enterprise data is important because it keeps information organized, accurate, and easy to manage. Random spreadsheets often contain duplicate entries, inconsistent formats, and errors that make data difficult to use.

With structured data:
- Information can be accessed quickly
- Reports can be generated easily
- Data remains accurate and secure
- Different departments can work together efficiently
- Automation becomes possible

In a college management system, structured data helps connect students, faculty, departments, and courses properly. This improves administration, reduces mistakes, and saves time.
