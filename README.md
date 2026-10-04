# WHatNWXT-VISION-MOTORS
WhatNext Vision Motors is a smart mobility platform that connects customers, vehicles, and services to make vehicle management simple, efficient, and future-ready.



# 🚗 WhatNext Vision Motors

### Shaping the Future of Mobility with Innovation and Excellence

**WhatNext Vision Motors** is a Salesforce CRM-based vehicle management and sales automation project developed to simplify and automate the vehicle sales process.

The system provides centralized management of **vehicles, dealers, customers, orders, test drives, and service requests** while reducing manual work through Salesforce automation.

---

## 📌 Project Overview

Traditional vehicle sales processes often involve manual management of customer orders, dealer allocation, and vehicle inventory. This can lead to delays, stock mismatches, inefficient order processing, and poor customer experience.

WhatNext Vision Motors addresses these challenges using **Salesforce CRM** to automate important business processes such as:

* Vehicle inventory management
* Customer management
* Dealer management
* Vehicle order processing
* Automatic dealer assignment
* Stock availability validation
* Test drive reminders
* Automated order and stock updates

---

## 🎯 Objectives

* Develop a centralized Salesforce CRM system for vehicle sales management.
* Manage vehicle, dealer, customer, and order information efficiently.
* Automatically assign dealers based on customer location.
* Prevent orders when vehicles are out of stock.
* Automate order processing and status updates.
* Send automated reminders for scheduled test drives.
* Reduce manual work using Salesforce automation.
* Improve customer satisfaction and operational efficiency.

---

## 🛠️ Technologies Used

* **Salesforce CRM**
* **Salesforce Lightning App**
* **Salesforce Flow**
* **Apex**
* **Apex Triggers**
* **Trigger Handler**
* **Batch Apex**
* **Scheduled Apex**
* **Custom Objects & Fields**
* **Salesforce Email Automation**

---

## 🏗️ Salesforce Custom Objects

| Custom Object                | Purpose                                      |
| ---------------------------- | -------------------------------------------- |
| `Vehicle__c`                 | Stores vehicle details and stock information |
| `Vehicle_Dealer__c`          | Stores dealer information and location       |
| `Vehicle_Customer__c`        | Stores customer details                      |
| `Vehicle_Order__c`           | Manages vehicle orders                       |
| `Vehicle_Test_Drive__c`      | Manages test drive bookings                  |
| `Vehicle_Service_Request__c` | Manages vehicle service requests             |

The project uses relationships between these objects to connect customers, vehicles, dealers, orders, test drives, and service requests.

---

## ⚙️ Key Features

### 1. 🚘 Vehicle Management

The system stores:

* Vehicle name
* Vehicle model/type
* Stock quantity
* Price
* Dealer
* Availability status

Vehicle status can be:

* Available
* Out of Stock
* Discontinued

---

### 2. 👤 Customer Management

Customer information includes:

* Customer name
* Email
* Phone
* Address
* Preferred vehicle type

---

### 3. 🏢 Dealer Management

Dealer information includes:

* Dealer name
* Dealer location
* Dealer code
* Phone
* Email

---

### 4. 📦 Vehicle Order Management

Customers can place vehicle orders through the system.

Order statuses include:

* Pending
* Confirmed
* Delivered
* Canceled

The system validates vehicle stock before allowing an order to proceed.

---

### 5. 📍 Automatic Dealer Assignment

A **Record-Triggered Flow** automatically processes a new pending vehicle order and retrieves customer information to assign a dealer based on the customer's location.

**Flow:**
`Vehicle Order → Get Customer Information → Find Dealer → Assign Dealer`

---

### 6. 📧 Test Drive Reminder

A Salesforce Flow automatically sends an email reminder to customers before their scheduled test drive.

The reminder is scheduled **one day before the test drive date**.

Example notification:

> Reminder: Your Test Drive is Tomorrow!

---

### 7. 🔒 Stock Validation Using Apex

An Apex Trigger Handler validates vehicle stock before an order is confirmed.

If the vehicle has no available stock, the system prevents the order and displays an error message.

```text
This vehicle is out of stock. Order cannot be placed.
```

---

### 8. 📉 Automatic Stock Update

