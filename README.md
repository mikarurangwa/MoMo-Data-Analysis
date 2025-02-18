**MoMo Dashboard**

MoMo Dashboard is a web-based financial transaction analysis tool designed to help users visualize and filter their Mobile Money (MoMo) transactions. It provides an interactive dashboard with categorized transactions, a bar chart representation of spending, and filtering capabilities.

**Features**

**Dashboard Overview**: Displays categorized transactions with total amounts and counts.

**Interactive Chart**: Bar chart visualization of financial data.

**Search Functionality**: Allows users to search transactions by keywords.

**Filtering Options**: Users can filter transactions by:
Transaction Type (Incoming Money, Transfers, Withdrawals, etc.)
Date Range
Amount Range

**Modal for Details**: Clicking on a transaction category or applying filters displays relevant transactions.
Responsive Design: Works seamlessly on desktops, tablets, and mobile devices.

**Running the Application**

1. **Extracting SMS Data from XML File**

The application begins by extracting mobile money transaction data from an XML file. The extraction process involves parsing the XML and structuring it into a CSV file for easy insertion into MySQL.

**Steps to Extract Data**

1. Place the XML file (modified_sms_v2.xml) in the appropriate directory.
2. Run the Python script to extract and process transactions:
  -This script reads the XML file.
  -It extracts key details such as transaction ID, amount, date, and category.
  -The extracted data is saved as a CSV file.

2. **Setting Up and Accessing MySQL Database**
To store transaction data, a MySQL database is used.

**Steps to Set Up MySQL**
1. Start the MySQL server on your local machine.
2. Access MySQL from the command line or MySQL Workbench.
3. Create a new database:
CREATE DATABASE momo_data;
4. Create a user with access to the database:

CREATE USER 'momo_data'@'localhost' IDENTIFIED BY 'momo_password';
GRANT ALL PRIVILEGES ON momo_data.* TO 'momo_user'@'localhost';
FLUSH PRIVILEGES;
5. Switch to the newly created database:

USE momo_data;
6. Import the table structure and sample data by running:

SOURCE path/to/table.sql;

3. **Uploading Extracted CSV Data to MySQ**
Once the database is set up, the extracted CSV file needs to be inserted into the database.

**Steps to Insert CSV Data**

1. Run python Data insert.py
- This script import the CSV file and inserts data into MySQL.
- It converts date formats, ensures numerical values are correct, and handles errors.
2. After execution, the MySQL database is populated with transaction data.

**4. Running the Flask Application**

With the database ready, the Flask web application can be started.

**Steps to Run the App**
1. Start the Flask server

python app.py

2. Open a browser and visit:

http://127.0.0.1:5000

3. The dashboard loads, displaying transaction data from MySQL.

**Technologies Used**

**Frontend:**
1. HTML
2. CSS

**Backend:**
1. MySQL (Data storage)
2. Pandas (Data processing)
3. XML Parsing (Extracting SMS data)

**Future Improvements**

Optimize performance for large datasets.
Add authentication for personalized dashboards.
Implement AI-based spending insights.

**Contributors**

Developed by
1. Kakooza Mahad 
2. El Hadji Faly Seck 
3. Rurangwa Mika
4. Julio Elise Hakizimana
