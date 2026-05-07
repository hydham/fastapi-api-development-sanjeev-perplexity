# 11_request_body_and_pydantic_basics

So now that we know how to send data in the body of a request, the next thing that we want to do is make sure that the data that the user sends us is actually shaped the way we expect.

Because right now, sure, we can extract the body and convert it into a Python dictionary, but the problem is that we have no validation. We don't know if the title exists, we don't know if the content exists, and we don't know if the published field is a boolean or not.

And so this is where Pydantic comes into play.

What we want to do is define a schema, and that schema is going to represent exactly what a post request body should look like. So inside our code we can create a class that extends `BaseModel`.

```python
from pydantic import BaseModel

class Post(BaseModel):
    title: str
    content: str
    published: bool = True
```

So now we've said that a post needs a `title`, it needs `content`, and then `published` is optional because we gave it a default value of `True`.

And then in our path operation, instead of manually extracting the body into a dictionary, what we can do is just accept that schema directly.

```python
@app.post("/posts")
def create_posts(post: Post):
    return {"data": post}
```

So what FastAPI is going to do is it's going to take the body of the request, it's going to validate it against this schema, and if everything lines up, then it's going to store it in this variable called `post`.

Now the really nice thing is that if the client doesn't send the required data, or they send the wrong type, FastAPI is automatically going to send back a validation error. So we don't have to manually check every single field ourselves.

And if we want to actually access individual properties, we can do that with dot notation.

```python
@app.post("/posts")
def create_posts(post: Post):
    print(post.title)
    print(post.content)
    print(post.published)
    return {"new_post": post}
```

So now we have a much cleaner way of working with request bodies. We define exactly what we expect, and Pydantic takes care of validating that input for us.
