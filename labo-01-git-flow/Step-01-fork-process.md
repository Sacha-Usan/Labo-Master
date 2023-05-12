# Fork process

[Source](https://docs.github.com/en/get-started/quickstart/fork-a-repo)

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Git-flow scenario to master</p></figcaption></figure>

* [ ] Fork the "upstream" repository in your github organisation

![image1](screenshots/1.PNG)

* [ ] Clone your own repo in your local machine

```
[INPUT]
git clone https://github.com/Sacha-Usan/Labo-Master.git

[OUTPUT]
Cloning into 'Labo-Master'...
remote: Enumerating objects: 24, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 24 (delta 3), reused 3 (delta 3), pack-reused 16
Receiving objects: 100% (24/24), 6.29 KiB | 6.29 MiB/s, done.
Resolving deltas: 100% (3/3), done.
```

* [ ] Init Git flow (with standard settings)

```
[INPUT]
git flow init

[OUTPUT]
Which branch should be used for bringing forth production releases?
   - main
Branch name for production releases: [main]
Branch name for "next release" development: [develop]

How to name your supporting branch prefixes?
Feature branches? [feature/]
Bugfix branches? [bugfix/]
Release branches? [release/]
Hotfix branches? [hotfix/]
Support branches? [support/]
Version tag prefix? []
Hooks and filters directory? [C:/Users/sacha/Documents/Tech_ES/MON1/Labo-Master/.git/hooks]
```

* [ ] Integrate updates from upstream (main) into your repository (develop)

```
[INPUT]
git remote add upstream https://github.com/CPNV-MON1/Labo-Master.git
git remote -v

[OUTPUT]
origin  https://github.com/Sacha-Usan/Labo-Master.git (fetch)
origin  https://github.com/Sacha-Usan/Labo-Master.git (push)
upstream        https://github.com/CPNV-MON1/Labo-Master.git (fetch)
upstream        https://github.com/CPNV-MON1/Labo-Master.git (push)

[INPUT]
git pull upstream main

[OUTPUT]
From https://github.com/CPNV-MON1/Labo-Master
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> upstream/main
Already up to date.
```

* [ ] Create a branch feature called "terraformBasicScript"

```
[INPUT]
git flow feature start terraformBasicScript

[OUTPUT]
Switched to a new branch 'feature/terraformBasicScript'

Summary of actions:
- A new branch 'feature/terraformBasicScript' was created, based on 'develop'
- You are now on branch 'feature/terraformBasicScript'

Now, start committing on your feature. When done, use:

     git flow feature finish terraformBasicScript

```

* [ ] Add this code and commit it (feat:add basic terraform script")

```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```

```
[INPUT]
git add .
git commit -m "feat:add basic terraform script"

[OUTPUT]
[feature/terraformBasicScript 780819c] feat:add basic terraform script
 4 files changed, 89 insertions(+), 26 deletions(-)
 create mode 100644 labo-01-git-flow/screenshots/1.PNG
 create mode 100644 labo-01-git-flow/script
```

* [ ] Finish the feature

```
[INPUT]
git stash

[OUTPUT]
Saved working directory and index state WIP on feature/terraformBasicScript: 780819c feat:add basic terraform script

[INPUT]
git flow feature finish terraformBasicScript

[OUTPUT]
Switched to branch 'develop'
Updating 3192b2b..780819c
Fast-forward
 labo-01-git-flow/Step-01-fork-process.md  |  61 ++++++++++++++++++++++++------
 labo-01-git-flow/Step-02-prerequisites.md |  31 ++++++++-------
 labo-01-git-flow/screenshots/1.PNG        | Bin 0 -> 6276 bytes
 labo-01-git-flow/script                   |  23 +++++++++++
 4 files changed, 89 insertions(+), 26 deletions(-)
 create mode 100644 labo-01-git-flow/screenshots/1.PNG
 create mode 100644 labo-01-git-flow/script
Deleted branch feature/terraformBasicScript (was 780819c).

Summary of actions:
- The feature branch 'feature/terraformBasicScript' was merged into 'develop'
- Feature branch 'feature/terraformBasicScript' has been locally deleted
- You are now on branch 'develop'
```

* Push this modification on your repository

```
[INPUT]
git push --set-upstream origin develop

[OUTPUT]
Exception non gérée : System.ComponentModel.Win32Exception: Handle de fenêtre non valide
   à MS.Win32.ManagedWndProcTracker.HookUpDefWindowProc(IntPtr hwnd)
   à MS.Win32.ManagedWndProcTracker.OnAppDomainProcessExit()
   à MS.Internal.ShutDownListener.HandleShutDown(Object sender, EventArgs e)
info: please complete authentication in your browser...
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (8/8), 8.72 KiB | 8.72 MiB/s, done.
Total 8 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'develop' on GitHub by visiting:
remote:      https://github.com/Sacha-Usan/Labo-Master/pull/new/develop
remote:
To https://github.com/Sacha-Usan/Labo-Master.git
 * [new branch]      develop -> develop
branch 'develop' set up to track 'origin/develop'.
```

* What happens to the feature/branch ?

```
Il a été enlevé

[INPUT]
git branch

[OUTPUT]
* develop
  main
```

* Open a pull request comparing your develop branch to your main
* Assign the pull request to your partner

![image2](screenshots/2.PNG)
![image3](screenshots/3.PNG)


* Notify him using a issue "Could you please review my pull request ?"

![image4](screenshots/4.PNG)