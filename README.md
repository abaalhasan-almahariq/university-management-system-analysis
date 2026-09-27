# University Management System — Software Analysis & Modeling

A **Software System Analysis and Modeling** team project for a proposed Palestine University management / e-learning system. The project focuses on requirements engineering, stakeholder analysis, use cases, UML modeling, activity flows, and UI prototyping rather than a full production implementation.

The proposed system aims to reduce paper-based university workflows by centralizing common academic and administrative services. Students can register or withdraw courses, pay fees, view marks, submit homework, track attendance, and submit absence excuses. Professors can manage courses, create exams and homework, upload marks, record attendance, and review student requests.

> **Team project:** the original report lists four team members. My own work focused on the use-case descriptions, functional and non-functional requirements, the class diagram and class documentation, all three activity diagrams, and the application prototype.

## What This Repository Demonstrates

- Requirements analysis and documentation
- Stakeholder identification and user stories
- Functional and non-functional requirements
- Detailed use-case descriptions
- UML class modeling
- Activity-diagram modeling
- UI/UX prototyping
- Translating university workflows into a structured software design

## Project Scope

The source project models a PU E-Learning / University Management System with these main areas:

- Authentication and user accounts
- Course registration and withdrawal
- Online fee payment through a third-party banking/payment flow
- Student marks and average calculation
- Online exams and homework
- Attendance management
- Absence excuse submission and review
- Professor course and student management

The project uses **Extreme Programming (XP)** as its proposed development methodology, emphasizing short iterations, user stories, incremental design, testing, and repeated customer feedback.

## Documentation

- [Project Overview](docs/PROJECT_OVERVIEW.md)
- [Stakeholders & User Stories](docs/STAKEHOLDERS_AND_USER_STORIES.md)
- [Requirements](docs/REQUIREMENTS.md)
- [Use Cases](docs/USE_CASES.md)
- [Class Documentation](docs/CLASS_DOCUMENTATION.md)

## UML & Activity Diagrams

### Use Case Diagram

![Use case diagram](diagrams/use-case-diagram.png)

### Class Diagram

![Class diagram](diagrams/class-diagram.png)

### UC-1 — Register Course

![Register course activity diagram](diagrams/activity-uc1-register-course.png)

### UC-2 — Pay Fees

![Pay fees activity diagram](diagrams/activity-uc2-pay-fees.png)

### UC-3 — View Student Marks

![View student marks activity diagram](diagrams/activity-uc3-view-student-marks.png)

## Prototype

The project includes a visual prototype for both student and professor workflows.

### Student Dashboard

![Student dashboard](prototype/student-dashboard.png)

### Course Management

![Student courses](prototype/student-courses.png)

![Available courses](prototype/available-courses.png)

### Attendance & Excuse Submission

![Attendance](prototype/student-attendance.png)

![Submit excuse](prototype/submit-excuse.png)

### Professor Dashboard

![Professor dashboard](prototype/professor-dashboard.png)

A prototype walkthrough video was also included with the original project material:

[Prototype video on YouTube](https://youtu.be/7k-uxTylGtM)

## Repository Structure

```text
university-management-system-analysis/
├── README.md
├── docs/
│   ├── PROJECT_OVERVIEW.md
│   ├── STAKEHOLDERS_AND_USER_STORIES.md
│   ├── REQUIREMENTS.md
│   ├── USE_CASES.md
│   └── CLASS_DOCUMENTATION.md
├── diagrams/
│   ├── use-case-diagram.png
│   ├── class-diagram.png
│   ├── activity-uc1-register-course.png
│   ├── activity-uc2-pay-fees.png
│   ├── activity-uc3-view-student-marks.png
│   └── editable/
└── prototype/
    ├── student-dashboard.png
    ├── student-courses.png
    ├── available-courses.png
    ├── student-attendance.png
    ├── submit-excuse.png
    └── professor-dashboard.png
```

## Important Note

This repository presents the **analysis, modeling, and prototype work** produced for the university project. It should not be interpreted as a completed production implementation of the proposed system.

## Author Contribution

**Aba-al-Hasan Al-Mahariq** — Software Engineering graduate, Zarqa University

My contributions to this team project included:

- Use-case descriptions
- Functional and non-functional requirements
- UML class diagram
- Class description documentation
- Three activity diagrams
- Application prototype
