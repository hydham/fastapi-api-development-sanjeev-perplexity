# 14_sql_queries_filters_updates_deletes

So now that we've got Postgres installed and we've got pgAdmin up and running, what we want to do is actually start creating tables and running some SQL.

And really the whole point here is to get comfortable with the basics of how data is stored and manipulated inside a relational database.

So when we create a table, what we're really doing is defining the structure of our data. We're saying what columns exist, what data types those columns have, and what constraints apply to them.

For example, if we wanted to create a simple posts table, the important columns might be things like `id`, `title`, `content`, `published`, and `created_at`.

And once that table exists, we can start running the core SQL operations that you're going to use all the time.

To retrieve all posts, we use:

```sql
SELECT * FROM posts;
```

If we want to retrieve just a single post, we can filter by id.

```sql
SELECT * FROM posts WHERE id = 1;
```

If we want to insert a brand new row into the table, we can use an insert statement.

```sql
INSERT INTO posts (title, content, published)
VALUES ('my first post', 'this is awesome', true);
```

And if we want to change something that already exists, then we use an update statement.

```sql
UPDATE posts
SET title = 'updated title'
WHERE id = 1;
```

And finally, if we want to remove a row completely, we can use delete.

```sql
DELETE FROM posts WHERE id = 1;
```

So that's really the core workflow. We create tables, we insert data, we retrieve data, we filter it, we update it, and we delete it.

And once those SQL fundamentals click, then connecting all of this to FastAPI becomes a whole lot easier because at that point you're not really guessing what the database is doing anymore.
