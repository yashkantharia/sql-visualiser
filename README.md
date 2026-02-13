# ⚡ SQL Visualizer - Live Execution Visualizer

A powerful, fully client-side SQL workbench for visualizing the internal execution flow of SQL queries. Powered by **SQL.js** (SQLite compiled to WebAssembly), this tool breaks down queries into logical steps and animates the data retrieval process row-by-row in real-time.

**Live Demo:** [https://yashkantharia.github.io/sql-visualiser](https://yashkantharia.github.io/sql-visualiser)

## 🚀 Key Features

### 1. 🧠 Granular Execution Pipeline
* **Logical Breakdown:** Visualizes the query lifecycle in specific stages: `FROM` → `JOIN` → `WHERE` → `SELECT`.
* **Live Tracking:** A dedicated sidebar tracks which part of the query is currently being executed (`Pending`, `Active`, `Done`).

### 2. 👁️ Real-Time Row-by-Row Animation
* **Nested Loop Simulation:** Visually simulates how a database engine scans tables.
    * <span style="background:#fef08a; padding:2px 5px; border-radius:3px; color:#000">**Yellow**</span>: **Scanning** rows in the source table.
    * <span style="background:#f9a8d4; padding:2px 5px; border-radius:3px; color:#000">**Pink**</span>: **Reading** specific cells for comparison.
    * <span style="background:#86efac; padding:2px 5px; border-radius:3px; color:#000">**Green**</span>: **Match Found!** The row is merged into the result set.
* **Intermediate Results:** Watch as temporary tables are built dynamically during `JOIN` operations.

### 3. 🛠️ Full Interactive Schema Editor
* **Manage Structure:** Add or remove Tables, Columns, and Rows with a single click.
* **Inline Editing:** Click on **any cell** (header or data) to edit values directly.
* **Smart Tooltips:** Hover over truncated cells to view their full content.
* **CSV Import:** Easily populate tables by uploading CSV files.

### 4. 💻 IDE-Style SQL Editor
* **Syntax Highlighting:** Color-coded text for SQL keywords, strings, and comments.
* **Smart Layout:** Optimized for code readability with auto-syncing scroll.

### 5. ⚡ Live Output Streaming
* **Zero Latency:** Results are pushed to the "Final Output" table the instant a match is found, rather than waiting for the entire query to finish.
* **Smart Aliasing:** Automatically handles column name collisions (e.g., `Orders.id` vs `Customers.id`) by prefixing them in intermediate views.

### 6. 🛡️ Robust Error Handling
* **Console Tab:** Automatically switches to a "Messages" tab to display detailed SQL syntax errors if a query fails.

## 🛠️ Installation & Usage

This project is a **single-file application**. No Node.js, Python, or backend server is required.

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yashkantharia/sql-visualiser.git


2. **Run the App:**
Simply double-click `index.html` to open it in your browser.
* *Requirement:* An active internet connection is needed on the first load to fetch the SQL.js WASM library from the CDN.



## 📖 How to Use

1. **Setup Data (Left Panel):**
* Use the **+ Add** button to create tables manually.
* Use the **📂 Upload CSV** button to import existing datasets instantly.
* *Tip:* Click `Reset` in the header to load the default E-Commerce dataset.


2. **Write Query (Right Panel):**
* Enter standard SQLite syntax in the editor.
* Supports `CTEs`, `Window Functions`, `Aggregations`, and `Subqueries`.


3. **Visualize:**
* Adjust the **Speed Slider** (Top Right) to control the animation pace.
* Click **▶ Run & Visualize**.
* Watch the **"Process Visualization"** stage to see the engine traverse your data.



## ⚙️ Technical Stack

* **Engine:** [SQL.js](https://sql.js.org/) (SQLite via WebAssembly).
* **Frontend:** Pure HTML5, CSS3 (Grid/Flexbox), and Vanilla JavaScript.
* **Visualization Logic:** Custom asynchronous event loop that parses SQL strings to reconstruct the logical "Physical Plan" of execution for educational visualization.

---

**Built for educational purposes to demystify SQL execution.**

---

**Created with ❤️ using HTML, CSS, JavaScript, and Google Gemini.**

```
