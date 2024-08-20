![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2 - Joins

1. Using an **INNER JOIN**, list all books (left table) that have an assigned author (right table). The result should include only books with assigned authors.

```sql
SELECT books.title, authors.name
FROM books
INNER JOIN authors
ON books.author_id = authors.id;
                  title                  |      name
-----------------------------------------+-----------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling
 Harry Potter and the Goblet of Fire     | J.K. Rowling
 1984                                    | George Orwell
 Animal Farm                             | George Orwell
 Adventures of Huckleberry Finn          | Mark Twain
 The Adventures of Tom Sawyer            | Mark Twain
 Murder on the Orient Express            | Agatha Christie
 The Shining                             | Stephen King
 Oliver Twist                            | Charles Dickens
 War and Peace                           | Leo Tolstoy
 To Kill a Mockingbird                   | Harper Lee
(11 rows)


```

<br>

2. Using a **LEFT JOIN**, list all authors (left table) and their corresponding books on the (right table). The result should include all authors, including those who don't have any books assigned.

```sql
SELECT authors.name, books.title
FROM authors
LEFT JOIN books
ON authors.id = books.author_id;
        name         |                  title
---------------------+-----------------------------------------
 J.K. Rowling        | Harry Potter and the Chamber of Secrets
 J.K. Rowling        | Harry Potter and the Goblet of Fire
 George Orwell       | 1984
 George Orwell       | Animal Farm
 Mark Twain          | Adventures of Huckleberry Finn
 Mark Twain          | The Adventures of Tom Sawyer
 Agatha Christie     | Murder on the Orient Express
 Stephen King        | The Shining
 Charles Dickens     | Oliver Twist
 Leo Tolstoy         | War and Peace
 Harper Lee          | To Kill a Mockingbird
 Virginia Woolf      |
 F. Scott Fitzgerald |
(13 rows)


```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding authors on the (left table). The result should include books without assigned authors.

```sql
SELECT books.title, authors.name
FROM books
RIGHT JOIN authors
ON books.author_id = authors.id;
                  title                  |        name
-----------------------------------------+---------------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling
 Harry Potter and the Goblet of Fire     | J.K. Rowling
 1984                                    | George Orwell
 Animal Farm                             | George Orwell
 Adventures of Huckleberry Finn          | Mark Twain
 The Adventures of Tom Sawyer            | Mark Twain
 Murder on the Orient Express            | Agatha Christie
 The Shining                             | Stephen King
 Oliver Twist                            | Charles Dickens
 War and Peace                           | Leo Tolstoy
 To Kill a Mockingbird                   | Harper Lee
                                         | Virginia Woolf
                                         | F. Scott Fitzgerald
(13 rows)


```

<br>

4. Using a **FULL JOIN**, list all records from the `books` and `authors` tables. The result should include all details from both tables, even if there are no match.

```sql
SELECT books.title, authors.name
FROM books
FULL JOIN authors
ON books.author_id = authors.id;
                  title                  |        name
-----------------------------------------+---------------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling
 Harry Potter and the Goblet of Fire     | J.K. Rowling
 1984                                    | George Orwell
 Animal Farm                             | George Orwell
 Adventures of Huckleberry Finn          | Mark Twain
 The Adventures of Tom Sawyer            | Mark Twain
 Murder on the Orient Express            | Agatha Christie
 The Shining                             | Stephen King
 Oliver Twist                            | Charles Dickens
 War and Peace                           | Leo Tolstoy
 To Kill a Mockingbird                   | Harper Lee
                                         | Virginia Woolf
                                         | F. Scott Fitzgerald
(13 rows)


```

<br>

## BONUS: Iteration 3 - Joins (continued)

1. Using an **INNER JOIN**, list all books (left table) and their corresponding publishers on the (right table). The result should include the book's title, publisher's name, and location.

```sql
SELECT books.title, publishers.name, publishers.location
FROM books
INNER JOIN publishers
ON books.publisher_id = publishers.id;
                  title                  |         name         | location
-----------------------------------------+----------------------+----------
 Harry Potter and the Chamber of Secrets | Bloomsbury           | London
 Harry Potter and the Goblet of Fire     | Bloomsbury           | London
 1984                                    | Secker & Warburg     | London
 Animal Farm                             | Secker & Warburg     | London
 Adventures of Huckleberry Finn          | Chatto & Windus      | London
 The Adventures of Tom Sawyer            | Chatto & Windus      | London
 Murder on the Orient Express            | Penguin Books        | London
 The Shining                             | HarperCollins        | New York
 Oliver Twist                            | Simon & Schuster     | New York
 War and Peace                           | Random House         | New York
 To Kill a Mockingbird                   | Macmillan Publishers | London
(11 rows)


```

<br>

2. Using a **LEFT JOIN**, list all publishers (left table) and any books they have published on the (right table). The result should include all publishers, including those who haven't published any books.

```sql
SELECT publishers.name, books.title
FROM publishers
LEFT JOIN books
ON publishers.id = books.publisher_id;
         name         |                  title
----------------------+-----------------------------------------
 Bloomsbury           | Harry Potter and the Chamber of Secrets
 Bloomsbury           | Harry Potter and the Goblet of Fire
 Secker & Warburg     | 1984
 Secker & Warburg     | Animal Farm
 Chatto & Windus      | Adventures of Huckleberry Finn
 Chatto & Windus      | The Adventures of Tom Sawyer
 Penguin Books        | Murder on the Orient Express
 HarperCollins        | The Shining
 Simon & Schuster     | Oliver Twist
 Random House         | War and Peace
 Macmillan Publishers | To Kill a Mockingbird
 Hachette Book Group  |
 Scholastic Inc.      |
(13 rows)


```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding publishers on the (left table). The result should include all books, even those without a linked publisher.

```sql
SELECT books.title, publishers.name
FROM books
RIGHT JOIN publishers
ON books.publisher_id = publishers.id;
                  title                  |         name
-----------------------------------------+----------------------
 Harry Potter and the Chamber of Secrets | Bloomsbury
 Harry Potter and the Goblet of Fire     | Bloomsbury
 1984                                    | Secker & Warburg
 Animal Farm                             | Secker & Warburg
 Adventures of Huckleberry Finn          | Chatto & Windus
 The Adventures of Tom Sawyer            | Chatto & Windus
 Murder on the Orient Express            | Penguin Books
 The Shining                             | HarperCollins
 Oliver Twist                            | Simon & Schuster
 War and Peace                           | Random House
 To Kill a Mockingbird                   | Macmillan Publishers
                                         | Hachette Book Group
                                         | Scholastic Inc.
(13 rows)



```

<br>

4. Using a **FULL JOIN**, list all records from the `authors`, `books`, and `publishers` tables. The result should include all records from the three tables, even if there are no matches between them.

```sql
SELECT books.title, authors.name AS author, publishers.name AS publisher
FROM books
FULL JOIN authors
ON books.author_id = authors.id
FULL JOIN publishers
ON books.publisher_id = publishers.id;
                  title                  |       author        |      publisher
-----------------------------------------+---------------------+----------------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling        | Bloomsbury
 Harry Potter and the Goblet of Fire     | J.K. Rowling        | Bloomsbury
 1984                                    | George Orwell       | Secker & Warburg
 Animal Farm                             | George Orwell       | Secker & Warburg
 Adventures of Huckleberry Finn          | Mark Twain          | Chatto & Windus
 The Adventures of Tom Sawyer            | Mark Twain          | Chatto & Windus
 Murder on the Orient Express            | Agatha Christie     | Penguin Books
 The Shining                             | Stephen King        | HarperCollins
 Oliver Twist                            | Charles Dickens     | Simon & Schuster
 War and Peace                           | Leo Tolstoy         | Random House
 To Kill a Mockingbird                   | Harper Lee          | Macmillan Publishers
                                         | Virginia Woolf      |
                                         | F. Scott Fitzgerald |
                                         |                     | Hachette Book Group
                                         |                     | Scholastic Inc.
(15 rows)


```

<br>
