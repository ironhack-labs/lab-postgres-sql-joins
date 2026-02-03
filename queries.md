![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

## Iteration 2 - Joins

1. Using an **INNER JOIN**, list all books (left table) that have an assigned author (right table). The result should include only books with assigned authors.

```sql
library=# SELECT books.title, authors.name
library-# FROM books
library-# INNER JOIN authors ON books.author_id = authors.id;
                  title                  |      name
-----------------------------------------+-----------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling
 Harry Potter and the Goblet of Fire     | J.K. Rowling
 1984                                    | George Orwell
 Animal Farm                             | George Orwell
 Adventures of Huckleberry Finn          | Mark Twain
 The Adventures of Tom Sawyer            | Mark Twain
 Murder on the Orient Express            | Agatha Christie
 Oliver Twist                            | Charles Dickens
 To Kill a Mockingbird                   | Harper Lee
```

<br>

2. Using a **LEFT JOIN**, list all authors (left table) and their corresponding books on the (right table). The result should include all authors, including those who don't have any books assigned.

```sql
library=# SELECT authors.name, books.title
library-# FROM authors
library-# LEFT JOIN books ON authors.id = books.author_id;
        name         |                  title
---------------------+-----------------------------------------
 J.K. Rowling        | Harry Potter and the Chamber of Secrets
 J.K. Rowling        | Harry Potter and the Goblet of Fire
 George Orwell       | 1984
 George Orwell       | Animal Farm
 Mark Twain          | Adventures of Huckleberry Finn
 Mark Twain          | The Adventures of Tom Sawyer
 Agatha Christie     | Murder on the Orient Express
 Charles Dickens     | Oliver Twist
 Harper Lee          | To Kill a Mockingbird
 Stephen King        |
 Virginia Woolf      |
 F. Scott Fitzgerald |
 Leo Tolstoy    
```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding authors on the (left table). The result should include books without assigned authors.

```sql
library=# SELECT books.title, authors.name
library-# FROM authors
library-# RIGHT JOIN books ON authors.id = books.author_id;
                  title                  |      name
-----------------------------------------+-----------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling
 Harry Potter and the Goblet of Fire     | J.K. Rowling
 1984                                    | George Orwell
 Animal Farm                             | George Orwell
 Adventures of Huckleberry Finn          | Mark Twain
 The Adventures of Tom Sawyer            | Mark Twain
 Murder on the Orient Express            | Agatha Christie
 Oliver Twist                            | Charles Dickens
 To Kill a Mockingbird                   | Harper Lee
 The Mysterious Manuscript               |
 Echoes in the Void    
```

<br>

4. Using a **FULL JOIN**, list all records from the `books` and `authors` tables. The result should include all details from both tables, even if there are no match.

```sql
library=# SELECT books.title, authors.name
library-# FROM books
library-# FULL JOIN authors ON books.author_id = authors.id;
                  title                  |        name
-----------------------------------------+---------------------
 Harry Potter and the Chamber of Secrets | J.K. Rowling
 Harry Potter and the Goblet of Fire     | J.K. Rowling
 1984                                    | George Orwell
 Animal Farm                             | George Orwell
 Adventures of Huckleberry Finn          | Mark Twain
 The Adventures of Tom Sawyer            | Mark Twain
 Murder on the Orient Express            | Agatha Christie
 Oliver Twist                            | Charles Dickens
 To Kill a Mockingbird                   | Harper Lee
 The Mysterious Manuscript               |
 Echoes in the Void                      |
                                         | Stephen King
                                         | Virginia Woolf
                                         | F. Scott Fitzgerald
                                         | Leo Tolstoy
```

<br>

## BONUS: Iteration 3 - Joins (continued)

1. Using an **INNER JOIN**, list all books (left table) and their corresponding publishers on the (right table). The result should include the book's title, publisher's name, and location.

```sql
library=# SELECT books.title, publishers.name, publishers.location
library-# FROM books
library-# INNER JOIN publishers ON books.publisher_id = publishers.id;
                  title                  |         name         | location
-----------------------------------------+----------------------+----------
 Harry Potter and the Chamber of Secrets | Bloomsbury           | London
 Harry Potter and the Goblet of Fire     | Bloomsbury           | London
 1984                                    | Secker & Warburg     | London
 Animal Farm                             | Secker & Warburg     | London
 Adventures of Huckleberry Finn          | Chatto & Windus      | London
 The Adventures of Tom Sawyer            | Chatto & Windus      | London
 Murder on the Orient Express            | Penguin Books        | London
 Oliver Twist                            | Simon & Schuster     | New York
 To Kill a Mockingbird                   | Macmillan Publishers | London
```

<br>

2. Using a **LEFT JOIN**, list all publishers (left table) and any books they have published on the (right table). The result should include all publishers, including those who haven't published any books.

```sql
library=# SELECT publishers.name, books.title
library-# FROM publishers
library-# LEFT JOIN books ON publishers.id = books.publisher_id;
         name         |                  title
----------------------+-----------------------------------------
 Bloomsbury           | Harry Potter and the Chamber of Secrets
 Bloomsbury           | Harry Potter and the Goblet of Fire
 Secker & Warburg     | 1984
 Secker & Warburg     | Animal Farm
 Chatto & Windus      | Adventures of Huckleberry Finn
 Chatto & Windus      | The Adventures of Tom Sawyer
 Penguin Books        | Murder on the Orient Express
 Simon & Schuster     | Oliver Twist
 Macmillan Publishers | To Kill a Mockingbird
 Hachette Book Group  |
 HarperCollins        |
 Scholastic Inc.      |
 Random House         |
```

<br>

3. Using a **RIGHT JOIN**, list all books (right table) and their corresponding publishers on the (left table). The result should include all books, even those without a linked publisher.

```sql
library=#
library=# SELECT books.title, publishers.name
library-# FROM publishers
library-# RIGHT JOIN books ON publishers.id = books.publisher_id;
                  title                  |         name
-----------------------------------------+----------------------
 Harry Potter and the Chamber of Secrets | Bloomsbury
 Harry Potter and the Goblet of Fire     | Bloomsbury
 1984                                    | Secker & Warburg
 Animal Farm                             | Secker & Warburg
 Adventures of Huckleberry Finn          | Chatto & Windus
 The Adventures of Tom Sawyer            | Chatto & Windus
 Murder on the Orient Express            | Penguin Books
 Oliver Twist                            | Simon & Schuster
 To Kill a Mockingbird                   | Macmillan Publishers
 The Mysterious Manuscript               |
 Echoes in the Void                      |
```

<br>

4. Using a **FULL JOIN**, list all records from the `authors`, `books`, and `publishers` tables. The result should include all records from the three tables, even if there are no matches between them.

```sql
library=# SELECT authors.name, books.title, publishers.name
library-# FROM authors
library-# FULL JOIN books ON authors.id = books.author_id
library-# FULL JOIN publishers ON books.publisher_id = publishers.id;
        name         |                  title                  |         name
---------------------+-----------------------------------------+----------------------
 J.K. Rowling        | Harry Potter and the Chamber of Secrets | Bloomsbury
 J.K. Rowling        | Harry Potter and the Goblet of Fire     | Bloomsbury
 George Orwell       | 1984                                    | Secker & Warburg
 George Orwell       | Animal Farm                             | Secker & Warburg
 Mark Twain          | Adventures of Huckleberry Finn          | Chatto & Windus
 Mark Twain          | The Adventures of Tom Sawyer            | Chatto & Windus
 Agatha Christie     | Murder on the Orient Express            | Penguin Books
 Charles Dickens     | Oliver Twist                            | Simon & Schuster
 Harper Lee          | To Kill a Mockingbird                   | Macmillan Publishers
                     | The Mysterious Manuscript               |
                     | Echoes in the Void                      |
 Stephen King        |                                         |
 Virginia Woolf      |                                         |
 F. Scott Fitzgerald |                                         |
 Leo Tolstoy         |                                         |
                     |                                         | Hachette Book Group
                     |                                         | HarperCollins
                     |                                         | Scholastic Inc.
                     |                                         | Random House
```

<br>
