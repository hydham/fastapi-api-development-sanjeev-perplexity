# 15_connecting_fastapi_to_postgres

All right, so now it's time to actually connect our FastAPI application to Postgres.

And the first thing that we're going to do is use the default Postgres driver for Python, which is `psycopg2`.

So once you've installed that package, what we can do is import it into our application and then create a connection.

```python
import time
import psycopg2
from psycopg2.extras import RealDictCursor

while True:
    try:
        conn = psycopg2.connect(
            host='localhost',
            database='fastapi',
            user='postgres',
            password='password123',
            cursor_factory=RealDictCursor
        )
        cursor = conn.cursor()
        print('Database connection was successful!')
        break
    except Exception as error:
        print('Connecting to database failed')
        print('Error: ', error)
        time.sleep(2)
```

So what we're doing here is trying to connect to the database, and if it fails, we're just going to keep retrying every couple of seconds until it works.

And the reason I like doing it this way is because if the database isn't ready yet, or if there's some temporary issue, I don't want my whole app to just crash once and be done. I want it to keep retrying until the connection is available.

Now once we have a connection, we also create a cursor, and the cursor is what we're going to use to actually execute SQL commands.

And just as a quick test, if I change my password here and put it as an incorrect value, save this, and then run the code, we can see that the password failed. So that tells us the connection logic is actually working the way we expect.

Now I do want to point out one thing. Generally when you're working with your code, what we did right here is very bad. We hard coded all of our database information right into our code.

This creates a problem because first of all when we check this into Git, now our database password is stored in there. And then we run into some extra issues because this is the connection for our development environment. Our production Postgres server is not going to be running on localhost. Maybe the database might be called something else. The username and the password are for sure going to be different.

So if we hard code it in, we won't actually be able to change it in the future. We need a dynamic way to kind of have our code change based off of if it's in our development environment or our production environment.

So later on in this course we'll figure out how to do that. However, for now we're just going to work on keeping things simple and just learning how to interact with the database before we start moving into things like environment variables.

All right, so the first thing that we're going to work on is retrieving all of our posts from our post table.

And so what we're going to do is we'll go to our specific path operation for that, which is the `@app.get("/posts")` right here, and let's figure out how to do this.

So if we go back up to our connection, right, you'll see that we have access to this object right here, which is `cursor`. So we're going to use that to actually make a query.

```python
@app.get("/posts")
def get_posts():
    cursor.execute("""
        SELECT * FROM posts
    """)
    posts = cursor.fetchall()
    return {"data": posts}
```

So we'll say `cursor.execute`, and this is where we are going to paste in our SQL statements.

So in this case, right, to retrieve all posts we just do `SELECT * FROM posts`.

And then to actually run it and pull the rows back, we use `fetchall()`. Since we're retrieving multiple posts, we're going to always use `fetchall()`.

And at this point, you know, we don't actually need to save this in some fake variable anymore. We can save the output of this to be `posts`, and then return that back to the client.

So now we've actually successfully been able to retrieve posts from our Postgres database, and you can see how easy it is to actually work with that.

In fact, it was actually a little bit easier to do this than to actually work with just an array stored in memory. It really just comes down to understanding SQL, and since we spent, you know, the last half an hour or so really drilling into how SQL works, you'll see that SQL is pretty easy.

And then once you know SQL, you know, fetching, retrieving, updating, deleting posts from a SQL database, even within your Python code, is dead simple.
