# 10_creating_post_routes

Till now we've only been working with GET requests, so all of the HTTP requests we've sent to our API all have been GET requests. And so now we're going to learn about POST requests, and they're a little bit different, and I want to kind of highlight what makes POST requests different than GET requests.

Now we're going to compare the two right now, and I've drawn out a little diagram for us. So at the left side we've got our web browser, or it could be our mobile device depending on whatever the front end is, and on the right side we've got our API server, so this is our FastAPI server.

Now with the GET request, what we do is we just send an HTTP GET request, and then we send that to our API server, and then our API server sends back some kind of data depending on what they're trying to get. So if they're trying to get a whole bunch of posts, we send back the posts.

Now with a POST request, it's going to be similar except there's one minor difference, and that is that with a POST request we can send data to the API server. So in this case a lot of times what you use a POST request for is for creating things.

So if I want to create a post, and when I say post I mean like a social media post, not POST as in POST request, but if I wanted to create a social media post, I would send an HTTP POST request, and I would include all of the data needed to create a post on my API server. So we'll send that data over to the API server, and the API server will send back whatever data it thinks it needs to send.

And so in real life if we were trying to create a post, we would include whatever data we needed for a post. So in this case we would include what's the title of the post, what's the content of the post, what's the user of the post. We send that to the API server. The API server can then talk to whatever database to actually create the post, and then it can send back some data, you know, something like hey I've successfully created the post, um, and then here's the final post after I create it, and send those details back to your web browser or your mobile devices.

So think of it like this. A GET request is basically saying, hey API server, give me some data, whereas a POST request is saying, hey API server, here's some data, do whatever you need to do with it. So it really controls the direction, uh, of flow of data, uh, between the front end and the API server.

So GET requests are getting data from the API server, whereas the POST request is sending data to the API server.

So now that we have a basic understanding of how POST requests work, let's go back to our code and see if we can create a path operation for a POST request.

So let's go below our last path operation, which was for getting posts, and let's create one for creating posts.

First things first, let's just actually create our decorator first.

```python
from fastapi import Body, FastAPI

app = FastAPI()

@app.get("/")
def root():
    return {"message": "Hello World"}

@app.get("/posts")
def get_posts():
    return {"data": "this is your post"}

@app.post("/createposts")
def create_post(payload: dict = Body(...)):
    print(payload)
    return {"message": "successfully created post"}
```

We'll do `app.post`, and instead of GET, uh, sorry, instead of GET we're going to say POST. So that's all it takes to convert a traditional GET request to a POST request. You just say `.post`, and then once again we're going to say whatever specific URL the user should go to to actually create the post.

Uh, now I'm going to do something a little bit bad. I'm going to say the path that we want to go to is called `createposts`, and if you've ever worked with APIs this is kind of going against best practice, but don't worry, we'll correct this in the next lesson because there are certain best practices. It's not going to break our application by any means.

Uh, we'll say this, and then we'll say `def`, and then here we'll just name our function. I'll just say `create_post`. Like I said, the name of the function never matters.

And then here what we're going to do is we're going to return, uh, we'll say `message`, and then we'll say `successfully created post`.

Let's save that, and let's go to our Postman. So we've got already one request, so I could just change this to POST, and then we have to change the URL in this case. So we'll go back and see that `createposts`, so it's going to be `/createposts`, and let's hit send and let's see what happens.

Look at that. `message successfully created`, so we have successfully sent a POST request to our API.

Now one thing I like to do with Postman is that you can create multiple requests and then have them saved. So I'm going to actually change this back to just go to `/posts`, and then go to GET, and we'll keep that, and what we can do is we can just add another request.

And so I'm just going to copy the URL here, I'm going to paste this, and then this is actually going to be `create posts`, and this could be a POST request. And so now we can hit a GET request and then hit a POST request really quickly because they're essentially, uh, we've got them in two different windows.

Now that's cool and all. However, the whole idea behind a POST request is to send some data to our API server. So how do we do that?

Well let's go to our POST request, and what we want to do is we want to send some data in the body of the request. And to do that within, uh, Postman you would go to the body section right here, and then within body what we want to do is go to raw and then select the type.

And normally when you're working with APIs you want to use JSON. However you can use XML and a few others. However most people use JSON, so we'll select JSON.

And then JSON looks very, it operates very similarly to a Python dictionary, so it's, uh, you know, curly braces and then it's going to be a whole bunch of key-value pairs. So here I'll say what's the title of my post? Well title of my post is going to be say `Top beaches in Florida`, and then the content of the post is going to say `Check out these awesome beaches`.

```json
{
  "title": "Top beaches in Florida",
  "content": "Check out these awesome beaches"
}
```

And so now if we hit send, let's see what happens. Great, so it says `successfully create a post`.

So we successfully, um, hit this endpoint, but in our path operation how do we actually extract the data that we sent in the body? How do we retrieve that body data?

Well what we can do is within our path operation function, I can just assign it some variable. So what variable do we want to store our body data? You can pick any name you want. I'm just going to say this represents `payload`, although it could be something like `body` or anything else.

So we'll say `payload`, and then what we want to do is call in, and then we want to say it's going to be of a type `dict`, and we want to set this equal to `Body(...)`, and we want to import this. So this is actually something that comes from the FastAPI library.

What this is going to do is it's going to extract all of the fields from the body. It's going to basically convert it to a Python dictionary, and it's going to store it inside a variable named `payload`. Pretty simple.

And all we have to do is let's say:

```python
print(payload)
```

Now if we hit that POST request again, look at this right here. We can see that it converted into a Python dictionary, and we extracted the title field as well as the content field.

And so that's how we extract the data from the body of the payload.
