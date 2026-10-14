===Add an image in the README.md file.===

<img width="260" height="220" alt="Screenshot 2026-10-14 132518" src="https://github.com/user-attachments/assets/44126f4e-c700-4634-aed8-4883073a3f06" />


Commands Used:
1)Create a new project on your local machine,then push it your remote repo.
git init
git remote add origin git@github.com:aya5671/Lab_2.gi
git push -u origin main

2)Create two branches (dev & test) then create one file on each branch, and push this changes to the remote repo.
git swtich -c dev
git add .
git commit -c -m "dev created"
git push -u origin dev

git swtich -c test
git add .
git commit -c -m "test created"
git push -u origin test

git checkout dev
git merge test -m "test merged onto dev"

git checkout main
git merge dev -m "dev merged onto main"

git push

3)Tell me how to remove them locally and remotely.
Locally:
git branch -d test
git branch -d dev

Remotely:
left click on "View all branches"
and delete each one manually

4)Tell me how to checkout another branch without commit
changes
git stash
git stash pop

5)Create an annotated tag with tagname (v1.7) .Push it to the remote repository. Tell me how to list tags. Tell me how to delete tag locally and remotely.
git tag v1.0
git push origin --tags
git tag -l

Locally:
git tag -d v1.

Remotely:
press on Tags
and delete manually


