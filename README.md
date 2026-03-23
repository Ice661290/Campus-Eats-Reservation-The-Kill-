# Canteen Food Queue Booking System (The Kill)

A web application designed to facilitate food ordering and queue management within the canteen of Huachiew Chalermprakiet University. It features an intuitive user interface for students and staff to order food in advance, along with a dedicated dashboard for vendors to manage orders efficiently.

---

## 🌟 Features

### 1. 🔐 User Management (Authentication)
* **Register:** Students can register using their student ID (UserID), name, and password. It includes password hashing for security and checks for duplicate IDs.
* **Unified Login:** A single login page can differentiate whether the user is a student or a vendor. The system checks the user database first; if no match is found, it checks the vendor database, automatically redirecting the user to the appropriate dashboard based on their role.

### 2. 🎓 User Features
* **Main Dashboard:** Displays a list of all available shops in the system, allowing users to click and view their menus.
* **Food Ordering and Shopping Cart:**
  * View menus, prices, and remaining stock in real-time.
  * Add items to the cart (utilizes sessionStorage for fast performance without needing to reload the page).
  * Adjust item quantities (increase/decrease) or remove items from the cart.
  * Features a Floating Cart Icon displaying the total number of selected items.
* **Checkout & Queue Generation:**
  * Upon confirmation, the system immediately deducts the food stock (utilizing Database Transactions to prevent data errors).
  * Automatically calculates the daily queue number for that specific shop.
  * Displays a receipt detailing the queue number and the number of people waiting ahead (Wait Queue).
* **Order Tracking:**
  * Includes a Clipboard icon to view the status of orders currently being prepared.
  * Features an on-screen popup alert when the shop marks the food as finished.
* **Receipt History:**
  * Includes a receipt icon to view past order history, retrieving order summaries from both the database and localStorage.

### 3. 🏪 Shop Dashboard Features
* **Menu Management:**
  * Add new menu items, along with setting prices and stock quantities.
  * Edit or delete existing menu items.
  * Guard Feature: Includes a safeguard that prevents vendors from deleting or editing menu items that are "currently in the queue" to avoid losing or corrupting customer order data.
* **Queue Management:**
  * Displays a notification banner if there are new orders or pending queues.
  * Shows a list of orders grouped by customer and order time (Grouped Orders), allowing the shop to see exactly what items a specific customer ordered in a single bill.
  * Displays an "in progress" status and provides a "Complete" button.
  * Once marked as complete, the status updates, and the system immediately sends a notification signal to the student's side.
