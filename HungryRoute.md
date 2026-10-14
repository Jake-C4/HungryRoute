# HungryRoute - A Fast Grocery and Food Delivery Database

**Author** Jacob clark
**Date** 09/20/2026
**Class** DataBase Systems
**Version** 1.0.0

HungryRoute is backend database system for food and grocery delivery services that tracks stores, customers, orders, drivers, and payments and other promotions

---

## Revision History

| Date  | Version | Notes|
|-------|---------|------|
| 9/20/2026 | 1.0.0 | Outline for Phase 0 deliverable
| 10/9/2026 | 2.0.0 | Phase 1: ER Diagram, enitities, data dictionary, design, considerations

---

## Table of Contents
1. [Introductions]
    - [Purpose]
    - [Project Scope]
    - [Intended Audience]
2. [ER Diagram]
    - [People]
    - [Stores]
    - [Orders and Deliveries]
    - [Promos/Engagment]
3. [Prototype]

---

## 1. Introduction

### Purpose

HungryRoute is a database that replicates the backend of a food and grocery delivery service such as DoorDash or Uber Eats. The system is designed to release orders to drivers nearby in order fo grocery or restuarant chains through one application. The features are as follows:

- Keep record of different stores or restaurants in the area of the user, as well as the items they sell.
- Allows customers to place orders and track them.
- The database releases the order to a delivery driver in the area.
- Database also handles payments, promotions, and store and driver reviews.

### Project Scope
**In Scope:**
- Tracking Customer and Driver accounts since it is just those 2 roles
- Two different store types, either a restaurant or grocery.
- Orders, order status, and line items such as items, quantity, and price.
- Assign order/deliveries for drivers and delivery tracking
- Payments and promotional codes for orders.
- Customer reviews for drivers and stores

**Not In Scope**
- Passenger riding service
- No storing payment information, but there are records of transactions
- Store inventory tracking

### Intended Audience
- **Customers - ** are able to browes grocery stores for groceries or restaurants for take-out food, place orders, track deliveries, pay, and leave reviews for the store or drivers.
- **Drivers - ** are able to receive and accept orders/deliveries and get paid
- **Stores - ** are able to keep track and update their item inventory.
- **Administrators - ** be in charge of onboarding new restaurants or stores and goin through customer reviews.

---

## ER Diagram
Diagram 1 shows the full model, all entities, relationships, specialization, and constraints. Diagrams 2 to 6 show the attributes for each part of it. Rounded boxes are entities shown only for context; their attributes appear in the figure where they belong.

**Diagram 1**

![Diagram 1: Full ER/EER diagram](HungryRoute.drawio.png)
 
**Diagram 2: People and Accounts**
 
![Diagram 2: People and Accounts](People_Accounts.drawio.png)
 
**Diagram 3: Stores and Catalog**
 
![Diagram 3: Stores and Catalog](Stores.drawio.png)
 
**Diagram 4: Orders and Payment**
 
![Diagram 4: Orders and Payment](Orders_Payment.drawio.png)
 
**Diagram 5: Delivery and Route Tracking**
 
![Diagram 5: Delivery and Route Tracking](Delivery_Tracking.drawio.png)
 
**Diagram 6: Reviews**
 
![Diagram 6: Reviews](Reviews.drawio.png)

### People

- **Entity: USERS**
    - Attribute: UserID
    - Attribute: Name
    - Attribute: Email
    - Attribute: Phone
    - Relationship: Can either be a CUSTOMER or DRIVER but a user can be both

- **Entity: CUSTOMER**
    - Attribute: PaymentMethod
    - Relationship: Places ORDER
    - Relationship: Writes REVIEW
    - Relationship: has an ADDRESS

- **Entity: DRIVER**
    - Attribute: Has a LicenseNumber
    - Attribute: Has a Rating
    - Relationship: Can complete a DELIVERY
    - Relationship: Has a VEHICLE

- **Entity: ADDRESS**
    - Attribute: Has an AddressID
    - Attribute: Street
    - Attribute: City
    - Attribute: State
    - Attribute: Zip Code

- **Entity: VEHICLE**
    - Attribute: Has a VehicleID
    - Attribute: Make
    - Attribute: Model
    - Attribute: Year
    - Attribute: License plate

