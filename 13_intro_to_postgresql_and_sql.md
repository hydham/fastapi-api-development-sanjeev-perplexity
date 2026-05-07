# 13_intro_to_postgresql_and_sql

At this point I think we have a basic understanding of how to work with FastAPI and how to set up basic routes and work with path operations. Until now we've been storing all of our posts in memory, and I think we've made it to a point where we are ready to now start working with databases.

And so if you don't know what a database is, a database is a collection of organized data that can be easily accessed and managed. And so when it comes to any kind of application-related data, so things like users that have registered, posts that have been created, all of these pieces of information are going to be stored within a database. So it's going to be stored on disk so that we can retrieve this information at a later point in time.

Now when it comes to databases, we never actually interact with the databases directly. Instead what we have is a database management system that's going to sit in the middle. So when we want to perform an operation on a database, we're going to send that request to a database management system. That management system is then going to actually perform that operation, and then it's going to send the result back to us.

So we never talk to the databases directly. Instead we have a piece of software that sits in the middle and acts as the brains behind the database.

Now there's two major branches of databases. There's relational and NoSQL databases. Relational databases are usually SQL-based databases, and we're going to cover that in the next slide or so, but these are just some of the more popular relational and NoSQL databases that you guys have probably heard of.

In this course we're going to work exclusively with relational databases, and more specifically we're going to work with Postgres.

Now if you ultimately want to learn how to work with MySQL or Oracle or SQL Server or any of the other databases, keep in mind that at the core they are fundamentally no different than Postgres. You know, 90, I would say 97 percent of the things that we cover when it comes to Postgres is going to be almost identical in all of these other databases, because they all at the end of the day use SQL.

However, there is a little bit of slight, uh, nuance when it comes to each database. Each of them will implement it in a slightly different way, so you'll see that certain SQL commands aren't available in others. But for the most part all of the core things that we cover from a SQL perspective are going to be applicable to any of the other relational-based databases.

And so let's talk about SQL now.

So SQL, or structured query language, is a language that's used to communicate with the database management system. And so, you know, when we want to perform an operation, we're going to send a specific SQL statement to the database management system. It's going to then take that statement and then perform the operation on the database, and then it's going to send that result back to us.

So SQL is the language that we use to communicate with the database management system.

Now in the next video what we're going to do is we're going to install Postgres on both Windows and Mac depending on what you're using, and there's an important thing to note when it comes to installing Postgres, or really any database.

When you install an instance of Postgres, what we can actually do is we can carve out multiple separate databases, right? And this is kind of confusing at first because you're thinking, well we installed Postgres, we have a database. Yes, but what we can do is we can actually create two different databases that are completely isolated and have nothing to do with one another.

And that way if I have application one, we can create a database just for app one. And then if I have a second application that I create, this application can have a separate database as well. And these two databases are going to be completely separate and completely isolated so that they don't step on each other's toes.

So it's pretty cool, and it's a pretty awesome feature to be able to kind of carve out your Postgres instance to multiple databases.

And keep in mind that you don't necessarily always create a separate database instance for each application, right? There are scenarios where you might actually create an app that's going to make use of more than, uh, one database instance within Postgres. However those are very specific situations, maybe if you want some sort of multi-tenancy or things like that.

However we're just going to create one individual database instance for our application that's going to handle everything that we need.

Now when we install Postgres, what's going to happen is that the installation process is going to create a database within the Postgres instance called `postgres`. A little confusing, right? It's, uh, Postgres within Postgres.

But it's actually going to create this database named `postgres`, and the reason we need to do this is that if you ever want to connect to a Postgres instance, uh, what you have to do is you have to specify a database that you want to connect to. So some kind of default database that you want to connect to. You can't just connect to Postgres. You have to specify a database.

And so that's why the installation process creates one database for you, so that you can have something to connect to. However we won't necessarily need that instance once we create our own. However I usually just keep it in by default because it's not going to hurt anyone.