When a confirmed vehicle order is placed, the system automatically decreases the vehicle stock quantity.

Example:

```text
Available Stock: 5
        ↓
Vehicle Ordered
        ↓
Updated Stock: 4
```

---

### 9. 🔄 Batch Apex

Batch Apex is used to process vehicle orders periodically.

If a vehicle was previously unavailable, the batch process can update the order after new stock becomes available.

---

### 10. ⏰ Scheduled Apex

Scheduled Apex is used to execute automated batch processing at a scheduled time.

This reduces the need for manual processing of vehicle orders.

---

## 🔄 System Workflow

```text
Customer
   ↓
Select Vehicle
   ↓
Create Vehicle Order
   ↓
Check Vehicle Stock
   ↓
 ┌───────────────────────┐
 │ Vehicle Available?    │
 └───────────────────────┘
       ↓           ↓
      YES          NO
       ↓           ↓
 Confirm Order   Keep Pending
       ↓           ↓
 Update Stock    Batch Processing
       ↓           ↓
 Dealer Assignment
       ↓
 Order Processing
       ↓
 Vehicle Delivery
```

---

## 🤖 Salesforce Automation

The project uses multiple Salesforce automation technologies:

| Automation            | Purpose                                |
| --------------------- | -------------------------------------- |
| Record-Triggered Flow | Dealer assignment and order automation |
| Flow + Scheduled Path | Test drive reminder                    |
| Apex Trigger          | Stock validation                       |
| Trigger Handler       | Reusable business logic                |
| Batch Apex            | Periodic order processing              |
| Scheduled Apex        | Automated scheduled execution          |

---

## 📊 Project Architecture

```text
                    Salesforce CRM
                          │
        ┌─────────────────┼─────────────────┐
        │                 │                 │
     Customers         Vehicles          Dealers
        │                 │                 │
        └────────────┬────┴────┬────────────┘
                     │         │
                  Orders    Test Drives
                     │         │
                     └────┬────┘
                          │
                    Service Requests
                          │
              ┌───────────┴───────────┐
              │                       │
         Salesforce Flow          Apex Automation
              │                       │
       Dealer Assignment       Apex Trigger
       Email Reminder          Trigger Handler
                               Batch Apex
                               Scheduled Apex
```

---

## 📈 Advantages

* Centralized vehicle, dealer, customer, and order management
* Automatic dealer assignment
* Prevents out-of-stock orders
* Better vehicle stock management
* Automated order status updates
* Automated test drive reminders
* Reduced manual work
* Improved processing efficiency
* Better customer experience

---

## ⚠️ Limitations

* Salesforce configuration requires maintenance.
* Apex and automation require technical knowledge.
* Stock information must remain accurate.
* Automation requires proper testing.
* Configuration changes may affect dependent processes.

---

## 🚀 Future Scope

The project can be further enhanced with:

* 🤖 AI-based vehicle recommendations
* 📍 GPS-based dealer location services
* 💳 Online payment integration
* 📱 Mobile application
* 📊 Advanced sales and inventory dashboards
* 🔗 External inventory management integration
* 👤 Customer self-service features
* 📈 Predictive vehicle demand analysis

---

## 👥 Team Members

| Name               | Role        |
| ------------------ | ----------- |
| **Sanjaya B**      | Team Leader |
| **Fathima H**      | Team Member |
| **Mubharak C**     | Team Member |
| **Ashik Ahamed A** | Team Member |

**College:** University College of Engineering, Pattukkottai
**College Code:** 8221

The project document identifies Sanjaya B as the team leader and Fathima H, Mubharak C, and Ashik Ahamed A as team members.

---

## 🎓 Project Conclusion

WhatNext Vision Motors brings vehicle, dealer, customer, and order management into a centralized Salesforce CRM platform.

By combining **Salesforce Flows, Apex Triggers, Trigger Handlers, Batch Apex, and Scheduled Apex**, the system automates stock validation, dealer assignment, order processing, test drive reminders, and stock updates.

The solution helps reduce manual effort, improve operational efficiency, and provide a better customer experience.

---

## ⭐ Project Highlights

**Salesforce CRM | Vehicle Management | Inventory Automation | Apex | Salesforce Flow | Batch Apex | Scheduled Apex | CRM Automation**
