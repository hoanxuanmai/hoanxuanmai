- [Câu Hỏi Phỏng Vấn MySQL](#câu-hỏi-phỏng-vấn-mysql)
  - [1. MySQL là gì?](#1-mysql-là-gì)
  - [2. Các loại JOIN trong MySQL?](#2-các-loại-join-trong-mysql)
    - [1. INNER JOIN](#1-inner-join)
    - [2. LEFT JOIN (LEFT OUTER JOIN)](#2-left-join-left-outer-join)
    - [3. RIGHT JOIN (RIGHT OUTER JOIN)](#3-right-join-right-outer-join)
    - [4. FULL JOIN (FULL OUTER JOIN) *(MySQL không hỗ trợ trực tiếp)*](#4-full-join-full-outer-join-mysql-không-hỗ-trợ-trực-tiếp)
    - [5. CROSS JOIN](#5-cross-join)
    - [6. SELF JOIN](#6-self-join)
  - [3. Cách phòng chống SQL Injection trong MySQL?](#3-cách-phòng-chống-sql-injection-trong-mysql)
  - [4. Chức năng của INDEX trong MySQL?](#4-chức-năng-của-index-trong-mysql)
    - [Phân loại INDEX trong MySQL:](#phân-loại-index-trong-mysql)
    - [So sánh các loại INDEX:](#so-sánh-các-loại-index)
    - [Khi nào nên sử dụng INDEX?](#khi-nào-nên-sử-dụng-index)
    - [Khi nào KHÔNG nên sử dụng INDEX?](#khi-nào-không-nên-sử-dụng-index)
  - [5. Sự khác nhau giữa MyISAM và InnoDB?](#5-sự-khác-nhau-giữa-myisam-và-innodb)
  - [6. Các loại ràng buộc (Constraints) trong MySQL?](#6-các-loại-ràng-buộc-constraints-trong-mysql)
  - [7. ACID trong MySQL là gì?](#7-acid-trong-mysql-là-gì)
- [**Tối ưu hóa**](#tối-ưu-hóa)
  - [**1. Tối ưu hóa thiết kế database (Database Schema Optimization)**](#1-tối-ưu-hóa-thiết-kế-database-database-schema-optimization)
    - [**1.1. Chọn kiểu dữ liệu phù hợp**](#11-chọn-kiểu-dữ-liệu-phù-hợp)
      - [**🛠️ Nguyên tắc chọn kiểu dữ liệu:**](#️-nguyên-tắc-chọn-kiểu-dữ-liệu)
        - [**❌ Ví dụ kém tối ưu:**](#-ví-dụ-kém-tối-ưu)
        - [**✅ Tối ưu hơn:**](#-tối-ưu-hơn)
    - [**1.2. Bình thường hóa (Normalization) vs. Phi chuẩn hóa (Denormalization)**](#12-bình-thường-hóa-normalization-vs-phi-chuẩn-hóa-denormalization)
  - [**2. Tối ưu hóa chỉ mục (Index Optimization)**](#2-tối-ưu-hóa-chỉ-mục-index-optimization)
    - [**2.1. Khi nào nên sử dụng chỉ mục?**](#21-khi-nào-nên-sử-dụng-chỉ-mục)
    - [**2.2. Các loại chỉ mục**](#22-các-loại-chỉ-mục)
        - [**✅ Ví dụ tạo chỉ mục:**](#-ví-dụ-tạo-chỉ-mục)
        - [**📊 Kiểm tra MySQL có dùng chỉ mục không?**](#-kiểm-tra-mysql-có-dùng-chỉ-mục-không)
  - [**3. Tối ưu hóa truy vấn (Query Optimization)**](#3-tối-ưu-hóa-truy-vấn-query-optimization)
        - [**❌ Truy vấn kém tối ưu:**](#-truy-vấn-kém-tối-ưu)
        - [**✅ Truy vấn tối ưu hơn:**](#-truy-vấn-tối-ưu-hơn)
  - [**4. Cấu hình MySQL để tối ưu hiệu suất**](#4-cấu-hình-mysql-để-tối-ưu-hiệu-suất)
    - [**4.1. Tăng bộ nhớ (`innodb_buffer_pool_size`)**](#41-tăng-bộ-nhớ-innodb_buffer_pool_size)
    - [**4.2. Giới hạn kết nối để tránh quá tải (`max_connections`)**](#42-giới-hạn-kết-nối-để-tránh-quá-tải-max_connections)
    - [**4.3. Bật bộ nhớ cache (`query_cache_size`)** (chỉ với MySQL 5.7 trở xuống)](#43-bật-bộ-nhớ-cache-query_cache_size-chỉ-với-mysql-57-trở-xuống)
  - [**5. Dùng Cache để giảm tải MySQL**](#5-dùng-cache-để-giảm-tải-mysql)
    - [**5.1. Sử dụng Redis để cache kết quả truy vấn**](#51-sử-dụng-redis-để-cache-kết-quả-truy-vấn)
  - [**Tóm tắt**](#tóm-tắt)
      - [**Phân biệt Index, FULLTEXT Index và Partitioning trong MySQL**](#phân-biệt-index-fulltext-index-và-partitioning-trong-mysql)
    - [**1. INDEX (B-Tree Index) – Chỉ mục thông thường**](#1-index-b-tree-index--chỉ-mục-thông-thường)
      - [**1.1. Mục đích**](#11-mục-đích)
      - [**1.2. Đặc điểm**](#12-đặc-điểm)
      - [**1.3. Ví dụ**](#13-ví-dụ)
        - [**✅ Tạo INDEX thông thường**](#-tạo-index-thông-thường)
        - [**📊 Kiểm tra MySQL có sử dụng INDEX không?**](#-kiểm-tra-mysql-có-sử-dụng-index-không)
    - [**2. FULLTEXT INDEX – Chỉ mục toàn văn**](#2-fulltext-index--chỉ-mục-toàn-văn)
      - [**2.1. Mục đích**](#21-mục-đích)
      - [**2.2. Đặc điểm**](#22-đặc-điểm)
      - [**2.3. Ví dụ**](#23-ví-dụ)
        - [**✅ Tạo FULLTEXT INDEX**](#-tạo-fulltext-index)
        - [**✅ Tìm kiếm toàn văn**](#-tìm-kiếm-toàn-văn)
        - [**✅ Tìm kiếm Boolean (AND, OR, NOT)**](#-tìm-kiếm-boolean-and-or-not)
    - [**3. PARTITIONING – Chia nhỏ bảng để tối ưu hiệu suất**](#3-partitioning--chia-nhỏ-bảng-để-tối-ưu-hiệu-suất)
      - [**3.1. Mục đích**](#31-mục-đích)
      - [**3.2. Đặc điểm**](#32-đặc-điểm)
      - [**3.3. Các loại Partitioning**](#33-các-loại-partitioning)
      - [**3.4. Ví dụ**](#34-ví-dụ)
        - [**✅ Partition theo năm (`RANGE`)**](#-partition-theo-năm-range)
        - [**✅ Partition theo khu vực (`LIST`)**](#-partition-theo-khu-vực-list)
  - [**🔍 Tổng kết: Nên dùng loại nào?**](#-tổng-kết-nên-dùng-loại-nào)
  - [**Tối ưu hóa Transaction trong MySQL**](#tối-ưu-hóa-transaction-trong-mysql)
    - [**1. Nguyên tắc cơ bản của Transaction trong MySQL**](#1-nguyên-tắc-cơ-bản-của-transaction-trong-mysql)
      - [**1.1. ACID – 4 tính chất quan trọng của transaction**](#11-acid--4-tính-chất-quan-trọng-của-transaction)
      - [**1.2. Các câu lệnh transaction cơ bản**](#12-các-câu-lệnh-transaction-cơ-bản)
    - [**2. Các vấn đề hiệu suất khi sử dụng Transaction**](#2-các-vấn-đề-hiệu-suất-khi-sử-dụng-transaction)
    - [**2.1. Hiện tượng Lock (Khóa dữ liệu)**](#21-hiện-tượng-lock-khóa-dữ-liệu)
      - [**🔹 MySQL có hai loại lock chính:**](#-mysql-có-hai-loại-lock-chính)
    - [**2.2. Hiện tượng Deadlock (Giao dịch bị kẹt nhau)**](#22-hiện-tượng-deadlock-giao-dịch-bị-kẹt-nhau)
      - [**🔹 Ví dụ deadlock:**](#-ví-dụ-deadlock)
      - [**🔹 Cách tránh Deadlock**](#-cách-tránh-deadlock)
    - [**3. Kỹ thuật tối ưu Transaction trong MySQL**](#3-kỹ-thuật-tối-ưu-transaction-trong-mysql)
      - [**3.1. Giảm thời gian giữ lock**](#31-giảm-thời-gian-giữ-lock)
      - [**3.2. Sử dụng Batch Processing thay vì Transaction dài**](#32-sử-dụng-batch-processing-thay-vì-transaction-dài)
      - [**3.3. Chỉ dùng Transaction khi thực sự cần**](#33-chỉ-dùng-transaction-khi-thực-sự-cần)
    - [**4. Cấu hình MySQL để tối ưu Transaction**](#4-cấu-hình-mysql-để-tối-ưu-transaction)
      - [**4.1. Tăng bộ nhớ InnoDB Buffer Pool**](#41-tăng-bộ-nhớ-innodb-buffer-pool)
      - [**4.2. Kiểm tra và tối ưu transaction log**](#42-kiểm-tra-và-tối-ưu-transaction-log)
      - [**4.3. Giới hạn thời gian transaction (`innodb_lock_wait_timeout`)**](#43-giới-hạn-thời-gian-transaction-innodb_lock_wait_timeout)
    - [**5. Kết hợp Transaction và Queue để tăng hiệu suất**](#5-kết-hợp-transaction-và-queue-để-tăng-hiệu-suất)
  - [**🔍 Tổng kết – Cách tối ưu Transaction hiệu quả**](#-tổng-kết--cách-tối-ưu-transaction-hiệu-quả)
  - [**Lock trong MySQL: Khi nào xảy ra và các loại Transaction**](#lock-trong-mysql-khi-nào-xảy-ra-và-các-loại-transaction)
  - [**1. Khi nào MySQL xảy ra Lock?**](#1-khi-nào-mysql-xảy-ra-lock)
      - [**1.1. Khi có thao tác đọc và ghi đồng thời**](#11-khi-có-thao-tác-đọc-và-ghi-đồng-thời)
      - [**1.2. Khi dùng các câu lệnh sau**](#12-khi-dùng-các-câu-lệnh-sau)
  - [**2. Các loại Lock trong MySQL**](#2-các-loại-lock-trong-mysql)
    - [**2.1. Table Lock (Khóa bảng)**](#21-table-lock-khóa-bảng)
    - [**2.2. Row Lock (Khóa dòng - InnoDB)**](#22-row-lock-khóa-dòng---innodb)
    - [**2.3. Shared Lock (Khóa chia sẻ - S)**](#23-shared-lock-khóa-chia-sẻ---s)
    - [**2.4. Exclusive Lock (Khóa độc quyền - X)**](#24-exclusive-lock-khóa-độc-quyền---x)
    - [**2.5. Gap Lock (Khóa khoảng - InnoDB)**](#25-gap-lock-khóa-khoảng---innodb)
  - [**3. Các loại Transaction Isolation Levels trong MySQL**](#3-các-loại-transaction-isolation-levels-trong-mysql)
  - [**4. Tổng kết – Cách tránh Lock và tối ưu Transaction**](#4-tổng-kết--cách-tránh-lock-và-tối-ưu-transaction)
  - [**Các loại Transaction trong MySQL – Chi tiết và Ví dụ Cụ thể**](#các-loại-transaction-trong-mysql--chi-tiết-và-ví-dụ-cụ-thể)
  - [**1. Các loại Transaction trong MySQL**](#1-các-loại-transaction-trong-mysql)
    - [**1.1. Implicit Transaction (Giao dịch ngầm định)**](#11-implicit-transaction-giao-dịch-ngầm-định)
    - [**1.2. Explicit Transaction (Giao dịch tường minh)**](#12-explicit-transaction-giao-dịch-tường-minh)
    - [**1.3. Savepoint Transaction (Giao dịch có điểm lưu)**](#13-savepoint-transaction-giao-dịch-có-điểm-lưu)
    - [**1.4. Chained Transaction (Giao dịch liên kết)**](#14-chained-transaction-giao-dịch-liên-kết)
    - [**1.5. Distributed Transaction (Giao dịch phân tán)**](#15-distributed-transaction-giao-dịch-phân-tán)
  - [**2. So sánh các loại Transaction**](#2-so-sánh-các-loại-transaction)
  - [**3. Cách tối ưu Transaction để tránh Lock và Deadlock**](#3-cách-tối-ưu-transaction-để-tránh-lock-và-deadlock)
  - [**4. Kết luận**](#4-kết-luận)
  - [**Các Chế Độ (Mode) của Transaction trong MySQL**](#các-chế-độ-mode-của-transaction-trong-mysql)
  - [**1. Các Chế Độ Isolation của Transaction (Isolation Levels)**](#1-các-chế-độ-isolation-của-transaction-isolation-levels)
    - [**2. Chi Tiết Từng Chế Độ Isolation**](#2-chi-tiết-từng-chế-độ-isolation)
      - [**2.1. READ UNCOMMITTED (Đọc dữ liệu chưa commit)**](#21-read-uncommitted-đọc-dữ-liệu-chưa-commit)
      - [**2.2. READ COMMITTED (Chỉ đọc dữ liệu đã commit)**](#22-read-committed-chỉ-đọc-dữ-liệu-đã-commit)
      - [**2.3. REPEATABLE READ (Mặc định trong MySQL)**](#23-repeatable-read-mặc-định-trong-mysql)
      - [**2.4. SERIALIZABLE (Mức cô lập cao nhất)**](#24-serializable-mức-cô-lập-cao-nhất)
  - [**3. Các Chế Độ Truy Cập (Access Mode)**](#3-các-chế-độ-truy-cập-access-mode)
  - [**4. Chọn Chế Độ Isolation Phù Hợp**](#4-chọn-chế-độ-isolation-phù-hợp)
  - [**5. Tối Ưu Transaction để Tránh Lock và Deadlock**](#5-tối-ưu-transaction-để-tránh-lock-và-deadlock)
  - [**6. Kết Luận**](#6-kết-luận)
  - [**Access Mode trong MySQL Transactions**](#access-mode-trong-mysql-transactions)
  - [**1. READ WRITE Mode (Mặc định)**](#1-read-write-mode-mặc-định)
  - [**2. READ ONLY Mode**](#2-read-only-mode)
  - [**3. Khi nào sử dụng READ ONLY?**](#3-khi-nào-sử-dụng-read-only)
  - [**4. So sánh READ WRITE vs READ ONLY**](#4-so-sánh-read-write-vs-read-only)
  - [**5. Kết luận**](#5-kết-luận)
  - [**1. SAVEPOINT và ROLLBACK TO SAVEPOINT**](#1-savepoint-và-rollback-to-savepoint)
      - [🔹 **Cho phép rollback một phần transaction thay vì toàn bộ.**](#-cho-phép-rollback-một-phần-transaction-thay-vì-toàn-bộ)
  - [**2. DEADLOCK: Cách phát hiện và tránh**](#2-deadlock-cách-phát-hiện-và-tránh)
      - [🔹 **Deadlock xảy ra khi 2 transaction chờ nhau giải phóng tài nguyên.**](#-deadlock-xảy-ra-khi-2-transaction-chờ-nhau-giải-phóng-tài-nguyên)
      - [✅ **Cách tránh Deadlock**](#-cách-tránh-deadlock-1)
  - [**3. GROUP COMMIT: Tối ưu hiệu suất COMMIT**](#3-group-commit-tối-ưu-hiệu-suất-commit)
      - [🔹 **Group Commit giúp giảm thời gian disk I/O khi có nhiều transaction cùng lúc.**](#-group-commit-giúp-giảm-thời-gian-disk-io-khi-có-nhiều-transaction-cùng-lúc)
  - [**4. MULTI-STATEMENT TRANSACTION: Thực thi nhiều lệnh trong một transaction**](#4-multi-statement-transaction-thực-thi-nhiều-lệnh-trong-một-transaction)
      - [🔹 **Giảm số lần gửi lệnh từ ứng dụng đến MySQL, tăng tốc độ xử lý.**](#-giảm-số-lần-gửi-lệnh-từ-ứng-dụng-đến-mysql-tăng-tốc-độ-xử-lý)
  - [**5. PARTITION TABLE: Chia bảng lớn thành nhiều phần nhỏ**](#5-partition-table-chia-bảng-lớn-thành-nhiều-phần-nhỏ)
      - [🔹 **Giảm tải cho index và tối ưu truy vấn khi bảng quá lớn.**](#-giảm-tải-cho-index-và-tối-ưu-truy-vấn-khi-bảng-quá-lớn)
  - [**6. VIRTUAL COLUMN: Cột ảo giúp tối ưu truy vấn**](#6-virtual-column-cột-ảo-giúp-tối-ưu-truy-vấn)
      - [🔹 **Tạo cột dựa trên biểu thức, giảm chi phí lưu trữ nhưng vẫn có index.**](#-tạo-cột-dựa-trên-biểu-thức-giảm-chi-phí-lưu-trữ-nhưng-vẫn-có-index)
  - [**7. TUNING TRANSACTIONS: Tinh chỉnh MySQL để tối ưu hiệu suất**](#7-tuning-transactions-tinh-chỉnh-mysql-để-tối-ưu-hiệu-suất)
      - [🔹 **Một số tham số quan trọng cần điều chỉnh**](#-một-số-tham-số-quan-trọng-cần-điều-chỉnh)
  - [**KẾT LUẬN**](#kết-luận)

------------

# Câu Hỏi Phỏng Vấn MySQL

## 1. MySQL là gì?
**Trả lời:**
MySQL là hệ quản trị cơ sở dữ liệu quan hệ (RDBMS) nguồn mở, được sử dụng rộng rãi trong các ứng dụng web. Nó sử dụng SQL (Structured Query Language) để quản lý dữ liệu. MySQL hỗ trợ nhiều tính năng như replication, clustering, stored procedures, triggers và views.

## 2. Các loại JOIN trong MySQL?
**Trả lời:**
### 1. INNER JOIN
- Trả về các bản ghi có trong cả hai bảng khi có điều kiện khớp.
- Loại bỏ các bản ghi không có giá trị tương ứng trong bảng kia.
- **Ví dụ:**
  ```sql
  SELECT employees.id, employees.name, departments.name AS department_name
  FROM employees
  INNER JOIN departments ON employees.department_id = departments.id;
  ```

### 2. LEFT JOIN (LEFT OUTER JOIN)
- Trả về tất cả bản ghi từ bảng bên trái và các bản ghi khớp từ bảng bên phải.
- Nếu không có giá trị tương ứng ở bảng bên phải, sẽ trả về NULL.
- **Ví dụ:**
  ```sql
  SELECT employees.id, employees.name, departments.name AS department_name
  FROM employees
  LEFT JOIN departments ON employees.department_id = departments.id;
  ```

### 3. RIGHT JOIN (RIGHT OUTER JOIN)
- Trả về tất cả bản ghi từ bảng bên phải và các bản ghi khớp từ bảng bên trái.
- Nếu không có giá trị tương ứng ở bảng bên trái, sẽ trả về NULL.
- **Ví dụ:**
  ```sql
  SELECT employees.id, employees.name, departments.name AS department_name
  FROM employees
  RIGHT JOIN departments ON employees.department_id = departments.id;
  ```

### 4. FULL JOIN (FULL OUTER JOIN) *(MySQL không hỗ trợ trực tiếp)*
- Trả về tất cả bản ghi từ cả hai bảng, nếu không có giá trị tương ứng thì trả về NULL.
- MySQL không hỗ trợ `FULL JOIN`, nhưng có thể mô phỏng bằng UNION.
- **Ví dụ:**
  ```sql
  SELECT employees.id, employees.name, departments.name AS department_name
  FROM employees
  LEFT JOIN departments ON employees.department_id = departments.id
  UNION
  SELECT employees.id, employees.name, departments.name AS department_name
  FROM employees
  RIGHT JOIN departments ON employees.department_id = departments.id;
  ```

### 5. CROSS JOIN
- Kết hợp tất cả các bản ghi từ hai bảng (tích Descartes), không có điều kiện kết hợp.
- Số dòng trả về = số dòng bảng A × số dòng bảng B.
- **Ví dụ:**
  ```sql
  SELECT employees.name, departments.name AS department_name
  FROM employees
  CROSS JOIN departments;
  ```

### 6. SELF JOIN
- Thực hiện JOIN chính nó bằng cách tạo ra alias.
- Dùng để tìm mối quan hệ trong cùng một bảng, chẳng hạn như danh sách cấp trên - cấp dưới.
- **Ví dụ:**
  ```sql
  SELECT e1.name AS employee, e2.name AS manager
  FROM employees e1
  LEFT JOIN employees e2 ON e1.manager_id = e2.id;
  ```

## 3. Cách phòng chống SQL Injection trong MySQL?
**Trả lời:**
SQL Injection xảy ra khi đối tượng nhập dữ liệu có thể thao tác câu lệnh SQL. Các cách phòng chống bao gồm:
- **Sử dụng Prepared Statements**: Tránh việc ghép nối chuỗi SQL trực tiếp.
- **Sử dụng ORM (Object-Relational Mapping)**: Như Sequelize, Hibernate để tránh lỗi.
- **Kiểm tra và lọc dữ liệu đầu vào**: Không cho phép ký tự đặc biệt khi nhập dữ liệu.
- **Hạn chế quyền truy cập vào database**: Chỉ cấp quyền cần thiết.
- **Sử dụng Web Application Firewall (WAF)**: Ngăn chặn tấn công SQL Injection.

## 4. Chức năng của INDEX trong MySQL?
**Trả lời:**
INDEX giúp tăng tốc độ truy vấn trong MySQL bằng cách tạo ra một cấu trúc dữ liệu riêng biệt để tìm kiếm nhanh hơn.

### Phân loại INDEX trong MySQL:
1. **Primary Key Index**:
   - Chỉ mục duy nhất và không thể NULL.
   - Mỗi bảng chỉ có một Primary Key.
   - Tạo mặc định khi khai báo PRIMARY KEY.
2. **Unique Index**:
   - Đảm bảo giá trị trong cột là duy nhất.
   - Cho phép NULL nhưng chỉ một giá trị NULL.
   - Cú pháp:
     ```sql
     CREATE UNIQUE INDEX idx_unique_email ON employees(email);
     ```
3. **Full-text Index**:
   - Dùng cho tìm kiếm văn bản (TEXT, VARCHAR).
   - Chỉ hỗ trợ trong MyISAM và InnoDB từ MySQL 5.6 trở lên.
   - Cú pháp:
     ```sql
     CREATE FULLTEXT INDEX idx_fulltext_name ON employees(name);
     ```
4. **Composite Index**:
   - Chỉ mục trên nhiều cột, giúp tăng tốc truy vấn khi kết hợp nhiều cột trong điều kiện.
   - Cú pháp:
     ```sql
     CREATE INDEX idx_composite ON employees(department_id, name);
     ```
5. **Spatial Index**:
   - Dùng cho dữ liệu không gian (GIS).
   - Chỉ hỗ trợ trên bảng MyISAM và InnoDB (MySQL 8.0 trở lên).
   - Cú pháp:
     ```sql
     CREATE SPATIAL INDEX idx_spatial_location ON locations(geo_point);
     ```

### So sánh các loại INDEX:
| Loại INDEX        | Đặc điểm chính | Hỗ trợ NULL | Khi nào sử dụng? |
|-------------------|---------------|------------|----------------|
| **Primary Key**  | Chỉ mục duy nhất, không NULL, duy nhất trên bảng | Không | Khi cần định danh duy nhất cho mỗi bản ghi |
| **Unique Index** | Chỉ mục duy nhất, có thể NULL | Có | Khi cần tránh dữ liệu trùng lặp trên cột |
| **Full-text Index** | Dùng để tìm kiếm văn bản | Có | Khi cần tìm kiếm trong dữ liệu lớn |
| **Composite Index** | Tối ưu truy vấn với nhiều cột | Tùy vào từng cột | Khi truy vấn có điều kiện trên nhiều cột |
| **Spatial Index** | Dành cho dữ liệu không gian | Không | Khi lưu trữ và truy vấn dữ liệu địa lý |

### Khi nào nên sử dụng INDEX?
- Khi truy vấn dữ liệu trên bảng có số lượng bản ghi lớn.
- Khi cột được sử dụng nhiều trong điều kiện `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`.
- Khi cần tìm kiếm văn bản nhanh với Full-Text Index.

### Khi nào KHÔNG nên sử dụng INDEX?
- Khi bảng có ít dữ liệu, INDEX có thể không mang lại lợi ích đáng kể.
- Khi có quá nhiều INDEX trên một bảng, vì điều này có thể làm chậm hiệu suất INSERT, UPDATE, DELETE.
- Khi cột chứa quá nhiều giá trị trùng lặp (INDEX hiệu quả hơn trên cột có tính duy nhất cao).

## 5. Sự khác nhau giữa MyISAM và InnoDB?
**Trả lời:**
- **MyISAM**:
  - Không hỗ trợ giao dịch (ACID), không có khóa ngoại.
  - Hỗ trợ FULLTEXT Index.
  - Nhanh hơn InnoDB trong các truy vấn đọc dữ liệu.
- **InnoDB**:
  - Hỗ trợ giao dịch với tính ACID đầy đủ.
  - Có khóa ngoại (Foreign Key) đảm bảo tính toàn vẹn dữ liệu.
  - Hỗ trợ khóa dòng (Row-level Locking) giúp cải thiện hiệu suất khi có nhiều giao dịch đồng thời.

## 6. Các loại ràng buộc (Constraints) trong MySQL?
**Trả lời:**
- **NOT NULL**: Cột không được phép chứa giá trị NULL.
- **UNIQUE**: Mỗi giá trị trong cột phải là duy nhất.
- **PRIMARY KEY**: Kết hợp giữa NOT NULL và UNIQUE, chỉ có một PRIMARY KEY trên mỗi bảng.
- **FOREIGN KEY**: Ràng buộc tham chiếu đến khóa chính của một bảng khác.
- **CHECK**: Kiểm tra điều kiện ràng buộc trên một cột (hỗ trợ từ MySQL 8.0).
- **DEFAULT**: Gán giá trị mặc định nếu không nhập giá trị cho cột.

## 7. ACID trong MySQL là gì?
**Trả lời:**
ACID là tập hợp các thuộc tính đảm bảo tính toàn vẹn của giao dịch trong cơ sở dữ liệu:
- **Atomicity**: Giao dịch phải hoàn thành toàn bộ hoặc không có gì thay đổi.
- **Consistency**: Cơ sở dữ liệu phải ở trạng thái hợp lệ trước và sau giao dịch.
- **Isolation**: Các giao dịch phải chạy độc lập với nhau.
- **Durability**: Khi giao dịch hoàn thành, dữ liệu phải được lưu vĩnh viễn.

---
# **Tối ưu hóa**
## **1. Tối ưu hóa thiết kế database (Database Schema Optimization)** 

Tối ưu hóa MySQL là một quá trình phức tạp, bao gồm nhiều khía cạnh như thiết kế database, tối ưu truy vấn, tối ưu hệ thống và sử dụng cache. Tôi sẽ phân tích chi tiết từng phần để bạn hiểu rõ cách áp dụng trong thực tế.  

---
 
Đây là bước quan trọng vì một thiết kế tốt ngay từ đầu sẽ giúp hệ thống chạy nhanh hơn và tiết kiệm tài nguyên.  

### **1.1. Chọn kiểu dữ liệu phù hợp**  
Mỗi kiểu dữ liệu trong MySQL có mức sử dụng bộ nhớ khác nhau, vì vậy cần chọn loại phù hợp để tiết kiệm tài nguyên và tăng hiệu suất.  

#### **🛠️ Nguyên tắc chọn kiểu dữ liệu:**  
✅ **Dùng kiểu dữ liệu nhỏ nhất có thể:**  
- `TINYINT` (1 byte) thay vì `INT` (4 byte) nếu chỉ lưu số nhỏ (0-255 hoặc -128 đến 127).  
- `SMALLINT` (2 byte) thay vì `INT` nếu chỉ cần lưu từ -32,768 đến 32,767.  
- `BIGINT` (8 byte) chỉ nên dùng khi thực sự cần số rất lớn.  

✅ **Dùng `VARCHAR` thay vì `CHAR` nếu độ dài thay đổi:**  
- `CHAR` luôn chiếm đủ số ký tự, còn `VARCHAR` chỉ chiếm đúng số ký tự đang lưu.  
- Ví dụ: `CHAR(50)` luôn chiếm **50 byte**, nhưng `VARCHAR(50)` chỉ chiếm **đúng số ký tự + 1 hoặc 2 byte lưu độ dài**.  
- Nên dùng `CHAR` cho dữ liệu có độ dài cố định như mã quốc gia (`US`, `VN`, `JP`).  

✅ **Tránh sử dụng `TEXT` và `BLOB` không cần thiết**  
- `TEXT` và `BLOB` lưu dữ liệu ngoài bảng chính (`off-page storage`), làm chậm truy vấn.  
- Nếu dữ liệu nhỏ, nên dùng `VARCHAR(255)` thay vì `TEXT`.  

##### **❌ Ví dụ kém tối ưu:**
```sql
CREATE TABLE users (
    id INT NOT NULL AUTO_INCREMENT,
    name CHAR(255),   -- Không cần thiết dùng 255 ký tự
    email TEXT,       -- Email không cần TEXT
    PRIMARY KEY (id)
);
```
##### **✅ Tối ưu hơn:**
```sql
CREATE TABLE users (
    id INT UNSIGNED NOT NULL AUTO_INCREMENT,
    name VARCHAR(100),  -- Chỉ dùng đủ
    email VARCHAR(255), -- Email thường dưới 255 ký tự
    PRIMARY KEY (id)
);
```

---

### **1.2. Bình thường hóa (Normalization) vs. Phi chuẩn hóa (Denormalization)**  
Bình thường hóa giúp loại bỏ dữ liệu trùng lặp, nhưng phi chuẩn hóa đôi khi cần để tăng hiệu suất.  

**🎯 Quy tắc chung:**  
- Nếu hệ thống **ghi nhiều (OLTP - Online Transaction Processing)** → **Dùng bình thường hóa** để giảm trùng lặp.  
- Nếu hệ thống **đọc nhiều (OLAP - Online Analytical Processing)** → **Dùng phi chuẩn hóa** để giảm số lần JOIN.  

✅ **Ví dụ bình thường hóa:**  
```sql
CREATE TABLE customers (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(255) UNIQUE
);

CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    total DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```
- Bảng `orders` chỉ lưu `customer_id`, không lặp lại tên/email khách hàng.  

✅ **Ví dụ phi chuẩn hóa (tăng tốc báo cáo doanh thu theo khách hàng):**  
```sql
CREATE TABLE orders (
    id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    customer_name VARCHAR(100),  -- Lưu thêm tên khách hàng để giảm JOIN
    total DECIMAL(10,2)
);
```
- Dữ liệu có chút dư thừa nhưng giúp **truy vấn nhanh hơn**.  

---

## **2. Tối ưu hóa chỉ mục (Index Optimization)**  
Chỉ mục giúp MySQL tìm dữ liệu nhanh hơn, nhưng cần dùng đúng cách.  

### **2.1. Khi nào nên sử dụng chỉ mục?**  
✅ **Cột được dùng trong `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`**.  
✅ **Cột có tính duy nhất cao (vd: email, username)**.  
✅ **Cột là khóa chính hoặc khóa ngoại**.  

❌ **Không nên tạo chỉ mục trên:**  
- Cột có **nhiều giá trị trùng nhau** (vd: `status` chỉ có `active`, `inactive`).  
- Cột thường xuyên **bị cập nhật** (vd: `views_count`).  

### **2.2. Các loại chỉ mục**  
- **PRIMARY KEY**: Chỉ mục duy nhất trên cột khóa chính.  
- **UNIQUE INDEX**: Đảm bảo không có giá trị trùng lặp.  
- **INDEX** (B-Tree Index): Chỉ mục thông thường giúp tăng tốc truy vấn.  
- **FULLTEXT INDEX**: Dùng cho tìm kiếm văn bản.  

##### **✅ Ví dụ tạo chỉ mục:**
```sql
CREATE INDEX idx_email ON users(email);
CREATE INDEX idx_name ON users(first_name, last_name);
```

##### **📊 Kiểm tra MySQL có dùng chỉ mục không?**
```sql
EXPLAIN SELECT * FROM users WHERE email = 'test@example.com';
```
Nếu MySQL **không dùng index**, có thể cần kiểm tra lại thiết kế chỉ mục.  

---

## **3. Tối ưu hóa truy vấn (Query Optimization)**  
- **Tránh `SELECT *`**, chỉ lấy cột cần thiết.  
- **Dùng `EXPLAIN` để kiểm tra truy vấn**.  
- **Tránh `JOIN` quá nhiều bảng** nếu không cần thiết.  
- **Sử dụng `LIMIT` hợp lý** khi lấy dữ liệu lớn.  

##### **❌ Truy vấn kém tối ưu:**
```sql
SELECT * FROM orders;
```
##### **✅ Truy vấn tối ưu hơn:**
```sql
SELECT id, order_date, total FROM orders;
```

📊 **Dùng `EXPLAIN` để phân tích truy vấn:**
```sql
EXPLAIN SELECT id, order_date FROM orders WHERE total > 100;
```
Nếu **`type = ALL`**, nghĩa là MySQL đang quét toàn bộ bảng → Cần thêm chỉ mục.  

---

## **4. Cấu hình MySQL để tối ưu hiệu suất**  
### **4.1. Tăng bộ nhớ (`innodb_buffer_pool_size`)**  
```sql
SHOW VARIABLES LIKE 'innodb_buffer_pool_size';
SET GLOBAL innodb_buffer_pool_size = 1G;
```
- Giá trị này nên chiếm **70% - 80% RAM** nếu chỉ chạy MySQL.  

### **4.2. Giới hạn kết nối để tránh quá tải (`max_connections`)**  
```sql
SHOW VARIABLES LIKE 'max_connections';
SET GLOBAL max_connections = 500;
```

### **4.3. Bật bộ nhớ cache (`query_cache_size`)** (chỉ với MySQL 5.7 trở xuống)  
```sql
SHOW VARIABLES LIKE 'query_cache_size';
SET GLOBAL query_cache_size = 64M;
```

---

## **5. Dùng Cache để giảm tải MySQL**  
### **5.1. Sử dụng Redis để cache kết quả truy vấn**  
```js
const redis = require('redis');
const client = redis.createClient();

async function getUserData(userId) {
    const cachedData = await client.get(`user:${userId}`);
    if (cachedData) return JSON.parse(cachedData);

    const user = await db.query('SELECT * FROM users WHERE id = ?', [userId]);
    client.setex(`user:${userId}`, 3600, JSON.stringify(user)); // Lưu cache trong 1 giờ
    return user;
}
```

---

## **Tóm tắt**
1. **Tối ưu thiết kế bảng** (chọn kiểu dữ liệu nhỏ, chuẩn hóa hợp lý).  
2. **Tạo chỉ mục đúng cách** (cho `WHERE`, `JOIN`, `ORDER BY`).  
3. **Viết truy vấn tối ưu** (`EXPLAIN`, tránh `SELECT *`, tối ưu `JOIN`).  
4. **Cấu hình MySQL hợp lý** (`innodb_buffer_pool_size`, `max_connections`).  
5. **Dùng cache với Redis/Memcached** để giảm truy vấn MySQL.  

---

#### **Phân biệt Index, FULLTEXT Index và Partitioning trong MySQL**  

Trong MySQL, `INDEX`, `FULLTEXT INDEX` và `PARTITIONING` đều là các kỹ thuật tối ưu hóa hiệu suất, nhưng chúng có mục đích khác nhau. Hãy đi sâu vào từng loại để hiểu rõ khi nào nên sử dụng chúng.  

---

### **1. INDEX (B-Tree Index) – Chỉ mục thông thường**  
#### **1.1. Mục đích**  
- **Tăng tốc truy vấn** bằng cách giúp MySQL tìm kiếm nhanh hơn thay vì quét toàn bộ bảng.  
- Hoạt động dựa trên **cấu trúc cây B-Tree**, giúp tìm kiếm theo khoảng giá trị nhanh.  
- Dùng cho các cột trong `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY`.  

#### **1.2. Đặc điểm**  
✅ **Tìm kiếm nhanh hơn với điều kiện so sánh (`=`, `>`, `<`, `LIKE 'abc%'`).**  
✅ Hỗ trợ **multi-column index** (chỉ mục nhiều cột).  
✅ Dùng cho dữ liệu dạng số, chuỗi ngắn, ngày tháng.  
❌ **Không tối ưu cho tìm kiếm văn bản dài (vd: tìm kiếm toàn văn trong bài viết).**  

#### **1.3. Ví dụ**  
##### **✅ Tạo INDEX thông thường**  
```sql
CREATE INDEX idx_email ON users(email);
```
##### **📊 Kiểm tra MySQL có sử dụng INDEX không?**
```sql
EXPLAIN SELECT * FROM users WHERE email = 'test@example.com';
```
- Nếu `type = ALL` → MySQL đang quét toàn bộ bảng, cần kiểm tra lại chỉ mục.  
- Nếu `type = ref` hoặc `type = range` → Chỉ mục đang hoạt động tốt.  

---

### **2. FULLTEXT INDEX – Chỉ mục toàn văn**  
#### **2.1. Mục đích**  
- **Tối ưu tìm kiếm văn bản dài (vd: bài viết, mô tả sản phẩm, bình luận, tin tức).**  
- Thay vì so sánh từng ký tự như `LIKE '%keyword%'`, MySQL dùng **công cụ phân tích ngữ nghĩa** để tìm kết quả phù hợp nhất.  
- Hỗ trợ **tìm kiếm nhiều từ, gần đúng, hoặc tìm kiếm với mức độ liên quan (`MATCH ... AGAINST`)**.  

#### **2.2. Đặc điểm**  
✅ **Chỉ hoạt động với bảng InnoDB & MyISAM**.  
✅ **Tìm kiếm văn bản tốt hơn `LIKE '%keyword%'`**.  
✅ Hỗ trợ **tìm kiếm tự nhiên, Boolean, truy vấn dạng vector**.  
❌ **Không hoạt động tốt với dữ liệu số hoặc tìm kiếm chính xác (`=`).**  

#### **2.3. Ví dụ**  
##### **✅ Tạo FULLTEXT INDEX**  
```sql
CREATE TABLE articles (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255),
    content TEXT,
    FULLTEXT(title, content)  -- Tạo chỉ mục toàn văn
);
```
##### **✅ Tìm kiếm toàn văn**  
```sql
SELECT * FROM articles WHERE MATCH(title, content) AGAINST('MySQL Optimization');
```
##### **✅ Tìm kiếm Boolean (AND, OR, NOT)**  
```sql
SELECT * FROM articles WHERE MATCH(title, content) AGAINST('+MySQL -PostgreSQL' IN BOOLEAN MODE);
```
📌 **Lưu ý:**  
- `+MySQL` (bắt buộc có từ "MySQL").  
- `-PostgreSQL` (loại bỏ từ "PostgreSQL").  

📊 **Tại sao FULLTEXT tốt hơn `LIKE '%keyword%'`?**  
| **Phương pháp** | **Tốc độ** | **Hỗ trợ ngữ nghĩa** | **Tìm kiếm nhiều từ** |
|---------------|----------|----------------|----------------|
| `LIKE '%keyword%'` | Chậm | ❌ Không | ❌ Không |
| `FULLTEXT` | Nhanh hơn | ✅ Có | ✅ Có |

---

### **3. PARTITIONING – Chia nhỏ bảng để tối ưu hiệu suất**  
#### **3.1. Mục đích**  
- **Tăng tốc truy vấn với bảng dữ liệu lớn (hàng triệu đến hàng tỷ bản ghi).**  
- Chia bảng thành nhiều phần (`partition`), mỗi phần lưu trên ổ đĩa khác nhau để **tăng tốc tìm kiếm và tránh quá tải**.  
- Hữu ích khi truy vấn theo **ngày tháng, ID, hoặc danh mục cụ thể**.  

#### **3.2. Đặc điểm**  
✅ **Tăng hiệu suất cho bảng lớn bằng cách chia nhỏ dữ liệu.**  
✅ **Hoạt động tốt với truy vấn lọc (`WHERE partition_column = value`).**  
❌ **Không hỗ trợ chỉ mục trên cột được partition.**  
❌ **Không hỗ trợ `FOREIGN KEY`.**  

#### **3.3. Các loại Partitioning**  
| **Loại** | **Mô tả** | **Khi nào dùng?** |
|---------|---------|-----------------|
| **RANGE** | Chia theo khoảng giá trị (vd: năm, tháng) | Khi có dữ liệu theo thời gian |
| **LIST** | Chia theo danh sách giá trị cụ thể | Khi có dữ liệu theo nhóm xác định |
| **HASH** | Chia theo giá trị băm (ngẫu nhiên) | Khi cần chia đều dữ liệu |
| **KEY** | Giống HASH nhưng do MySQL tự tính toán | Khi không có cột số rõ ràng để chia |

#### **3.4. Ví dụ**  
##### **✅ Partition theo năm (`RANGE`)**  
```sql
CREATE TABLE orders (
    id INT NOT NULL,
    order_date DATE NOT NULL,
    total DECIMAL(10,2) NOT NULL,
    PRIMARY KEY (id, order_date)
) PARTITION BY RANGE(YEAR(order_date)) (
    PARTITION p2019 VALUES LESS THAN (2020),
    PARTITION p2020 VALUES LESS THAN (2021),
    PARTITION p2021 VALUES LESS THAN (2022)
);
```
- Lệnh trên chia bảng `orders` thành 3 phần dựa trên năm.  
- Khi tìm kiếm `WHERE order_date >= '2020-01-01'`, MySQL **chỉ quét partition 2020 trở đi** → Truy vấn nhanh hơn.  

##### **✅ Partition theo khu vực (`LIST`)**  
```sql
CREATE TABLE customers (
    id INT NOT NULL,
    region VARCHAR(20) NOT NULL,
    PRIMARY KEY (id, region)
) PARTITION BY LIST COLUMNS(region) (
    PARTITION pNorth VALUES IN ('North America', 'Europe'),
    PARTITION pAsia VALUES IN ('China', 'Japan', 'India')
);
```
- Nếu tìm kiếm khách hàng ở `China`, MySQL chỉ quét partition `pAsia` thay vì toàn bộ bảng.  

---

## **🔍 Tổng kết: Nên dùng loại nào?**
| **Loại** | **Dùng khi nào?** | **Ưu điểm** | **Nhược điểm** |
|----------|-----------------|-------------|--------------|
| **INDEX (B-Tree)** | Khi tìm kiếm dữ liệu chính xác (`=`, `>`, `<`, `LIKE 'abc%'`). | Tăng tốc tìm kiếm với cột có tính duy nhất cao. | Không tối ưu cho tìm kiếm văn bản dài. |
| **FULLTEXT INDEX** | Khi tìm kiếm văn bản dài, mô tả sản phẩm, bài viết. | Hỗ trợ tìm kiếm nhiều từ, Boolean search. | Không hoạt động với số và không hỗ trợ JOIN tốt. |
| **PARTITIONING** | Khi bảng có dữ liệu rất lớn (hàng triệu dòng). | Truy vấn nhanh hơn khi lọc theo `WHERE`. | Không hỗ trợ chỉ mục trên cột partition. |

---

📌 **Kết luận:**  
- **Tìm kiếm chính xác → Dùng `INDEX`**.  
- **Tìm kiếm văn bản dài → Dùng `FULLTEXT INDEX`**.  
- **Dữ liệu quá lớn → Dùng `PARTITIONING`**.  

## **Tối ưu hóa Transaction trong MySQL**  
Transaction (giao dịch) là một tập hợp các thao tác SQL được thực hiện cùng nhau để đảm bảo tính nhất quán của dữ liệu. Nếu một thao tác thất bại, tất cả các thao tác khác trong transaction sẽ bị hủy (`ROLLBACK`).  

Việc tối ưu transaction giúp **giảm lock, tăng hiệu suất, tránh deadlock và cải thiện độ tin cậy của hệ thống**.  

---

### **1. Nguyên tắc cơ bản của Transaction trong MySQL**
#### **1.1. ACID – 4 tính chất quan trọng của transaction**
🔹 **Atomicity (Tính nguyên tử):** Toàn bộ transaction thành công hoặc bị hủy toàn bộ.  
🔹 **Consistency (Tính nhất quán):** Dữ liệu luôn ở trạng thái hợp lệ trước và sau transaction.  
🔹 **Isolation (Tính cô lập):** Transaction không bị ảnh hưởng bởi transaction khác đang chạy.  
🔹 **Durability (Tính bền vững):** Dữ liệu được lưu vĩnh viễn sau khi transaction `COMMIT`.  

#### **1.2. Các câu lệnh transaction cơ bản**
```sql
START TRANSACTION;  -- Bắt đầu transaction
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;  -- Xác nhận transaction
```
- Nếu một bước thất bại, bạn có thể `ROLLBACK` để hủy toàn bộ transaction.  

---

### **2. Các vấn đề hiệu suất khi sử dụng Transaction**
Việc sử dụng transaction không hợp lý có thể làm chậm hệ thống do **lock**, **deadlock**, và **giữ tài nguyên quá lâu**.  

### **2.1. Hiện tượng Lock (Khóa dữ liệu)**
#### **🔹 MySQL có hai loại lock chính:**
- **Table Lock:** Khóa toàn bộ bảng (thường thấy ở MyISAM).  
- **Row Lock:** Chỉ khóa các dòng liên quan (InnoDB hỗ trợ).  

✅ **Dùng InnoDB để hỗ trợ Row Lock, tránh khóa toàn bộ bảng!**  
```sql
ALTER TABLE accounts ENGINE = InnoDB;
```

✅ **Tránh SELECT ... FOR UPDATE khi không cần thiết**  
```sql
START TRANSACTION;
SELECT balance FROM accounts WHERE id = 1 FOR UPDATE;  -- Lock dòng này
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
COMMIT;
```
- Chỉ sử dụng `FOR UPDATE` khi thực sự cần tránh cập nhật đồng thời.  

---

### **2.2. Hiện tượng Deadlock (Giao dịch bị kẹt nhau)**
Deadlock xảy ra khi 2 transaction cùng khóa tài nguyên mà bên kia cần để tiếp tục.  

#### **🔹 Ví dụ deadlock:**
```sql
-- Transaction 1
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
```sql
-- Transaction 2
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 2;
UPDATE accounts SET balance = balance + 100 WHERE id = 1;
COMMIT;
```
🚨 **Cả hai transaction đều đang chờ nhau giải phóng lock → Deadlock!**  

#### **🔹 Cách tránh Deadlock**
✅ **Luôn cập nhật dữ liệu theo cùng một thứ tự trong tất cả transaction**.  
✅ **Sử dụng timeout cho transaction dài**:  
```sql
SET innodb_lock_wait_timeout = 5;  -- Chỉ chờ 5 giây nếu bị lock
```
✅ **Tách nhỏ transaction thay vì cập nhật quá nhiều dữ liệu cùng lúc**.  

---

### **3. Kỹ thuật tối ưu Transaction trong MySQL**
#### **3.1. Giảm thời gian giữ lock**
- Chỉ `START TRANSACTION` khi thực sự cần.  
- Tránh các câu lệnh `SELECT` kéo dài trong transaction.  
- **Chốt transaction nhanh chóng (`COMMIT` hoặc `ROLLBACK` sớm nhất có thể).**  
- Hạn chế `UPDATE` hoặc `DELETE` trên quá nhiều hàng cùng lúc.  

✅ **Ví dụ tối ưu hơn:**  
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;  -- Kết thúc transaction ngay khi có thể
```
🚀 **Không giữ transaction mở quá lâu!**

---

#### **3.2. Sử dụng Batch Processing thay vì Transaction dài**
Nếu bạn cần cập nhật nhiều bản ghi, thay vì chạy nhiều transaction, hãy dùng `BULK UPDATE` hoặc `INSERT`.  

✅ **Ví dụ tối ưu:**
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id IN (1, 2, 3, 4);
COMMIT;
```
⏩ **Nhanh hơn so với việc chạy 4 transaction riêng biệt!**

---

#### **3.3. Chỉ dùng Transaction khi thực sự cần**
Không phải thao tác nào cũng cần transaction.  
❌ **Ví dụ transaction không cần thiết:**  
```sql
START TRANSACTION;
SELECT * FROM users WHERE id = 10;
COMMIT;
```
✅ **Chỉ cần dùng `SELECT` thông thường.**

---

### **4. Cấu hình MySQL để tối ưu Transaction**
#### **4.1. Tăng bộ nhớ InnoDB Buffer Pool**
InnoDB sử dụng bộ nhớ cache (`innodb_buffer_pool_size`) để giảm truy vấn đĩa.  
```sql
SHOW VARIABLES LIKE 'innodb_buffer_pool_size';
SET GLOBAL innodb_buffer_pool_size = 2G;  -- Tăng nếu có nhiều RAM
```
📌 **Nên đặt giá trị này chiếm khoảng 70% RAM nếu chỉ chạy MySQL.**

---

#### **4.2. Kiểm tra và tối ưu transaction log**
MySQL ghi transaction vào log (`innodb_log_file_size`), nếu log quá nhỏ có thể làm chậm `COMMIT`.  
```sql
SHOW VARIABLES LIKE 'innodb_log_file_size';
SET GLOBAL innodb_log_file_size = 512M;
```
📌 **Giá trị tối ưu thường là 25% tổng `innodb_buffer_pool_size`.**

---

#### **4.3. Giới hạn thời gian transaction (`innodb_lock_wait_timeout`)**
Nếu transaction bị lock quá lâu, nó có thể làm chậm toàn bộ hệ thống.  
```sql
SET GLOBAL innodb_lock_wait_timeout = 5;  -- Chỉ chờ 5 giây
```
✅ **Tránh trường hợp transaction bị treo quá lâu.**

---

### **5. Kết hợp Transaction và Queue để tăng hiệu suất**
Thay vì chạy transaction ngay lập tức, có thể **đẩy vào hàng đợi (queue) như RabbitMQ, Redis Queue** để xử lý sau.  

✅ **Ví dụ sử dụng queue với transaction trong Node.js (Sequelize):**
```javascript
async function transferMoney(userFrom, userTo, amount) {
    const transaction = await sequelize.transaction();
    try {
        await Account.update({ balance: sequelize.literal(`balance - ${amount}`) }, 
            { where: { id: userFrom }, transaction });

        await Account.update({ balance: sequelize.literal(`balance + ${amount}`) }, 
            { where: { id: userTo }, transaction });

        await transaction.commit();  // Chốt transaction nếu thành công
    } catch (error) {
        await transaction.rollback();  // Hủy nếu có lỗi
    }
}
```
🚀 **Cách này đảm bảo transaction không giữ lock lâu và tránh ảnh hưởng hiệu suất.**

---

## **🔍 Tổng kết – Cách tối ưu Transaction hiệu quả**
✅ **Giữ transaction ngắn gọn, tránh giữ lock lâu**.  
✅ **Luôn cập nhật theo cùng thứ tự để tránh deadlock**.  
✅ **Sử dụng Batch Processing thay vì transaction dài**.  
✅ **Tăng bộ nhớ `innodb_buffer_pool_size` để giảm I/O**.  
✅ **Giới hạn `innodb_lock_wait_timeout` để tránh treo hệ thống**.  
✅ **Kết hợp Queue để xử lý transaction lớn.**  

---

## **Lock trong MySQL: Khi nào xảy ra và các loại Transaction**  
Trong MySQL, **lock (khóa dữ liệu)** xảy ra khi nhiều transaction cùng truy cập hoặc thay đổi dữ liệu, nhằm đảm bảo tính toàn vẹn và nhất quán. Nếu lock không được quản lý tốt, nó có thể gây chậm hiệu suất hoặc **deadlock** (giao dịch bị kẹt nhau).  

---

## **1. Khi nào MySQL xảy ra Lock?**  
#### **1.1. Khi có thao tác đọc và ghi đồng thời**
- Nếu một transaction đang đọc (`SELECT ... FOR UPDATE` hoặc `LOCK IN SHARE MODE`), transaction khác không thể ghi vào dòng đó.  
- Nếu một transaction đang ghi (`INSERT`, `UPDATE`, `DELETE`), transaction khác không thể đọc hoặc ghi vào dòng đó cho đến khi nó `COMMIT` hoặc `ROLLBACK`.  

#### **1.2. Khi dùng các câu lệnh sau**
| **Lệnh SQL** | **Loại Lock** | **Mô tả** |
|-------------|-------------|---------|
| `SELECT ... LOCK IN SHARE MODE` | **Shared Lock (S)** | Không ai có thể sửa dữ liệu khi đang đọc. |
| `SELECT ... FOR UPDATE` | **Exclusive Lock (X)** | Khóa dữ liệu để chuẩn bị cập nhật. |
| `UPDATE`, `DELETE`, `INSERT` | **Exclusive Lock (X)** | Khóa dòng dữ liệu bị tác động. |
| `LOCK TABLES table_name WRITE` | **Table Lock** | Khóa toàn bộ bảng, không ai có thể đọc hoặc ghi. |
| `LOCK TABLES table_name READ` | **Table Lock** | Chỉ cho phép đọc, không ai có thể ghi. |

---

## **2. Các loại Lock trong MySQL**  
### **2.1. Table Lock (Khóa bảng)**
- **Khóa toàn bộ bảng**, không cho phép thao tác đồng thời.  
- Thường xảy ra trên MyISAM (không hỗ trợ khóa dòng).  
- Dùng khi cần **đảm bảo toàn bộ bảng không bị thay đổi** trong khi thao tác.  

✅ **Ví dụ khóa bảng**  
```sql
LOCK TABLES orders WRITE;   -- Chỉ cho phép ghi, không ai đọc được
UPDATE orders SET status = 'shipped' WHERE id = 1;
UNLOCK TABLES;
```

🚨 **Nhược điểm**:  
- Giữ lock quá lâu có thể gây tắc nghẽn.  
- Hạn chế tính đồng thời khi nhiều người dùng truy vấn cùng lúc.  

---

### **2.2. Row Lock (Khóa dòng - InnoDB)**
- Chỉ khóa các dòng dữ liệu liên quan thay vì toàn bộ bảng.  
- **Hỗ trợ trong InnoDB**, giúp tăng tính đồng thời.  
- Xảy ra khi dùng `SELECT ... FOR UPDATE`, `UPDATE`, `DELETE`.  

✅ **Ví dụ khóa dòng**  
```sql
START TRANSACTION;
SELECT balance FROM accounts WHERE id = 1 FOR UPDATE;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
COMMIT;
```
📌 **Trong lúc này, không transaction nào khác có thể ghi vào `accounts.id = 1`.**

🚨 **Nhược điểm**:  
- Nếu nhiều transaction cố gắng cập nhật cùng một dòng, có thể dẫn đến **deadlock**.  
- Khi truy vấn quá nhiều dòng, **Row Lock có thể biến thành Table Lock** (gọi là **Gap Lock**).  

---

### **2.3. Shared Lock (Khóa chia sẻ - S)**
- **Cho phép nhiều transaction đọc cùng lúc**, nhưng không ai có thể ghi.  
- Dùng `LOCK IN SHARE MODE`.  

✅ **Ví dụ Shared Lock**  
```sql
START TRANSACTION;
SELECT * FROM products WHERE id = 1 LOCK IN SHARE MODE;
COMMIT;
```
📌 **Các transaction khác có thể đọc, nhưng không thể UPDATE hoặc DELETE `products.id = 1`.**  

---

### **2.4. Exclusive Lock (Khóa độc quyền - X)**
- **Không cho phép đọc hoặc ghi đồng thời trên dòng bị lock**.  
- Xảy ra khi dùng `SELECT ... FOR UPDATE`.  

✅ **Ví dụ Exclusive Lock**  
```sql
START TRANSACTION;
SELECT * FROM orders WHERE id = 5 FOR UPDATE;
UPDATE orders SET status = 'processing' WHERE id = 5;
COMMIT;
```
📌 **Không ai có thể đọc `orders.id = 5` cho đến khi transaction này `COMMIT`.**  

---

### **2.5. Gap Lock (Khóa khoảng - InnoDB)**
- **Khóa khoảng giữa các dòng để tránh chèn dữ liệu mới.**  
- Xảy ra khi sử dụng `SELECT ... FOR UPDATE` hoặc `UPDATE` trên nhiều dòng.  

🚨 **Ví dụ Deadlock do Gap Lock**  
```sql
-- Transaction 1
START TRANSACTION;
SELECT * FROM customers WHERE id BETWEEN 10 AND 20 FOR UPDATE;
```
```sql
-- Transaction 2
START TRANSACTION;
INSERT INTO customers (id, name) VALUES (15, 'John Doe');  -- Bị chặn vì bị khóa khoảng
```
📌 **Transaction 2 bị kẹt vì khoảng `id BETWEEN 10 AND 20` đã bị Transaction 1 khóa!**  

✅ **Cách tránh:**  
- Chỉ khóa đúng dòng cần thiết.  
- Dùng `READ COMMITTED` thay vì `REPEATABLE READ` để giảm phạm vi Gap Lock.  
```sql
SET GLOBAL transaction_isolation = 'READ COMMITTED';
```

---

## **3. Các loại Transaction Isolation Levels trong MySQL**  
**Transaction Isolation Level** quyết định **mức độ ảnh hưởng giữa các transaction chạy song song**.  

| **Isolation Level** | **Hiện tượng** | **Tác động đến Lock** |
|--------------------|--------------|-------------------|
| **READ UNCOMMITTED** | Có thể đọc dữ liệu chưa commit (Dirty Read) | Không có lock, hiệu suất cao nhưng không an toàn. |
| **READ COMMITTED** | Chỉ đọc dữ liệu đã commit (Không có Dirty Read) | Chặn ghi, nhưng không chặn đọc dữ liệu đang cập nhật. |
| **REPEATABLE READ** *(Mặc định InnoDB)* | Mọi lần `SELECT` trong cùng một transaction đều thấy dữ liệu như ban đầu | Dùng **Gap Lock** để ngăn chèn dữ liệu mới. |
| **SERIALIZABLE** | Tất cả transaction chạy tuần tự, không song song | **Khóa toàn bộ bảng**, chậm nhưng an toàn nhất. |

✅ **Ví dụ thay đổi Isolation Level**  
```sql
SET SESSION TRANSACTION ISOLATION LEVEL REPEATABLE READ;
START TRANSACTION;
SELECT * FROM orders WHERE id = 1 FOR UPDATE;
COMMIT;
```

🚀 **Khi nào nên dùng gì?**  
- **READ UNCOMMITTED** → Khi chỉ cần hiệu suất cao, không quan trọng độ chính xác.  
- **READ COMMITTED** → Khi cần tránh **Dirty Read** nhưng vẫn muốn tốc độ cao.  
- **REPEATABLE READ** (Mặc định) → Khi cần tránh **Phantom Read** nhưng vẫn giữ hiệu suất tốt.  
- **SERIALIZABLE** → Khi cần dữ liệu chính xác tuyệt đối (ví dụ: xử lý ngân hàng).  

---

## **4. Tổng kết – Cách tránh Lock và tối ưu Transaction**
✅ **Sử dụng InnoDB thay vì MyISAM để hỗ trợ Row Lock.**  
✅ **Tránh giữ transaction quá lâu, commit sớm nhất có thể.**  
✅ **Luôn cập nhật dữ liệu theo cùng thứ tự để tránh Deadlock.**  
✅ **Chỉ khóa dòng khi cần (dùng `FOR UPDATE` thay vì `LOCK TABLES`).**  
✅ **Dùng Isolation Level phù hợp với ứng dụng.**  
✅ **Tránh Gap Lock bằng cách dùng `READ COMMITTED`.**  
✅ **Dùng Queue (RabbitMQ, Redis Queue) để giảm tải transaction đồng thời.**  

## **Các loại Transaction trong MySQL – Chi tiết và Ví dụ Cụ thể**  

Trong MySQL, **transaction** là một tập hợp các câu lệnh SQL thực hiện như một đơn vị duy nhất để đảm bảo tính nhất quán của dữ liệu.  
Khi làm việc với transaction, cần hiểu rõ **các loại transaction** cũng như **cách chúng ảnh hưởng đến dữ liệu và lock**.  

---

## **1. Các loại Transaction trong MySQL**  
### **1.1. Implicit Transaction (Giao dịch ngầm định)**
- Mỗi câu lệnh SQL như `INSERT`, `UPDATE`, `DELETE` được MySQL coi là một transaction riêng lẻ.  
- **Mặc định, MySQL chạy ở chế độ Auto-Commit**, nghĩa là mỗi lệnh SQL tự động `COMMIT` ngay sau khi thực hiện.  

✅ **Ví dụ:**  
```sql
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
```
📌 **Mỗi lệnh là một transaction riêng biệt → Không thể `ROLLBACK` nếu có lỗi.**  

✅ **Tắt Auto-Commit để kiểm soát transaction thủ công:**  
```sql
SET autocommit = 0;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

🚀 **Nhược điểm:**  
- Không đảm bảo tính nhất quán nếu một lệnh bị lỗi giữa chừng.  
- Không thể thực hiện `ROLLBACK` nếu có lỗi xảy ra.  

---

### **1.2. Explicit Transaction (Giao dịch tường minh)**
- Cho phép **nhóm nhiều câu lệnh thành một transaction duy nhất**.  
- Chỉ `COMMIT` khi tất cả câu lệnh thành công, nếu có lỗi thì `ROLLBACK`.  

✅ **Ví dụ chuyển tiền (có kiểm soát lỗi):**  
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
📌 **Nếu bất kỳ lệnh nào lỗi, dữ liệu không bị ảnh hưởng (có thể `ROLLBACK`).**  

🚀 **Ưu điểm:**  
- Đảm bảo dữ liệu nhất quán nếu có lỗi.  
- Có thể kiểm soát việc `COMMIT` hoặc `ROLLBACK`.  

---

### **1.3. Savepoint Transaction (Giao dịch có điểm lưu)**
- **Cho phép rollback từng phần trong transaction**, thay vì rollback toàn bộ.  
- Dùng `SAVEPOINT` để tạo điểm khôi phục trong transaction.  

✅ **Ví dụ:**  
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
SAVEPOINT before_second_update;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

-- Giả sử lệnh thứ hai bị lỗi
ROLLBACK TO before_second_update;  -- Quay lại trước khi update tài khoản 2
COMMIT;
```
📌 **Tài khoản 1 đã bị trừ tiền, nhưng tài khoản 2 chưa được cộng tiền do lỗi.**  

🚀 **Khi nào nên dùng?**  
- Khi cần rollback một phần dữ liệu mà không phải rollback toàn bộ transaction.  
- Khi có nhiều bước trong transaction và muốn rollback linh hoạt.  

---

### **1.4. Chained Transaction (Giao dịch liên kết)**
- Tự động bắt đầu một transaction mới sau khi `COMMIT` hoặc `ROLLBACK`.  

✅ **Ví dụ:**  
```sql
SET autocommit = 0;
START TRANSACTION;
UPDATE orders SET status = 'shipped' WHERE id = 5;
COMMIT;  -- Transaction này kết thúc, nhưng MySQL tự bắt đầu transaction mới
```
📌 **Mỗi lần `COMMIT`, một transaction mới được tạo ngay lập tức.**  

🚀 **Khi nào dùng?**  
- Khi làm việc với nhiều transaction nối tiếp nhau mà không cần phải `START TRANSACTION` thủ công mỗi lần.  

---

### **1.5. Distributed Transaction (Giao dịch phân tán)**
- Giao dịch thực hiện trên **nhiều cơ sở dữ liệu hoặc nhiều server khác nhau**.  
- Dùng **XA Transactions** để đảm bảo tất cả database tham gia đều commit thành công.  

✅ **Ví dụ giao dịch trên nhiều database khác nhau:**  
```sql
XA START 'txn1';
UPDATE bank1.accounts SET balance = balance - 100 WHERE id = 1;
UPDATE bank2.accounts SET balance = balance + 100 WHERE id = 2;
XA END 'txn1';
XA PREPARE 'txn1';
XA COMMIT 'txn1';  -- Commit trên cả hai database
```
📌 **Nếu một lệnh lỗi, có thể rollback trên cả hai database.**  

🚀 **Khi nào dùng?**  
- Khi làm việc với **nhiều database khác nhau** (MySQL, PostgreSQL, MongoDB, v.v.).  
- Khi cần đảm bảo **tính toàn vẹn dữ liệu giữa các hệ thống khác nhau**.  

---

## **2. So sánh các loại Transaction**  

| **Loại Transaction** | **Tính năng chính** | **Khi nào dùng?** |
|---------------------|-----------------|---------------|
| **Implicit** | Tự động commit sau mỗi lệnh | Khi không cần rollback. |
| **Explicit** | Cho phép `COMMIT` hoặc `ROLLBACK` thủ công | Khi cần kiểm soát tính toàn vẹn dữ liệu. |
| **Savepoint** | Rollback từng phần trong transaction | Khi cần undo một phần dữ liệu thay vì toàn bộ. |
| **Chained** | Tự động bắt đầu transaction mới sau khi commit | Khi làm việc với nhiều transaction liên tiếp. |
| **Distributed (XA)** | Chạy trên nhiều database khác nhau | Khi cần giao dịch giữa nhiều server/database. |

---

## **3. Cách tối ưu Transaction để tránh Lock và Deadlock**
✅ **Luôn COMMIT sớm nhất có thể** để tránh giữ lock quá lâu.  
✅ **Sử dụng `ROW LOCK` thay vì `TABLE LOCK`** để tăng hiệu suất.  
✅ **Luôn cập nhật dữ liệu theo cùng thứ tự trong tất cả transaction** để tránh deadlock.  
✅ **Hạn chế `SELECT ... FOR UPDATE` nếu không cần thiết.**  
✅ **Dùng `READ COMMITTED` thay vì `REPEATABLE READ` để giảm Gap Lock.**  

📌 **Ví dụ tối ưu hóa giao dịch ngân hàng**  
```sql
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
🚀 **Giảm lock không cần thiết, tránh deadlock, và tăng hiệu suất!**  

---

## **4. Kết luận**
🔹 **Implicit Transaction:** Mặc định, mỗi câu SQL là một transaction.  
🔹 **Explicit Transaction:** Cần `START TRANSACTION` và `COMMIT`.  
🔹 **Savepoint Transaction:** Rollback từng phần thay vì toàn bộ.  
🔹 **Chained Transaction:** Tự động bắt đầu transaction mới sau khi commit.  
🔹 **Distributed Transaction:** Giao dịch trên nhiều database khác nhau.  

✅ **Chọn đúng loại transaction giúp đảm bảo tính toàn vẹn dữ liệu và tăng hiệu suất!**  

## **Các Chế Độ (Mode) của Transaction trong MySQL**  

Trong MySQL, **các chế độ của Transaction (Transaction Mode)** giúp kiểm soát cách dữ liệu được quản lý và lock trong quá trình xử lý. MySQL hỗ trợ các **Isolation Levels** và **Access Modes** để tối ưu hóa hiệu suất và tính nhất quán của dữ liệu.  

---

## **1. Các Chế Độ Isolation của Transaction (Isolation Levels)**  
Chế độ **Isolation Level** quy định mức độ **cô lập** giữa các transaction. MySQL hỗ trợ 4 cấp độ:  

| **Isolation Level** | **Dirty Read** | **Non-Repeatable Read** | **Phantom Read** | **Hiệu suất** |
|--------------------|--------------|------------------|--------------|--------------|
| **READ UNCOMMITTED** | ✅ Có | ✅ Có | ✅ Có | ⚡ Rất cao |
| **READ COMMITTED** | ❌ Không | ✅ Có | ✅ Có | 🔥 Cao |
| **REPEATABLE READ** (Mặc định MySQL) | ❌ Không | ❌ Không | ✅ Có | 🔄 Trung bình |
| **SERIALIZABLE** | ❌ Không | ❌ Không | ❌ Không | 🐢 Thấp (Lock toàn bộ bảng) |

💡 **Giải thích các vấn đề:**  
- **Dirty Read:** Đọc dữ liệu chưa commit của transaction khác.  
- **Non-Repeatable Read:** Một transaction đọc cùng một dòng dữ liệu nhiều lần nhưng thấy giá trị khác nhau.  
- **Phantom Read:** Transaction A đọc một tập dữ liệu, Transaction B thêm bản ghi mới, Transaction A đọc lại và thấy khác.  

✅ **Cách thiết lập Isolation Level:**  
```sql
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```

---

### **2. Chi Tiết Từng Chế Độ Isolation**  

#### **2.1. READ UNCOMMITTED (Đọc dữ liệu chưa commit)**
- **Cho phép đọc dữ liệu chưa được commit** từ transaction khác.  
- **Nguy cơ:** Dirty Read → Transaction đọc dữ liệu tạm thời mà có thể bị rollback.  

✅ **Ví dụ:**  
```sql
-- Session 1: Chưa commit, nhưng Session 2 vẫn đọc được
START TRANSACTION;
UPDATE accounts SET balance = 1000 WHERE id = 1;
-- Không commit
```
```sql
-- Session 2: Đọc giá trị chưa commit
SELECT balance FROM accounts WHERE id = 1;  -- Kết quả: 1000 (có thể bị rollback sau đó)
```

---

#### **2.2. READ COMMITTED (Chỉ đọc dữ liệu đã commit)**
- **Chỉ đọc dữ liệu đã được commit** → Không bị dirty read.  
- **Nhược điểm:** Non-Repeatable Read → Nếu transaction khác update dữ liệu, ta đọc lại sẽ thấy giá trị thay đổi.  

✅ **Ví dụ:**  
```sql
-- Session 1: Transaction 1 bắt đầu
START TRANSACTION;
SELECT balance FROM accounts WHERE id = 1; -- Giá trị: 500

-- Session 2: Update rồi commit
START TRANSACTION;
UPDATE accounts SET balance = 1000 WHERE id = 1;
COMMIT;
```
```sql
-- Session 1: Đọc lại thấy giá trị đã thay đổi
SELECT balance FROM accounts WHERE id = 1; -- Giá trị: 1000 (khác so với lần đầu)
```

---

#### **2.3. REPEATABLE READ (Mặc định trong MySQL)**
- **Dữ liệu đọc trong transaction không thay đổi, ngay cả khi transaction khác update.**  
- **Ngăn Non-Repeatable Read, nhưng có thể gặp Phantom Read.**  

✅ **Ví dụ:**  
```sql
-- Session 1: Transaction 1 bắt đầu
START TRANSACTION;
SELECT balance FROM accounts WHERE id = 1; -- Giá trị: 500

-- Session 2: Update rồi commit
START TRANSACTION;
UPDATE accounts SET balance = 1000 WHERE id = 1;
COMMIT;
```
```sql
-- Session 1: Đọc lại vẫn thấy giá trị cũ (500)
SELECT balance FROM accounts WHERE id = 1; -- Giá trị: 500 (vì dùng REPEATABLE READ)
```
📌 **Dữ liệu trong transaction vẫn giữ nguyên đến khi commit!**  

---

#### **2.4. SERIALIZABLE (Mức cô lập cao nhất)**
- **Lock toàn bộ bảng khi đọc dữ liệu → Không có Dirty Read, Non-Repeatable Read, Phantom Read.**  
- **Tốn tài nguyên → Giảm hiệu suất đáng kể.**  

✅ **Ví dụ:**  
```sql
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
START TRANSACTION;
SELECT * FROM accounts WHERE balance > 100;
```
📌 **Transaction khác không thể update hoặc insert vào bảng này cho đến khi transaction hoàn tất.**  

---

## **3. Các Chế Độ Truy Cập (Access Mode)**
Access Mode kiểm soát cách transaction đọc và ghi dữ liệu.  

| **Access Mode** | **Ý nghĩa** | **Khi nào dùng?** |
|--------------|-----------|----------------|
| **READ WRITE** (Mặc định) | Có thể đọc và ghi dữ liệu | Khi cần thay đổi dữ liệu |
| **READ ONLY** | Chỉ đọc, không thể ghi dữ liệu | Khi chỉ cần đọc, không cập nhật dữ liệu |

✅ **Cách thiết lập READ ONLY**  
```sql
SET TRANSACTION READ ONLY;
START TRANSACTION;
SELECT * FROM accounts;
COMMIT;
```
📌 **Tăng hiệu suất vì không cần lock dữ liệu để ghi!**  

---

## **4. Chọn Chế Độ Isolation Phù Hợp**
| **Trường hợp** | **Isolation Level phù hợp** |
|--------------|----------------------|
| **Hệ thống cần hiệu suất cao, không quan tâm dữ liệu tạm thời** | READ UNCOMMITTED |
| **Hệ thống cần đảm bảo dữ liệu đọc là dữ liệu đã commit** | READ COMMITTED |
| **Hệ thống giao dịch tài chính, không muốn dữ liệu bị thay đổi giữa transaction** | REPEATABLE READ (mặc định) |
| **Hệ thống yêu cầu dữ liệu chính xác tuyệt đối, tránh hoàn toàn lỗi** | SERIALIZABLE |

---

## **5. Tối Ưu Transaction để Tránh Lock và Deadlock**
✅ **1. Luôn COMMIT sớm nhất có thể** để giải phóng lock.  
✅ **2. Dùng khóa hàng (Row Lock) thay vì khóa bảng (Table Lock).**  
✅ **3. Cập nhật dữ liệu theo cùng thứ tự trong mọi transaction để tránh deadlock.**  
✅ **4. Hạn chế sử dụng `SELECT ... FOR UPDATE` nếu không cần thiết.**  
✅ **5. Dùng `READ COMMITTED` thay vì `REPEATABLE READ` nếu không cần dữ liệu cố định trong transaction.**  

📌 **Ví dụ tối ưu giao dịch ngân hàng:**  
```sql
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
🚀 **Giảm lock không cần thiết, tránh deadlock, và tăng hiệu suất!**  

---

## **6. Kết Luận**
- **Isolation Level** giúp kiểm soát tính nhất quán của dữ liệu.  
- **Access Mode** giúp tối ưu hiệu suất khi chỉ đọc dữ liệu.  
- **Chọn đúng Transaction Mode giúp tối ưu hiệu suất và tránh deadlock.**  

## **Access Mode trong MySQL Transactions**  

Access Mode trong MySQL quyết định **transaction có thể đọc và ghi dữ liệu hay không**. Có hai chế độ chính:  

1. **READ WRITE (Mặc định)**
   - Cho phép transaction **đọc và ghi dữ liệu**.
   - Dùng khi cần cập nhật, xóa, chèn dữ liệu.  
   - Mặc định nếu không chỉ định.  

2. **READ ONLY**  
   - **Chỉ cho phép đọc dữ liệu, không thể ghi**.  
   - Giảm **lock**, tăng hiệu suất với các hệ thống chỉ cần đọc.  
   - Hữu ích trong **báo cáo, phân tích dữ liệu**.  

---

## **1. READ WRITE Mode (Mặc định)**
🔹 **Đọc và ghi dữ liệu bình thường**.  
🔹 Transaction có thể `INSERT`, `UPDATE`, `DELETE`.  

✅ **Ví dụ:**  
```sql
SET TRANSACTION READ WRITE;
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
📌 **Nếu có lỗi trong quá trình thực thi, có thể ROLLBACK.**  

---

## **2. READ ONLY Mode**
🔹 **Chỉ đọc dữ liệu, không cho phép INSERT, UPDATE, DELETE.**  
🔹 **Giúp tăng hiệu suất vì MySQL không cần theo dõi thay đổi dữ liệu.**  
🔹 **Hạn chế lock, tránh xung đột khi có nhiều transaction chạy đồng thời.**  

✅ **Cách thiết lập:**  
```sql
SET TRANSACTION READ ONLY;
START TRANSACTION;
SELECT * FROM accounts WHERE balance > 500;
COMMIT;
```
📌 **Chỉ có thể thực hiện SELECT, nếu cố ghi dữ liệu sẽ bị lỗi.**  

🚨 **Ví dụ thử ghi dữ liệu trong READ ONLY Mode (Sẽ bị lỗi):**  
```sql
SET TRANSACTION READ ONLY;
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;  -- ❌ Lỗi!
COMMIT;
```
⚠️ **MySQL sẽ báo lỗi:**  
```
ERROR 1792 (HY000): Cannot execute statement in a READ ONLY transaction.
```

---

## **3. Khi nào sử dụng READ ONLY?**
✅ **Dùng khi cần đọc dữ liệu mà không muốn thay đổi nó.**  
✅ **Giảm lock, tăng tốc độ khi chạy truy vấn lớn.**  
✅ **Hữu ích trong các hệ thống báo cáo, dashboard, backup dữ liệu.**  

📌 **Ví dụ: Chạy báo cáo mà không ảnh hưởng đến hệ thống chính**  
```sql
SET TRANSACTION READ ONLY;
START TRANSACTION;
SELECT SUM(balance) FROM accounts WHERE balance > 500;
COMMIT;
```
🚀 **Tăng hiệu suất vì MySQL không phải lo xử lý lock hoặc rollback!**  

---

## **4. So sánh READ WRITE vs READ ONLY**

| **Tính năng**          | **READ WRITE (Mặc định)** | **READ ONLY** |
|----------------------|-------------------|------------|
| **Có thể INSERT/UPDATE/DELETE?** | ✅ Có | ❌ Không |
| **Có thể SELECT?** | ✅ Có | ✅ Có |
| **Giảm lock và tăng hiệu suất?** | ❌ Không | ✅ Có |
| **Dùng cho transaction ghi dữ liệu?** | ✅ Có | ❌ Không |
| **Dùng cho báo cáo, dashboard?** | ❌ Không | ✅ Có |

---

## **5. Kết luận**
- **READ WRITE** → **Cho phép ghi dữ liệu**, dùng cho các transaction bình thường.  
- **READ ONLY** → **Chỉ đọc dữ liệu, tăng hiệu suất**, dùng cho báo cáo và đọc dữ liệu lớn.  

Có nhiều kiến thức nâng cao về **MySQL Transactions và tối ưu hóa hệ thống** mà bạn có thể quan tâm. Dưới đây là một số chủ đề quan trọng giúp bạn nâng cao hiệu suất và đảm bảo tính toàn vẹn dữ liệu.  

---

## **1. SAVEPOINT và ROLLBACK TO SAVEPOINT**  
#### 🔹 **Cho phép rollback một phần transaction thay vì toàn bộ.**  
- **Khi nào cần dùng?**  
  - Khi transaction phức tạp có nhiều bước, nhưng chỉ cần rollback một phần thay vì toàn bộ.  

✅ **Ví dụ: Dùng SAVEPOINT để rollback một phần dữ liệu**  
```sql
START TRANSACTION;

UPDATE accounts SET balance = balance - 500 WHERE id = 1;
SAVEPOINT sp1;  -- Lưu trạng thái

UPDATE accounts SET balance = balance - 300 WHERE id = 2;
SAVEPOINT sp2;  -- Lưu trạng thái

-- Nếu xảy ra lỗi, chỉ rollback phần sau SAVEPOINT sp1
ROLLBACK TO SAVEPOINT sp1;  -- Quay lại trạng thái sp1, giữ nguyên thay đổi trước đó

COMMIT;  -- Lưu lại các thay đổi còn lại
```
📌 **Tăng độ linh hoạt trong quản lý transaction, tránh rollback toàn bộ khi lỗi nhỏ.**

---

## **2. DEADLOCK: Cách phát hiện và tránh**
#### 🔹 **Deadlock xảy ra khi 2 transaction chờ nhau giải phóng tài nguyên.**  
- **MySQL tự động phát hiện deadlock và rollback một transaction.**  
- **Tuy nhiên, cần tối ưu để tránh bị rollback!**  

✅ **Ví dụ gây ra Deadlock**  
```sql
-- Session 1
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
-- Chờ vài giây...
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

-- Session 2
START TRANSACTION;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
-- Chờ vài giây...
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
```
📌 **Cả hai transaction khóa hàng và chờ nhau → Deadlock!**  

#### ✅ **Cách tránh Deadlock**
1. **Luôn cập nhật dữ liệu theo cùng một thứ tự** (ví dụ: luôn update `id=1` trước `id=2`).  
2. **Dùng `SELECT ... FOR UPDATE` cẩn thận** để tránh lock không cần thiết.  
3. **Giữ transaction ngắn gọn, commit sớm nhất có thể.**  
4. **Dùng InnoDB Engine thay vì MyISAM** (MyISAM chỉ hỗ trợ table-level locking).  

---

## **3. GROUP COMMIT: Tối ưu hiệu suất COMMIT**
#### 🔹 **Group Commit giúp giảm thời gian disk I/O khi có nhiều transaction cùng lúc.**  
- **MySQL ghi nhiều transaction vào disk cùng lúc thay vì từng cái một.**  
- **Hoạt động khi dùng InnoDB và Binary Log.**  

✅ **Cách kiểm tra Group Commit có hoạt động không**  
```sql
SHOW VARIABLES LIKE 'innodb_flush_log_at_trx_commit';
SHOW VARIABLES LIKE 'sync_binlog';
```
📌 **Nếu cả hai giá trị này là `1`, mỗi COMMIT sẽ ghi vào disk ngay lập tức, giảm hiệu suất.**  

✅ **Cách tăng hiệu suất bằng Group Commit**
```sql
SET GLOBAL innodb_flush_log_at_trx_commit = 2;
SET GLOBAL sync_binlog = 0;
```
🚀 **Tăng tốc độ khi có nhiều transaction mà không mất quá nhiều dữ liệu nếu hệ thống gặp sự cố.**  

---

## **4. MULTI-STATEMENT TRANSACTION: Thực thi nhiều lệnh trong một transaction**
#### 🔹 **Giảm số lần gửi lệnh từ ứng dụng đến MySQL, tăng tốc độ xử lý.**  
- **Thay vì gửi từng câu lệnh SQL, gửi nhiều lệnh cùng lúc để giảm overhead.**  

✅ **Ví dụ với MySQL CLI hoặc MySQLi (PHP)**  
```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;
COMMIT;
```
📌 **Gửi tất cả lệnh cùng lúc nhanh hơn gửi từng lệnh riêng lẻ.**  

---

## **5. PARTITION TABLE: Chia bảng lớn thành nhiều phần nhỏ**
#### 🔹 **Giảm tải cho index và tối ưu truy vấn khi bảng quá lớn.**  
- **Dùng khi bảng có hàng triệu hoặc hàng tỷ bản ghi.**  
- **MySQL tự động định tuyến truy vấn đến partition phù hợp.**  

✅ **Ví dụ: Chia bảng theo năm**  
```sql
CREATE TABLE orders (
    id INT NOT NULL,
    order_date DATE NOT NULL,
    amount DECIMAL(10,2) NOT NULL
) PARTITION BY RANGE (YEAR(order_date)) (
    PARTITION p2023 VALUES LESS THAN (2024),
    PARTITION p2024 VALUES LESS THAN (2025)
);
```
📌 **Tăng tốc độ truy vấn, vì MySQL chỉ tìm trong partition phù hợp!**  

---

## **6. VIRTUAL COLUMN: Cột ảo giúp tối ưu truy vấn**
#### 🔹 **Tạo cột dựa trên biểu thức, giảm chi phí lưu trữ nhưng vẫn có index.**  
- **Không cần lưu trữ dữ liệu thực tế, MySQL tự động tính toán khi truy vấn.**  

✅ **Ví dụ: Tạo cột `total_price` dựa trên `quantity * price`**  
```sql
ALTER TABLE orders ADD total_price DECIMAL(10,2) AS (quantity * price) VIRTUAL;
```
📌 **Không chiếm thêm dung lượng lưu trữ nhưng có thể index!**  

---

## **7. TUNING TRANSACTIONS: Tinh chỉnh MySQL để tối ưu hiệu suất**
#### 🔹 **Một số tham số quan trọng cần điều chỉnh**
| Tham số | Mặc định | Giá trị tối ưu |
|---------|----------|--------------|
| `innodb_buffer_pool_size` | 128MB | 50-75% RAM |
| `innodb_log_file_size` | 48MB | 512MB - 1GB |
| `innodb_flush_log_at_trx_commit` | 1 | 2 (Tăng hiệu suất) |
| `sync_binlog` | 1 | 0 (Tăng tốc độ ghi Binary Log) |

✅ **Cách kiểm tra và thay đổi giá trị này**  
```sql
SHOW VARIABLES LIKE 'innodb_buffer_pool_size';
SET GLOBAL innodb_buffer_pool_size = 4G;
```
📌 **Điều chỉnh giúp giảm I/O Disk và tăng hiệu suất transaction.**  

---

## **KẾT LUẬN**
| **Chủ đề** | **Lợi ích** |
|------------|------------|
| **SAVEPOINT** | Rollback một phần transaction |
| **Deadlock Handling** | Tránh conflict giữa transaction |
| **Group Commit** | Tăng tốc độ COMMIT |
| **Multi-Statement Transactions** | Giảm latency từ ứng dụng |
| **Partition Table** | Giảm tải cho bảng lớn |
| **Virtual Column** | Tăng tốc độ truy vấn |
| **Tuning MySQL** | Tối ưu bộ nhớ và hiệu suất |

📌 **Nếu bạn làm việc với hệ thống lớn hoặc cần tối ưu transaction, các kỹ thuật này sẽ giúp bạn cải thiện hiệu suất đáng kể!**  



