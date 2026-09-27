# Use Case Descriptions

The project includes three detailed use-case descriptions that expand the higher-level use-case diagram into implementation-oriented flows.

## UC-1 — Register Course

**Primary Actor:** Student  
**Secondary Actor:** Deanship of Admission and Registration

### Description
The student selects a course for the next semester by course name or ID. The system checks whether the class has available seats before completing registration.

### Trigger
The student indicates that they want to register in a course.

### Preconditions
- The student has an active university account.
- The student is logged in to PU E-Learning.
- Required fees have been paid.

### Postcondition
- The registered course appears in the student's study schedule for the next semester.

### Normal Flow
1. A list of courses is displayed to the student.
2. The student selects a course by name or ID.
3. The system checks whether a seat is available.
4. If a seat is available, the student is registered in the class.

### Alternative Flow — Registration through the Deanship
1. The Deanship enters the student's ID.
2. The student requests registration through the Deanship.
3. The Deanship selects the course by name or ID.
4. The system checks whether a seat is available.
5. If a seat is available, the student is registered.

### Exception — Class Full
1. The system rejects the registration because the class is full.
2. The student submits a request to open the class.
3. The academic advisor reviews the request.
4. The department administrator reviews the request.
5. The faculty dean reviews the request.
6. If approved, the Deanship registers the student.

---

## UC-2 — Pay Fees

**Primary Actor:** Student  
**Secondary Actor:** Bank

### Description
The student pays university fees through a third-party payment gateway connected to PU E-Learning. The student specifies the amount, the bank checks the account balance, and the payment is completed if sufficient funds are available.

### Trigger
The student indicates that they want to pay fees.

### Preconditions
- The student has funds deposited in the bank account.
- The bank system can check the account balance.
- The student is logged in to PU E-Learning.

### Postconditions
- The payment amount is withdrawn from the bank account.
- The account balance is updated.
- Course registration becomes available.

### Normal Flow
1. The student logs in to PU E-Learning.
2. The student chooses the bank-payment service.
3. The student specifies the amount to pay.
4. The bank checks the account balance.
5. If sufficient funds are available, the amount is withdrawn.

### Alternative Flow — Payment through the Bank
1. A bank employee enters the student's ID.
2. The employee enters the payment amount.
3. The bank checks the account balance.
4. If sufficient funds are available, the amount is withdrawn.

### Exception — Payment Rejected
1. A withdrawal-failed message is shown.
2. The student deposits additional funds.
3. The balance is checked again.
4. If sufficient funds are then available, the amount is withdrawn.

---

## UC-3 — View Student Marks

**Primary Actors:** Student, Professor  
**Secondary Actor:** Server

### Description
Students and professors can view student marks. The professor uploads marks first and makes them available; students can then view their marks and calculate averages.

### Trigger
A student or professor requests to view student marks.

### Preconditions
- The student and professor are logged in.
- The professor has uploaded the student's marks.
- The professor has allowed the marks to be viewed.

### Postconditions
- The student or professor can calculate the average of the marks.
- The course mark/rank can be viewed.

### Normal Flow — Student Account
1. The professor logs in.
2. The professor uploads student marks.
3. The professor enables the marks for viewing.
4. The student logs in.
5. The student views the marks.
6. The student calculates the average.
7. The student views the course mark/rank.

### Alternative Flow — Professor Account
1. The professor logs in.
2. The professor enters the student's ID.
3. The professor views the student's marks.
4. The professor calculates the average.
5. The professor views the course mark/rank.

### Exception — System/Login Failure
1. The Deanship of Admission enters the student ID.
2. The Deanship views the student's marks.
3. The Deanship calculates the average.
4. The Deanship views the course mark/rank.
