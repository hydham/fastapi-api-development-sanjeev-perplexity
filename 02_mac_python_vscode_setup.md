# 02_mac_python_vscode_setup

In this video we'll take a look at how to set up Python as well as VS Code on a Mac machine.

The first thing we're going to do is we're going to just search for Python, and the first result should take us to the main Python page. And what we want to do is select downloads. It's automatically going to give us a button to download whatever the latest version of Python is, and the nice part is it'll automatically detect, uh, what platform you're using, so it'll know that we're on a Mac. And right now it says that the latest version is 3.9.6, so it's going to offer me that. Keep in mind if you're watching this video in the future, it's going to show a different version, and it's okay for you to download a newer version. As long as it's later than 3.7, you should be okay for this course.

So I'm going to select this, and it's going to download it like any other application. Once it's finished downloading, I'm going to select that and then select the file that we just downloaded, and then this is going to take us through the Python installation process. So we'll hit continue, we'll hit continue again, continue, we'll hit agree, and then install, and that's going to prompt us for a password.

All right, and so once you get this popup it means that Python was successfully installed, so we can then close that out real quick, and then we can move this to trash.

And the next thing that we want to do is I'll go up to your search bar at the top, and I want you to search for the terminal application, all right, and it should find that. Just double click on that so we can open up a terminal.

And with our terminal, what we want to do is we want to type in:

```bash
python3 --version
```

And the reason we, um, specify Python 3 is that you can actually have a Python 2 and a Python 3 version simultaneously installed on your machine. We want to make sure that we got Python 3 successfully installed, so if we type this in it should then print out the version that we installed. So we can see that we did successfully install Python 3.9.6, so we should be set from a Python perspective.

And now that we have Python installed, let's go ahead and install VS Code. So like I said, VS Code is going to act as our text editor or our IDE. And so what we're going to do is just search for VS Code, and this is going to take us to the Microsoft page, and then once again Microsoft will automatically detect that we're running a Mac, and then we can just go ahead and select download Mac universal.

All right, and once that's done installing or downloading, we can select that and open it up, and you'll get this warning. Just go ahead and select open.

And so this is going to open up our VS Code, and what we need to do is, uh, VS Code is just a very basic text editor. However, it comes with extensions that we can install that make it significantly more feature-rich, so it'll almost act like a traditional IDE.

And if you select the extensions icon, which is this icon right here with the extra blocks, select that, and I want you to search for Python. And the first result should be the one you want, and it should be the one that's made by Microsoft. So this is going to provide things like linting, IntelliSense, debugging, and a few other features that are going to come in handy when it comes to writing Python code within VS Code. So go ahead and install this.

All right, so now that it's installed, what we want to do is select this icon to go back to our folder menu, and we want to select open folder. So what we're going to do is we're going to create a folder to store all of our project code.

I'm going to select open folder. Now we haven't created a folder, uh, to actually store our application, so I'm going to go under my traditional users, Sanjeev, and then I'm just going to store this within my documents. So I'm going to make a new folder called, um, I'll call this, uh, well just call this `fast api`, so I'll create that. And then we're going to open up the `fast api` folder that we just created.

And so this is going to open up all of our project code. Right now we have no files, and that's to be expected, but what I want to do is I want to right click here and select new file, and we want to just type in `main.py`.

And before we hit enter, I want you to look down here. So when I hit enter you'll see that something's happening, so it's activating the Python extension, and it's automatically going to select a Python interpreter. And so like I said, you can have multiple different versions of Python, so technically we could, you know, for any one of our projects we could be running 3.9.6, or maybe we're running 2.7 if we want to stick to Python 2. We can actually select which specific Python interpreter we want to run on a per, uh, project basis.

And if you ever want to change this, or for some reason it wasn't able to find this correctly, just go ahead and select view, command palette, and then it automatically found the most recently used ones, but you would just search for Python select interpreter, select this, and it shows the currently selected interpreter. But you can also enter in the path to find a specific interpreter, so you would just find wherever Python 2.7 was installed if you wanted to use that, or if it was unable to find 3.9.6, go ahead and just find where Python 3.9.6 was installed on your machine and point to that Python file. Actually it's not called `.exe` within Mac. I forget what it's called on a Mac. I actually use a Windows machine for most of my things, but that's all you have to do.

Uh, and so at this point we've got Python set up and then we've got our VS Code set up. So once again, any time VS Code closes, you want to open it back up and then open up the folder `fast api` in this case.
