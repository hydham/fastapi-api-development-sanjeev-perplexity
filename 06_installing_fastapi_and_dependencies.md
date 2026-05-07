# 06_installing_fastapi_and_dependencies

So now that we got our environment set up, it's time to get started coding out our project.

And what I want you guys to do is first of all go to the FastAPI documentation. This is really important. What I want you guys to do is really get a solid understanding of how the documentation works, so pull up the FastAPI website and then head on over to the tutorial section and then select the intro part.

So this is going to walk us through setting up our project, and what we will need to do is first of all we need to install the FastAPI package. And so what we can do is we can either do `pip install fastapi` or we can do `pip install fastapi[all]`.

When we do `pip install fastapi[all]`, it's going to install all of the optional dependencies as well, which we may or may not need depending on what features we want. We're going to go ahead and use the all option because we're going to use a lot of them, and there's no point in having to go one by one and install them.

So that's what we're going to do. So here in our command line, and make sure that we are in our virtual environment, then just type in:

```bash
pip install fastapi[all]
```

And we'll let that run.

Now it's moving fairly fast, but if you kind of scroll through the history you'll notice a lot of packages and a lot of dependencies that are getting installed. So we'll take a look at those once it's done just to see what are the different dependencies that were installed.

And so now that that's done, if we type in:

```bash
pip freeze
```

This is going to show all of the packages that were installed. So it's not going to be just FastAPI. It's going to include a lot of the optional dependencies as well.

So if we take a look, um, you can see that we've got GraphQL installed if we want to use any GraphQL. We have `bcrypt`. We have `uvicorn`, that's going to be like our web server. We have `websockets` if we want to work with websockets. So it already comes bundled with a lot of things that we're going to use, um, and I just wanted to make sure that you guys understood what's happening when we passed that all flag.

And if you want to, if you open up your virtual environment folder and you go under `lib`, you'll see all of the, uh, the code associated with those packages that we installed. So that's where all of them are going to live.

So at this point FastAPI is installed, and in the next section we're finally going to create our first FastAPI application and get the server up and running.
