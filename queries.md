![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2 - Joins

1. Using an **INNER JOIN**, list all books (left table) that have an assigned author (right table). The result should include only books with assigned authors.

```sql
-- Your Query Goes Here
select books.title, authors.name from books
join authors
on authors.id = books.author_id
```

<br>

2. Using a **LEFT JOIN**, list all authors (left table) and their corresponding books on the (right table). The result should include all authors, including those who don't have any books assigned.

```sql
-- Your Query Goes Here
select books.title, authors.name from authors
left join books
on authors.id = books.author_id
```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding authors on the (left table). The result should include books without assigned authors.

```sql
-- Your Query Goes Here
select books.title, authors.name from authors
right join books
on authors.id = books.author_id
```

<br>

4. Using a **FULL JOIN**, list all records from the `books` and `authors` tables. The result should include all details from both tables, even if there are no match.

```sql
-- Your Query Goes Here
select * from authors
full join books
on authors.id = books.author_id
```

<br>

## BONUS: Iteration 3 - Joins (continued)

1. Using an **INNER JOIN**, list all books (left table) and their corresponding publishers on the (right table). The result should include the book's title, publisher's name, and location.

```sql
-- Your Query Goes Here
select books.title, publishers.name, publishers.location from books
join publishers
on publishers.id = books.publisher_id
```

<br>

2. Using a **LEFT JOIN**, list all publishers (left table) and any books they have published on the (right table). The result should include all publishers, including those who haven't published any books.

```sql
-- Your Query Goes Here
select publishers.name, publishers.location,books.title from publishers
left join books
on publishers.id = books.publisher_id
```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding publishers on the (left table). The result should include all books, even those without a linked publisher.

```sql
-- Your Query Goes Here
select publishers.name, publishers.location,books.title from publishers
right join books
on publishers.id = books.publisher_id
```

<br>

4. Using a **FULL JOIN**, list all records from the `authors`, `books`, and `publishers` tables. The result should include all records from the three tables, even if there are no matches between them.

```sql
-- Your Query Goes Here
select * from publishers
full join books
on publishers.id = books.publisher_id
full join authors
on authors.id = books.publisher_id
```

<br>
