# 🛒 E-commerce Platform – Oracle PL/SQL Capstone Project

# 🎓 Student Information  
**Name:** Cyusa Divince  
**ID:** 27516
**Course:**
INSY 8311 (2025–2026)  
**Instructor:** Eric Maniraguha  
**Institution:** AUCA  
---
## 📌 Overview
The **RetailFlow Management System** addresses challenges in online retail operations, including inventory mismanagement, order processing delays, and lack of audit trails. This Oracle PL/SQL 

---
## Solution Provide:
✔ **Real-time order processing**  
✔ **Automated inventory control**  
✔ **Business rule enforcement**  
✔ **Comprehensive activity auditing**  

---

##  Objectives

- [x] Centralize product, customer, and order data  
- [x] Automate order fulfillment with stored procedures  
- [x] Restrict inventory changes on weekends/holidays via triggers  
- [x] Ensure accountability through DML auditing  
- [x] Protect sensitive customer/payment data

---

## 🛠 Tech Stack  

| Component               | Tool                         |
|-------------------------|------------------------------|
| **Database**            | Oracle 21c                  |
| **Development**         | SQL Developer                |
| **Modeling**           | BPMN.io & SQL Modeler (ERD & BPMN)         |
| **Monitoring**         | Oracle Enterprise Manager    |

---
##  BPMN Diagram
Helps to so see the Work flow of the System through various processes and how their are conducted
![BPMN](https://github.com/cyusadivince/Final_Project/blob/main/ScreenShots/database_objects/BPMN.png)


## **Key Entities (Based on Schema Tables)**

### **1. Customer**

Stores customer details, enabling user identification, order history tracking, and personalized service.

### **2. Product**

Contains product information including price and stock level.

### **3. Category**

This Holds the list of all Products currently we have.

### **4. Orders**

Represents each order placed by a customer.

### **5. Order_Item**

Breaks down each order into individual product items, quantities, and totals. Critical for revenue calculation and stock management.

### **6. Payment**

Captures transaction detail.

### **7. Delivery**

Stores delivery schedule, dispatch status, and logistics information.


## **MIS Components & Organizational Impact**

### Key MIS Functions

* **Transaction Processing:**
  Orders, payments, deliveries, and stock adjustments recorded in real-time.

* **Data Storage & Integration:**
  The nine-table schema ensures structured data flow between different stages.

* **Internal Control & Accuracy:**
  Payment verification, stock validation, and delivery confirmation reduce errors.

* **Decision Support:**
  Management can analyze sales, customer trends, high-demand categories, and stock turnover.
