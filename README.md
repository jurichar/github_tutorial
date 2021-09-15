#  GitHub Tutorial!

- git **`add`** 
	-
		add <file>
		add <directory> 
		add -p
	> ajoute les fichiers ou les bouts de code a inclure dans le prochain `commit`

- git **`commit`**
	- 
		commit
		commit -a
		commit -m <msg>
	> capture l'état d'un projet à un point dans le temps.

- git **`pull`**
	-	
		pull
		pull <remote>
		pull --verbose
	> une combinaison de `git fetch` suivie de `git merge`.

- git **`fetch`**
	-	
		fetch
		fetch <remote> <branch>
		fetch --all
	> télécharge toute les `branch` d'un dépôt.

- git **`push`**
	- 
		push
		push -f
		push <remote> <branch>
	> push de la `branch`, avec tous les `commit` et objets internes nécessaires.

- git **`branch`**
	- 
		branch
		branch <branch>
		branch -d <branch>
		branch -m <branch>
	> permet de lister, créer, supprimer et renommer les `branch`.

- git **`checkout`**
	- 
		checkout <branch>
		checkout -b <new-branch>
	> permet de basculer d'une `branch` à l'autre, ou d'en créer.

- git **`merge`** 
	- 
		merge <branch>
	> utilisé pour combiner 2 `branch`, celle en argument s'implémente a celle courante, en cas de conflit les 2 séquences sont séparées.

- git **`rebase`**
	- 
		git rebase <base>
	> `rebase` automatiquement la branche courante sur la `base`
	
- git **`remote`**
	- 
		remote
		remote -v
	> permet de gérer les connexion entre les dépôts.

- git **`status`**
	- 
	> répertorie les fichiers stagés, non stagés et non trackés.
	
- git **`log`**
	- 
	> affiche la liste des messages de `commit`

## Exemple :

Je suis sur un projet a 2, j'ai donc créé ma `branch` (**` git branch -m <branch>`**) afin de travailler dessus.

A la fin de la journée, je vais **`git add <file>`** mes nouveaux fichiers, puis les  **`git commit`** et enfin les **`git push`** sur ma `branch`.

Après une semaine, mon travaille ayant bien avancer, je vais pouvoir j'ajouter a la `branch` principale. Pour cela je vais aller sur celle-ci, avec **`git checkout <branch>`** puis je vais **`git merge <branch>`** avec ma `branch`.

Mon collègue de retour de vacances, décide de voir l'état du projet via **`git log`**, après avoir vu l'immense quantité de travail, il va donc utiliser **`git rebase <base>`** afin de mettre a jour sa `branch`. 

Chez moi je ne me rappel plus si j'ai bien `push`, pour m'en assurer je vais donc utiliser **`git status`**. Le lendemain je pourrai utiliser **`git pull`** afin de récupérer ce que j'ai fais chez moi.
