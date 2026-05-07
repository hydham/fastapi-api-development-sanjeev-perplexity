# 04_virtual_environments_windows

So now that we have Python and VS Code set up, the next thing that we have to do is set up our virtual environment. Before we do that, we have to actually talk about what are virtual environments and what problem do they try to address.

So let me give you a little bit of an example scenario of the issue that we can run into when working with specific packages within Python on your local machine.

So let's say that we created a project, and this project is called project one. And what we need to do is we need to install FastAPI version 1.2.1. So what do we do? We install version 1.2.1 on our machine so that we can actually use that version.

Now let's say later down the road we start a new project called project two, and let's say this version requires us to run FastAPI version 2.4.3 because we want to try out some of the newer features.

Well at this point, if we need to try out a newer version, we have to upgrade FastAPI to version 2.4.3 on our local machine. And this may or may not be a problem. It really just depends on if version 2.4.3 is backwards compatible with version 1.2.1, because if version 2.4.3 has breaking changes, then ultimately that's going to create issues with our project one because that project expects us to run version 1.2.1.

And so if we can't upgrade, well we're in a little bit of a pickle because one project needs one version, the other project needs another version, and we can't have two different versions installed on our machine. So what exactly do we do?

Well this is where virtual environments come into play.

So with virtual environments, let's say we want to create a project. So we create project one, and what we do is we create a virtual environment, call it whatever you want. And so this is an isolated environment that will not affect any other environments. And within this environment we can install any Python packages running whatever version we want, and it's completely isolated to this project.

And so when we create a second project, what we can do is we can create its very own virtual environment as well. We'll call it virtual environment two. And within this virtual environment we can install any version of any package that we want, so then we can install version 2.4.3. And so both of these virtual environments are completely separated, completely isolated with one another.

And so we can essentially install multiple different versions of a single package for each of our projects, and that way our projects don't end up stepping on the toes of other projects.

And so now that we have a basic understanding of virtual environments, let's go ahead and figure out how we can actually create our first virtual environment and use it within our project.

In this video I'm going to walk you through setting up a virtual environment on a Windows machine. Now if you already closed out your VS Code window, go ahead and open up a new one, and make sure you open up the specific directory we created a couple lessons ago.

Now what we want to do is we want to select terminal, and we want to select new terminal. And this is an awesome feature with VS Code. It allows us to have an integrated terminal within our VS Code window, and this terminal is fundamentally no different than a regular terminal within Windows. It's just built into VS Code so that we don't have to keep flipping between different windows.

And if you actually take a look at this right column, we can have multiple terminals open, and we can even use different terminals. So the default one on this machine happens to be PowerShell, but you can also use command prompt if that's what you prefer. So if you select command prompt, it's going to create a new terminal, and you can see that this is a traditional command prompt. I'm going to use this one because that's the one I normally use. However, if you're more comfortable with PowerShell, feel free to use that.

Now the command to actually create a virtual environment within Windows is:

```bash
py -3 -m venv venv
```

So that stands for virtual environment, and then you want to give it a name. So give whatever name you want for your virtual environment. You can name it after your project name, or you could just do what I do, which is just call it `venv`.

And what I like to do is for all of my projects I give it the same exact name, and that's perfectly okay because this virtual environment is going to be isolated to this project directory. And so even though this project has a virtual environment named `venv`, I can create another virtual environment in any other project with the same exact name, and they're all going to be isolated to that specific project folder.

So go ahead and hit enter. And take a look over here. You'll see that a folder was created called virtual environment, or `venv`, and that's going to be the name of this folder. It's always going to refer to whatever name you gave it. So if I named this cookies, this would open up a new folder called cookies.

And if you want you could take a look at what's in here, and if you go under scripts specifically, you'll notice that we've got our Python executable. So this is going to act as our new interpreter.

And so what we want to do is, right now we are using our global interpreter, and we want to change that. We don't want to use the global one. We want to use the specific one in our virtual environment, and that way we can install packages that are exclusive to just this specific virtual environment.

And so to do that, go ahead and select view once again, and we want to go to command palette, and then search for Python select interpreter as usual. And then you'll see the one we're currently using, but we want to pass in our newest one. So select enter interpreter path, and then we want to give it the path to our interpreter, which is the path from the root of our project directory to this `python.exe` file. We're going to say dot, which is our current folder, so this is going to be the fast api folder, and then within here we want to go into the `venv` folder, then `Scripts`, and then `python.exe`.

Go ahead and hit enter, and then if you look down here you'll see that this gets updated. So now we're still using 3.9.6, but we're using our virtual environment, uh, and so that's all we need to do. And it should remember this every time we open up our project. However, double check every time you open them just to make sure you're using that. If it's for some reason moved back to the default one, just do the same process.

Now the second thing that we need to do is we need to make sure our terminal is also using the virtual environment. And so what we want to do to do that is just type in the path to the specific `activate.bat` file. So this is going to activate that virtual environment within our command line as well.

```bash
venv\Scripts\activate.bat
```

Hit enter, and then notice what's changed, right? So when you're using a virtual environment, right, you're going to see the name of the virtual environment to the side of it.

So always double check whenever you start up VS Code and you start up your project that this is enabled. If you don't see this, then just run the same exact command, and that's going to reactivate the virtual environment.

And so at this point we are good to go with our virtual environment, and we can start coding out our project.
