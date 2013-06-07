Préparer son environnement Löve/Lua
===================================

# Qu'est-ce Löve? Qu'est-ce Lua?

## Löve

Löve est un framework pour créer des jeux, c'est à dire un outil qui contient un ensemble cohérent d'instructions et modules qui facilitent la création de jeux.
Pour créer un jeu avec Löve, il suffit d'un éxecutable Löve et d'un dossier qui contiendra tout le code de jeu, ainsi que le contenu (images, sons, etc...)

## Lua

Lua n'est pas un acronyme, ça ne s'écrit donc pas LUA. Lua signifie "Lune" en portugais.
Lua est un langage de scriptage, ou langage interprété, crée au Brésil par le département Tecgraf de l'université PUC-Rio. A l'origine ce langage servait à configurer les outils que développait Tecgraf, mais il a été fortement étendu et optimisé. Il propose aujourd'hui une syntaxe et une philosophie de programmation simple mais extensible.

# Pourquoi Löve/Lua?

La bibliothèque de fonctions qu'offre Löve est simple mais complète, permettant de nous concentrer sur les problèmes intéressants du développement de jeux, sans non plus passer sur quelques difficultés qui sont importants. A noter, Löve ne propose pas de "logique" de jeu, il n'y a pas de notions d'objets de jeux, de plateformes ou de projectiles. Il faudra créer toutes ces choses soi-même. Löve propose plutôt des fonctions permettant de charger des fichiers sons et images, de déssiner ces choses à l'écran, de reconnaître les commandes clavier/souris/manette, et de mesurer le passage du temps.

Löve utilise Lua comme langage de programmation, et c'est un excellent langage pour apprendre, puisqu'il est rapide à prendre en main, mais s'étend jusqu'au plus profond des principes complexes de la programmation.

# Installons tout ça!

## Löve

Vous aurez besoin d'un éxecutable depuis le site http://www.love2d.org
Prenez la version "Zipped" pour votre système d'exploitation, je n'ai pas de Mac sous la mais pour tester la suite des hostilités, donc en attendant, j'espère qu'il y a assez de parallèles pour pouvoir suivre.

## Editeur de texte

Un logiciel de traitement de texte comme Word ou OpenOffice n'est PAS bon DU TOUT pour ce qu'on va faire. On a besoin d'un éditeur comme le bloc-notes qui édite directement les charactères qui composent le fichier.

### Mes préférés:
+ http://notepad-plus-plus.org/
+ http://www.sublimetext.com/

Ces outils fonctionnent exactement comme le bloc-notes, mais ont quelques avantages:
+ Ils permettent d'avoir plusieurs fichiers ouverts
+ Ils colorisent le texte afin de surligner les éléments de syntaxe
+ Ils donnent un meilleur accès à tous les fichiers d'un projet

## Environnement de travail

Créez quelque part un dossier qui contiendra vos projets de jeux avec Löve.
Dézippez le fichier zip que vous avec téléchargé depuis le site directement dedans.
Ensuite vous créerez dans ce dossier des sous dossiers qui contiendront vos projets.
Ca devrait ressembler à ceci (pour Windows)
'''
  /mes_projets
	|--- love.exe
	|--- DevIL.dll
	|--- OpenAL32.dll
	|--- SDL.dll
	|--- /pong
	|    |--- main.lua
	|    |--- conf.lua
	|    |--- palette.lua
	|
	|--- /casse_briques
	     |--- main.lua
	     |--- conf.lua
	     |--- brique.lua
'''

Pour tester un de vos jeux, vous ferez glisser le dossier de projet sur le l'executable pour l'ouvrir avec
