# Data Flow Diagram (DFD)

This directory contains the Data Flow Diagram (DFD) for the Airbnb-like application, illustrating how data moves through key system processes.

## 🗂️ Files Included

* `data-flow-diagram.drawio` — (Optional) Source file for editing the diagram in draw\.io.
* `data-flow.png` — Exported PNG image of the DFD.
* `README.md` — This documentation file explaining the diagram’s purpose and structure.

## 🎯 DFD Overview

The DFD covers the following core processes and data stores:

1. **User Management**

   * **Inputs:** Registration data, login credentials
   * **Process:** Validate and store user information
   * **Outputs:** Authentication tokens, user profiles

2. **Property Listings**

   * **Inputs:** Property details, images
   * **Process:** Create, update, delete property entries
   * **Outputs:** Property catalog

3. **Booking Process**

   * **Inputs:** Booking requests (user, property, dates)
   * **Process:** Check availability, calculate total price
   * **Outputs:** Booking confirmations, booking records

4. **Payment Processing**

   * **Inputs:** Payment details (amount, method)
   * **Process:** Process transaction via payment gateway
   * **Outputs:** Payment receipts, payment status

5. **Review & Messaging**

   * **Inputs:** Review ratings/comments, message texts
   * **Process:** Store feedback, deliver messages between users
   * **Outputs:** Review listings, user communications

## 🛠️ How to Create/Update Diagram

1. Open **draw\.io** at [https://app.diagrams.net](https://app.diagrams.net).
2. Select **File → New** and choose a blank diagram or open `data-flow-diagram.drawio`:

   * If new: choose **General → Flowchart** shapes.
3. Map out:

   * **External Entities:** User, Host, Admin
   * **Processes:** User Management, Property Listings, Booking, Payment, Review/Messaging
   * **Data Stores:** Users DB, Properties DB, Bookings DB, Payments DB, Reviews DB, Messages DB
   * **Data Flows:** Arrows showing flow between entities, processes, and data stores.
4. Label all flows clearly (e.g., "Booking Request", "Payment Info").
5. Export the diagram:

   * **File → Export As → PNG** → name it `data-flow.png`.
6. Save the source file:

   * **File → Save As → data-flow-diagram.drawio**.

## 📥 Viewing the Diagram

* Open `data-flow.png` in any image viewer for a quick overview.
* To edit, open `data-flow-diagram.drawio` in draw\.io.

---

*Prepared as part of the ALX Software Engineering Documentation.*
