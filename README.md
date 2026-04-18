# 🐄 Dairy Management System — Flask

**Dairy Management System** is a **modern full-stack web application** built with **Python, Flask, and MySQL**, designed to streamline dairy business operations with a clean and intuitive web interface.

The system supports **secure Admin authentication**, allowing administrators to manage customers, record daily milk collection (Morning & Evening), maintain fat/SNF-based pricing rate charts, and monitor all dairy operations efficiently through a structured web dashboard.

This project demonstrates **Flask web development, MySQL database integration, modular Blueprint architecture, session-based authentication, and real-world CRUD workflows**, making it ideal for academic mini-projects and portfolio showcases.

---

## ✨ Key Principles

1. **Secure Admin Access** – Session-based login with protected routes
2. **Customer Management** – Add, view, and manage dairy customers with unique codes
3. **Milk Collection Tracking** – Morning & Evening shift collection with fat/SNF records
4. **Rate Chart System** – Fat and SNF based dynamic pricing management
5. **Modular Architecture** – Clean Blueprint-based Flask structure with `.env` config

> This system is both **practical and educational**, demonstrating how real-world dairy management systems are built using Python and Flask.

---

## 🧩 System Overview

The application is built around a secure admin panel with four core modules:

### 👨‍💼 Admin
- Secure login with session management
- All routes are protected — unauthenticated users redirected to login
- Full control over all dairy operations

### 👥 Customer Management
- Add new dairy customers with unique customer codes
- Support for Cow 🐄 and Buffalo 🐃 milk types
- Customer status: Active (`ON`) / Inactive (`OFF`)
- View all registered customer records

### 🥛 Milk Collection
- Record daily milk collection — Morning & Evening shifts
- Capture Liters, Fat %, SNF %, Rate, and Total amount
- View complete collection history

### 📊 Rate Chart
- Add fat/SNF based milk pricing rates
- Separate rates for Cow and Buffalo milk
- View current and historical rate charts

---

## 🔗 Core Workflow

- Admin logs in securely
- Manages customer database (add/view)
- Records daily milk collection with shift details
- Maintains fat/SNF pricing rate charts
- Views all records through the dashboard

> Ensures smooth dairy business operations with fully web-based, database-backed management.

---

## ⚙️ Features

- Flask web application (Python)
- Secure session-based admin authentication
- Customer add & view system with Cow/Buffalo type support
- Morning & Evening shift milk collection recording
- Fat & SNF based rate chart management
- Admin dashboard homepage
- Blueprint-based modular Flask architecture
- MySQL-backed persistent storage
- Environment variable configuration via `.env`
- Sample data auto-inserted on DB setup

---

## 📁 Project Structure

```bash
Dairy-Management-System-Flask/
│
├── assets/                        # Screenshots / images
│
├── app/
│   ├── __init__.py                # App factory (create_app)
│   └── ...                        # Blueprints & API routes
│
├── .env                           # Environment variables (DB credentials)
├── config.py                      # App configuration class
├── db_setup.py                    # One-time database + sample data setup
├── main.py                        # Entry Point & page routing
├── requirements.txt               # Python dependencies
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

### 1️⃣ Prerequisites
- Python 3.10+
- Flask 3.0+
- MySQL Server (running locally)
- pip package manager

### 2️⃣ Clone Repository
```bash
git clone https://github.com/ShakalBhau0001/Dairy-Management-System-Flask.git
cd Dairy-Management-System-Flask
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ Configure Environment
Open the `.env` file and update with your MySQL credentials:
```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=dairy_management
SECRET_KEY=dairy_secret_key
```

### 5️⃣ Setup Database
```bash
python db_setup.py
```

> This creates the database, all tables, and inserts sample customers & rate data automatically.

### 6️⃣ Run Application
```bash
python main.py
```

Open your browser and visit:
```
http://127.0.0.1:5000
```

### 🔑 Default Login Credentials
```
Username : admin
Password : admin123
```

---

## 🔑 Modules

