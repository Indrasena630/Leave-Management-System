**LEAVE MANAGEMENT SYSTEM**

**1)Setup Steps**

Clone the repository:

git clone <repo-url>
cd leave-management-system


**2)Configure database in application.properties:**

spring.datasource.url=jdbc:mysql://localhost:3306/lmsdb?useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true


**3)Build and run the application:**

mvn spring-boot:run


**4)Access APIs at:**
http://localhost:8080/api.

**Assumptions**

* Each employee has a fixed leave balance allocated at the time of creation.

* Only managers (via approverId) can approve or reject leave requests.

* Employees can only apply for leaves after their joining date.

* Dates are provided in YYYY-MM-DD format.

* Leave balance is updated automatically after approval.

**Edge Cases Handled**

* Applying for leave before joining date.

* Applying for more days than available balance.

* Overlapping leave requests are rejected.

* Invalid dates (end date before start date).

* Employee not found for given employeeId.

* Preventing null values for mandatory fields (e.g., createdOn, startDate, endDate).

**Potential Improvements**

* Add role-based authentication (Employee, Manager, Admin).

* Provide a frontend UI for employees and managers.

* Send email notifications on leave approval/rejection.

* Add reporting module for leave history and analytics.

* Deploy on cloud platforms (Heroku, Render, AWS) for public access.

* Implement unit and integration testing for reliability
