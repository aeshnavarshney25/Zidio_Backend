🔗 ZIDIO CONNECT – Internship & Job Portal Backend
ZIDIO CONNECT is a Spring Boot-powered backend for a role-driven Job & Internship Management Platform that caters to Students, Recruiters, and Admins. This system delivers a robust set of RESTful APIs enabling user authentication, job postings, application processing, resume handling, and more.

🚀 Key Highlights
🔐 Role-Based Access Control: Separate features for Students, Recruiters, and Admins

✉️ OTP Email System for secure password recovery

🧑‍🎓 Student Features
Manage profile and upload resume
Browse jobs & internships
Track application status

🧑‍💼 Recruiter Tools

Post and manage job listings
View applicants and their resumes

⚙️ Admin Panel (coming soon)

📩 Email Integration with OTP via Gmail SMTP
🔄 JSON-based REST API with clear status messages and responses

⚙️ Tech Stack Overview
Layer	                        Technology
Backend            	Spring Boot,Spring Security
Database	          MySQL with JPA & Hibernate
Auth System	        JWT + Email-based OTP
File Uploads      	Multipart (Supports resumes & avatars)
API Docs	          SpringDoc OpenAPI (Swagger)
Build Tool        	Maven
Java Version      	Java 17 or later

🛠️ Setup Instructions
✅ Prerequisites
Ensure you have the following installed:
Java 17+
Maven 3.8+
MySQL
IDE of your choice (IntelliJ / Eclipse / VS Code)

📦 Local Development
1. Clone the repository
git clone https://github.com/<your-username>/zidio-connect-backend.git  
cd zidio-connect-backend

2. Configure Database and Environment
Update application.properties with your local credentials:
# --- Server Port ---
server.port=8080

# --- MySQL Config ---
spring.datasource.url=jdbc:mysql://localhost:3306/zidio_connect
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

# --- JWT Config ---
jwt.secret=your_jwt_secret
jwt.expirationMs=86400000

# --- Email (Gmail SMTP) ---
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email@gmail.com
spring.mail.password=your_app_password
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true

# --- Cloudinary ---
cloudinary.cloud_name=your_cloud_name
cloudinary.api_key=your_api_key
cloudinary.api_secret=your_api_secret

3. Run the Project:
./mvnw spring-boot:run
Application will launch at:
http://localhost:8080

🗂️ Project Architecture
in.zidio.zidioconnect
├── config         // Security, CORS, Email, Cloudinary configs
├── controller     // API endpoints for Auth, Student, Recruiter, Admin
├── dto            // DTOs for requests/responses
├── model          // JPA Entities (User, Job, Application, etc.)
├── repository     // Data access layer using Spring Data JPA
├── security       // JWT Filters, Auth Handlers
├── service        // Business Logic Layer
├── util           // Utility Classes (Cloudinary Upload, OTP Gen)
└── ZidioConnectApplication.java


🔐 Authentication Endpoints
Endpoint	                      Description
/api/auth/login	                Login using email & password
/api/auth/register              User registration
/api/auth/forgot-password	      Send OTP to email
/api/auth/verify-otp	          Verify OTP & reset password




