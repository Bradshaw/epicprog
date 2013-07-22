Variables et instructions
=========================

Ce tutorial utilise le framework Löve/Lua, donc assurez vous d'avoir préparé votre environnement de travail et créez un nouveau projet.

## Etape 1 - Afficher un rectangle (WTF!? TROP CLASSE!)

A ce moment du tutorial, votre fichier main.lua devrait ressembler à ceci:

```lua
function love.load(arg)

end

function love.update(dt)

end

function love.draw()

end
```


Ces trois fonctions sont les blocs de base d'un jeu:

```love.load(arg)``` est appellé pendant le chargement du jeu, on y mettra toutes notre phase de préparation du jeu, chargement du contenu, initialisation des niveaux, etc...

```love.update(dt)``` sera appellé à chaque trame du jeu, il connait (grâce au "dt") le temps passé depuis la dernière trame. Nous calculerons ici l'évolution du jeu.

```love.draw()``` sera aussi appellé à chaque trame, juste après ```love.update()```, il contiendra nos fonctions de dessin, c'est ici qu'on affichera tout à l'écran.

Pour tester, dessinons un rectangle avec la commande suivante:
```lua
love.graphics.rectangle("fill", 250, 200, 150, 100)
```

Les plus futés devineront qu'il faut écrire ceci à l'intérieur de la fonction ```love.draw()``` afin d'obtenir ceci:
```lua
function love.draw()
    love.graphics.rectangle("fill", 250, 200, 150, 100)
end
```

Important:
J'ai "indenté" l'intérieur de la fonction, ceci est une habitude à prendre! Ca permet de voir facilement la structure du programme, par éxemple, pour vérifier que la fonction est correctement terminée, il suffit de regarder s'il y a un ```end``` au même alignement.
Ceci est facultatif, mais sachez c'est peut-être un des conseils des plus importants dans la programmation!

Bon, testez votre projet, vous devriez voir un réctangle blanc, passionant n'est-ce pas?


## Etape 2 - Faisons bouger ce rectangle!

Regardons un peu plus près cette commande qui dessine le rectangle:
```lua
love.graphics.rectangle("fill", 250, 200, 150, 100)
```
Entre les parenthèses nous avons cinq "arguments", ce sont des paramètres que nous donnons à la fonction pour qu'elle sache _comment_ on veut dessiner ce rectangle.

```lua
love.graphics.rectangle(mode, x, y, largeur, hauteur)
```

+ ```mode```: Mode de dessin, plein ```"fill"``` ou lignes ```"line"```
+ ```x```: Position du coin haut-gauche sur l'axe x (de gauche à droite)
+ ```y```: Position du coin haut-gauche sur l'axe y (de haut en bas)
+ ```largeur```: La largeur du rectangle
+ ```hauteur```: La hauteur du rectangle

Notez bien que l'axe vertical est descendant, 0 marque le haut de l'écran et les nombres positifs descendent le long de la fenêtre.

Imaginons que nous voulons que le rectangle se déplace de gauche à droite, à raison de cent pixels par seconde.
Il faut modifier le deuxième paramètre (```x```) pour le faire grandir d'une trame à l'autre.

Nous allons donc créer une variable pour stocker la position du rectangle, puis modifier cette variable.

En Lua, pour stocker quelquechose il suffit de faire:
```lua
nom_de_la_variable = chose_a_stocker
```

Ceci crée une nouvelle variable nommée ```nom_de_la_variable``` et lui affecte la valeur de ```chose_a_stocker```.

Je propose donc de faire:
```lua
pos_x = 250
```

Mettons cette affectation dans ```love.load()``` puisque c'est une initialisation.
```lua
function love.load(arg)
    pos_x = 250
end
```

Et modifions notre appel à ```love.graphics.rectangle(mode, x, y, largeur, hauteur)``` afin d'utiliser la nouvelle variable:
```lua
function love.draw()
    love.graphics.rectangle("fill", pos_x, 200, 150, 100)
end
```

Testons le projet, on devrait avoir la même chose que tout à l'heure, décevant non?

Le rectangle ne bouge toujours pas, tout simplement parce que ```pos_x``` ne varie pas, ce qui est triste pour une variable.

Ce qu'on veut, c'est que ```pos_x``` soit un peu plus grand à chaque trame, pour faire ceci, on va affecter une nouvelle valeur pendant ```love.update(dt)```
```lua
function love.update(dt)
    pos_x = pos_x + 1
end
```

Ceci devrait piquer les yeux de tous les matheux, ```pos_x``` ne peut pas être égal à ```pos_x + 1```!
C'est parce qu'en programmation  le symbole ```=``` est le symbole d'affectation, ça veut dire qu'on stocke la valeur de la partie droite dans la partie gauche, rappellez-vous: ```nom_de_la_variable = chose_a_stocker```

Testons le projet, le rectangle devrait fuir l'écran vers la droite.

Petit problème, le rectangle se déplace à un pixel par trame, mais le nombre de trames par seconde varie d'un ordinateur à un autre, et aussi peut baisser considérablement lorsque beaucoup de choses se passent à l'écran, la vitesse du rectangle n'est donc pas du tout prévisible.

C'est à ça que sert le ```dt``` dans ```love.update(dt)```. La valeur de ```dt``` est le temps, en secondes, depuis la dernière trame.

On avait dit qu'on voulait que notre rectangle se déplace à cent pixels par seconde, donc faisons:
```lua
function love.update(dt)
    pos_x = pos_x + (100 * dt)
end
```
(La multiplication est prioritaire, mais je mets souvent des parenthèses pour clarifier la lecture.)

Maintenant le rectangle devrait se déplacer à vitesse continue, quels que soient les conditions, à raison de 100 pixels par seconde.

Et c'est tout pour aujourd'hui, faites une pause et prenez un petit goûter, vous l'avez mérité!
