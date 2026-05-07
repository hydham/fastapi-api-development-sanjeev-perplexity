# 03_windows_python_vscode_setup

In this video I'm going to walk you through setting up Python as well as VS Code on a Windows machine.

So the first thing that we're going to do is within your web browser just search for Python, and then we're going to select the first result. So this is going to take us to the main Python page, and we want to go to the download section.

And so here Python, the website's going to offer you up whatever the latest version of Python is. In this case it happens to be 3.9.6. Keep in mind if you're watching this video in the future, it's going to show some other version, and that's okay. Go ahead and just download the latest version. As long as it's later than 3.7, you should be okay.

So I'm going to just hit download Python 3.9.6. It's going to download that. Once it's finished downloading, I'm going to select that, and it's going to open up the installer.

Now with this installer open, it's very important that you select add Python 3.9 to path. Do not forget to do this or then you're going to run into some issues. So make sure that's selected, and then hit install now.

If you go through the installation process and you realize you forgot to do this, technically there's a way to fix it afterwards, but instead of me explaining how to do that, the best thing to do is just uninstall Python and reinstall it.

So we'll hit install now. You'll get a popup. Just go ahead and hit yes.

All right, and once you see this message where it says setup was successful, that means Python was installed. And the next thing that we want to do is just quickly verify that Python is up and running and working.

So what we're going to do is we're just going to search for `cmd`, so it's going to open up our command prompt or terminal. And then in here just type in:

```bash
py -3 --version
```

All right, and so when you type this command in, uh, it's going to tell us the specific version that we installed. So we can see that I successfully installed Python 3.9.6. If you get any kind of error or any message saying that this command is not available, that means that Python wasn't installed successfully, so just go ahead and redo that process just in case.

Now the next thing that we want to do is install VS Code. So let's open up a new tab, just search for VS Code, and then we'll select this. It's going to take us to this page, and you'll see that VS Code will automatically detect what version you're running, so you can just select download for Windows.

And then once it's finished downloading, go ahead and open it up, hit the accept agreement, hit next, next, next, and then you can leave everything as default and then go ahead and run install.

All right, and then go ahead and finish. It's going to automatically open up VS Code.

Now there's a couple things I want to do. So VS Code, at its core, is just a basic text editor. However, we can install extensions that give it extra functionality, extra features that'll make it operate a little bit more like a full-blown IDE.

So go ahead and select this icon right here. This is for extensions. And then what we want to do is we want to search for Python, and we usually just want to select the first one. It'll have a star, and it's going to be the one made by Microsoft. You'll see that there's other ones made by other users, but we want the main Microsoft one. Hit install.

And so this extension is going to give us IntelliSense, linting, debugging, and a few other features that are going to make it a little bit easier to start working with Python within VS Code.

All right, uh, and so now that it's done installing, we can just close this, close this, and then select this one to get back to your main file browser.

And, uh, right now we haven't opened up any folder, so what we want to do is we want to create a folder to store all of our application code. So select open folder, and then figure out where you want to store your application code. So I'm just going to store this in my documents. You can store this wherever you want.

I'm going to create a new file or a new folder. I'm just going to call it `fast api`, but you can name your project whatever you want. So just select folder. And so that's going to not only create the folder but it's going to open it up within VS Code.

If you get this error, just select trust the author and just click yes, and then we can close out this welcome menu.

And so now what we have is we've opened up, whoops, we've opened up VS Code, and within VS Code we've opened up our project code. So right now there's no code. That's to be expected.

But what I want to do is I want to create a new file real quick just, uh, for testing purposes. So I'm just going to right click, hit new file, and I'm going to name it `main.py`. Uh, and so we want to name it `.py` because this is going to be a Python file.

And before I hit enter, I want you to focus your eyes right down here, and you'll notice something happens down there. So when I hit enter, you'll see activating extension. So it's activating the Python extension.

And what the Python extension is going to do is it's automatically going to select the correct Python interpreter, or it may not be correct depending on what happens on your machine. For me it automatically detected Python 3.9.6 was installed on this machine, so it selected that one for me. Keep in mind if you have multiple versions of Python installed, it may select the wrong interpreter.

So what you can do is if you ever want to change the interpreter or specify a specific interpreter, go to view, command palette, and what I want you to do is search for Python interpreter and then look for Python select interpreter. So right now it's going to highlight where, um, the current Python interpreter is, which one is selected, and what's the executable for it. But if you want to change that, you can select enter interpreter path and then provide the path to the specific version that you want. So you can obviously change it, but usually it's able to detect the latest version, so you should be good to go.

Uh, and so that's all I wanted to do from a setup perspective. There's one more thing that we'll cover, uh, later, but we'll get to that in the next section. Um, but right now we've got Python installed and we've got VS Code set up and we've got our project directory set up, so we should be good to go.
