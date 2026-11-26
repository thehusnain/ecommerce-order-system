# E-commerce Order Processing System

A small Streamlit app that demonstrates basic order management with a **stack** for recent orders and a **queue** for pending orders. Orders are stored in the current Streamlit session; this project is a learning/demo app, not a persistent order database.

## Features

- Add an order by entering a product name.
- View recent orders in last-in, first-out (LIFO) order.
- View pending orders in first-in, first-out (FIFO) order.
- Process the next pending order.
- Search pending orders by product name.
- Add timestamps to orders when they are placed.

## Requirements

- Python 3.8 or later
- Streamlit (listed in `requirments.txt`)

## Run locally

```bash
git clone https://github.com/thehusnain/ecommerce-order-system.git
cd ecommerce-order-system
python -m venv .venv

# Activate the virtual environment:
# macOS/Linux
source .venv/bin/activate
# Windows PowerShell
# .venv\Scripts\Activate.ps1

pip install -r requirments.txt
streamlit run app.py
```

Streamlit will print a local URL (usually `http://localhost:8501`) that you can open in your browser.

## How to use

1. Enter a product name in **Enter Product Name**. The app adds it to the recent-orders stack and pending-orders queue.
2. Select **View Recent Orders** to see recent orders, newest first.
3. Select **View Pending Orders** to see the processing queue, oldest first.
4. Select **Process Next Order** to remove the oldest pending order.
5. Search for a product using **Search Order**; searches include pending orders only.

## Data and limitations

Orders are kept in Streamlit session state in memory. They are not written to a file or database, and can be lost when the session ends or the app restarts. Processing an order removes it from the pending queue but leaves it in the recent-orders list for the current session.
