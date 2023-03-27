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

## git **pull**

| cmd               | description                                                                                              |
| ----------------- | -------------------------------------------------------------------------------------------------------- |
| git pull          | permet de récupérer les dernières modifications effectuées sur une branche distante et de les fusionner. |
| - `pull <remote>` | permet de récupérer les dernières modifications effectuées sur toutes les branches distantes.            |
| - `pull <branch>` | permet de récupérer les dernières modifications effectuées sur une branche distante spécifique.          |
| - `pull --rebase` | permet de récupérer les dernières modifications et de les intégrer avec un rebase plutôt qu'un merge.    |
| - `pull --force`  | permet de forcer la fusion des branches locales et distantes en écrasant les éventuels conflits.         |

## git **stash**

| cmd                         | description                                                                                     |
| --------------------------- | ----------------------------------------------------------------------------------------------- |
| git stash                   | permet de sauvegarder temporairement les modifications non-committées du répertoire de travail. |
| - `stash apply`             | permet d'appliquer la sauvegarde la plus récente du stash.                                      |
| - `stash apply <stash@{n}>` | permet d'appliquer la sauvegarde numéro n du stash.                                             |
| - `stash drop`              | permet de supprimer la sauvegarde la plus récente du stash.                                     |
| - `stash drop <stash@{n}>`  | permet de supprimer la sauvegarde numéro n du stash.                                            |
| - `stash list`              | permet d'afficher la liste des sauvegardes stockées dans le stash.                              |

## git **reset**

| cmd                          | description                                                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------- |
| git reset                    | permet de retirer les fichiers de la zone de staging et de les remettre dans le répertoire de travail.         |
| - `reset <file>`             | permet de retirer un fichier spécifique de la zone de staging.                                                 |
| - `reset <commit>`           | permet de réinitialiser la branche courante à un commit précis.                                                |
| - `reset --hard <commit>`    | permet de réinitialiser la branche courante à un commit précis, en perdant toutes les modifications suivantes. |
| - `reset --soft <commit>`    | permet de réinitialiser la branche courante à un commit précis, en conservant les modifications suivantes.     |
| - `reset HEAD~`              | permet de réinitialiser la branche courante au commit précédent.                                               |
| - `reset --merge <commit>`   | permet de réinitialiser la branche courante en annulant un commit de fusion.                                   |
| - `reset --hard origin/main` | permet de réinitialiser la branche locale à l'état actuel de la branche distante.                              |

## git **revert**

| cmd           | description                                                                                                                         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| git revert    | utilisée pour annuler des changements apportés à l'historique de commits d'un dépôt (un `undo` pour git) et cree un nouveau commit. |
| - `revert -e` | ouvrira l'editeur pour modifier le message de `commit`.                                                                             |
| - `revert -n` | git revert ne fera pas de nouveau commit.                                                                                           |

## git **rm**

| cmd             | description                                                        |
| --------------- | ------------------------------------------------------------------ |
| git rm          | permet de supprimer un fichier du répertoire de travail et de git. |
| - `rm <file>`   | permet de supprimer un fichier spécifique.                         |
|                 |
| - `rm -r <dir>` | permet de supprimer un dossier récursivement.                      |
|                 |

## git **clean**

| cmd                                    | description                                                                         |
| -------------------------------------- | ----------------------------------------------------------------------------------- |
| git clean                              | permet de supprimer les fichiers non tracés par git.                                |
| - `clean -n`                           | permet de simuler le nettoyage.                                                     |
| - `clean -f` (ou `--force`)            | permet de forcer le nettoyage et la suppression des fichiers.                       |
| - `clean -d`                           | permet de supprimer également les dossiers non tracés par git.                      |
| - `clean -i`                           | affiche la liste des fichiers non suivis et offre la possibilité de les supprimer.  |
| - `clean -xdf` (ou `--force -d -f -x`) | supprime les fichiers et les dossiers non suivi par git dans le repertoire courant. |

## git **cherry-pick**

| cmd                                                             | description                                                                                                                  |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| git cherry-pick `commit-hash`                                   | permet d'appliquer les modifications d'un commit spécifique sur la branche courante.                                         |
| git cherry-pick `commit-hash1` `commit-hash2` `commit-hash3`... | permet d'appliquer les modifications de plusieurs commits spécifiques sur la branche courante.                               |
| git cherry-pick `branch-name`                                   | permet d'appliquer les modifications du dernier commit de la branche spécifiée sur la branche courante.                      |
| git cherry-pick `commit-hash` `--strategy-option=value`         | permet d'utiliser une stratégie spécifique lors de l'application des modifications du commit.                                |
| git cherry-pick `commit-hash` `--no-commit`                     | permet d'appliquer les modifications sans faire de commit.                                                                   |
| git cherry-pick `commit-hash` `--edit`                          | permet de modifier le message de commit avant de créer le commit.                                                            |
| git cherry-pick `commit-hash` `--strategy`                      | permet de spécifier la stratégie de fusion à utiliser.                                                                       |
| git cherry-pick `commit-hash` `-m parent-number`                | permet de spécifier le parent d'un commit à fusionner.                                                                       |
| git cherry-pick `commit-hash` `-x`                              | ajoute la ligne "Cherry-pick commit-hash" à la fin du message de commit.                                                     |
| git cherry-pick `commit-hash` `--ff` (ou `--no-ff`)             | permet de fusionner les commits à l'aide de la méthode "fast-forward" (`--ff`) ou en créant un commit de fusion (`--no-ff`). |
| git cherry-pick `commit-hash` `--abort`                         | permet d'annuler la commande en cours de `cherry-pick`.                                                                      |
| git cherry-pick `commit-hash` `--continue`                      | permet de poursuivre le processus de `cherry-pick` après la résolution d'un conflit.                                         |
| git cherry-pick `commit-hash` `--skip`                          | permet de sauter le commit si celui-ci a déjà été appliqué.                                                                  |

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

| cmd                    | description                                                         |
| ---------------------- | ------------------------------------------------------------------- |
| git rebase             | permet de changer la base de la `branch` d'un commit vers un autre. |
| - `rebase <base>`      | applique automatiquement le `rebase`.                               |
| - `rebase -- i <base>` | applique le `rebase` en mode interactif\*.                          |

p, pick = use commit

r, reword = use commit, but edit the commit message

e, edit = use commit, but stop for amending

s, squash = use commit, but meld into previous commit

f, fixup = like “squash”, but discard this commit’s log message

x, exec = run command (the rest of the line) using shell

d, drop = remove commit

## git **remote**

| cmd                            | description                                              |
| ------------------------------ | -------------------------------------------------------- |
| `git remote`                   | permet d'afficher les depots distants associes au depot. |
| - `remote -v` (ou `--verbose`) | affiche les URLs completes des depots distants associes. |
| - `remote add <remote> <url>`  | permet d'ajouter un depot distant.                       |
| - `remote remove <remote>`     | permet de supprimer un depot distant.                    |
| - `remote rename <old> <new>`  | permet de renommer un depot distant.                     |

## git **status**

| cmd                   | description                                                     |
| --------------------- | --------------------------------------------------------------- |
| `git status`          | permet d'afficher l'etat du depot par rapport au commit courant |
| - `-s` (ou `--short`) | affiche un resume en mode court.                                |

## git **log**

| cmd     | description                               |
| ------- | ----------------------------------------- |
| git log | affiche l'historique des commit du depot. |
