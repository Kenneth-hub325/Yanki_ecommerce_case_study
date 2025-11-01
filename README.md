🛒 **Yanki E-Commerce ETL Project**

📘 **Overview**
The Yanki E-Commerce ETL Project showcases a complete Extract, Transform, and Load (ETL) process using an online retail dataset.
The goal of this project was to take unstructured sales data and convert it into clean, normalized tables that can easily be used for analysis or database storage.
It follows proper data engineering steps — cleaning, transformation, normalization, and data export — all implemented in Python with Pandas.

---

⚙️ **Project Objectives**

* Extract data from the raw CSV file.
* Transform the data by cleaning and standardizing formats.
* Normalize and organize it into relational tables.
* Load the cleaned data into structured CSV files.
* Create an ER diagram showing table relationships.

---

🏗️ **Data Model (ER Diagram)**
The data model shows how the e-commerce tables relate to one another.
Each **customer** can place multiple **orders**, each **order** contains multiple **products**, and every order is linked to a **payment method** and **shipping address**.

The final tables created are:

1. Customers table — stores customer details like name, email, and phone number.
2. Products table — contains product names, brands, categories, and prices.
3. Orders table — keeps records of customer purchases including quantity, price, and date.
4. Payment method table — holds payment type and transaction status.
5. Shipping address table — records the customer’s delivery address and region.

---

🧩 **Step 1: Importing Libraries**
The process started by importing the necessary Python libraries for data manipulation.

```python
import numpy as np
import pandas as pd
```

These libraries made it easy to clean, analyze, and reshape the data.

---

📥 **Step 2: Extraction Layer**
The raw dataset named *yanki_ecommerce.csv* was loaded using Pandas.
Basic checks such as `.head()`, `.info()`, and `.columns` were used to understand the structure and identify missing values or incorrect data types.

---

🧹 **Step 3: Data Cleaning and Transformation**
The raw data contained missing and inconsistent values, which were fixed during this stage.

• Rows without an Order_ID or Customer_ID were removed because they represented incomplete transactions.
• Missing values in the State column were also dropped for accuracy.
• The Order_Date column was converted from text into a proper datetime format using `pd.to_datetime()` so that time-based analysis could be done correctly.

After cleaning, the dataset was divided into smaller, organized tables to reduce redundancy and make future analysis easier.

---

📦 **Step 4: Data Normalization**
The dataset was normalized into separate tables, each focused on a single entity.
Each table was created by selecting relevant columns and removing duplicates.

• Customers_df – Customer_ID, Customer_Name, Email, Phone_Number
• Products_df – Product_ID, Product_Name, Brand, Category, Price
• Shipping_address_df – Shipping_ID, Customer_ID, Shipping_Address, City, State, Country, Postal_Code
• Orders_df – Order_ID, Customer_ID, Product_ID, Quantity, Total_Price, Order_Date
• Payment_method_df – Order_ID, Payment_Method, Transaction_Status

A unique Shipping_ID index was created to serve as a primary key for the shipping table.

---

💾 **Step 5: Loading Layer**
Each cleaned and normalized table was exported as a separate CSV file and saved in the “cleandata” folder.
This step ensures the data can easily be loaded into databases or used for further analysis.

Example:

```python
customer_df.to_csv('dataset/cleandata/customers.csv', index=False)
```

All tables — customers, products, orders, payments, and shipping — were successfully saved.

---

✅ **Final Outcome**
After the ETL process, the data became fully structured and analysis-ready.
The final version:

* Has no missing or invalid records.
* Uses consistent datatypes and naming.
* Follows the third normal form (3NF).
* Includes all relationships clearly defined through primary and foreign keys.

The result is a complete, reliable dataset ready for visualization, reporting, or storage in a SQL database.

---

🧰 **Tools and Technologies Used**

* Python 3
* Pandas
* NumPy
* Jupyter Notebook
* CSV files for storage
* Relational data modeling (ER diagram)

---

🚀 **Future Improvements**

* Automate the ETL process with Apache Airflow or Prefect.
* Load the cleaned tables into a relational database such as PostgreSQL.
* Create dashboards with Power BI or Tableau for business insights.
* Expand the data model to include suppliers, inventory, and delivery tracking.

---

📁 **Project Structure**
Yanki_Ecommerce_ETL
│
├── dataset
│   ├── rawdata → contains the original yanki_ecommerce.csv file
│   └── cleandata → contains all cleaned and normalized CSV tables
│
├── yanki_etl.ipynb → main notebook with ETL steps
├── Data_Model.png → entity-relationship diagram
└── README.txt → project documentation

---

✨ **Author**
Kenneth Chizaram Mbadugha
Data Engineer
Email: [mbadughakenneth2021@gmail.com](mailto:mbadughakenneth2021@gmail.com)

