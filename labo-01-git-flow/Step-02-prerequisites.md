# Prerequisites

## Setting up/updating the git environment and git flow

[Get the installer](https://git-scm.com/downloads)

{% hint style="info" %}
Git-flow library:\
For Windows, is natively integrated.\
For Mac, [here is the procedure](https://git-scm.com/download/mac).\
Pour Linux, [here is the procedure.](https://howtoinstall.co/en/git-flow)
{% endhint %}

```
[INPUT]
choco install git.install
```

* [ ] Confirm the installed version

```
[INPUT]
git flow version

[OUTPUT]
1.12.3 (AVH Edition)
```

* [ ] What do you think about this release?

```
source : https://github.com/petervanderdoes/gitflow-avh/releases/tag/1.12.3
```

## What's git-flow, branches feature.

[Source](https://nvie.com/posts/a-successful-git-branching-model/)

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption><p>Source : A successful git branching model</p></figcaption></figure>

* [ ] Which branches are persistent and what do they contain?

```
main et develop

main : branche de production
develop : branche de la prochaine version
```

* [ ] Why do we have to merge hotfix in both master and develop branches, but not into all active feature branches?

```
hotfix sert à corriger les bugs présent dans la branche de production
c'est pourquoi il faut le merger sur main et develop

contrairement aux autres branches qui sont temporaires et servant à rajouter des nouvelles fonctionnalitées
```

## Initialize git flow on an existing project

* [ ] What happens when you run the "git flow init" command on an existing local repository?

```
créer la branche develop et nous y déplace dessus
```

* [ ] When do we need to make this git command?

```
après avoir cloné un dépôt
```

## Practice the basic git commands

[Source](https://www.atlassian.com/git/glossary)

* [ ] What does this git command "git add -all" achieve (.gitignore impacts)?

```
ajout tout les fichiers sauf ceux indiqués dans le fichier .gitignore
```

* [ ] What does this git command "git status" achieve?

```
affiche le statut de la branche actuel
```

* [ ] What does this git command "git remote add upstream \<url>" achieve?

```
ajout un dépôt de référence
```
