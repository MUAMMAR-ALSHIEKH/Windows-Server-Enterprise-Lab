Day 8 – Enterprise File Server Architecture (NTFS + ABE)

Overview

In Day 8, a secure enterprise-level File Server architecture was designed and implemented.
The objective was to enforce department-level isolation using NTFS permissions and Access-Based Enumeration (ABE) while following best practices for share design and least privilege access.

---

Objectives

- Design a structured department-based file system
- Implement a single root share model
- Configure NTFS permissions per department
- Enable Access-Based Enumeration (ABE)
- Test user-based visibility and access control
- Document and validate results

---

Tasks Completed

1. Folder Structure Creation

Created a centralized directory:

D:\Departments
│
├── IT
├── HR
├── Finance
└── Sales

Only one share was created at the root level.

---

2. Share Configuration

Share Name:

Departments

Network Path:

\\FS01\Departments

Share Permissions:

- Domain Users → Full Control

Note:
Access control is enforced strictly using NTFS permissions (Best Practice).

Access-Based Enumeration (ABE):

- Enabled to hide unauthorized folders from users.

---

3. NTFS Permission Configuration

Inheritance was disabled on department folders and unnecessary entries removed.

IT Folder

- IT_Users → Modify
- Domain Admins → Full Control
- SYSTEM → Full Control

HR Folder

- HR_Users → Modify
- Domain Admins → Full Control
- SYSTEM → Full Control

Finance Folder

- Finance_Users → Modify
- Domain Admins → Full Control
- SYSTEM → Full Control

Sales Folder

- Sales_Users → Modify
- Domain Admins → Full Control
- SYSTEM → Full Control

---

4. User Testing & Validation

Test 1 – HR User

Accessed:

\\FS01\Departments

Result:

- Visible: HR
- Hidden: IT, Finance, Sales

---

Test 2 – IT User

Result:

- Visible: IT
- Hidden: HR, Finance, Sales

---

Test 3 – Dual Membership User (IT + HR)

Result:

- Visible: IT and HR
- Hidden: Finance, Sales

Confirms cumulative NTFS permission behavior.

---

Test 4 – Unauthorized Access Attempt

Attempted direct access:

\\FS01\Departments\Finance

Result:

- Access Denied

Confirms least privilege enforcement.

---

Key Concepts Demonstrated

- NTFS Permission Design
- Single Share Architecture Model
- Access-Based Enumeration (ABE)
- Cumulative Group Membership Behavior
- Inheritance Management
- Enterprise Security Best Practices

---

Verification Results

- Share accessible from client machine
- Folder visibility aligned with group membership
- Unauthorized folders hidden automatically
- Access denied when attempting direct path entry
- No permission conflicts detected

---

Status

✔ Secure File Server Architecture Implemented
✔ Department Isolation Enforced
✔ Access Visibility Controlled
✔ Day 8 Completed Successfully