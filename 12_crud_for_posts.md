# 12_crud_for_posts

At this point we have enough pieces in place that we can build out the full CRUD flow for posts, even if we're still keeping things simple.

So we've already got a route for getting all posts, and we've got a route for creating a post. Now we want to also be able to get a single post by id, update a post by id, and delete a post by id.

So first let's handle getting a single post.

```python
@app.get("/posts/{id}")
def get_post(id: int):
    return {"post_detail": f"here is post {id}"}
```

So this is using a path parameter. Whatever value the user provides in the URL is going to get passed into our function as `id`.

Now for deleting a post, we can do something very similar.

```python
@app.delete("/posts/{id}")
def delete_post(id: int):
    return {"message": f"post {id} deleted successfully"}
```

And then for updating a post, we usually want both the `id` from the path and the request body from the client.

```python
from pydantic import BaseModel
from fastapi import FastAPI

app = FastAPI()

class Post(BaseModel):
    title: str
    content: str
    published: bool = True

@app.put("/posts/{id}")
def update_post(id: int, post: Post):
    return {"data": post}
```

So now we have the basic CRUD structure for posts. We can create one, retrieve all of them, retrieve one of them, update one, and delete one.

At this stage we might still be using temporary in-memory data or dummy responses, but the important thing is that the API shape is now there. And once that API shape is there, it's much easier to replace the fake data with a real database later.
