# UML Class Documentation

## Abstract Class: User

Represents a generic system participant and provides shared identity and authentication features.

**Attributes**
- `userID: int`
- `name: String`
- `email: String`
- `password: String`

**Operations**
- `login()`
- `logout()`
- `updateProfile(): void`

**Relationships**
- Generalization parent of `Student` and `Professor`.

## Class: Student

Represents a student enrolled in courses and interacting with academic and administrative features.

**Attributes**
- `major: String`
- `attendance: Map<Course, Boolean>`
- `marks: Map<Course, Float>`

**Operations**
- `registerCourse()`
- `submitHomework()`
- `payFees()`
- `submitExcuse()`

**Relationships**
- Inherits from `User`.
- Many-to-many association with `Course`.
- One-to-many relationship with `Homework`.
- One-to-many relationship with `Excuse`.
- One-to-many relationship with `Payment`.
- Many-to-many relationship with `Exam`.

## Class: Professor

Represents a faculty member responsible for teaching and evaluating students.

**Attributes**
- `department: String`
- `coursesTaught: List<Course>`

**Operations**
- `assignHomework()`
- `createExam()`
- `reviewExcuse()`

**Relationships**
- Inherits from `User`.
- One-to-many association with `Course`.
- One-to-many relationship with `Homework`.
- One-to-many relationship with `Exam`.
- One-to-many relationship with `Excuse`.

## Class: Course

Represents a university course taught by a professor and attended by students.

**Attributes**
- `courseID: String`
- `courseName: String`
- `enrolledStudents: List<Student>`
- `examList: List<Exam>`

**Operations**
- `addExam(): void`
- `scheduleExam(exam: Exam)`

**Relationships**
- Many-to-many aggregation with `Student`.
- Professor association modeled as one-to-one or one-to-many in the original class documentation.
- One-to-many composition with `Homework`.
- One-to-many composition with `Exam`.

## Class: Excuse

Represents a student's request to justify an absence.

**Attributes**
- `excuseNo: int`
- `reason: String`
- `status: String`

**Operations**
- `submit()`
- `updateStatus()`

**Relationships**
- Many-to-one association with `Student`.
- Many-to-one association with `Professor`.
- Many-to-one association with `Course`.

## Class: Payment

Represents a financial transaction made by a student.

**Attributes**
- `paymentID: int`
- `amount: double`
- `method: String`
- `status: String`

**Operations**
- `process()`
- `validate()`

**Relationships**
- Many-to-one association with `Student`.

## UI Classes

### DashboardUI
Central interface for accessing major system features such as courses, marks, attendance, and payments. It is associated with the `User` class.

### CoursesUI
Interface for course registration, browsing, and viewing. It interacts with `Course`, `Student`, and `Professor`.

### AbsenceUI
Interface for attendance tracking and absence-excuse submission/tracking. It interacts with `Excuse`, `Student`, and `Professor`.

## Additional Classes Visible in the UML Diagram

The final class diagram also models additional domain elements including `Homework`, `Exam`, `Attendance`, and `Mark`, as well as their associations with students, professors, and courses. The diagram itself is preserved in `diagrams/class-diagram.png` and the editable source is included under `diagrams/editable/`.
