# ⚡ SQL.js Studio - Live Execution Visualizer

A lightweight, fully client-side SQL workbench designed to visualize the logical execution flow of SQL queries in real-time. Powered by **SQL.js** (SQLite compiled to WebAssembly), this tool breaks down queries into granular steps and animates the data retrieval process row-by-row.

*(Replace this link with an actual screenshot of your application)*

## 🚀 Features

* **Granular Execution Pipeline:** Visualizes the logical order of operations (`FROM` → `JOIN` → `WHERE` → `SELECT`) in a dedicated sidebar.
* **Row-by-Row Join Animation:** Simulates the "Nested Loop Join" process, highlighting rows as they are Scanned (Yellow), Read (Pink), and Matched (Green).
* **Real-Time Output:** Results are streamed to the "Final Output" table instantly as matches are found, rather than waiting for the entire query to finish.
* **Fully In-Browser Engine:** Uses [SQL.js](https://sql.js.org/) to run a full SQLite database inside your browser. No server setup required.
* **Interactive Schema Editor:**
* Add/Remove tables.
* Add/Remove columns and rows.
* Directly edit cell values.


* **Smart Aliasing:** Automatically handles column name collisions (e.g., `o.id` vs `c.id`) during intermediate join steps.
* **Execution Controls:**
* Adjust animation speed (Slow motion to Fast forward).
* Dark/Light Mode toggle.
* Reset Data button.



## 🛠️ Installation & Usage

This project is a **single-file application**. There are no build steps, NPM installs, or backend servers required.

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/sql-js-studio.git

```


2. **Open the file:**
Simply double-click `index.html` to open it in any modern web browser (Chrome, Firefox, Edge, Safari).
*Note: The application requires an internet connection initially to load the SQL.js library via CDN.*

## 📖 How to Use

### 1. Define Your Data

Use the **Left Panel** to manage your database schema.

* Click **+ Add** to create a new table.
* Use the **+ Row** / **+ Col** buttons on specific tables to expand them.
* Click on any cell to edit the data directly.

### 2. Write a Query

Use the **Query Editor** on the right. Standard SQLite syntax is supported.

* **Example Query:**
```sql
SELECT
    o.id, c.name, p.name as Product
FROM Orders o
JOIN Customers c ON o.customer_id = c.id
JOIN Products p ON o.product_id = p.id
WHERE o.quantity > 0

```



### 3. Run & Visualize

Click the **▶ Run & Visualize** button.

* **Animation:** Watch the "Process Visualization" stage to see tables being scanned and joined.
* **Pipeline:** Track the current stage of the query in the "Execution Pipeline" sidebar.
* **Results:** Watch the "Final Output" table populate in real-time.

## ⚙️ Technical Details

* **Core Engine:** [SQL.js](https://www.google.com/search?q=https://github.com/sql-js/sql.js) (WASM).
* **Visualization Logic:** The application uses a custom JavaScript parser to identify query clauses (`FROM`, `JOIN`, `WHERE`) and constructs a visual simulation of the execution plan. It highlights DOM elements corresponding to data rows to visualize scan operations.
* **Layout:** Built with CSS Grid and Flexbox for a responsive, dashboard-style layout.

## 🤝 Contributing

Contributions are welcome! If you'd like to improve the visualization logic or add support for more complex SQL clauses:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

**Created with ❤️ using HTML, CSS, JavaScript, and Google Gemini.**
