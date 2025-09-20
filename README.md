
﻿ 🌐 Network Request Automation – ServiceNow

## 📝 Project Description

The Network Request Automation project digitizes and automates the process of submitting, approving, and tracking network service requests in ServiceNow.

Traditionally, requests were handled through emails, spreadsheets, and calls, leading to delays, inefficiencies, and poor traceability. This project introduces a self-service catalog item that allows employees to submit requests, which are then automatically:

- Stored in a custom table,
- Routed for manager approvals,
- Sent as email notifications,
- Updated in real time with the final status.

This solution is scalable, reusable, and production-oriented – a practical demonstration of ServiceNow Flow Designer, Catalog Items, Notifications, and Approvals.

## Demo Link
**[Video](https://drive.google.com/file/d/18q0tVJXj8YcEBNS1EIMzTCd_f2l0YzHB/view?usp=sharing)**

---

## 🎯 Objectives

- Provide a centralized catalog item for network service requests.
- Eliminate manual interventions by automating approvals, record creation, and notifications.
- Maintain data consistency with a dedicated database table.
- Ensure real-time communication through automated emails.
- Design for scalability and reusability.

---

## 🏗️ Architecture & Workflow
```
Employee Submits Request (Service Catalog)
│
▼
Variable Set (Requestor Information + Network Details)
│
▼
Flow Designer
├── Get Catalog Variables
├── Create Record (u_network_database_table)
├── Send Email Notification
├── Ask for Approval (Manager/Approver)
├── Evaluate Approval Result
└── Update Record (Status: Approved/Rejected)
```

---

## 📂 Project Structure
```
📁 Network Request Automation
│
├── 📄 README.md                # Project documentation (this file)
├── 📄 Flow_Chart.png           # Workflow diagram
├── 📄 Network_Database_Table.png # Custom table design
├── 📄 Variable_Set_Config.png  # Variable set configuration
├── 📄 Relationships.png        # Relationship mapping
└── 📄 Update_Set_Export.xml    # Update set (import into ServiceNow)

```
---

## ⚙️ Key Components

### 1️⃣ Service Catalog Item – Network Request

- **Entry point** for end users.
- Linked with **Requestor Information** variable set.
- **Captures:** Requestor Name, Email, Department, Device Type, Location, Justification.

### 2️⃣ Variable Set – Requestor Information

- **Reusable** across catalog items.
- Ensures consistency and avoids duplication.
- Uses unique internal variable names to prevent conflicts.

### 3️⃣ Custom Table – `u_network_database_table`

- Dedicated table for storing requests.
- **Fields include:** Requestor Name, Email ID, Department, Device Type, Location, Status (`Pending` / `Approved` / `Rejected`).

### 4️⃣ Flow Designer Automation

- **Flow actions:**
  - `Get Catalog Variables` – Capture form inputs.
  - `Create Record` – Insert into custom table.
  - `Send Email` – Notify requestor & approver.
  - `Ask for Approval` – Routed to manager.
  - `If Condition` – Check approval result.
  - `Update Record` – Mark status accordingly.

### 5️⃣ Notifications

- Configured dynamic email templates for requestor & approvers.
- Supports `To`, `CC`, `BCC` (static or dynamic).

### 6️⃣ Approvals

- **Approval type:** `Anyone Approves`.
- Configurable for static or dynamic approvers.
- Decision tracked in the request record.

---

## 🧪 Testing Journey & Fixes

### ✅ Successful Validations

- Records created correctly in the custom table.
- Email notifications triggered after enabling SMTP.
- Approval flow updated the `status` field as expected.

### ⚠️ Issues & Fixes

- **Duplicate variable conflict** → Fixed by assigning unique internal names.
- **Journal field warning** → Ignored, as the table didn’t require journal fields.
- **Email sending disabled** → Resolved by enabling `glide.email.smtp.active`.
- **Flow stuck in pending** → Fixed by assigning the correct dynamic approver.

---

## 🚀 Outcomes

- Automated the entire Network Request lifecycle.
- Eliminated manual tracking with real-time status updates.
- Boosted efficiency through self-service and automation.
- **Demonstrated skills in:**
  - ServiceNow Catalog Development
  - Flow Designer Automation
  - Notifications & Approvals
  - Custom Table Design

---

## 🛠️ Setup & Deployment

1.  **Import into ServiceNow**
    - Navigate to `System Update Sets` > `Retrieved Update Sets`.
    - Import `Update_Set_Export.xml`.
    - Preview & Commit the update set.

2.  **Enable Email Notifications**
    - Go to `System Properties` > `Email` and enable:
      - `glide.email.smtp.active = true`
      - `glide.email.read.active = true`

3.  **Test End-to-End**
    - Submit a request via the Service Catalog.
    - Verify record creation in `u_network_database_table`.
    - Check for email notifications.
    - Approve/Reject the request and verify the status is updated automatically.

---

## 📚 Learnings

- Best practices for variable set reuse.
- Configuring email notifications effectively.
- Building robust flows with conditional logic.
- Debugging common ServiceNow issues.

---

## 🌟 Why This Project Stands Out

✔️ **Real-world ITSM use case**
✔️ **Complete automation lifecycle** (request → approval → notification)
✔️ **Professional project documentation & assets**
✔️ **Demonstrates ServiceNow developer skills end-to-end**

---

## 👨‍💻 Author

**Sai Prasanth Tamarapalli**

🔗 **[LinkedIn](https://www.linkedin.com/in/prasanth-tamarapalli-48b27b256/)** | 🔗 **[GitHub](https://github.com/SaiPrasanth27)**

