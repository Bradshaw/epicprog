Variables et instructions
=========================

Ce tutorial utilise le framework Löve/Lua, donc assurez vous d'avoir préparé votre environnement de travail et créez un nouveau projet.

## Etape 1 - afficher un rectangle (WTF!? TROP CLASSE!)

A ce moment du tutorial, votre fichier main.lua devrait ressembler à ceci:
'''lua
    function love.load(arg)
    
    end
    
    function love.update(dt)
    
    end
    
    function love.draw()
    
    end
'''
Ces trois fonctions sont les blocs de base d'un jeu:

love.load(arg) est appellé pendant le chargement du jeu, on y mettra toutes notre phase de préparation du jeu, chargement du contenu, initialisation des niveaux, etc...

love.update(dt) sera appellé à chaque trame du jeu, il connait (grâce au "dt") le temps passé depuis la dernière trame. Nous calculerons ici l'évolution du jeu.

love.draw() sera aussi appellé à chaque trame, juste après love.update(), il contiendra nos fonctions de dessin, c'est ici qu'on affichera tout à l'écran.

Pour tester, dessinons un rectangle.
