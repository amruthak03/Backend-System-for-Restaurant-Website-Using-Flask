# Restaurant Backend System Using Flask

This project implements the backend system for a restaurant website using Flask. It includes functionalities for customer and vendor management, order placement, item management, and administrative control. The backend is designed with a role-based authentication system and supports various actions like signup, login, item management, and order tracking.

## Features
- User Authentication
  - Signup and login for customers, vendors, and admins.
  - Role-based access control with different permissions for customers (level 0), vendors (level 1), and admins (level 2).
 
- Vendor Management
  - Vendors can add items to the menu with details such as name, price, quantity, and calories.
  - Vendors can view all their items and manage them.
 
- Order Management
  - Customers can place orders with selected items.
  - Admins can view and manage all orders placed by customers.

- Database Models
  - User: Stores information about customers, vendors, and admins.
  - Item: Stores menu items with vendor and nutritional details.
  - Order: Stores orders placed by customers, linked to the user and items.
  - OrderItems: A relationship table for orders and ordered items, tracking quantities.

  ## Project Structure
  - app/models.py: Contains database models for User, Item, Order, and OrderItems.
  - app/apis.py: Contains API routes for signup, login, order management, item management, and role-based operations.
  - main.py: Starts the Flask application and handles routing.
  - requirements.txt: Lists all the necessary dependencies for the project.
 
## Installation
