<!-- Step to Learn Git and GitHub -->


1: Git: Git is a version control system (VCS) that helps developers keep track of changes to their code over time. It allows multiple people to collaborate on the same project, track the history of changes, and manage different versions of a project efficiently.

<!-- Configure git -->


git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"


You can verify the configuration:
git config --list


<!-- How to see hidden folder -->
In Mac: CMD + SHIFT + .
In Windows:
In Windows 10: Click on the View tab at the top, then check the box for Hidden items in the "Show/Hide" section.
In Windows 11: Click the View dropdown (three dots) in the toolbar, then select Show > Hidden items.


<!-- **************************** -->


git status
<!-- What changes are staged , not staged, untracked-->


<!-- git diff -->
q for exit
<!-- What has been changed line by line in your report. -->
<!-- it will show which parts of the report have been edited but are not yet staged for commit. -->

<!--Add file to staging area  -->
git add .

<!--Commit file -->
git commit -m "message"

<!-- Remove file from staging area -->
git reset <file>
git restore --staged <file>

<!-- Get logs of commit -->
git log
got log --oneline
git show <hash>

<!-- Revert the changes -->
git reset --hard <hashCode>
git revert <hashcode>
<!-- git add . -->
<!-- git commit -m "next" -->

<!-- How to create a branch -->
git checkout -b <branch-name>

<!-- Delete a branch -->
git branch -d branch-name
git branch -D branch-name (unmerged also)

<!-- ESC :wq --> helpful(Escape the writing mode, save and quit)
<!-- i: insert mode -->

<!-- How to change the name of branch -->
git branch -m <branch_name>

<!-- Git stash -->
allows you to temporarily save your uncommitted changes (both staged and unstaged) in a "stash" and revert your working directory back to the last commit.

<!-- git stash -->
<!-- git stash list -->
<!-- git stash apply -->
<!-- git stash apply stash@{1} -->
<!-- git stash pop -->
<!-- git stash clear -->


<!-- Working with Github -->
<!-- git remote add origin https://github.com/mohitji-dons/Helloji.git
git branch -M main
git push -u origin main -->

<!-- git pull origin main -->
<!-- git pull --rebase origin main-->

<!-- git branch -r —>
To know which branches are there in GitHub.


<!-- git push origin --delete feature -->
To delete a branch on GitHub using vscode terminal , or can go in GitHub n delete by view branches.


In rebasing we make them linear as seen in img rebasing.png, it forms a linear chain instead of directed graph sort of which is seen above. In rebasing, at then end of last commit of master, we attach feature’s commits  in line.

To remove tackign of git:
Rm -rf .git after going into the directory of that folder.


So in the diagram given, payment and master thing, the graph with ABCDE is the branch normal one, but the another ABCD’E’ is the rebasing one, here ABC code remains same, but at D it would change, as  our commits in both situation are dependent on prev ones, so here when we see D need to depend on C, but in above sceneior D depend on B, so D will modify n accept changes from C n then implement D so we get d’ similarly we get E’.

So to change the base of D from B to C(ie last node), for rebasing

git checkout payment - the branch where d lies
Git rebase master
Solve the conflicts
Git add .
Git rebase —continue (please dont do commit here, as we need to modify in E as well)
It shows a new file, I want to update the name from payment added -> payment updated, do I to make it insert mode. After editing name do esc, then write :wq to exit the file

Successfully rebased and updated refs/heads/payment. This line shows everyting rebased.


Imp:
After rebasing, only payment branch updated, but still master shows only it’ part.
So do git merge payment.

Logically seeing, it means ke if I am using Radha branch and we have a common project branch, so I was rebase my changes to project branch and then at end just merge with common project branch, it won’t give any conflict as Radha branch has ( common project + her code). 


Branching helps like multiple person can work together on same project, eg: person A works on login page , person B works on css, so when A /B anyone complete they just merge with master one.
But the problem is how the person informs the other one I updated it, please consider accordingly. So a common platflorm is used, ie GITHUB where code is kept centrally.

It’s. Basically like A made changes to payment so uplaod that on GitHub so B can pull it and integrate locally on his laptop where he is making login page. 

git remote add origin https://github.com/radha04official/Git-Learning.git 
Here origin is name given to the link.

Git branch -m main , changes your branch name, here it changes form master to main.

Create new project, then repository, then exisitng repo through command line , copy those n paste in vscode terminal

Git push -u origin main => to push from your folder to origin folder. For 1st time we use -u., u = upstring.

So, after 1st time, next time when you make changes in your code,
Git add . , git commit -m “latestchange”, git push
Update done.


So if I make any new branch in my folder, first push that branch on GitHub, then merge
-> git push -u origin bugfix

For merging we do, compare & pull request from GitHub.

WHEN YOU work with someone, make a separate branch n then do the merge as it will show conflicts. N then the host(code viewer) has rights to accept/delete changes.

If conflict resolved, then the GitHub main branch first.js would have changes applied, but the main file in your vscode won’t have chsanged yet.

After going to main branch on vscode, 
git pull origin main
 It updates the code on vscode as well. 



