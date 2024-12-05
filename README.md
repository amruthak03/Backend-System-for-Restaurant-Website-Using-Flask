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
1. Clone the repository:
  ```bash
  git clone https://github.com/amruthak03/restaurant-backend-flask.git
  cd restaurant-backend-flask
  ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up the database by running the necessary migrations or creating the tables manually through a database client.
5. Run the Flask application:
   ```bash
   python main.py
   ```
The application will run on http://127.0.0.1:8000

## API Endpoints
- POST /signup
  Sign up a new user (customer, vendor, or admin).
  - Parameters: name, username, password, level (0 = customer, 1 = vendor, 2 = admin).
 
- POST /login
  Log in a user using their username and password.
  - Parameters: username, password.
 
- POST /logout
  Log out the current user.

- POST /add_vendor
  Add a vendor (only for customers).
  - Parameters: user_id.
 
- POST /add_item
  Add an item to the vendor’s menu (only for logged-in vendors).
  - Parameters: item_id, item_name, restaurant_name, available_quantity, unit_price, calories_per_gm.
 
- POST /place_order
  Place an order (only for logged-in customers).
  - Parameters: customer_id, vendor_id, item_id, quantity.
 
- GET /get_all_orders_by_customer
  Get all orders placed by a customer (only for logged-in users).
  - Parameters: customer_id.

- GET /get_all_orders
  Get all orders (only for admins).

## Technologies Used
- Flask: Python web framework for building RESTful APIs.
- SQLAlchemy: ORM for managing database operations.
- MySQL: Lightweight database for development purposes (can be swapped with other databases).
- Python: Main programming language for backend logic.

