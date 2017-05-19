# Collaborating on Code

What are we talking about tonight?

- Explaining background of version control (and why you care)
- Learning the vocabulary and basics of git and github
- Discussing about git workflow
- Discussing DevOps (and why you care)
- ~~Discussing best practices for project documentation _(if time!)_~~



## Git and Version Control Systems

You need to back up your files. If you've ever lost a term paper, or saved over a file you needed, you know this. "Version control" is a fancy name for "backing things up." 

But it can be more than that! Modern version control systems let multiple people collaborate on a single file or a directory of them.

Let's think about version control with a _A Brief, Very Inaccurate History Of How You Do Version Control:_

1. save lots of files with different names:
   `shirt_design.pdf` (first version)  
   `shirt_design_v2.pdf` (second version)  
   `shirt_design_v2_mj.pdf` (second version with MJ's comments)  
   `shirt_design_20170429.03_final.pdf` (later date, third iteration, final, yep)  
   `shirt_design_20170429.03_final_FINAL.pdf` (...yeah.)
2. use something like Time Machine to backup past versions (same filename) so that you can roll back to them (it keeps copies of every file that's changed)
3. share this backup on a server within a file repository (**repo**) so that everyone can commit and update files, and pull down changes or new files
4. keep your file up to date with the version of the file on the server...

   - what if someone tries to edit a file that someone else has open? will it lock the file? is it a race to see who can save first? 
   - what if you don't want the latest version because it will overwrite your code? what if someone is working from a really old version of the file and accidentally saves over all of the changes you were working on? 
   - how do you **merge** your changes? what did you change? what did they change? (**diff**)
   - what if you want to noodle away on an experiment, and change a bunch of things to see if things will work? what if you want to fix a bug, but don't want to break the code of your colleagues who are working on new features? (**branch**)
   - what if the central version control server goes down? :scream:
5. change your workflow and decentralize your version control system!
   - make lots of tiny changes (save often)
   - commit these changes to a repository on your local machine and comment them so that you (and others) know what you did 
   - you can pull/push updates from/to a repo, but you can _also point to a different copy of the repo_
   - when you make changes, you generally do so in a branch
   - you can work offline without worrying about getting out of sync
   - when these changes are ready to go, you pull the latest changes
   - you merge your changes into the code from the repo—if it's a text file (like code!), and you worked on a part of it that's different from what was edited, it auto-merges and lets you review
   - if you have permission, you can push your changes back to the central repository, and it carries with it the full log of _all the tiny changes you committed to your local repo_
   - OR, do a Pull Request (PR), which is requesting that the central repo pull from your local repo to update its code

Git is the name of a popular decentralized version control system / tool. 
​(:warning: It's an awkward name, because it's a [slur in the UK](https://en.wikipedia.org/wiki/Git_(slang)).) 
It's often run on the command line, and there are fancier user interfaces for it. 

If the code you're working on is open source, you can host it for free in repos on sites like [GitHub](https://github.com/) (where you're reading this now). The GitHub site will let you edit files online, and even drag and drop files to the browser to upload them or update them.

GitHub is handy because it hosts so many open source projects! You can search GitHub to find code that can help you on a project, and if you write code, it's easy to share what projects you've contributed to, and build up a kind of coding resume. 

GitHub also makes it easy to document your code with a [Markdown](https://guides.github.com/features/mastering-markdown/) `README.md` file (like this one you're reading), or host web pages for each of your projects. You can upload static HTML files along with your code, or set up a more dynamic blog using the [Jekyll](https://jekyllrb.com/) content management system. (In fact, [codekitchen.club](http://codekitchen.club/) is [hosted on GitHub](https://github.com/codekitchensd/codekitchensd.github.io)!)

We'll look at GitHub, but to get the fundamentals of git, we're going to dive into the command line. 

### Resources

- [Understanding DVCS if you're coming from another VCS](http://hginit.com/) (for Hg, not git, but same principles!)
- [Git for Humans](https://speakerdeck.com/alicebartlett/git-for-humans) (a presentation)
- [Git for Humans](https://abookapart.com/products/git-for-humans) (a different book)
- [24 Ways - Git for Grownups](https://24ways.org/2013/git-for-grownups/) (on workflows)
- [Git for Teams](https://github.com/emmajane/gitforteams) (on workflows, a workshop that turned into an O'Reilly book)

## Let's use Git!

Download git. <https://git-scm.com/>

**Really basic concept:** <http://tomcreighton.com/2011/09/git-for-designers/>

Still basic (and ...somewhat wrong): <https://twitter.com/justsomeguy/status/603776826381578240>
![https://pbs.twimg.com/media/CGEL0vRW8AEGjxB.png:large](https://pbs.twimg.com/media/CGEL0vRW8AEGjxB.png:large)

There are lots of tutorials (from videos, to textbooks, to interactive manuals), many listed below in **Resources**, but lets start with this one: <https://rogerdudler.github.io/git-guide/>

#### Getting Started

- `git init` (if you're starting a new repo on your machine) 
- `git clone` (if you're copying an existing repo from elsewhere, like github)
- setting up remote origin
- `git checkout` 

#### Committing Code

- `git status` :sparkles:
- `git add`
- `git commit -m "…"`
  - [The Art of the Commit](https://alistapart.com/article/the-art-of-the-commit)
  - [What's In A Good Commit](http://dev.solita.fi/2013/07/04/whats-in-a-good-commit.html)
- `git diff`
- `git reset` and `git stash`
- `git log`

#### Branching and Collaborating

- `git branch`
- `git checkout -b`
- `git fetch` and `git pull`
- `git merge`
- `git push`

#### Other Things To Talk About!

- GitHub: Issues and Pull Requests
- Git LFS
- Rolling back to previous commits
- Rebasing?

### Resources

- [Try Git](https://try.github.io/) (15 minute interactive walkthrough from GitHub)
- [Git Guide](https://rogerdudler.github.io/git-guide/) :point_left:
- [Codecademy Git course](https://www.codecademy.com/learn/learn-git) (another interactive walkthrough)
- [Software Carpentry's 3-hour workshop](https://swcarpentry.github.io/git-novice/) (free coding tutorials for scientists)
- [Gitignore.io](https://www.gitignore.io/) (for ignoring common system files, e.g. MacOS resources, )
- [Oh S#!t, Git](http://ohshitgit.com/) (for fixing problems)
- [Git LFS](https://git-lfs.github.com/) (for working with large binary files, like PSDs)



## What is DevOps?

When you're programming, there's a lot of stuff you do that isn't …well, programming. You have to set up your system. You have to get the code (git!), and make sure that your development environment is configured properly to run it. You may have coding standards you need to write towards so that everything is written in the same style as your collaborators. You may have to compile code to run it. You might have scripts that are testing your code to see if it runs every time you commit it to the repo. You might have to host your code on a server or on the cloud. 

Developers don't like wasting their time, so they set up standards, build infrastructure, and adopt practices to streamline all of these non-code things so that they can spend more of their time writing code. These standards, infrastructure, and practices are referred to broadly as Developer Operations, or DevOps. 

There are a lot of things that fall under this title!

### What do you do for DevOps? 

- Containers! Start by looking into [Docker](https://www.docker.com/), it's probably the most popular system.
- Try to use tools that are as cross-platform as possible, so that if you have to develop on a different system, you're not introducing new changes in the configuration. (Try to keep things the same as possible!)
- Use tests more. (Want to learn more about it!)
- If you have a time-dependent project that is long running, use a cron job to take screenshots throughout the day so that you don't have to watch it throughout the day.
- Use stable releases of open source libraries. (Click on Releases under the Code tab in a repo in GitHub.)
- Use [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).
- Don't use git for games...or at least not for binary files. It's hard to remove something from your repo! If you accidentally commit a .PSD, it's still in your history even if you delete it, and it's hard to get rid of. If you can serialize things as text (to check into git), do so. Be aware of the size limit of your repo; unlike SVN or Perforce, git does not do _deltas_ of binary files, nor file-locking (which is also useful for binary files). Git is really popular, but it's not the best for everything. ([SVN](https://tortoisesvn.net/) is simpler for non-coders, too.)
- What if you don't want a public git repo site? GitHub is a service that does have private repos, although it charges for private repos. There's also [GitLab](https://about.gitlab.com/) (which you can install on a server, and it looks a lot like GitHub) and they also have a hosted service, as does [BitBucket](https://bitbucket.org/).
  - Git UI clients that are better than the default [`git-gui`](https://git-scm.com/docs/git-gui): [GitHub Desktop app](https://desktop.github.com/), [TortoiseGit](https://tortoisegit.org/), [SourceTree](https://www.sourcetreeapp.com/):nerdy_face:, [Tower](https://www.git-tower.com/), [GitKraken](https://www.gitkraken.com/):sparkles:
- Diff tools: [BeyondCompare](http://scootersoftware.com/):sparkles:, [TortoiseSVN's diff tool](https://tortoisesvn.net/docs/release/TortoiseSVN_en/tsvn-dug-diff.html), [WinMerge](http://winmerge.org/), [Kaleidoscope](http://www.kaleidoscopeapp.com/) (for Mac)
- `gitk` on Mac Terminal command line (is like `git-gui`)

### Further Resources

- [Looking Inside p5.js](https://vimeo.com/156838703) (video that explains basics of DevOps on P5.js open source project)
- [Getting Started with Development](https://github.com/processing/p5.js/wiki/Development) (P5.js has a wonderful community that encourages newbies to contribute, so their guide has a lot of best practices for getting involved in open source)
- [Periodic Table of DevOps Tools](https://xebialabs.com/periodic-table-of-devops-tools/) (links to so many other DevOps tools!)



## Documenting Your Projects 

_Will we have time to talk about this?_ 
ANSWER: Nope! _Some other time, perhaps!_