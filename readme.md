# 📝 Raji3li Platform: Online Examination & Academic Tracking Architecture

> **Note on Availability:** The source code for this project is hosted within a private academic registry. This repository serves as a public architectural case study and system design breakdown.
> 
> 🌐 **Project Recognition:** You can view the project milestone announcement and team implementation notes on the official [LinkedIn Project Post](https://www.linkedin.com/posts/amina-aitkaci-51aa41335_a-while-back-i-teamed-up-with-some-brilliant-ugcPost-7461755289965580288-YsfM/).

Raji3li is an advanced online examination platform engineered to streamline student assessments, log relational testing matrices, and optimize academic review workflows.

## 🚀 My Contributions & Engineering Scope

As a Full-Stack Engineer on this project, I owned the core data layer and backend business logic execution:
- **Relational Database Design:** Formulated and optimized the relational database schema using MariaDB/MySQL to handle many-to-many relationships between students, examinations, and dynamic question banks.
- **State Management:** Implemented strict backend state validation to ensure test integrity, preventing submission modifications once an exam session timestamp expired.
- **API Optimization:** Developed efficient data abstraction layers to fetch student performance metrics and generate granular progress reports.

## 📐 System Architecture & Data Flow

### 1. Database Schema Core
The engine relies on a robust relational structure designed to maintain data integrity across hundreds of concurrent examination matrices:
- `users` (Roles: Student, Professor, Administrator)
- `exams` (Foreign key links to creator, duration limits, threshold parameters)
- `questions` (Polymorphic associations supporting multiple-choice, text inputs, and scoring weights)
- `submissions` (Tracks atomic student answers tied to an active session instance)

### 2. Security & Session Control
- Implemented middleware security gates to verify that only authorized student tokens could request active exam payloads.
- Structured atomic write operations to prevent concurrent request handling failures during peak multi-user examination submittals.

## 🧠 Key Technical Challenges & Solutions

* **Challenge:** Handling high-volume database writes when an entire class submits their exams at the exact same deadline window.
* **Solution:** Designed optimized indexing pathways on foreign keys (`exam_id`, `student_id`) to significantly reduce lock wait times and prevent database timeout constraints.

## 🛠️ The Tech Core
- **Backend Framework:** PHP / Laravel
- **Database Engine:** MariaDB / MySQL
- **Frontend Layer:** Blade Templating / JavaScript & Tailwind CSS
