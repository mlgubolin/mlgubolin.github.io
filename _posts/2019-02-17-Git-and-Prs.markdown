---
layout: post
title:  "Configuring Your Git and Creating a Pull Request."
description: This is a tutorial to help you setup git inside your computer and teach you how to make PRs! \:D
date:   2019-02-17
categories: Git
---


First, we need to tell the git in our pc who we are. To do that, we must open terminal (by pushing command + space bar and typing terminal) and copying and paste these commands:

```
git config --global user.email "email@example.com"
git config --global user.name "name"
```
Remember to change the quotes with the email you used in GitHub and your name.

Before we create a repository, we'll do a trick to make our life easier. We're going to create an SSH key to identify our computer. But what is a SSH key?

![ssh_key](https://www.keycdn.com/img/support/create-ssh-key.png)

Imagine you want two computers to tell each other apart from all others who contact them. There is a lot of ways we can do it securely and insecurely, but our friends from Mathematics already discovered the best way to do it. Thats what we'll learn now.

These friends thought a way the computers could create and check certain keys very fast. To know this key, in other hand, its waaay more complicated. It would take roughly $10^{15}$ to be exact.

The second smart part is to use **two** keys, one you'll share and other you'll keep for yourself (we'll call them _private_ and _public_, respectively). Wherever you use the _public_ key to **encrypt** something, you can only open with the respective _private_ key. And you cannot guess the _private_ key using the _public_ key, what makes it secure. To understand better how the communication between computers work with these keys, you can check [here](https://www.hostinger.com/tutorials/ssh-tutorial-how-does-ssh-work).

So, lets create our keys. To do that we must type the command:

``` 
ssh-keygen 
```

You can press enter until it ends, the standard options are good enough.
![ssh](./images/ssh.png)

ssh-keygen creates the two keys and we must give the one with `.pub` to GitHub. You can go to your home folder and find it on `.ssh` or, after opening a terminal, type:

```
cd .ssh
cat id_rsa.pub

```

Great! :D 
Now we must paste it in GitHub's setting page. To that, you can go to your settings, clicking in your avatar:

![github main page](./images/github_pag_inicial.png)

Once in Settings, click on SSH and GPG keys. Click on new key on the right of SSH Keys and paste your key, giving it a name you'll remember.

![github ssh page](./images/github_ssh.png)

Nice! Now we need to create a repository so we put things onto it. Go back to the main page and click New on the top left.

Give it a name and a short description and you'll end up in a page with a code similar to this:

```
echo "#*#####* >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/your_username/your_repository.git
git push -u origin master
```
These are the commands we need to type in the terminal so a folder can be used as the location to our git repository. So open the terminal again, go to the folder of your preference and create our repository's folder:
```
mkdir your_repository
```
Then we enter it using cd:
```
cd your_repository
```
And we finally paste the code git gave us. You can use the one I wrote up there (the one that starts with `echo`). Just copy and paste all the lines, remembering to change `your_username` and `your_repository` to yours, respective.

So, where's the Pull Request? *What* is a Pull Request? Why programming is a mistake?
So, to answer the first two, a Pull Request, or PR, is what we do when we want to make changes into a code that is used by a lot of people like in companies, as an example. The PR is the way we can control and guarantee that everything isn't going to explode if you let the intern do a few tasks. But before we fully understand what a PR is, we must understand git branches.

A git branch is a copy of your code where you can do the craziest things imaginable without changing the main code, which we call *master*. Here is a picture that helps:

![All credit to Atlassian](./images/branch.png)

A branch is a way we can work in an organised way when a lot of people is dealing with a lot of problems at once. So how do we create one? In `your_repository` folder in the terminal, type this:
```
git checkout -b your_branch_name
```
The `-b` indicates you want to create a new branch with the name `your_branch_name ` and checkout is the function you use to create (using `-b`) a new one or change to an existing one (without `-b`). You should receive a message like this:

![All credit to Atlassian](./images/terminal_branches.png)

Now we should create a file, so git can push this branch with something on it. You then create a file with nothing inside using, for example:
```
touch new_file.txt
```

Now its finally time to send to GitHub, using git, all the information that we changed here in this folder. To do that we need this three commands:
```
git add .
git commit -m "message"
git push
```
Add is, well, to add what you did (`.` indicates `here` in terminal language). Commit is the command that tells git you want a **snapshot** of the things you added with `git add .`. A message is mandatory because programmers are lazy and wouldn't explain their code if it wasn't. Finally, `push` pushes your code to GitHub. 

So, what about that error that the terminal gave you when you tried to run `git push`?

![](./images/giterror.png)

Fear you not! It's just GitHub telling git that it doesn't know this new branch you created. Fortunately, git gives you the correct command, so you can just paste it and be free, like in the image.

To finish this lengthy text, we must now go to GitHub page to create a new pull request (if you look closely, git gave us the link in terminal to go there directly).

![All credit to Atlassian](./images/prpage.png)

You can type a brief description of what you did and voilá, we made our PR. You can now share with friends and enemies this new code that you want to add to your repository. (By the way, the title of the PR is the same text you typed in the message. Smart, right? :3)

This is a daily practice to a software engineer in the industry and, as soon we get to understand it and master (haha) it, sooner we will not even remember that was a problem one day. Thank you :)

![All credit to Atlassian](./images/crunchify.png)

