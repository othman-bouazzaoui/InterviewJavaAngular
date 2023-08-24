# les questions technique sur git.

## - c'est quoi git ?
git est une technologie qui permet de versionner le code source d'une application ou des fichiers(txt/docx ...)

## - c'est quoi la différence entre git et github/gitlab ... ?
git c'est une technique, il s'agit des commandes qu'on écrit sur l'invit du commande ou il y a aussi des outils qui nous prpose IHM pour faciliter la vie des developpeurs par exemple(gui, turtoise ou les extentions intégré dans les ide).

github/gitlab represent les serveurs qui support cette technologie(git), qui nous permet de stocker le code.

## - que sont les commandes git les plus utiliser ?
* `git init :>` permet d'initialiser un repository git.
* `git clone :>` permet de cloner/récupèrer un repository distant en local
* `git status :>`  permet de voir le statut des modifications faite sur des fichiers en local.
* `git add :>` permet de préparer les fichiers modifiés afin de les versionner par un commit.
* `git commit :>` permet de créer une version/commit du code.
* `git push :>` permet de pousser le code depuis une branch/repo local vers la branch/repo distante.
* `git pull :>`  permet de mettre à jour une branche en local par les modifications dans la branche equivalente en repo distant

* `git checkout :>` permet de switcher d'une branche vers une autre avec la création d'une branche si on ajoute l'option -b
* `git branch branch_Name: >` permet creer une branche.
* `git branch:>` permet d'afficher tous les branches local.
* `git branch -M oleName newName:>` permet de renommer une branche.
* `git branch -r :>` permet d'afficher tous les branches distantes.
* `git branch -a :>` permet d'afficher tous les branches local et distant.
* `git merge branche1 branche2 :>` permet de merger une branche dans une autre.
* `git rebase master :>` permet de faire un rebase sur branche pour qu'elle soit la branche de base.
* `git cherry-pick :> ` permet de prendre un commit depuis une branche et l'intérger dans une autre branche d'une manière intélligente(bien sûr le commit ne sera pas supprimer de la première).
* `git revert commmit_Id :> ` permet de faire un revert/annuler d'un commit.
* `git revet commit_id :>` permet de remmetre l'état de la branche vers ce commit(comme un point de restauration).
* `git tag tag_name:>` permet de tagger/créer une d'une branche, il est très utilisé dans les cas où on travaille en mode agil à chaque fois qu'on livre une fiche(s), on doit tagger la version.


## - c'est quoi la différence entre git merge et git rebase ?
>> les 2 font la mêmes choses avec des manières différents
* `git merge :` garde une traçabilité, les commits ne seront plus stillé.
* `git rebsae :` ne garde pas une traçabilité, les commits reste stillé et ordonné(mais attention, il faut être prudant, cette action peut casser tous)



