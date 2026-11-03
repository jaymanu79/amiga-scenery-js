# Scene Generator JS

Réimplémentation en JavaScript du moteur de **Scene Generator V2.11** (Brett Casebolt, Natural Graphics, 1990), un générateur de paysages fractals pour Amiga. Suite commerciale du domaine public *Scenery* (Fish Disk 155, 1988).

**Démo : https://jaymanu79.github.io/amiga-scenery-js/**

## Ce qui est reproduit

Les quatre niveaux de détail du menu Project (Preview, Med, Hi, X Hi), en NTSC et en PAL, sont **identiques au pixel près** au programme d'origine. Ils ont été vérifiés sur les six scènes d'exemple fournies avec le logiciel, par comparaison avec le code 68000 d'origine exécuté dans un émulateur :

- générateur aléatoire 16 bits, relief par déplacement du point milieu, lissages ;
- placement automatique de la caméra, projection en arithmétique entière du 68000 ;
- table d'éclairage, choix des matériaux (neige, verdure, roche grise, terre brune), plages ;
- nuages fractals, dégradé tramé du ciel, texture de l'eau ;
- y compris un bug d'origine : la table de largeur des plages est lue hors de ses limites.

## En plus de l'original

- réglages en direct (curseurs, cases, positions du menu Lighting, palette éditable, tooltypes en texte) ;
- rendu plein écran à la résolution native, avec des niveaux de détail supplémentaires calculés automatiquement ;
- export PNG indexé, et export Amiga (image IFF ILBM et icône `.info` avec les tooltypes, à ouvrir dans Scene Generator) ;
- explorateur des 65 536 graines possibles, avec des critères de choix.
- mode **Hicolor** (hors original) : sans tramage, avec 15 niveaux de lumière au lieu de 8, un dégradé de ciel continu et des nuages doux, toujours à partir de la palette de 32 couleurs.

## Texture de l'eau

L'option « Add texture » utilise une image de vaguelettes (384×180, 2 plans de bits) stockée dans l'exécutable. Elle n'est pas incluse ici : sans elle, la page dessine une mer procédurale de remplacement (reflets fins à l'horizon, vaguelettes plus grandes au premier plan), d'aspect proche mais différente.

La même texture, à l'octet près, se trouve dans la démo librement diffusée de Scene Generator (`SceneGenDemo`, Fred Fish disk 299, disponible sur Aminet). Pour un rendu exact, on peut charger dans la page le fichier `water_tex.bin` (17 280 octets) extrait de son propre exemplaire, version complète ou démo.

## Avertissement

Projet personnel de rétro-ingénierie à des fins de préservation et d'interopérabilité, sans lien avec Natural Graphics. Aucune image, aucun binaire ni aucune donnée graphique du logiciel d'origine ne sont distribués ici. Le moteur est un code JavaScript écrit de zéro à partir de l'analyse de l'algorithme.
