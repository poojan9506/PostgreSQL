# Online Bookstore SQL Analysis

A SQL analysis project built with **PostgreSQL**. It uses three related tables (Books, Customers and Orders) to answer 20 business questions about a fictional online bookstore, from basic filtering to joins, aggregations and subqueries.

## Objective

To practise writing real-world SQL queries and to extract useful business insights from relational data, such as which genres sell the most, who the top customers are, and which books are running out of stock.

## Dataset

The project uses three CSV files, with 500 records in each:

| File | Table | Columns |
|------|-------|---------|
| `Books.csv` | Books | Book_ID, Title, Author, Genre, Published_Year, Price, Stock |
| `Customers.csv` | Customers | Customer_ID, Name, Email, Phone, City, Country |
| `Orders.csv` | Orders | Order_ID, Customer_ID, Book_ID, Order_Date, Quantity, Total_Amount |

**Quick facts about the data**
- 7 genres: Biography, Fantasy, Fiction, Mystery, Non-Fiction, Romance, Science Fiction
- Books published between 1900 and 2023
- Orders placed between December 2022 and December 2024
- Customers from 215 countries

## Database Design

```
Customers (Customer_ID PK)  ──┐
                              ├──<  Orders (Order_ID PK, Customer_ID FK, Book_ID FK)
Books (Book_ID PK)          ──┘
```

- `Orders.Customer_ID` references `Customers.Customer_ID`
- `Orders.Book_ID` references `Books.Book_ID`

## Tech Stack

- PostgreSQL
- SQL (DDL and DML)
- pgAdmin or any PostgreSQL client

## SQL Concepts Used

- `CREATE TABLE`, primary keys, foreign keys, `SERIAL`
- Filtering with `WHERE`, `AND`, comparison operators
- `ORDER BY`, `LIMIT`, `DISTINCT`
- Aggregate functions: `SUM`, `AVG`, `COUNT`, `MIN`, `MAX`
- `GROUP BY` and `HAVING`
- `INNER JOIN` and `LEFT JOIN`
- Subqueries (nested queries)
- `COALESCE` and `ROUND`

## Questions Solved

**Basic Queries**
1. Retrieve all books in the "Fiction" genre
2. Find books published after the year 1950
3. List all customers from Canada
4. Show orders placed in November 2023
5. Retrieve the total stock of books available
6. Find the details of the most expensive book
7. Show all customers who ordered more than 1 quantity of a book
8. Retrieve all orders where the total amount exceeds $20
9. List all genres available in the Books table
10. Find the book with the lowest stock
11. Calculate the total revenue generated from all orders

**Advanced Queries**
1. Total number of books sold for each genre
2. Average price of books in the "Fantasy" genre
3. Customers who have placed at least 2 orders
4. The most frequently ordered book
5. Top 3 most expensive books of the "Fantasy" genre
6. Total quantity of books sold by each author
7. Cities where customers who spent over $30 are located
8. The customer who spent the most on orders
9. Stock remaining after fulfilling all orders

## Key Insights

- **Total revenue:** about **$75,629** across 500 orders
- **Best-selling genre:** **Mystery** with 504 copies sold, followed by Science Fiction (447) and Fantasy (446)
- **Lowest-selling genre:** Fiction with 225 copies sold
- **Top customer:** Kim Turner, who spent about **$1,399** in total
- **Most ordered books:** 7 books are tied, each ordered 4 times
- **Stock problem:** for **30 books**, the ordered quantity is more than the stock, so the remaining stock comes out negative. These titles need restocking or the stock data needs checking.

## Project Structure

```
Online Bookstore SQL Analysis/
├── Online_Bookstore.sql   # Table creation and all 20 queries
├── Books.csv
├── Customers.csv
├── Orders.csv
└── README.md
```

## How to Run

1. Install PostgreSQL and pgAdmin
2. Create a new database, for example `OnlineBookstore`
3. Open the Query Tool and run the `CREATE TABLE` statements from `Online_Bookstore.sql`
4. Import the CSV files into their tables (right-click the table, choose **Import/Export Data**, select the CSV file, and enable the **Header** option). Import in this order: **Books**, **Customers**, then **Orders**, because Orders depends on the other two.
5. Run the queries one by one and check the results

## Future Improvements

- Add window functions (`RANK`, `ROW_NUMBER`) for ranking books and customers
- Monthly and yearly sales trend analysis
- Create views for common reports
- Build a dashboard (Power BI or Tableau) on top of this data

## Author

**Poojan Desai**
- GitHub: [poojan9506](https://github.com/poojan9506)
- LinkedIn: [poojan-desai](https://linkedin.com/in/poojan-desai)
- Email: poojandesai06@gmail.com
