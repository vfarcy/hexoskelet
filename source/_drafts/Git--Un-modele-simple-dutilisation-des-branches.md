title: "Git : Un modèle simple d'utilisation des branches"
tags:
---

**Article en test, en cours d'adaptation**

# Un workflow simple qui fonctionne

Le modèle présenté est très largement répandu, simple et fonctionnel. En tant que tel, ou bien via des variantes, il est utilisé par beaucoup de développeurs, par exemple chez [Athena](http://athena.ai), [GitHub](https://github.com), ou encore par Zach Holman qui le mentionne mentionne dans sa [présentation](http://www.youtube.com/watch?v=qyz3jkOBbQY&t=09m12s).


### Le principe 

1. `master` est la branche prête à être déployée en production.
1. **tous les changements** (pull-request + merge) sont effectués dans la branche `feature`
1. rebase to avoid/resolve conflicts; merge in to `master` **A VOIR !**

Pour faire simple, tout est résumé sur ce schémas de Zach Holman :

![flow](https://gist.github.com/shvechikov/de39c99574488a3de12a/raw/24c6696441e40eae24805426ba5465583414d046/z-git-branching.jpeg)

### Le workflow

```bash
# tout est ok, la branche master est la référence de production
git checkout master
git pull origin master

# let's branch to make changes
git checkout -b my-new-feature

# En avant pour les changements.
$EDITOR file

# on commit les changements, incrementaux et atomiques
git add -p
git commit -m "my changes"

# keep abreast of other changes, to your feature branch or master.
# rebasing keeps our code working, merging easy, and history clean.
git fetch origin
git rebase origin/my-new-feature
git rebase origin/master

# en option: push de votre branche pour discussion (pull-request)
#           à faire autant de fois que nécessaire pendant le développement.
git push origin my-new-feature

# en option: feel free to rebase within your feature branch at will.
#           ok to rebase after pushing if your team can handle it!
git rebase -i origin/master

# quand la développment sont terminés, on merge.
# --no-ff preserves feature history and easy full-feature reverts
# merge commits should not include changes; rebasing reconciles issues
# github takes care of this in a Pull-Request merge
git checkout master
git pull origin master
git merge --no-ff my-new-feature


# optional: tag important things, such as releases
git tag 1.0.0-RC1
```

### useful config

```bash
# autosetup rebase so that pulls rebase by default
git config --global branch.autosetuprebase always

# if you already have branches (made before `autosetuprebase always`)
git config branch.<branchname>.rebase true
```

### A faire, ... et à ne pas faire

Bien évidemment il y à des exceptions, ici rien n'est inscrit dans le marbre, mais voici néammoins des recommendations utiles.

#### A faire

- **DO** keep `master` in working order.
- **DO** rebase your feature branches.
  - **DO** pull in (rebase on top of) changes
- **DO** tag releases
- **DO** push feature branches for discussion
- **DO** learn to rebase


#### A ne pas faire

- **DON'T** merge in broken code.
- **DON'T** commit onto `master` directly.
  - **DON'T** hotfix onto master! use a feature branch.
- **DON'T** rebase `master`.
- **DON'T** merge with conflicts. handle conflicts upon rebasing.


### Liens à visiter

- https://github.com/blog/1124-how-we-use-pull-requests-to-build-github


## FAQ


### Won't `git merge --no-ff` generate merge bubbles?

Yes. Merge bubbles aren't inherently bad. They allow you to revert entire
features at a time. They get confusing and annoying to deal with if they cross
(commits interleave), so don't do that.

![merge bubbles](https://gist.github.com/shvechikov/de39c99574488a3de12a/raw/4a6876d77884853521692df8dbb22914f9f81109/z-git-bubbles.png)


### What do you mean by "incremental, atomic" changes?

http://en.wikipedia.org/wiki/Atomic_commit#Atomic_Commit_Convention

Thanks wikipedia, I couldn't have put it better myself.


### Why not [gitflow](http://nvie.com/git-model/) or another complex workflow?

Be my guest. I've used gitflow and other similar models.
After working in various teams, this is just what I've come to use.
But next time you have to ask someone whether it is okay to push or pull from
this or that branch, remember
[my face](http://juan.benet.ai/img/juan.batizbenet.headshotsq.jpg).


### But, is it [web-scale](http://mongodb-is-web-scale.com/)?

Friends claim more complex models are necessary for scaling large teams,
maintaining old releases, controlling information flow, etc. It very well may
be that using multiple mainlines (e.g. `develop`, `stable`, `release`, `v2`,
`tested`, etc) is exactly what fits your organization's constraints. That's
for you to decide, not me (unless we work together -- oh hi there!).

But you always have to wonder, "shouldn't I use tags for that"? For example,
tracking releases on a branch is a bit silly. A release commit can be tagged.
You can checkout a tag, just like any branch, or any commit, and do
whatever it is you need to do.

My guess is this relationship holds:

![headless](https://gist.github.com/shvechikov/de39c99574488a3de12a/raw/ef8be1e41fb8ae0e58de732103e09588f6ba8156/z-git-headless.jpeg)

So, perhaps taking five minutes to teach your team how to use `checkout` and
`tag` might save you more than 15% on car insurance.


## GitHub notes


### Don't fork. Push feature branches to main repo.

Sometimes I see people forking repositories in order to issue pull-requests.
Yes, you may have to do this when contributing to open-source projects you 
don't regularly contribute to. But, if you are a contributor, or working in the same org, get push rights on the repo and push all your feature branches to it. 
**Issue pull requests from one branch to another within the same repo.**


### Should I merge Pull Requests on the site or commandline?

Up to you. Github does `git merge --no-ff` so that the commit message indicates the pull request number. This is useful information to have, don't just throw away history for the sake of it. You never know what will be useful to look at in the future.

[Source](https://gist.github.com/jbenet/ee6c9ac48068889b0912)






 