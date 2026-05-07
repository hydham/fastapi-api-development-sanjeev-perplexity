# 01_course_overview

Hey how's it going everyone? I just wanted to welcome you to my Python API development course.

So in this course I'm going to walk you through building out your very own API in Python. However, keep in mind this course is so much more than just building out a simple API. In fact, as I'm sure you saw the video length, this course does come out to a whopping 19 hours in length.

And so you're probably wondering, well what exactly are we going to be covering for 19 hours? We don't need 19 hours to create an API.

Well first of all we're going to build out a fully featured API that includes authentication, CRUD operations, schema validation, and we're going to set up documentation for our API because that's very important.

However, the learning doesn't stop just there. This course is going to extend well past just basic API development. We'll also learn all of the tooling that surrounds building a complete and robust API.

I've dedicated a large section of this course to learning SQL, and I've noticed that a lot of the other API and web development courses, they just quickly gloss over SQL without diving into the nitty-gritty of how SQL databases work. For this course we're going to cover SQL extensively, and we're going to start from the absolute basics. So you don't need to know a single thing about databases or SQL in general, but by the time you complete this course you will be very proficient at generating database schemas. You'll know core SQL concepts like primary keys, foreign keys, table constraints, and you can pretty much be able to generate SQL queries to grab the exact data that you're looking for.

And on top of that, I'll show you how to integrate your SQL databases in your API using two different methods. So we'll cover both using raw SQL queries as well as ORMs so that no matter which method you ultimately prefer, you'll have all the skills and resources to start building out your own projects.

We'll also familiarize ourselves with database migration tools like Alembic, which allow us to make incremental changes to our database schema, to track changes in Git just like we can with our regular Python code.

We'll also learn how to use tools like Postman to construct HTTP packets so that we could test our API during the whole development process.

And when it comes to testing, I've added about, you know, two to three hours of content going over how to set up automated integration tests so that when you make changes to your code, you can run these automated tests to verify that your code changes haven't broke any pre-existing functionality.

And then after testing, we're going to move on to the deployment phase. We're going to actually deploy our application. And I didn't just include one method of deployment. I've actually included two different deployment scenarios.

The first scenario is probably, um, the most common scenario, which is deploying our app onto like an Ubuntu machine that can be hosted on any cloud provider like AWS, GCP, Azure, or even DigitalOcean. And, you know, we'll cover things like how to set up Nginx to act as a reverse proxy. We'll configure our own systemd service. We'll set up a firewall to block all non-HTTP traffic, and we'll even set up SSL so that our application can handle HTTPS traffic.

Um, but after that we'll also take a look at how we can deploy our application onto Heroku, just because if you don't have, you know, maybe you can't afford to pay for cloud services, um, or you just don't have the ability to sign up for an account or something like that, I do want to make sure that, uh, you still have a way of, uh, deploying your applications that you can show off to your friends and family what you created.

So I added the Heroku section because they've got a very, very nice and convenient free tier where we can deploy our entire application for free. We don't need to sign up with a credit card, so that's why I included that second deployment scenario.

And since all the cool kids are hardcore into Docker today, I'm going to show you how to Dockerize your API in case that is your preferred method of deployment.

And then finally we're going to wrap things up by building out our very own CI/CD pipeline using GitHub Actions. This will allow us to push out changes to GitHub, resulting in our pipeline running, which will pull our code, run all of our integration tests, build all of the necessary images, and if all the tests ultimately pass, it'll actually push out our changes to our production environment so that we can do all of this in an automated fashion without having to manually go in and run each step manually.

So let's take a look at our tech stack. Since this is a Python API course, we will be using Python to build out our API. There were a couple of different web frameworks in Python that we could have used, most notably Django and Flask. I decided to use neither one of them, and I decided to use a newer framework called FastAPI.

And the reason why I chose to use this framework was because it has APIs, uh, kind of built in mind, right? It wasn't there to address like the model-view-controller type scenario. It really is all about building out APIs.

And on top of that, it is really fast, right? But when I say fast, it's not just fast from a performance perspective, which it is, but it's also fast from the fact that it makes it really easy and quick to spin up new APIs.

And one of my favorite features of this framework is the auto documentation functionality. When you build an API you have to document how your API works, and this is a very cumbersome task because any time you make any changes to your API you have to remember to update your API or then the front end can be making the wrong request. FastAPI automatically documents your API for you so that you don't have to do it yourself. It's truly a game changer.

And finally, the most important reason why I chose FastAPI is because of this. You see this magnificent beast? This is the creator of the FastAPI framework, and my mom always told me when someone with the mustache as glorious as that creates a web framework, you use that damn framework.

Now as I mentioned, we will be covering SQL extensively, and I've decided to go with Postgres. It doesn't really matter what type of SQL database you use. They're all fundamentally the same with only minor differences. I chose Postgres because that's my favorite, and who doesn't like elephants anyways?

