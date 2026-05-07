# 08_path_operations_basics

All right guys, so let's quickly recap what we learned in the previous lecture. I want to make sure that you guys have a solid understanding of the different components of a path operation, because ultimately that's all your API is. It's just a bunch of path operations.

So first things first, we have our decorator. So our decorator has the little `@` symbol, and so that's what signifies it as a decorator. And then we reference our FastAPI instance, which we called `app`, and then we have our HTTP method. So in this case this is going to match only GET methods, and then we have our specific path or the URL, so this is the root URL in this case.

And then below that we've got our specific path operation function. So this function is going to contain all the logic for performing some kind of task, and it's going to return some data, and that's the data that gets returned to the user when they hit this specific path operation.

So now that we have a solid understanding of how path operations work, let's see if we can create a new path operation, and let's say this one represents retrieving a bunch of social media posts from our application.

So in this case, you know, there's two things that we need. So the first thing is our function, our path operation function. So we'll say `def`, and then we'll give this function any name. I think since we're going to be retrieving a bunch of posts, I think a good name is going to be `get_posts`, but keep in mind you can name this anything you want. Like I said, it does not impact the behavior of anything.

And then we want to say, uh, so here we would pass in all of our logic for retrieving posts, but we don't actually have an application, so I'm just going to say return, and then we'll just say, um, maybe, I don't know, data, and this is going to be `this is your post`, but in reality we would provide a list of posts.

So let's save that, and then there's one last thing. We have to pass in our decorator like we did before to actually make this turn into a special path operation function.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def root():
    return {"message": "Hello World"}

@app.get("/posts")
def get_posts():
    return {"data": "this is your post"}
```

So we'll say `@`, and we reference the instance, the FastAPI instance. We'll do `app.get`, and then we have to figure out what HTTP method we want to use for this path operation. So when it comes to retrieving data, uh, you usually use a GET operation.

Now for the URL, I'm going to say to retrieve posts we want to go to the `/posts` URL. So let's save this, and then let's see, um, if we can retrieve that data.

So if I hit refresh here, it's going to say `Hello World`, but that's because if you take a look at this, we're at the root path, and that's going to match this specific path operation. Uh, and this path operation is on `/posts`.

So if we go to `/posts` and then hit enter, take a look at that. We have now got our data, which is our post. So we've hit that second path operation that we just created, and it really is as simple as that. You just define a function, you define the HTTP method, and then the URL.

Now there's one thing to note, and that is that, um, you know, the way that FastAPI works is that when any time we send a request to our API server, uh, it's going to actually go down the list of all of our path operations, um, and then it's going to find the first match. And as soon as it finds the first match, it's going to stop running your code.

So if I actually change this to just a slash URL, just like this one above, what do you think is going to happen? All right, they both reference the GET method, and they both reference the same URL. So which one do you think is going to win?

Well let's take a look. If I do just the slash again, it says `Hello World`, so it looks like the first one won. And the reason for that is that once again FastAPI literally just goes to the code and it looks for the first match.

So there's really only two criteria in this case. What's the HTTP method? It's a GET, so any time you work in your browser, your browser is always going to send a GET method by default. And then what's the URL? So the URL is the slash URL, so it matches this one, and it does not continue past that. So it never runs this code.

So the first path operation that matches is always going to be the one that runs. Simple as that. So the order does in fact matter. However, if I change this to `posts` and leave this at the top, right, if I hit refresh, we get `Hello World` because they're hitting two different paths or two different URLs.

And the reason I wanted to highlight this is that the order in fact does matter, so you have to keep that in mind, and it can impact the way, uh, your API ultimately works.