### Login System
- Admin login interface at `/login`
- Session-based authentication
- All protected routes redirect to login if session is missing

### Dashboard
- Admin homepage after login (`/dashboard`)
- Central navigation to all modules

### Customer Management
- Add new customer → `/customers/add`
- View all customers → `/customers/view`

### Milk Collection
- Add daily collection entry → `/collection/add`
- View collection records → `/collection/view`

### Rate Chart
- Add pricing rates → `/rates/add`
- View rate charts → `/rates/view`

---

## 🧠 Route Overview

| Route | Description |
|---|---|
| `/` | Redirects to login |
| `/login` | Admin login page |
| `/dashboard` | Admin homepage (protected) |
| `/customers/add` | Add new customer (protected) |
| `/customers/view` | View all customers (protected) |
| `/collection/add` | Add milk collection (protected) |
| `/collection/view` | View collection records (protected) |
| `/rates/add` | Add rate chart entry (protected) |
| `/rates/view` | View rate charts (protected) |

> All routes except `/login` are session-protected.

---

## 🗄️ Database Design

### `users` — Admin Accounts
```sql
id, first_name, last_name, username, mobile, password, created_at
```

### `customers` — Dairy Customers
```sql
id, code, first_name, last_name, full_name, mobile,
milk_type ENUM('Cow','Buffalo'), status ENUM('ON','OFF'), created_at
```

### `collection` — Daily Milk Collection
```sql
id, date, time ENUM('Morning','Evening'),
milk_type ENUM('Cow','Buffalo'), customer_code,
liters, fat, snf, rate, total, created_at
```

### `rates` — Pricing Rate Chart
```sql
id, milk_type ENUM('Cow','Buffalo'), fat, snf, rate, date, created_at
```

---

## 📦 Sample Data (Auto-inserted on Setup)

### Customers
| Code | Name | Milk Type | Status |
|---|---|---|---|
| 10 | Ramesh P. Mane | Buffalo | ON |
| 20 | Dinesh R. Kale | Buffalo | ON |
| 30 | Atul S. Mile | Cow | ON |
| 40 | Pradip H. Pise | Cow | OFF |
| 50 | Rohan Y. Patil | Cow | ON |

### Rate Chart
| Milk Type | Fat % | SNF % | Rate (₹/L) |
|---|---|---|---|
| Cow | 3.5 | 8.0 | 28.00 |
| Cow | 4.0 | 8.5 | 30.00 |
| Buffalo | 6.0 | 9.0 | 38.00 |
| Buffalo | 6.5 | 9.5 | 41.00 |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python 3.10+ | Backend language |
| Flask 3.0.0 | Web framework |
| MySQL | Relational database |
| mysql-connector-python 8.3.0 | Database connectivity |
| python-dotenv 1.0.0 | Environment config |
| HTML / CSS | Frontend templates |

---

## 🖼️ Screenshots

### 1. Login Screen
![Login](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/Login.png)

### 2. Dashboard
![Dashboard](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/Dashboard.png)

### 3. Add Customer
![Add Customer](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/AddCustomer.png)

### 4. Customer Details
![Customer Details](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/CustomerDetails.png)

### 5. Add Collection
![Add Collection](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/AddCollection.png)

### 6. View Collection
![View Collection](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/ViewCollection.png)

### 7. Rate Chart
![Rate Chart](https://github.com/ShakalBhau0001/Dairy-Management-System-Flask/blob/main/assets/RateChart.png)

---

## 🛣️ Future Improvements

- PDF bill / receipt generation for customers
- Monthly & yearly summary reports
- Customer-wise collection graphs & analytics
- Multi-admin role support
- REST API endpoints
- Mobile-responsive UI improvements
- SMS/WhatsApp notification for bill delivery

---

## 🙏 Acknowledgments

- Python community
- Flask documentation & contributors
- MySQL
- Open-source contributors

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Contributors

> Developer: **Shakal Bhau**

> GitHub: **[ShakalBhau0001](https://github.com/ShakalBhau0001)**

---