For our ORM, when we do eventually migrate to ORMs from using raw SQL queries, we will be using SQLAlchemy. Um, I decided to use that because that seems like that's the most standard one for Python. I really could have chosen any of them. I didn't really care which one I used, so I just picked the most popular one.

So that covers our tech stack. Let's now take a look at the project that we'll be building.

Now I would love to show you some cool flashy website that you can show off to your friends. However, we're not building a website. We're building an API, and unfortunately APIs don't really have a visual aspect to them, so I don't really have anything to show you. I mean, I could, I guess, construct a couple of HTTP packets that send it and verify that we get the proper JSON response, but that's not really exciting.

So what I'm going to do is I'm going to show you our documentation for our project so that you can see all the different features that we implement. And the nice part about the documentation is these are interactive docs, so from the documentation I can actually send HTTP requests to my application and get a response back. So you can really see all of the different features, things like the authentication and the CRUD operations that we'll be performing and setting up in our API.

So the app that we're going to build for this course is going to be a social media type application where users can create posts, uh, they can read other people's posts, they'll be able to perform all the CRUD operations, so they'll create, read, update, and delete posts, and we'll also be able to, uh, vote on posts. So, you know, most social media apps have some sort of like system or voting system, and so we will be able to like other users' posts as well.

So this is the built-in documentation that comes with FastAPI, and you'll be able to see all of the API endpoints that we're going to create in this course. So we're going to have all of the post endpoints, which is going to be responsible for retrieving all posts, creating posts, uh, retrieving an individual post, updating a post, as well as deleting a post. Then we'll have the user-specific, um, endpoints of things like creating a user, getting a user's information. And then we've got our authentication, which is going to be used for logging in. And then finally we've got the one for voting, so when you want to vote on a specific, um, a specific post that you like, you can go ahead and like that post.

So let's just use the documentation to actually, uh, you know, test out our API. So first things first, let's actually try to retrieve any or all of our posts. So if I hit this get button right here, we can actually try to send a request to our API with the built-in documentation. So you can just say execute, right, and you'll see that we got a 401, which means that we are right now not logged in, so we are unauthorized to retrieve any of the posts. So, uh, the API that we're going to build is going to require all users to be logged in to even be able to read the posts.

So let's actually go ahead and create a user. And so we'll go down to the users endpoint under create user, and I'm going to do try it out, and it's going to give us an example of the structure of the data that we have to send to our API to create a user. So we need to provide a username or an email and a password. So I'm going to create an email. I'll call this `john@gmail.com`, and the password is going to be something simple just for demonstration purposes, and we'll execute that, right, so it'll actually send that data back to our backend. You can see we get a 201, which means we're successfully able to create it. You can see the id of the user account that was created. We could see the email is what it is, and then we can see the date that it was created at as well.

And so now we can actually log in as this user. So there's a couple of different ways to log in. I can go to the login endpoint or we can just go up here at the top and just do authorize, and then we can provide that information. So I'll do `john@gmail.com`, and we'll provide his password, and if we do authorize now we can see that we have successfully logged in. So I'll close this out.

And so now if I try to retrieve the posts and then hit execute, you could see that we were able to retrieve all of the posts in our database. Right now there's only two, but you can see that these were created by some other users like Sanjeev in this case, and then `sanjeev123`.

And if we want to create our own post, we can go ahead and do that. So I'll go to the create post endpoint and we'll do try it out, and it's going to give us an example here. So we have to provide title, content, as well as is this post going to be published or is it going to be a draft. And you'll actually see the structure of this schema right down here. I think it's at the bottom actually. So if you go to post create here, this is going to show us the, uh, the schema that we have to pass. So we have to provide a title, a content, so the asterisk means it's required. The published is not required, and you can see that it defaults to true, so if we don't provide a value it'll default to true.

So let's test that out. And so I'll just say, um, favorite foods is going to be the title, and the content is going to be pizza and burgers, and I will remove the published section because it is optional and it'll default to true anyways, and we'll hit execute. And if we take a look at the response, we get a 201, which means it successfully created it, and you can see what the post looks like in our database. You've got the title, content. We can see the publish got defaulted to true. We could see the id of the post, when it was created. We could see the owner id, which is, you know, who created the post, and so that's the id of our account which is 17, and we can see the information about the owner, so this is `john@gmail.com`.

And then, you know, as usual, we could perform all the other CRUD operations, so we can retrieve an individual post, update it, and delete it. And then once again, if we go down here we can also vote to like a post as well.

And so, you know, this kind of forms the backbone of a traditional social media type application. So once you can really do this, you can really create any application you want. And I think this covers enough things from an API perspective as well as from a SQL and database perspective that you will have a solid foundation to really build out any API that you're interested in building out.

And so I think that's enough talking. Let's get to actually start coding out our application.
