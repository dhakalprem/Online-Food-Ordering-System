## 🍔💻 Online Food Ordering System – ASP.NET + C# + SQL Server 

An Online Food Ordering System is a web application where users can browse food menus, place orders, and make payments online.

This project is built using:

ASP.NET

C#

SQL Server

HTML / CSS / JavaScript for frontend

The system is commonly used in restaurants, cafes, and food delivery services.

## 1️⃣ Purpose of Online Food Ordering System

The system allows customers to:

View food menu

Add food items to cart

Place orders online

Track order status

Example order:

Customer: Rahul
Food Item: Pizza
Quantity: 2
Price: ₹300
Total: ₹600

## 2️⃣ Main Modules of the System

1. User Registration & Login

Customers must register before ordering.

Fields:

UserID
Name
Email
Password
Phone
Address

Example:

Name: Amit Kumar
Email: amit@gmail.com
Phone: 9876543210

2. Food Menu Management

Displays available food items.

Fields:

FoodID
FoodName
Category
Price
Description
Image

Example:

Food: Burger
Category: Fast Food
Price: ₹120

3. Cart System

Customers can add food items to a cart.

Example cart:

Cart
------------------
Burger      ₹120
Pizza       ₹300
Cold Drink  ₹50

Total = ₹470

4. Order Management

Stores order details.

Example:

OrderID: 101
Customer: Rahul
Total: ₹470
Order Date: 10-03-2026
Status: Pending

5. Admin Panel

Admin manages the system.

Admin functions:

Add food items

Update food prices

Delete food items

View customer orders

## 3️⃣ System Architecture

The project follows 3-tier architecture.

Presentation Layer
(ASP.NET Web Pages)

        ↓

Business Logic Layer
(C# Classes)

        ↓

Data Access Layer
(ADO.NET / SQL Queries)

        ↓

Database
(SQL Server)

## 4️⃣ Project Structure

Example folder structure:

OnlineFoodOrdering
│
├── Pages
│   ├── Login.aspx
│   ├── Register.aspx
│   ├── Menu.aspx
│   ├── Cart.aspx
│   ├── Order.aspx
│
├── Admin
│   ├── AddFood.aspx
│   ├── ManageOrders.aspx
│
├── App_Code
│   ├── Food.cs
│   ├── Order.cs
│
├── Database
│   └── DBConnection.cs
│
└── Web.config

## 5️⃣ Database Design

Users Table

Users
--------
UserId
Name
Email
Password
Phone
Address

FoodItems Table

FoodItems
-----------
FoodId
FoodName
Category
Price
Description
Image

Orders Table

Orders
--------
OrderId
UserId
OrderDate
TotalAmount
Status

OrderDetails Table

OrderDetails

-------------
OrderDetailId
OrderId
FoodId
Quantity
Price

## 6️⃣ ER Diagram

Users
   |
   | (1)
   |
   |------< Orders

Orders
   |
   | (1)
   |
   |------< OrderDetails
               |
               |
             FoodItems

Meaning:

One user → many orders

One order → many food items

## 7️⃣ Database Connection Example (C#)

Example using ADO.NET:

using System.Data.SqlClient;

string connectionString =
"Server=localhost;Database=FoodDB;Trusted_Connection=True;";

SqlConnection con = new SqlConnection(connectionString);

con.Open();

Response.Write("Database Connected");

con.Close();

## 8️⃣ Insert Order Example

string query = "INSERT INTO Orders(UserId,TotalAmount) VALUES(@uid,@total)";

SqlCommand cmd = new SqlCommand(query, con);

cmd.Parameters.AddWithValue("@uid", userId);
cmd.Parameters.AddWithValue("@total", total);

con.Open();
cmd.ExecuteNonQuery();
con.Close();

## 9️⃣ Display Food Menu Example

string query = "SELECT * FROM FoodItems";

SqlCommand cmd = new SqlCommand(query, con);

con.Open();

SqlDataReader reader = cmd.ExecuteReader();

while(reader.Read())
{
    Response.Write(reader["FoodName"]);
}

con.Close();

## 🔟 Example Workflow

Customer registers
      ↓
Login to system
      ↓
Browse food menu
      ↓
Add items to cart
      ↓
Place order
      ↓
Admin processes order
      ↓
Food delivered

## 1️⃣1️⃣ System Features

✔ User registration & login
✔ Food menu display
✔ Shopping cart system
✔ Order placement
✔ Admin dashboard
✔ Order tracking

## 1️⃣2️⃣ Real-World Usage

Online Food Ordering Systems are used by:

Restaurants

Fast food chains

Food delivery companies

Cafes

Examples of real apps:

Zomato

Swiggy

## ✅ In simple words

An Online Food Ordering System built with ASP.NET and C# is a web application where customers can browse food items, place orders online, and restaurants can manage orders using a SQL Server database.