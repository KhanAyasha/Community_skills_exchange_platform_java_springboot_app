# Community_skills_exchange_platform_java_springboot_app


## Description:
Spring Boot + JSP web application for an online learning/skill‑exchange platform. application designed to allow users to exchange skills and services within a community. It promotes collaboration and learning by enabling users to list their skills, book sessions, and engage in real-time, one-to-one tutoring sessions. Users can search for skills, schedule sessions, and participate in community forums. This platform aims to create a comprehensive environment for learning and skill development through interactive and live sessions.It supports two roles — **students** and **contributors** — and lets contributors create courses while students browse courses and schedule study sessions. The app uses **Hibernate** with **MySQL** and stores data for students, contributors, courses, and study sessions.

## What the app does
- **Authentication**: register/login/logout for student or contributor roles.
- **Role‑based access**: custom role filter plus Spring Security to restrict student and contributor pages.
- **Courses**: contributors can add and delete courses; students can browse all courses.
- **Sessions**: students can schedule sessions for a course; both roles can view their sessions.
- **Profile**: basic profile view/update for both roles from the dashboard.

## Tech stack
- Spring Boot 3 (WAR packaging)
- JSP/JSTL views
- Hibernate (manual SessionFactory config)
- MySQL
- Spring Security (custom filter + security config)

## Key routes and pages
- Auth: `/login.htm`, `/register.htm`, `/logout.htm`
- Student: `/student/home.htm`, `/student/view-courses.htm`, `/student/my-sessions.htm/{emailId}`, `/student/add-session.htm/{emailId}`
- Contributor: `/contributor/home.htm`, `/contributor/add-course.htm/{emailId}`, `/contributor/my-courses.htm/{emailId}`, `/contributor/my-sessions.htm/{emailId}`
- REST APIs: `/courses/*`, `/sessions/*`, `/student/*`, `/contributor/*`

## Database setup
The app expects a local MySQL database defined in `WebProject/src/main/resources/hibernate.cfg.xml`:
- URL: `jdbc:mysql://localhost:3306/finalproject`
- Username: `username`
- Password: `password`
- Hibernate: `hbm2ddl.auto=update`

Update these values for your environment.

## Run locally
From the repo root:
1. `cd WebProject`
2. `mvn spring-boot:run`
3. Open `http://localhost:8080/` (default)

If you prefer WAR deployment, run `mvn package` and deploy the WAR from `WebProject/target` to a servlet container.

