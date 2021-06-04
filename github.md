# Github !

## Créer une branche 

**$ git checkout master** : s'assurer qu'on est sur la branche master sur son ordi.
**$ git pull origin master** : récupérer de GitHub la dernière version de master.
**$ git branch nom_de_ta_feature** : créer une branche nommée "nom_de_ta_feature" à partir de master qui est désormais à jour.
**$ git checkout nom_de_ta_feature** : se positionner sur la branche "nom_de_ta_feature".

Chaque commit aura lieu uniquement sur la branche "nom_de_ta_feature". 
Pour cela, on utilise les classiques :
**$ git add** : préparer à commit tous les fichiers ayant été modifiés
**$ git commit -m "commentaire sur mon commit"** : faire un commit


## Fusionner une branche

**$ git checkout master** : se mettre sur la branche master pour la mettre à jour.
**$ git pull origin master** : récupérer tout le travail qui a été effectué et mets la branche master à jour
**$ git checkout nom_de_ta_feature** : se remettre sur ta branche de feature en vue de la fusionner.
**$ git merge master** : demander à Git de fusionner master dans ta branche. L'ordre est important : c'est master qui va DANS ta branche et pas l'inverse. La branche master n'est pas modifiée pour le moment.
**$ git checkout master** : se remettre sur master
**$ git merge nom_de_ta_feature** : faire la fusion dans l'autre sens. On fusionne ta branche DANS master. La branche master est donc mise à jour.
**$ git push origin master** : La fusion est faite, il faut mettre GitHub à jour.


## Gérer les conflits
En cas de conflit, affichage du message suivant dans ton terminal, juste après un git merge :

```$ git merge master
Auto-merging foo.rb
CONFLICT (content): Merge conflict in foo.rb
CONFLICT (content): Merge conflict in bar.rb
Automatic merge failed; fix conflicts and then commit the result.
```

Se rendre dans les fichiers identifiés par les lignes **CONFLICT (content)**, et voir les modif de Github via l'ajout de balise :

```
<<<<<<<<< HEAD
p "Kikou !" #version de code A
============
p "Hello !" #version de code B
>>>>>>>>> la_branche
```

Conserver les parties nécessaires et faire les commandes suivantes pour valider la résolution des conflits :

**$ git add** : ajouter les fichiers à commit
**$ git commit (sans le -m "commentaire")** : commiter les changements

À ce moment-là, le programme devrait envoyer un message pour te demander de rajouter un commentaire et nommer ton conflit. Pas besoin de le gérer, tu peux quitter le programme en faisant **:x** puis **Enter**. 