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
