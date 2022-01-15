# Git-Bash-Commands

Let's test it. Create a folder, right-click, and choose Git Bash Here.
Before anything else, let's inform Git who you are so that your commits can be identified. 
Enter the commands mentioned below, replace the quoted data with your real name and e-mail: (press Enter after each one).
```ruby
git config --global user.name "Firstname Lastname"
git config --global user.email "your_email@example.com"
```
Now let's initialize a Git repository on this folder:
```ruby
git init
```
See that (master) on the command line? It tells you the current branch you are in a Git repository.
The master branch is the main branch on every Git repo.
Now let's add a new file and commit it. 
Look at the command sequence (press Enter after each one):
```ruby
touch test.txt
git add .
git commit -m "First commit"
```
First, we create an empty text file (you can create the file any way you like, not necessarily with the touch command).
Then we add all new and modified files to the Git index (we tell Git which files we want to commit on the next commit). 
And finally we commit the changes with a message.

Initial Setup
If you don't have a GitHub account yet, go to http://github.com and create one. It's free.
After you signup and login, let's add an SSH key so GitHub can link your account with this computer.
That way it won't have to ask for your password on every commit.
On Git Bash enter the command:
```ruby
ssh-keygen -t rsa -C "your_email@example.com"
```
Use the same email you registered at GitHub.
On the next question, press Enter to choose the default value.
Now it will ask for a password. Enter a password (this is NOT your GitHub password).
When it asks for a confirmation, enter the password again. 
Now enter the command:
```ruby
notepad ~/.ssh/id_rsa.pub
```
To open on Notepad the file that was created.
On GitHub, go to Settings and then SSH and GPG Keys. Click New SSH key.
Enter a title to identify this computer and in the field Key paste all the contents of the file id_rsa.pub.
Be careful to copy and paste all the contents of the file, beginning at "ssh-ras ..." up to your email (including it).
Click Add SSH key. Let's check if everything is ok. On Git Bash enter:
```ruby
ssh -T git@github.com
```
It will ask if you want to connect to a remote machine. Type yes and press Enter. Next, it will ask for a password. Enter the password you used on the ssh-keygen command.

If you see a message like:
```ruby
Hi user! You've successfully authenticated, but GitHub does not provide shell access.
```
Then everything is correct!

Creating Your First Remote Repository
On GitHub, let's create a new repository (button New repository on your dashboard). 
Enter a name; it should not have spaces or special characters, as it will be part of the URL of your new repo. 
You can leave the rest of the options at their defaults.
You will be taken to the main page of your repository, that doesn't have any files yet.
On Git Bash (on the folder of your local repository) enter:
```ruby
git remote add origin git@github.com:user/repo_name.git
```
Note that user/repo_name must be entered the same way they appear in your repository URL, like:
https://github.com/user/repo_name
Now, to send your files to GitHub, enter:
```ruby
git push origin master
```
Inform the password of the SSH key if it asks.
Reload the page of your repo on GitHub and you should see your committed files.
