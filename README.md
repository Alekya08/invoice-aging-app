# invoice-aging-app
This project is a simple web application that helps manage customer invoices and track their payments.  It calculates how much has been invoiced, how much has been received, how much is still outstanding,  and what percentage of invoices are overdue.
The user interface is built with **Streamlit** and the data is stored in a **MySQL database**.
---
## How to Set It Up
1. **Install Python**  
2. **Set up a virtual environment** inside the project folder:  
   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```  
3. **Install the required libraries**:  
   ```bash
   pip install streamlit pandas sqlalchemy pymysql pytest
   ```  
4. **Create a MySQL database**:  
   - Open MySQL Workbench.  
   - Run:  
     ```sql
     CREATE DATABASE invoicedb;
     USE invoicedb;
     ```  
   - Load the schema:  
     ```sql
     SOURCE C:/invoice-aging-app/invoice-aging-app/sql/schema_mysql.sql;
     ```  
   - Load sample data:  
     ```sql
     SOURCE C:/invoice-aging-app/invoice-aging-app/sql/sample_data.sql;
     ```
     5. **Configure the app**:  
   - Copy `.env.example` to `.env`.  
   - Edit the file and set your MySQL connection:  
     ```
     DATABASE_URL=mysql+pymysql://root:YOURPASSWORD@localhost:3306/invoicedb
     ```
6. **Run the app**:  
   ```bash
   streamlit run app/app.py
   ```  
   Open the link shown (http://localhost:8501) in your browser.
---
## What You Can Do in the App
- Filter invoices by customer and date.  
- See KPIs: *Total Invoiced, Total Received, Total Outstanding, % Overdue*.  
- View invoices in a table (overdue ones are highlighted).  
- Record new payments (partial or full).  
- See a chart of the **Top 5 customers by outstanding balance**.
---
## Screenshots
- Dashboard.  
- Record Payment form.  
- Top 5 Customers chart.  
---
## Notes
- This project was tested with **MySQL 9.4** and **Streamlit 1.40+**.  
- If payments are added, the dashboard automatically refreshes to show the new outstanding balances.
