# Git

### Create a new repository on the command line
~~~sh
echo "# project_name" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:wtw24/project_name.git
git push -u origin main
~~~

### Push an existing repository from the command line
~~~sh
git remote add origin git@github.com:wtw24/project_name.git
git branch -M main
git push -u origin main
~~~