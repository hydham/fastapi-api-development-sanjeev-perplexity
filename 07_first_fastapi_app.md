# 07_first_fastapi_app

Now that FastAPI is installed, let's go ahead and create our first application.

Inside of `main.py`, what we want to do is import FastAPI, create an instance of it, and then define our very first route.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def root():
    return {"message": "Hello World"}
```

So let's break down what's happening here.

First of all, we imported `FastAPI` from the library. Then we created an instance of `FastAPI` and stored it in a variable called `app`. And then below that, we created our first path operation.

Now to actually run our API, we need to start up a server, and the server we're going to use is Uvicorn. So in the terminal, make sure you're still in your virtual environment, and then run:

```bash
uvicorn main:app
```

And what this means is: look for a file called `main`, and then inside that file look for an object called `app`, which is our FastAPI instance.

Now once that starts, it should tell you what URL the server is running on. Usually it's going to be something like `http://127.0.0.1:8000`.

So if we go back to the browser, go to our web server, if you take a look at this message `Hello World`, that's exactly what we sent. And if we change this to be whatever we want, it's going to get returned back in the same way.

So here we're just returning a Python dictionary, I guess, and what happens is FastAPI will automatically convert this to JSON, which is the main universal language of APIs, right? We all use JSON to send data back and forth between an API. So it converts this to JSON and it sends it back to the user, and that's why we see that on the web browser.

Now the next thing that we have is this decorator. If you're not really familiar with decorators in Python, it's okay. You don't really actually need to understand, you know, the core concept of a decorator. Just understand that when you apply a decorator to a function, it's going to perform a little magic to this function.

Because if I remove this decorator, if we just comment it out, take a look at this code. This code has nothing to do with FastAPI. It's a plain old function. So how do we actually make it, you know, act like an API? Well we have to use this magical decorator.

This decorator turns this into an actual path operation so that someone who wants to use our API can hit this endpoint. Uh, and so you just specify the `@` symbol, that's how we clarify that this is going to be a decorator. Then we reference our FastAPI instance, and then we have a couple of different options.

So what here we pass in is the HTTP method that the user should use. So this is a GET method, which means that we have to send a GET request to our API, but we can use plenty of different HTTP methods.

And finally we have the path, uh, and so this is the root path. So it's a little bit hard to explain the path, but it's basically the path after the specific domain name of your API.

So if you take a look at our URL, our web server is hosted on this specific URL. If I go to this page, let's open up a new link and paste it in here, so the URL and the path in this case is just `/`, so that's the equivalent of just hitting enter right here or putting a slash, which doesn't change anything. It's the root path.

Now what I want to do is let's go ahead and make a simple change. So what I'm going to do is I'm going to change the message. I'm going to change the message to be `Welcome to my API`.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def root():
    return {"message": "Welcome to my API"}
```

We'll save this, go back to the root URL, because we changed it to the root URL, let's hit refresh. Notice how it still says `Hello World`. Nothing changed.

So what gives, right? You know, our code's changed, I saved it, why are we not updating it so that it returns `Welcome to my API`?

Well the problem is that anytime you make a change, we have to restart our server. So to restart our server, you hit `Control + C`, which is going to stop it. Then you could just hit the up arrow key so that you can find that command that you ran before, and just run it again.

And so now if I hit refresh, we can see that it updated.

And I'm sure you're thinking, well that's a little annoying. Every time I change my code I have to do a `Control + C` and then an up arrow and then hit enter just so that I can, you know, make sure that the server actually implements those changes.

And it is a little annoying, but there is a workaround. So if we go to the documentation, you'll see that when they run Uvicorn they pass in the `--reload` flag, and the reload flag will actually take a look at your code and monitor your code so anytime that you change your code it'll automatically restart your server for you.

So let's try that out. I'm going to do a `Control + C`, I'm going to hit the up arrow, and I'm going to pass in the `--reload` flag.

```bash
uvicorn main:app --reload
```

So we'll hit enter, and now what I want you to do is make some changes. So it doesn't really matter what you change. I'm just going to add a couple exclamation points, and then I'm going to hit save, and I want you to focus on what happens down here.

So if I hit save, look at that. It automatically restarted the server for me.

And so now if I go back to my website or my API, hit refresh, you can see that the exclamation points are there.

So moving forward, in a development environment only, when we're in a development environment, we're going to pass in the `--reload` flag. When we go to production, we don't need that. We're not going to be setting it up, because we're not going to be changing our code in a production environment.

And so I think that's a good stopping point here. Uh, in the next video we'll just quickly review exactly what is a path operation so that we could just reinforce what we learned in this lecture.
