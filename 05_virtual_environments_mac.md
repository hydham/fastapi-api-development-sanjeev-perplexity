# 05_virtual_environments_mac

In this video I'm going to walk you through setting up a virtual environment on a Mac machine.

Now if you've already closed out your VS Code window, go ahead and open it back up and open up the folder that we created a couple lessons ago.

Now within here what we want to do is we want to access our terminal. So we can access our terminal just by selecting this, and then this is our terminal. However, VS Code has a feature where we can access the terminal directly within our VS Code window, so if we select terminal and then new terminal, that's going to create a new terminal for us.

All right, and so this is fundamentally the same thing as this terminal right here. It's no different. But at least by having it built into VS Code, we don't have to keep flipping back and forth between the two, so you can use either one, whichever your preference is.

Keep in mind that when you open up the terminal within VS Code, it automatically moves you to the, um, the directory folder of your project, so you don't have to move there yourself. You can use whichever one you want.

Now I'm actually using, I'm running Mac on a virtual machine right now just because I natively use a Windows machine, so I don't actually own a Mac. So this is a little bit buggy. You know, if you see me type things, you can see it vanish. So for demonstration purposes I'm just going to use the regular terminal, but I strongly recommend you use the one built into VS Code so you don't have to keep flipping back and forth.

Now to actually create a virtual environment, there's one command that we have to run. So you run:

```bash
python3 -m venv venv
```

For virtual environment, and then you have to give it a name. So what name do you want to give your virtual environment? You can technically give it any name you want. You can name it after, uh, your project. Uh, you can give it some arbitrary name.

What I like to do is I like to name all of my virtual environments `venv`, and so for every project that I create, I just create, uh, the same exact virtual environment name `venv`, and that's not going to create an issue. It's perfectly okay to name all of your virtual environments the same thing because it's all going to be exclusive to this specific project folder, so no other projects can access it. So it's okay if they all use the same name. It's just easier.

And so that way, you know, if I ever create a `.gitignore` file, I can automatically add `venv`, and I can make sure to just use the same exact gitignore template across all of my Python projects.

So I'm going to use `venv`, and I want to make sure that you pay attention right here because after I run this command, take a look at what happens. It creates a folder called `venv`, and that's based off of the name of the virtual environment.

If we take a look at our virtual environment, you can see a couple of different files. You can see the Python file as well. So if you go under `bin`, this is going to be the new Python file, or the Python 3 file, that we're going to use for our interpreter.

So down here at the bottom you'll see that we are still using the global interpreter. We no longer want to use the global one. We want to use the one in our virtual environment. That way we don't, you know, cause any issues with other projects. We want to use the virtual environment.

So to do that, what we want to do is we want to select view, command palette, and then we want to do the Python select interpreter again. So we'll select that, right, and so right now it shows us that we are using the global one. However, we're going to pass in the path to our specific interpreter within our virtual environment. So we'll select enter interpreter path, we'll say dot for current directory, and so that's going to mean, uh, the current fast api directory. Then within there we want to go into the virtual environment folder, and then within there we want to go into `bin`, and then just say `python`.

So we'll hit enter, and then take a look at what happens down here, right? You notice that the version still says 3.9.6, but our interpreter is actually pointing to our local virtual environment now because we changed the interpreter to use this specific Python file right here. And so this is what's going to allow us to install our own specific FastAPI version, as well as any other version of any package that we want, so it doesn't actually install it globally on our machine.

Now we're almost done, but there's one other thing to note. If you look at our terminal, our terminal isn't using our virtual environment. So if I run `pip install` any package, it's not going to install it for a specific virtual environment. It's going to install it globally. So we have to enable the virtual environment for the command line as well.

And to do that, all you have to do is type in `source`, and then we want to pass in, uh, the path to this specific activate file right here within `bin`.

```bash
source venv/bin/activate
```

Hit enter, and then notice how our command line changes. Now it's prepended by the name of our virtual environment, so since we named it `venv`, you can see that it shows it right before the terminal.

And so that's all you have to do. Our virtual environment is set up. Keep in mind if you close out your terminal and then reopen it, you'll notice that your virtual environment is gone, so you have to run that same exact command every time you open up your terminal to ensure that you are in your virtual environment.

And any time you close out VS Code, make sure that when you reopen your project it still points to the virtual environment. If for some reason it changes, then just go back to that command palette by going to view, command palette, and then selecting the interpreter that you specifically want.

But that's all we have to do, guys. So our virtual environment is set up, and so at this point we can go ahead and get started on coding out our project.
