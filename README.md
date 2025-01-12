# Job Portal Application

## Overview
The **Job Portal Application** is a comprehensive platform designed to streamline the job-hiring process by connecting **Job Seekers**, **Recruiters**, and an **Admin**. It offers features such as user registration, job postings, job applications, and profile management.

## Features

### **1. Job Seekers**
- Register with email/mobile and verify via OTP.
- Create a detailed profile with education, experience, and resume upload.
- Search and apply for jobs based on roles and skills.
- Track the status of job applications.

### **2. Recruiters**
- Register with email/mobile and verify via OTP.
- Post job openings with details like skills, location, and salary.
- Manage posted jobs: Edit, delete, or view applications.
- Review candidates and update their application statuses.

### **3. Admin**
- Manage the platform by approving/rejecting job postings.
- Moderate platform activities and ensure integrity.

---

## Tech Stack
- **Backend**: Spring Boot, JPA, Hibernate
- **Frontend**: Thymeleaf (for dynamic web pages)
- **Database**: MySQL
- **File Storage**: Cloudinary (for resumes and profile pictures)
- **Email Service**: Spring Mail (for OTP verification)
- **Server**: Embedded Tomcat

---

## Modules and Structure

### **Controllers**
1. **GeneralController**: Manages public pages (home, login, etc.) and admin functionalities.
2. **JobSeekerController**: Handles job seeker registration, profile completion, and applications.
3. **RecruiterController**: Manages recruiter registration, job postings, and application reviews.

### **DTOs**
- `JobSeeker`, `Recruiter`: Represent user entities with validations.
- `Job`, `JobApplication`: Capture job postings and applications.
- `Education`, `Experience`: Model job seeker qualifications and work history.

### **Repositories**
- Extend `JpaRepository` for database interactions.
- Examples: `JobRepository`, `RecruiterRepository`, `JobSeekerRepository`.

### **Services**
- **JobSeekerService**: Handles business logic for job seekers.
- **RecruiterService**: Manages recruiter-specific operations.

### **Helpers**
- **AES**: Encrypts/decrypts sensitive user data (e.g., passwords).
- **CloudinaryHelper**: Handles file uploads to Cloudinary.
- **MyEmailSender**: Sends OTP emails using Spring Mail.

---

## Application Properties
```properties
# Application Configuration
spring.application.name=job-portal
server.port=9696

# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/job-portal?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=peace
spring.jpa.hibernate.ddl-auto=update

# Email Configuration
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=<your-email>
spring.mail.password=<your-password>
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true

# Cloudinary Configuration
CLOUDINARY_URL=cloudinary://api_key:api_secret@cloud_name
```

---

## How to Run

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd job-portal-application
   ```
3. Configure the database and email settings in `application.properties`.
4. Run the application using Maven:
   ```bash
   ./mvnw spring-boot:run
   ```
5. Access the application at:
   ```
   http://localhost:9696
   ```

---

## Future Enhancements
- Add job recommendations based on user skills.
- Implement real-time notifications for application updates.
- Introduce multi-language support.



## Contact
For any queries or contributions, contact:
- **Email**: ramoffical06@gmail.com
