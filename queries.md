
# Answers

## Iteration 2 - Joins

1. Using an **INNER JOIN**, list all books (left table) that have an assigned author (right table). The result should include only books with assigned authors.

SELECT \*
FROM books b
INNER JOIN authors a ON b.author_id = a.id



2. Using a **LEFT JOIN**, list all authors (left table) and their corresponding books on the (right table). The result should include all authors, including those who don't have any books assigned.


SELECT \*
FROM authors a
LEFR JOIN books b ON b.author_id = a.id


3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding authors on the (left table). The result should include books without assigned authors.


SELECT \*
FROM authors a
RIGHT JOIN books b ON b.author_id = a.id


4. Using a **FULL JOIN**, list all records from the `books` and `authors` tables. The result should include all details from both tables, even if there are no match.


SELECT \*
FROM authors a
FULL JOIN books b ON b.author_id = a.id

## BONUS: Iteration 3 - Joins (continued)

SELECT \*
FROM books b
INNER JOIN publishers p ON b.publisher_id = p.id

2. Using a **LEFT JOIN**, list all publishers (left table) and any books they have published on the (right table). The result should include all publishers, including those who haven't published any books.

SELECT \*
FROM publishers p
LEFT JOIN books b ON b.publisher_id = p.id

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding publishers on the (left table). The result should include all books, even those without a linked publisher.


SELECT \*
FROM publishers p
RIGHT JOIN books b ON b.publisher_id = p.id


4. Using a **FULL JOIN**, list all records from the `authors`, `books`, and `publishers` tables. The result should include all records from the three tables, even if there are no matches between them.


SELECT \*
FROM books b
FULL JOIN authors a ON b.author_id = a.id
FULL JOIN publishers p ON b.publisher_id = p.id


