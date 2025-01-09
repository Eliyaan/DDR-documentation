# DIY Dance Dance Revolution (inspired) pad !


Let's make our own DDRs!
If you have any suggestions, ideas, questions or corrections, open an issue or send us an e-mail. The more we help each other, the better the DDRs we'll make!

And don't hesitate to send us photos of your finished DDR, so that we can add it to the documentation for different flavors of DDR and encourage new people to make their own!

Photos of finished DDRs: 

- The first working version of the DDR at the Nantes Maker Campus in the middle of all the junk. It works really well for our beginner level (no latency).

![image](https://github.com/user-attachments/assets/d993d4aa-2651-4f5b-9c55-d98638f8bf16)

<details> <summary>English</summary>
## Game software

To be able to play a DDR game, you need software that serves as the game. The one I used is [itgmania](https://www.itgmania.com/) but [stepmania](https://www.stepmania.com/) should work too. Install the one of your choice and run a game to see if it works properly (by playing with the keyboard's directional arrows).

![image](https://github.com/user-attachments/assets/769ceec6-9dec-42e0-90fe-56b5d476b1ff)

## USB arcade encoder

The most important component is the one that will make the pad (what you're going to step on) communicate with the computer so that it can tell it which arrow to press.
The two easiest options are : 
- a [USB arcade encoder]([https://www.ebay.com/itm/133163133451?itmprp=ck](https://www.ebay.com/itm/133163133451?itmprp=cksum%3A133163133451e007b8d0f3d14994b8030d134ee26497%7Cenc%3AAQAJAAABYMSBbt5JfLmj%252BdlAgetRxKsk9uNZiEHlB3hfttt0hmv1%252BpJoUCdSpe1JVf49yGC5tKtQ3g6HKD95AS2%252Bj%252BzdEev%252BQFVLBEv0%252FCdcgJMGFwLFhJ53WzLi3lqhEgvTYlFP2n6dii0kr%252BCTa3CZ07LoBuz1bIWF0E36UoD6Bg5wn9NHEbrtr8LCCZo7D2G7QFE2tU%252BgmskmJjQcEt38U8n3vZsRhwFqvi0NvXASBtDk8gMZQb%252FFHv2RJref%252FQNDsgRmSpZyfIAhV91ozNZLIXKqzGcR3PxoKrmLGvfoRSCLVMdXhwf4sEn2%252BBliRxkdirfad2y3d5IEWpKMLk3jcst7a8AoqvCRMio0Pu36K2YGqBcKHCFru45UG31HTXr6Y%252BBge0rzwG0aOGLbCa4xCdcnzYUNXazCn4xWNNnpeBtGUwyIvbTjh9hYmUsJvVwIpulV3MTIYWKsHE1bTtU0GPHcWFk%253D%7Campid%3APL_CLK%7Cclp%3A2332490&itmmeta=01HV44EGGQ89AKT6VV3G4BBDRD)), it's a card that's detected as a controller, so it's very easy to use. (the cable option is handy because you can just remove and add players by unplugging the associated cables easily)
- an old keyboard circuit (but we didn't test it)
- an Arduino (but more expensive and we didn't do it)
- a Makey Makey (more expensive and we didn't do it either)
![image](https://github.com/user-attachments/assets/418a8db9-dc3a-419f-a7c2-1c7f5b034cee)
![0](https://github.com/user-attachments/assets/121c5a22-0077-43fb-af21-6da257c28ca6)

The ports on the bottom of the board are easily detected by the software, so there are enough ports for two players! (The software supports both two-pad and two-player game modes).

The USB arcade encoder is plugged directly into the PC via the USB cable. Normally, it will be correctly detected (automatically).
To test whether it's working correctly, launch the software you've chosen, go to the settings in the area for testing detected keys and make two ends of a wire from the same button join together.
It will either display one of the arrows, or it will put text `"key name" (not mapped)`, in which case you'll have to go to the menu to add new keys (it's better to change unmapped keys to avoid getting stuck).
When you change something in the game parameters, exit the parameters using the menu buttons (exit or save and exit), as escape will not save your changes.

![image](https://github.com/user-attachments/assets/6cfe0f48-c5de-4ed0-87d9-98e003e9546c)
![image](https://github.com/user-attachments/assets/1cae8f71-b3ce-4bc9-b902-740c40c8a82d)
![image](https://github.com/user-attachments/assets/6950f926-b35d-4f01-9f01-d6247a45fac9)

# Pad

The purpose of the pad is to detect which arrows the user presses and transmit this information to the USB arcade encoder.
The usb arcade encoder detects its "directional arrow" inputs/buttons as either "key pressed" or "key released".
These two states correspond to whether or not electrical current is flowing between the two input/button wires.
Our aim is therefore to use each of the arrows on our DDR to make the electric current flow when the player has his foot on it, and not otherwise.
It's the same principle as a normal button. We'd also like there to be a minimum latency between the moment the player places his foot on the arrow and the moment the button is detected as being pressed (when the current flows).

The solution we came up with was to separate the plate into two conductive parts, each connected to one of the wires, and to put a conductive material under the player's foot so that he connects the two conductive parts of the plate when he puts his foot on it.
To enable him to press down on the plate in as many places as possible, the separation of the two conductive parts is crenellated, so that whatever the position of his foot, he has both parts under his foot.

![image](https://github.com/user-attachments/assets/10996519-3ac3-458b-b5ed-dbb8aa09ce66)
![image](https://github.com/user-attachments/assets/5145885e-146f-4232-adfa-ec0906b482b8)
![image](https://github.com/user-attachments/assets/4c3dd4a7-a7ff-4d32-8739-816a6ef5a67d)


The conductive material we've chosen is kitchen aluminum glued with varnish-glue to a sheet of agglomerated wood (for laser cutting). Note that only one side of the kitchen aluminum is conductive! We've reinforced the edges of the aluminum with adhesive tape to prevent it from peeling off at the edges.
But with intensive use, the aluminum is in danger of crumbling. We don't yet have a more effective solution to this problem.
One potential solution would be to use thicker aluminum, but cutting it would be much harder and the budget would be higher too.

To connect the USB encoder wire to the plate, we soldered the wire to copper tape, then taped the conductive part of the copper tape to the aluminum.
Because aluminum doesn't adhere to solder. This solution was rather simple and functional.
Its drawbacks are that you have to buy copper tape and that the copper tape tears.
At Nantes Maker Campus 2024, people got their feet caught in the wires, so the tape sometimes tore.

The solution we chose for the conductive material under the player's foot was to make a strip of cardboard that could be hooked to a foot with desoldering braid wrapped around it.
The solution was practical in that it could be adapted to different foot sizes (which worked very well at the Nantes Maker Campus 2024).
But after three days of intense DDR the braid started to break, as it's not very well adapted to intensive trampling.
We've replaced it with a wider braid (see photo), but it too will probably break (it did).
So this problem is still with us, and the main flaw in this design at the moment.

Here's the shoe after intensive outdoor use at the Nantes Maker Campus (hence its color):
![0](https://github.com/user-attachments/assets/31332251-a55e-4656-88ec-579c0ba25ddb)

The small cut-outs are oriented towards the player's ankle when the liner is around the foot, so that it adapts better to the shape of the foot and is more comfortable.

## Songs

Song packs can be found on the Internet, for example on (according to reddit): https://www.stepmaniaonline.net/ https://zenius-i-vanisher.com/v5.2/simfiles.php?category=simfiles https://docs.google.com/spreadsheets/d/1F1IURV1UAYiICTLhAOKIJfwUN1iG12ZOufHZuDKiP48/htmlview
The software is rather capricious when it comes to song packs. You have to unzip them into the game's Songs folder and make sure that no song folder is directly in Songs.
They must all be in a pack (a folder), which in turn must be in Songs.

That's it for the DDR, if we've forgotten any info, or you've got any problems, let us know! (open an issue here: https://github.com/Eliyaan/DDR-documentation/issues by clicking on the green button, or send us an e-mail)

Thank you for your interest in our project, and we hope it has inspired you to do your own!
</details>

Faisons nos propres DDRs !
Si vous avez des suggestions, des idées, des questions, des corrections, ouvrez un ticket (issue) ou envoyez nous un mail, plus on s'entraire plus les DDR fabriqués seront biens !

Et hésitez pas à envoyer des photos de votre DDR fini, comme ca on pourra l'ajouter à la documentation pour différentes saveurs de DDR et encourager de nouvelles personnes à faire le leur !

Photos de DDRs finis: 

- La première version fonctionnelle du DDR au Nantes Maker Campus au milieu de tout le bazard. Il marche vraiment bien pour notre niveau débutant (pas de latence).

![image](https://github.com/user-attachments/assets/d993d4aa-2651-4f5b-9c55-d98638f8bf16)

<details> <summary>Français</summary>
## Logiciel du jeu

Pour pouvoir jouer à un jeu de DDR, il faut un logiciel qui sert de jeu. Celui que j'ai utilisé est [itgmania](https://www.itgmania.com/) mais [stepmania](https://www.stepmania.com/) devrait marcher aussi. Installez celui de votre choix et lancez une partie pour tester si ca fonctionne correctement (en jouant avec les fleches directionnelles du clavier).

![image](https://github.com/user-attachments/assets/769ceec6-9dec-42e0-90fe-56b5d476b1ff)

## USB arcade encoder

Le composant le plus important est celui qui va faire communiquer le pad (ce sur quoi on va marcher) avec l'ordinateur pour qu'il puisse lui dire sur quelle fleche on appuie.
Les deux options les plus faciles sont : 
- un [USB arcade encoder](https://www.ebay.com/itm/133163133451?itmprp=cksum%3A133163133451e007b8d0f3d14994b8030d134ee26497%7Cenc%3AAQAJAAABYMSBbt5JfLmj%252BdlAgetRxKsk9uNZiEHlB3hfttt0hmv1%252BpJoUCdSpe1JVf49yGC5tKtQ3g6HKD95AS2%252Bj%252BzdEev%252BQFVLBEv0%252FCdcgJMGFwLFhJ53WzLi3lqhEgvTYlFP2n6dii0kr%252BCTa3CZ07LoBuz1bIWF0E36UoD6Bg5wn9NHEbrtr8LCCZo7D2G7QFE2tU%252BgmskmJjQcEt38U8n3vZsRhwFqvi0NvXASBtDk8gMZQb%252FFHv2RJref%252FQNDsgRmSpZyfIAhV91ozNZLIXKqzGcR3PxoKrmLGvfoRSCLVMdXhwf4sEn2%252BBliRxkdirfad2y3d5IEWpKMLk3jcst7a8AoqvCRMio0Pu36K2YGqBcKHCFru45UG31HTXr6Y%252BBge0rzwG0aOGLbCa4xCdcnzYUNXazCn4xWNNnpeBtGUwyIvbTjh9hYmUsJvVwIpulV3MTIYWKsHE1bTtU0GPHcWFk%253D%7Campid%3APL_CLK%7Cclp%3A2332490&itmmeta=01HV44EGGQ89AKT6VV3G4BBDRD), une carte qui est détectée comme une manette donc c'est très facile à gérer. (l'option avec les cables est pratique car on peut juste enlever et ajouter des joueurs en débranchant les cables associés facilement)
- un vieux circuit électronique de clavier (mais on n'a pas testé)
- une Arduino (mais plus cher et on ne l'a pas fait)
- un Makey Makey (plus cher et on ne l'a pas fait non plus)

![image](https://github.com/user-attachments/assets/418a8db9-dc3a-419f-a7c2-1c7f5b034cee)
![0](https://github.com/user-attachments/assets/121c5a22-0077-43fb-af21-6da257c28ca6)

Les ports du bas de la carte sont facilement détectés par les logiciels, donc il y a suffisament de ports pour pouvoir jouer à deux ! (les logiciels supportent le jeu à deux pad et le jeu à deux joueurs)

L'USB arcade encoder se branche avec le cable USB sur le PC directement. Normalement il sera correctement détecté (automatiquement).
Pour tester si il fonctionne correctement, lancez le logiciel choisi, allez dans les paramètres dans l'endroit pour tester les touches détectées et faites se joindre deux bouts d'un fil d'un même bouton.
Il affichera soit une des flèches soit il mettra du texte `"nom de la touche" (not mapped)` et dans ce cas là il faudra aller dans le menu pour ajouter des nouvelles touches (il vaut mieux changer les cases vides pour éviter d'être coincé).
Quand vous changez quelque chose dans les parametres du jeu, sortez des parametres avec les boutons des menus (bouton exit ou save and exit) car faire échap ne sauvegardera pas vos changements.

![image](https://github.com/user-attachments/assets/6cfe0f48-c5de-4ed0-87d9-98e003e9546c)
![image](https://github.com/user-attachments/assets/1cae8f71-b3ce-4bc9-b902-740c40c8a82d)
![image](https://github.com/user-attachments/assets/6950f926-b35d-4f01-9f01-d6247a45fac9)

# Pad

Le but du pad est de détecter sur quelles flèches l'utilisateur appuie et transmettre cette info à l'USB arcade encoder.
L'usb arcade encoder détecte ses entrées/boutons "flèches directionnelles" soit en "touche appuyée" soit en "touche lachée".
Ces deux états correspondent à se le courant électrique passe entre les deux fils de l'entrée/bouton ou pas.
Notre but est donc qu'avec chacune des flèches de notre DDR on fasse passer le courant électrique quand le joueur a le pieds dessus et pas sinon.
C'est le même principe qu'un bouton normal. On voudrait aussi qu'il y ait un minimum de latence entre le moment où le joueur pose son pied sur la flèche et le moment où le bouton est détecté comme appuyé (quand le courant passe).

La solution que l'on a trouvé était de séparer la plaque en deux partie conductrices connectées chacun à un des fils et de mettre un matériau conducteur sous le pied du joueur pour qu'il connecte les deux parties conductrices de la plaque quand il met le pied dessus.
Pour qu'il puisse appuyer à un maximum d'endroit sur la plaque, la séparation des deux parties conductrices est en forme de créneaux pour que peu importe la position du pied, il y ai les deux parties sous son pied.

![image](https://github.com/user-attachments/assets/10996519-3ac3-458b-b5ed-dbb8aa09ce66)
![image](https://github.com/user-attachments/assets/5145885e-146f-4232-adfa-ec0906b482b8)
![image](https://github.com/user-attachments/assets/4c3dd4a7-a7ff-4d32-8739-816a6ef5a67d)


Le matériau conducteur que l'on avait choisi est de l'aluminium de cuisine collé au vernis-colle sur une plaque de bois agloméré (pour découpe laser). Attention une seule des faces des l'aluminium de cuisine est conductrice ! On a renforcé les bords de l'aluminum en collant du scotch dessus pour éviter qu'il s'arrache/se décolle par les bords. 
Mais à force d'utilisation intensive l'aluminium risque de s'effritter. Nous n'avons pas encore de solution plus efficace pour ce problème. 
Une solution potentielle serait de mettre de l'aluminium plus épais mais le découper serait bien plus dur et le budjet serait plus important aussi.

Pour relier le fil de l'USB encoder à la plaque, on avait soudé le fil sur du scotch cuivre puis scotché la partie conductrice du scotch cuivre sur l'aluminium.
Car l'aluminium n'adhère pas aux soudure. Cette solution était plutot simple et fonctionnelle.
Ses défauts sont de devoir acheter du scotch cuivre et que le scotch cuivre se déchire.
Au Nantes Maker Campus 2024, les gens se prennaient les pieds dans les fils donc il est arrivé que le scotch se déchire.

La solution que l'on avait choisi pour le matériau conducteur sous le pied du joueur était de faire une bande de carton accrochable à un pied avec de la tresse à déssouder enroulée dessus.
La solution était pratique pour pouvoir s'adapter à différentes tailles de pieds (ce qui a très bien marché au Nantes Maker Campus 2024).
Mais après trois jours de DDR intenses la tresse a commencé à se rompre car elle est peu adaptée à un piétinage intensif.
On l'a changé par une tresse plus large (voir photo) mais elle va sans doute rompre aussi (elle s'est rompue).
Donc ce problème est toujours actuel et la faille principale de ce design actuellement.

Voici le chausson après l'avoir utilisé intensément en extérieur au Nantes Maker Campus (d'où sa couleur):
![0](https://github.com/user-attachments/assets/31332251-a55e-4656-88ec-579c0ba25ddb)


Les petites découpes sont orientées vers la cheville du joueur quand il a le chausson autour du pied pour qu'il s'adapte mieux à la forme du pied et qu'il soit plus agréable.

## Les chansons

Les packs de chansons se trouvent sur internet, par exemple sur (d'après reddit): https://www.stepmaniaonline.net/ https://zenius-i-vanisher.com/v5.2/simfiles.php?category=simfiles https://docs.google.com/spreadsheets/d/1F1IURV1UAYiICTLhAOKIJfwUN1iG12ZOufHZuDKiP48/htmlview
Les logiciels sont assez capricieux pour les packs de chansons. Il faut les dézipper dans le dossier Songs du jeu et bien veiller à ce qu'aucun dossier de chanson ne soit directement dans Songs.
Il faut qu'ils soient tous dans un pack (un dossier) qui lui doit être dans Songs.

Voilà pour le DDR, si on a oublié des infos, où que vous avez des problèmes dites le nous! (ouvrez un ticket ici: https://github.com/Eliyaan/DDR-documentation/issues en cliquant sur le bouton vert, ou envoyez nous un mail)

Merci pour votre intérêt au projet, en espérant qu'il vous aura inspiré et donné envie de faire le votre !
<details>
