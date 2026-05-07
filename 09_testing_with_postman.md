# 09_testing_with_postman

Till now we've been using our web browser to generate HTTP requests to test our API, and that's fine for now. However, once we start getting into more complex path operations and routes, so things that involve having to send a HTTP PUT or PATCH or any of the other methods, and having to send data to our API, it gets very complicated.

Because there's no way to natively do that in the browser without generating or building out a complete full front-end application, and to test an API you shouldn't have to build an entire front-end application to do that. That would be, you know, unmanageable, unscalable.

And so there's a lot of different tools that we have that we can use to test our API, and so one of these tools is called Postman. If you go to [Postman Downloads](https://www.postman.com/downloads/), you can download this app.

So go ahead and just hit the download button. It's going to automatically detect what your operating system is, but this is a very simple tool. It's just a tool that allows us to construct our own HTTP request.

So we get to specify the individual fields of an HTTP request. So we can specify, you know, what is the HTTP method, what's the URL, uh, what are the headers that we're going to apply, what's the body, what kind of data is that going to carry, is it going to have any authorization headers. So all of these things we get to construct in a nice GUI so that we can test our API.

So go ahead and download this. Now I've already got it downloaded, but once you've got it downloaded, open up the desktop application and you should see something like this, right? Everything should be relatively empty.

And what we want to do is if we want to create a new HTTP request, all we have to do is hit the plus button.

And before I do that, what I'm going to do is, um, let's change this to dark theme, so themes. I think this looks a little bit better. Yeah, that looks a lot better. And I'm also going to zoom in for you guys, uh, let's make it a little bit more. There you go. Hopefully that's nice and easy for you guys to see now.

Now so what we want to do is let's create a new HTTP request. So hit this plus button, and you can see that this provides us all of the fields that we need to actually create an HTTP request.

So the first thing that we need to do is specify what's the HTTP method. So if we go back to our code, right, we only have GET requests. So whether we want to hit either one of these path operations, it's going to have to be a GET request. So we're going to leave it as GET, but you can see we have all of the other options.

Then we have to specify the URL. So this is no different than the URL that we went to in our browser. So we just copy this URL, and we actually need the `http` in there as well probably. So if we actually go back to our server and see where we started it, and actually the best way to get the URL is just to stop it, start it, and then that's going to give us the URL.

And so if I leave this as the, you know, the root path, whether I include the slash it doesn't really matter actually, I can just hit send, and you look at this, this is the result that we got back from our API server. So it says `message hello world`, and once again you guys already know where that came from, and that came from this specific return statement.

And so you can see that this is so much easier than using a web browser. Well you guys may not notice how easy it is at this point, but once we get to constructing more complex path operations you'll see that it's so much easier to use a tool like this.

And keep in mind this isn't the only tool that does this. There are plenty of other applications that also do this. This is just the one that I'm familiar with and the one that I use, but I don't want to, you know, force any specific application down your throat. You guys can use whichever one you want. So if you already use one that you prefer, feel free to stick with it.

But before we wrap up this video, let's just test out our other, um, specific path. So this one's going to reside on `/posts`. We're going to try that, and we'll do `/posts`. We'll hit send, and look at that. We got our data that says `this is your post`.

So now we were successfully able to test both of our path operations using Postman, and moving forward for the rest of this course we're no longer going to use the web browser. We're going to use Postman to test out our API.
