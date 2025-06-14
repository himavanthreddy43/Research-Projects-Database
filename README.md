# 📚 Research Projects Database Management System

This project presents a relational database system to manage **research projects**, their **managers**, associated **employees**, and **funding agencies**. Built using **MySQL**, this system simulates a real-world scenario where organizations track projects, personnel involvement, funding sources, and managerial hierarchies.

---

## 📌 Key Features

- Stores information about **research projects**, including duration, budget, and managing agency.
- Tracks **employees** and their involvement in multiple projects.
- Manages **project managers**, who are also employees.
- Keeps records of **funding agencies** backing each project.
- Enforces **referential integrity** through foreign key relationships.

---

## 🗃️ Database Schema Overview

### 1. `Employee`
| Column      | Type         | Description           |
|-------------|--------------|------------------------|
| SSN         | INT (PK)     | Unique employee ID     |
| Emp_Name    | VARCHAR(50)  | Employee name          |
| Salary      | DECIMAL      | Employee salary        |

---

### 2. `FundingAgency`
| Column      | Type         | Description             |
|-------------|--------------|--------------------------|
| Agency_ID   | INT (PK)     | Unique agency ID         |
| Name        | VARCHAR(100) | Name of funding agency   |
| Address     | VARCHAR(255) | Agency address           |

---

### 3. `Project`
| Column      | Type         | Description                     |
|-------------|--------------|----------------------------------|
| Project_ID  | INT (PK)     | Unique project ID               |
| Name        | VARCHAR(100) | Project name                    |
| Duration    | INT          | Duration in months              |
| Budget      | DECIMAL      | Project budget                  |

> 🔗 Each project is **funded by one agency**.

---

### 4. `Project_Manager`
| Column       | Type     | Description                      |
|--------------|----------|----------------------------------|
| Project_ID   | INT (PK) | The project being managed        |
| Manager_SSN  | INT      | SSN of the manager (employee)    |

> 🔗 Establishes **one-to-one** relationship between a project and its manager.

---

### 5. `Employee_Project`
| Column       | Type     | Description                                  |
|--------------|----------|----------------------------------------------|
| SSN          | INT      | Employee working on the project              |
| Project_ID   | INT      | Assigned project                             |
| Manager_SSN  | INT      | Manager overseeing this employee in project  |

> 🔗 Many-to-many mapping between **employees** and **projects**.

---

## 💾 Sample Data

### Employees

```sql
INSERT INTO Employee (SSN, Emp_Name, Salary) VALUES
(101, 'John Doe', 55000.00),
(102, 'Jane Smith', 65000.00),
(103, 'Alice Brown', 72000.00);

![image](https://github.com/user-attachments/assets/aaee7349-90d3-4819-bf3f-1d9ca60fd1e0)


![image](https://github.com/user-attachments/assets/20583c3f-6c49-4a55-889b-c96219d9a95e)
