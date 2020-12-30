# note keeping

## what you want

* do you want version control?
* are you comfortable having to render a page to view the final view?
* do you want your documents to be extensible?

## use VScode and write markdown

* If you want to use Word, use http://www.writage.com/
* https://code.visualstudio.com/Docs/editor/versioncontrol#_git-support
* Create a workspace, then new folder, and new files (all with *.md extension).
* There's also a remote-ssh terminal built in to the editor, and you can actually open a file tree remotely via an installed service with a small footprint.
  * this is not be ideal for a target.
  * when I have an engagement. I spin up a digitalocean VM, install kali and use that single OS instance to attack that client.  This is when I use the remote-ssh extension.

### wanna here it?  here it go...

1. install git for windows
2. install vscode for windows, install the extensions "markdown all in one" by yu zhang and "paste image" by mushan (hit ctrl+shift+p to bring up the command palette)
3. start a github account
4. initialize a repo (in github, sure)
5. copy the "clone or download" URL for that repo
6. set the user info on your machine:
```
git config --global user.email "nope@no.com"
git config --global user.name "Matt"
```
7. open vscode
8. trigger the command pallet with ctrl+shift+p
9. type "git: clone"
10. provide the clone URL for the repo in (I use ../user/$username/documents/repos
11. create a new file, modify it.  changes will be tracked.
12. Save as you would normally.
12. when you are ready to commit all changes to the repo, click on the source fork icon on the left sidebar menu, then click the checkmark.  Stage all changes.
14. near the bottom there will be an up arrow with "1" next to it, you can click on this to push

Note, it is faster to commit and push via the command pallet (ctrl+shift+p, "git: commit", "git: push"


## Hey, why not?

* I'm feeling fancy, and would love to use jupyter notebooks.
* It's quite easy, and .net is now supported with `.net interactive notebook`.
* I've never used this, but I'm strongly considering this as a high touch method with a manual decision tree for pentesting enumeration actions.
    * [this post](https://www.reddit.com/r/oscp/comments/gb4k83/htb_bashed_and_my_learnings_oscp_journey/) inspired me to document a list of actions to take before I take the OSCP.  Maybe this is something you just learn to do while you're studying, particularly in a formal setting, but the idea that essentially everthing can be done with a fair success rate if performed methodically is appealing.  It's a The Answer for speed, and general accuracy.
    * I do believe, but will get absolute confirmation, that you can use your own automations on the OSCP.  IF you wrote metasploit, then you should use it.
    * maybe this can fit in somewhere: https://mybinder.org/
