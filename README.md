# Exercice Metro Git

## Prerequisite 
Nice to have, just in case, undo and lola : 
```
git config --global alias.undo '!f() { \
    git reset --hard $(git rev-parse --abbrev-ref HEAD)@{${1-1}}; \
}; f'

git config --global alias.lola 'log --graph --decorate --pretty=oneline --abbrev-commit --all'
```

1. Clone the projet https://github.com/lhoang/metro-git.git
2. Checkout locally all the branches : `ligne1, ligne1b, Ligne2, ligne2b, Ligne9`
   Ex: with `git checkout -b ligne1b origin/ligne1b`
3. Remove the link with the distant repository
  ```shell 
    git remote -v
    git remote rm origin
  ```

## Instructions

1. Rename Gare de Lyon
1. Switch Bastille <-> Gare de Lyon
1. Move ligne 2b onto ligne 2 _(hint: rebase)_
1. Move ligne 1 onto ligne 1 _(hint: rebase onto)_
1. Create ligne 9a from Franklin D. Roosevelt, add Miromesnil, République, Voltaire
1. Create Nation _(hint: Octopus merge)_
1. Clean the a and b branches, and finish the ligne 1 and 9.

## Extras 
* Empty commit :
``` 
git commit --allow-empty -m "commit message"
```

* Create Orphan branch :
```
git checkout --orphan orphan_name
git rm -rf .
```

* Merge Orphan branch : 
```
git merge orphan_name --allow-unrelated-histories
```

