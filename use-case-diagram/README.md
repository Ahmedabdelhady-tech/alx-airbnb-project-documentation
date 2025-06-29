# Use Case Diagram

This directory contains the use case diagram for the Airbnb-like application, visualizing the interactions between actors and key system functionalities.

## 🗂️ Files Included

* `use-case-diagram.png` — Exported PNG image of the use case diagram.
* `README.md` — This file explaining the diagram’s purpose and how to view it.

## 🎯 Use Case Overview

The use case diagram captures the following actors and primary use cases:

### Actors

* **Guest**: A user who browses properties, makes bookings, and writes reviews.
* **Host**: A user who lists properties, updates listings, and views bookings.
* **Admin**: Manages users, properties, and oversees system operations.

### Key Use Cases

1. **User Registration & Authentication**

   * Register an account (Guest/Host)
   * Login/Logout

2. **Property Management** (Host)

   * Create property listing
   * Update listing details
   * Remove listing

3. **Property Browsing & Search** (Guest)

   * Browse listings
   * Search by location/price

4. **Booking Process** (Guest)

   * Select dates and book a property
   * View booking history

5. **Payment Processing** (Guest)

   * Submit payment for booking
   * View payment receipt

6. **Review & Rating** (Guest)

   * Leave a review and rating on completed stay

7. **Messaging** (Guest & Host)

   * Send inquiries
   * Respond to messages

8. **Administration** (Admin)

   * Approve or suspend users
   * Review flagged content

## 🚀 How to Create/Update Diagram

1. Open `https://app.diagrams.net/`.
2. Select **File → Open From → Device** and choose `use-case-diagram.drawio` (if provided).
3. Use **Use Case** shapes (Actors, Ellipses) from the **General** or **UML** section.
4. Draw actors on the left, use cases as ellipses, and connect with lines.
5. Export via **File → Export As → PNG** to generate `use-case-diagram.png`.
6. Commit both the `.drawio` and `.png` files to this directory.

## 📥 Viewing the Diagram

* Open `use-case-diagram.png` in any image viewer.
* Or open `use-case-diagram.drawio` in draw\.io to edit.

---

*Prepared as part of the ALX Software Engineering Documentation.*
