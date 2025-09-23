![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2 - Joins

1. Using an **INNER JOIN**, list all books (left table) that have an assigned author (right table). The result should include only books with assigned authors.

```sql
SELECT b.title, a.name AS author
FROM books b
INNER JOIN authors a ON b.author_id = a.id;

```

<br>

2. Using a **LEFT JOIN**, list all authors (left table) and their corresponding books on the (right table). The result should include all authors, including those who don't have any books assigned.

```sql
SELECT a.name AS author, b.title AS book
FROM authors a
LEFT JOIN books b ON b.author_id = a.id
ORDER BY a.name;

```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding authors on the (left table). The result should include books without assigned authors.

```sql
SELECT a.name AS author, b.title AS book
FROM authors a
RIGHT JOIN books b ON b.author_id = a.id
ORDER BY b.title;

```

<br>

4. Using a **FULL JOIN**, list all records from the `books` and `authors` tables. The result should include all details from both tables, even if there are no match.

```sql
SELECT a.name AS author, b.title AS book
FROM authors a
FULL JOIN books b ON b.author_id = a.id
ORDER BY author NULLS LAST, book NULLS LAST;

```

<br>

## BONUS: Iteration 3 - Joins (continued)

1. Using an **INNER JOIN**, list all books (left table) and their corresponding publishers on the (right table). The result should include the book's title, publisher's name, and location.

```sql
SELECT b.title, p.name AS publisher, p.location
FROM books b
INNER JOIN publishers p ON b.publisher_id = p.id
ORDER BY b.title;

```

<br>

2. Using a **LEFT JOIN**, list all publishers (left table) and any books they have published on the (right table). The result should include all publishers, including those who haven't published any books.

```sql
SELECT p.name AS publisher, b.title AS book
FROM publishers p
LEFT JOIN books b ON b.publisher_id = p.id
ORDER BY p.name;

```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding publishers on the (left table). The result should include all books, even those without a linked publisher.

```sql
SELECT p.name AS publisher, b.title AS book
FROM publishers p
RIGHT JOIN books b ON b.publisher_id = p.id
ORDER BY b.title;

```

<br>

4. Using a **FULL JOIN**, list all records from the `authors`, `books`, and `publishers` tables. The result should include all records from the three tables, even if there are no matches between them.

```sql
SELECT a.name  AS author,
       b.title AS book,
       p.name  AS publisher
FROM authors a
FULL JOIN books b
  ON b.author_id = a.id
FULL JOIN publishers p
  ON b.publisher_id = p.id
ORDER BY author NULLS LAST, book NULLS LAST, publisher NULLS LAST;

```

<br>
