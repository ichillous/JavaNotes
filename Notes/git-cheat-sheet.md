<img width="631" alt="directory-structure-example" src="https://github.com/user-attachments/assets/436dc0d9-1ddf-4021-89ff-14ff2b0ece2a">


### Terminal commands:

1. ls - List directory contents Example: `ls -la`
2. cd - Change directory Example: 
	- `cd ~` Navigate to the home directory from anywhere.
	- `cd - `Switch to the previous working directory.
	- `cd .. `Move up one directory level.
	- `cd ../../ `Move up two directory levels.
1. mkdir - Make directory Example: `mkdir new_folder`
2. rm - Remove files or directories Example: `rm file.txt` or `rm -r directory`
3. cp - Copy files or directories Example: `cp file.txt backup_file.txt`
4. mv - Move or rename files/directories Example: `mv old_name.txt new_name.txt`
5. touch - Create file Example: `touch example.txt`

### Git commands:

1. git init - Initialize a new Git repository Example: `git init`
2. git clone - Clone a repository Example: `git clone https://github.com/user/repo.git`
3. git add - Stage changes Example: `git add .` (stage all changes)
4. git commit - Commit staged changes Example: `git commit -m "Add new feature"`
5. git push - Push commits to remote repository Example: `git push origin main`
6. git pull - Fetch and merge changes from remote Example: `git pull origin main`
7. git branch - List, create, or delete branches Example: `git branch new-feature`
8. git checkout - Switch branches or restore files Example: `git checkout develop`
9. git status - Show working tree status Example: `git status`
10. git log - Show commit logs Example: `git log --oneline`

## Examples
### Within Terminal :

```bash
isiahchillous ~ % ls  
Applications Desktop Pictures Documents Downloads Library 

isiahchillous ~ % cd Desktop

isiahchillous Desktop % mkdir test 

isiahchillous Desktop % cd test

isiahchillous Desktop/test % mkdir git 

isiahchillous Desktop/test % cd git

isiahchillous Desktop/test/git % touch example.txt

isiahchillous Desktop/test/git % ls
example.txt

isiahchillous Desktop/test/git git % git add .

isiahchillous Desktop/test/git git % git commit -m "test commit"
[master (root-commit) cdf15b8] test commit

 1 file changed, 0 insertions(+), 0 deletions(-)

 create mode 100644 example.txt

isiahchillous Desktop/test/git git % git remote add origin https://github.com/ichillous/test.git

isiahchillous Desktop/test/git git % git remote -v 
origin https://github.com/ichillous/test.git (fetch)
origin https://github.com/ichillous/test.git (push)

isiahchillous Desktop/test/git git % git push --set-upstream origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 231 bytes | 231.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/ichillous/test.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.

isiahchillous Desktop/test/git git %

```




### Results in Github : 

![[github-screenshot.png]]

