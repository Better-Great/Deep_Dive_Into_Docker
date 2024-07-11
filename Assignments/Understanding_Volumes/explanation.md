



1. Check if they're running containers 
`docker ps`

2. Go to Docker hub and choose a version of MySQL image



```
mysql> CREATE TABLE IF NOT EXISTS users (
    -> user_id INT AUTO_INCREMENT PRIMARY KEY,
    -> username VARCHAR(50) NOT NULL,
    -> email VARCHAR(100) NOT NULL
    -> );


```

```
mysql> CREATE TABLE IF NOT EXISTS oders (
    -> order_id INT AUTO_INCREMENT PRIMARY KEY,
    -> user_id INT,
    -> order_date DATE,
    -> total_amount DECIMAL(10,2),
    -> FOREIGN KEY (user_id) REFERENCES users(user_id)
    -> );
```

mysql> INSERT users (username, email) VALUES
    -> ('john_doe', 'john.doe@example.com'),
    -> ('jane_smith', 'jane.smith@example.com');

mysql> INSERT INTO oders (user_id, order_date, total_amount) VALUES
    -> (1, '2023-01-01', 100.00),
    -> (2, '2023-01-02', 100.00);