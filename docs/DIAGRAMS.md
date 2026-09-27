# GitHub-Rendered Diagrams

These Mermaid diagrams are portfolio-friendly recreations of the UML and activity diagrams from the original project material. They preserve the project structure and flows while making them viewable directly on GitHub.

## Use Case Overview

```mermaid
flowchart LR
    Student[Student]
    Professor[Professor]

    CA((Create Account))
    LI((Log In))
    RC((Register Course))
    PF((Pay Fees))
    VM((View Marks))
    OE((Access Online Exams))
    GE((Generate Exams))
    SM((Share Student Marks))
    RA((Record Attendance))

    Student --> CA
    Student --> LI
    Student --> RC
    Student --> PF
    Student --> VM
    Student --> OE

    Professor --> CA
    Professor --> LI
    Professor --> GE
    Professor --> SM
    Professor --> RA
    Professor --> VM
```

## Class Diagram

```mermaid
classDiagram
    class User {
        <<abstract>>
        +int userID
        +String name
        +String email
        +String password
        +login()
        +logout()
        +updateProfile() void
    }

    class Student {
        +String major
        +Map~Course,Boolean~ attendance
        +Map~Course,Float~ marks
        +registerCourse()
        +submitHomework()
        +payFees()
        +submitExcuse()
    }

    class Professor {
        +String department
        +List~Course~ coursesTaught
        +assignHomework()
        +createExam()
        +reviewExcuse()
    }

    class Course {
        +String courseID
        +String courseName
        +List~Student~ enrolledStudents
        +List~Exam~ examList
        +addExam() void
        +scheduleExam(exam)
    }

    class Homework {
        +int homeworkID
        +String title
        +String description
        +Date dueDate
        +submit()
    }

    class Exam {
        +int examID
        +String type
        +Date date
        +float totalMarks
        +schedule()
        +publishResults()
    }

    class Attendance {
        +int attendanceID
        +Date date
        +Boolean status
        +record()
    }

    class Excuse {
        +int excuseNo
        +String reason
        +String status
        +submit()
        +updateStatus()
    }

    class Payment {
        +int paymentID
        +double amount
        +String method
        +String status
        +process()
        +validate()
    }

    class Mark {
        +int studentID
        +int courseID
        +float grade
        +calculateAverage()
    }

    class DashboardUI
    class CoursesUI
    class AbsenceUI

    User <|-- Student
    User <|-- Professor

    Student "*" -- "*" Course : enrolls in
    Professor "1" -- "*" Course : teaches
    Course "1" *-- "*" Homework
    Course "1" *-- "*" Exam
    Student "1" -- "*" Homework : submits
    Professor "1" -- "*" Homework : assigns
    Student "1" -- "*" Exam : takes
    Professor "1" -- "*" Exam : creates
    Student "1" -- "*" Excuse : submits
    Professor "1" -- "*" Excuse : reviews
    Course "1" -- "*" Excuse
    Student "1" -- "*" Payment : makes
    Student "1" -- "*" Attendance
    Professor "1" -- "*" Attendance : records
    Course "1" -- "*" Attendance
    Student "1" -- "*" Mark
    Course "1" -- "*" Mark

    User --> DashboardUI
    CoursesUI --> Course
    CoursesUI --> Student
    CoursesUI --> Professor
    AbsenceUI --> Excuse
    AbsenceUI --> Student
    AbsenceUI --> Professor
```

## Activity Diagram — UC-1 Register Course

```mermaid
flowchart TD
    A([Start]) --> B[Student logs in]
    B --> C[Student opens course registration]
    C --> D[Choose course by name or ID]
    D --> E{Seat available?}
    E -- Yes --> F[Register student in course]
    F --> G[Add course to study schedule]
    G --> H([End])
    E -- No --> I[Reject registration]
    I --> J[Student submits request to open class]
    J --> K[Academic advisor reviews]
    K --> L[Department administrator reviews]
    L --> M[Faculty dean reviews]
    M --> N[Deanship registers student if approved]
    N --> H
```

## Activity Diagram — UC-2 Pay Fees

```mermaid
flowchart TD
    A([Start]) --> B[Student logs in]
    B --> C[Choose payment service]
    C --> D[Enter amount]
    D --> E[Bank checks account balance]
    E --> F{Sufficient funds?}
    F -- Yes --> G[Withdraw amount]
    G --> H[Update balance]
    H --> I[Open course-registration access]
    I --> J([End])
    F -- No --> K[Show withdrawal failed]
    K --> L[Student deposits additional funds]
    L --> E
```

## Activity Diagram — UC-3 View Student Marks

```mermaid
flowchart TD
    A([Start]) --> B[Professor logs in]
    B --> C[Professor uploads marks]
    C --> D[Professor enables marks for viewing]
    D --> E[Student logs in]
    E --> F[Student views marks]
    F --> G[Calculate average]
    G --> H[View course mark/rank]
    H --> I([End])

    B -. Professor path .-> J[Enter student ID]
    J --> K[View student marks]
    K --> G
```

## Source Note

The original project files also contain exported Draw.io images and editable Draw.io sources. This repository focuses on the analysis/design content itself, with Mermaid versions provided for direct GitHub rendering.
