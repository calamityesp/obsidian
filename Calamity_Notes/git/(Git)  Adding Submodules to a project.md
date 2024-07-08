---
tags:
  - Keep/Label/git
---

Short description: This  explains how to add submodules to a git repository as the title says dummy

-----------------------------
add sub module 
-----------------------------
git submodule add <url to repo or gist>  < path to submodule > 
git commit -m "adding submodules"
git push origin <branch-name>


-- uipdate submodules  ( changes in submodules must be explicitly updates if you want to push modifications to those submodule repositories) 

git submodule update --remote 
