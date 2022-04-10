#Домашнее задание к занятию «2.3. Ветвления в Git»

##Задание №1 – Ветвление, merge и rebase.

> git merge git-merge 
Merge made by the 'recursive' strategy.
 branching/merge.sh | 3 +++
 1 file changed, 3 insertions(+)


> git rebase -i main
Auto-merging branching/rebase.sh
CONFLICT (content): Merge conflict in branching/rebase.sh
error: could not apply 5ca6fd2... vetka ploskaya
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 5ca6fd2... vetka ploskaya



###Промежуточный итог.
- https://github.com/litvinenkoceo/devops-netology_Litvinenko/network


> git rebase --continue 
[detached HEAD 05599d5] 1 conflict solved --continue`
 1 file changed, 1 insertion(+)
Successfully rebased and updated refs/heads/git-rebase.


> git push -u github git-rebase 
To github.com:litvinenkoceo/devops-netology_Litvinenko.git
 ! [rejected]        git-rebase -> git-rebase (non-fast-forward)
error: failed to push some refs to 'git@github.com:litvinenkoceo/devops-netology_Litvinenko.git'


> git push -u github git-rebase -f
Enumerating objects: 7, done.

