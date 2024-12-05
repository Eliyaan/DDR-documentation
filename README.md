# DIY Dance Dance Revolution inspired game

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
L'usb arcade encoder
