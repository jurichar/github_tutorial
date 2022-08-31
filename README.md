# Git Tutorial

_Parce que git, plus on s'y connait mieux c'est !_

## .gitignore

> permet d'ignorer certains fichier lors d'un ajout (_ex: `git add .`_).

## git **init**

> vous disposez à présent d'un dépôt `git` entièrement fonctionnel.

## git **add**

| cmd                 | description                                                                       |
| ------------------- | --------------------------------------------------------------------------------- |
| git add             | ajoute un changement dans le répertoire de travail à la zone de staging.          |
| - `add <file>`      | permet de stager tous les changements dans `<fichier>` pour le commit suivant.    |
| - `add <directory>` | permet de stager tous les changements dans `<répertoire>` pour le commit suivant. |

## git **commit**

| cmd                       | description                                                           |
| ------------------------- | --------------------------------------------------------------------- |
| git commit                | permet d'archiver les changements ajouter (`git add` ou `git stage`). |
| `git commit`              | permet d'archiver les changements puis demande un message.            |
| `git commit -m "message"` | permet d'archiver les changement sans demander de message.            |
| `git commit -ammend`      | modifie le dernier commit au lieu d'en creer un nouveau.              |

<!--
## git **pull**

| cmd | description |
| --- | ----------- |
| 1   | 0           |

## git **stash**

| cmd | description |
| --- | ----------- |
| 1   | 0           |

## git **reset**

| cmd | description |
| --- | ----------- |
| 1   | 0           |
-->

## git **revert**

| cmd           | description                                                                                                                         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| git revert    | utilisée pour annuler des changements apportés à l'historique de commits d'un dépôt (un `undo` pour git) et cree un nouveau commit. |
| - `revert -e` | ouvrira l'editeur pour modifier le message de `commit`.                                                                             |
| - `revert -n` | git revert ne fera pas de nouveau commit.                                                                                           |

<!--
## git **rm**

| cmd | description |
| --- | ----------- |
| 1   | 0           |

## git **clean**

| cmd | description |
| --- | ----------- |
| 1   | 0           |

## git **cherry-pick**

| cmd | description |
| --- | ----------- |
| 1   | 0           |

-->

## git **fetch**

| cmd                         | description                                                                                 |
| --------------------------- | ------------------------------------------------------------------------------------------- |
| git fetch                   | telecharge des commits, des fichiers et des refs d'un depot distant vers votre depot local. |
| - `fetch <remote>`          | `fetch` toutes les `branch`, les fichiers et les `commits` du depot.                        |
| - `fetch <remote> <branch>` | comme la commande ci-dessus, mais fetche uniquement la `branch` specifiee.                  |
| - `fetch --all`             | fetch de tous les depots distants enregistres et de leurs `branch`.                         |

## git **push**

| cmd                        | description                                                                 |
| -------------------------- | --------------------------------------------------------------------------- |
| - `git push`               | permet de transférer les commits de votre dépôt local vers un dépôt distant |
| - `push <remote> <branch>` | permet de push la `branch` vers le `remote`                                 |
| - `push -f` (ou `--force`) | permet de forcer un push                                                    |

## git **branch**

| cmd                             | description                                     |
| ------------------------------- | ----------------------------------------------- |
| git branch                      | permet la gestion des `branch` d'un depot.      |
| - `branch` (ou `branch --list`) | permet de lister toutes les `branch` du depot.  |
| - `branch <branch>`             | permet de creer une `branch`.                   |
| - `branch -d <branch>`          | permet de supprimer une `branch`.               |
| - `branch -D <branch>`          | permet de forcer la suppression d'une `branch`. |
| - `branch -m <branch>`          | permet de renommer une `branch`.                |

## git **checkout**

| cmd                                   | description                                                         |
| ------------------------------------- | ------------------------------------------------------------------- |
| git checkout                          | permet de basculer entre les `branch`.                              |
| - `checkout <branch>`                 | permet de basculer entre les `branch` existante.                    |
| - `checkout -b <new-branch>`          | permet de basculer sur une `new-branch`.                            |
| - `checkout -b <new-branch> <branch>` | permet de basculer sur une `new-branch` qui prend en base `branch`. |

## git **merge**

`git merge <branch>` combine plusieurs sequences de commit.

la `branch` sur laquel nous sommes sera `merge` avec la `branch` en parametre.

en cas de conflit pendant ce processus nous aurons 3 indicateurs :

- `<<<<<<<`
- `=======`
- `>>>>>>>`

le contenu avant `=======` represente la `branch` cible et la partie apres represente la `branch` a `merge`.

le reste du code ne sera pas affecte par le conflit.

## git **rebase**

| cmd        | description                                                         |
| ---------- | ------------------------------------------------------------------- |
| git rebase | permet de changer la base de la `branch` d'un commit vers un autre. |
| - `rebase <base>` | applique automatiquement le `rebase`. |
| - `rebase -- i <base>` | applique le `rebase` en mode interactif*. |

p, pick = use commit

r, reword = use commit, but edit the commit message

e, edit = use commit, but stop for amending

s, squash = use commit, but meld into previous commit

f, fixup = like “squash”, but discard this commit’s log message

x, exec = run command (the rest of the line) using shell

d, drop = remove commit

<!-- 
## git **remote**

| cmd | description |
| --- | ----------- |
| 1   | 0           |

## git **status**

| cmd | description |
| --- | ----------- |
| 1   | 0           |
-->

## git **log**

| cmd     | description                               |
| ------- | ----------------------------------------- |
| git log | affiche l'historique des commit du depot. |
