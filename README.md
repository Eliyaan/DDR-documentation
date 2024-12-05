# DIY Dance Dance Revolution inspired game

Si vous avez des suggestions, des idées, des questions, des corrections, ouvrez un ticket (issue) ou envoyez nous un mail ! 
Plus on s'entraire plus les DDR fabriqués seront biens !

## Logiciel du jeu

Pour pouvoir jouer à un jeu de DDR, il faut un logiciel qui sert de jeu. Celui que j'ai utilisé est [itgmania](https://www.itgmania.com/) mais [stepmania](https://www.stepmania.com/) devrait marcher aussi. Installez celui de votre choix et lancez une partie pour tester si ca fonctionne correctement (en jouant avec les fleches directionnelles du clavier).

// Screen shot de ITG Mania

## USB arcade encoder

Le composant le plus important est celui qui va faire communiquer le pad (ce sur quoi on va marcher) avec l'ordinateur pour qu'il puisse lui dire sur quelle fleche on appuie.
Les deux options les plus faciles sont : 
- un [USB arcade encoder](https://www.ebay.com/itm/133163133451?itmprp=cksum%3A133163133451e007b8d0f3d14994b8030d134ee26497%7Cenc%3AAQAJAAABYMSBbt5JfLmj%252BdlAgetRxKsk9uNZiEHlB3hfttt0hmv1%252BpJoUCdSpe1JVf49yGC5tKtQ3g6HKD95AS2%252Bj%252BzdEev%252BQFVLBEv0%252FCdcgJMGFwLFhJ53WzLi3lqhEgvTYlFP2n6dii0kr%252BCTa3CZ07LoBuz1bIWF0E36UoD6Bg5wn9NHEbrtr8LCCZo7D2G7QFE2tU%252BgmskmJjQcEt38U8n3vZsRhwFqvi0NvXASBtDk8gMZQb%252FFHv2RJref%252FQNDsgRmSpZyfIAhV91ozNZLIXKqzGcR3PxoKrmLGvfoRSCLVMdXhwf4sEn2%252BBliRxkdirfad2y3d5IEWpKMLk3jcst7a8AoqvCRMio0Pu36K2YGqBcKHCFru45UG31HTXr6Y%252BBge0rzwG0aOGLbCa4xCdcnzYUNXazCn4xWNNnpeBtGUwyIvbTjh9hYmUsJvVwIpulV3MTIYWKsHE1bTtU0GPHcWFk%253D%7Campid%3APL_CLK%7Cclp%3A2332490&itmmeta=01HV44EGGQ89AKT6VV3G4BBDRD), une carte qui est détectée comme une manette donc c'est très facile à gérer. (l'option avec les cables est pratique car on peut juste enlever et ajouter des joueurs en débranchant les cables associés facilement)
- un vieux circuit électronique de clavier (mais je n'ai pas testé)

///// Image du USB arcade encoder

// Explication du USB arcade encoder (ports pour les boutons) + photo

L'USB arcade encoder se branche avec le cable USB sur le PC directement. Normalement il sera correctement détecté (automatiquement).
Pour tester si il fonctionne correctement, lancez le logiciel choisi, allez dans les paramètres dans l'endroit pour tester les touches détectées et faites se joindre deux bouts d'un fil d'un même bouton.

// screenshot de l'endroit pour tester les touches

# Pad

Le but du pad est de détecter sur quelles flèches l'utilisateur appuie et transmettre cette info à l'USB arcade encoder.
L'usb arcade encoder détecte ses entrées/boutons "flèches directionnelles" soit en "touche appuyée" soit en "touche lachée".
Ces deux états correspondent à se le courant électrique passe entre les deux fils de l'entrée/bouton ou pas.
Notre but est donc qu'avec chacune des flèches de notre DDR on fasse passer le courant électrique quand le joueur a le pieds dessus et pas sinon.
C'est le même principe qu'un bouton normal. On voudrait aussi qu'il y ait un minimum de latence entre le moment où le joueur pose son pied sur la flèche et le moment où le bouton est détecté comme appuyé (quand le courant passe).

La solution que l'on a trouvé était de séparer la plaque en deux partie conductrices connectées chacun à un des fils et de mettre un matériau conducteur sous le pied du joueur pour qu'il connecte les deux parties conductrices de la plaque quand il met le pied dessus.
Pour qu'il puisse appuyer à un maximum d'endroit sur la plaque, la séparation des deux parties conductrices est en forme de créneaux pour que peu importe la position du pied, il y ai les deux parties sous son pied.

// image de la plaque

Le matériau conducteur que l'on avait choisi est de l'aluminium de cuisine collé au vernis-colle sur une plaque de bois agloméré. Attention une seule des faces des l'aluminium de cuisine est conductrice ! On a renforcé les bords de l'aluminum en collant du scotch dessus pour éviter qu'il s'arrache/se décolle par les bords. 
Mais à force d'utilisation intensive l'aluminium risque de s'effritter. Nous n'avons pas encore de solution plus efficace pour ce problème. 
Une solution potentielle serait de mettre de l'aluminium plus épais mais le découper serait bien plus dur et le budjet serait plus important aussi.

Pour relier le fil de l'USB encoder à la plaque, on avait soudé le fil sur du scotch cuivre puis scotché la partie conductrice du scotch cuivre sur l'aluminium.
Car l'aluminium n'adhère pas aux soudure. Cette solution était plutot simple et fonctionnelle.
Ses défauts sont de devoir acheter du scotch cuivre et que le scotch cuivre se déchire.
Au Nantes Maker Campus 2024, les gens se prennaient les pieds dans les fils donc il est arrivé que le scotch se déchire.

La solution que l'on avait choisi pour le matériau conducteur sous le pied du joueur était de faire une bande de carton accrochable à un pied avec de la tresse à déssouder enroulée dessus.
La solution était pratique pour pouvoir s'adapter à différentes tailles de pieds (ce qui a très bien marché au Nantes Maker Campus 2024).
Mais après trois jours de DDR intenses la tresse a commencé à se rompre car elle est peu adaptée à un piétinage intensif.
Donc ce problème est toujours actuel et la faille principale de ce design actuellement.


