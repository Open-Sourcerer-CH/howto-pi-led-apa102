# Tutoriel pour faire fonctionner un bandeau LED RGBW de type *APA102* avec un *Raspberry Pi* !
Ce tutoriel décrit la marche à suivre pour faire fonctionner un bandeau LED RGBW de type *APA102* avec un *Raspberry Pi* !

# Prérequis
Pour pouvoir suivre ce tutoriel, il te faudra rassembler les éléments suivants,
* 1x *Raspberry Pi* 2/3/4 ou *Raspberry Pi* Zero
* 1x *APA102* Bandeau LED RGBW // (30/60/144 LEDs/mètre)
* 1x *RS-50-5* Transformateur 230[VAC]/12[VDC] de la marque *MEAN WELL*
* 1x petit matériel fils, bornes, etc
* 1x outillage usuel pince coupante, tournevis, etc

# Avant de commencer
Pour être sûr et certain de commencer sur de bonnes bases, il est conseillé de suivre le [tutoriel de mise en marche du *Raspberry Pi*](howto-pi).

Une fois les étapes de ce tutoriel exécutées, tu peux passer à l'étape suivante.

# RASPBERRY PI

`sudo apt-get update`

`sudo apt-get upgrade`

`sudo apt-get install python3 python3-dev python3-pip`

`sudo pip3 install apa102-pi`

# RACCORDEMENTS

PIN_ID | PIN_PHYSIQUE | FIL (PI) | => | FIL (LED)
----|--------------|----------|---|------------
GND | 06 | Noir | => | Jaune
10 | 19 | Bleu | => | Vert
11 | 23 | Jaune | => | Bleu

[Schéma de raccordement](img/schema_raccordement.jpg) ***Ajouter l'image***

# Test de fonctionner
Afin de tester le bon fonctionnement de l'installation, tu vas devoir créer un petit script python :snake: !

Ne soit pas effrayé. Tu veras c'est trop simple et facile a comprendre.

Si tu es prêt tu peux ouvrir ton éditeur de texte et créer le fichier *rgbcalibrate* avec la commande suivante,

`nano ~/rgbcalibrate.python3`

Pour ta faciliter la vie, nous avons écrit ce script pour toi.

Si tu es flemmard aujourd'hui tu peux simplement le copier. Pour ce faire depuis un *terminal* entre la commande suivante,

Se rendre dans le dossier /home de l'utilisateur pi.
`cd ~/`

Télécharger le fichier example.
`git clone https://github.com/Open-Sourcerer-CH/howto-pi-led-apa102/example/rgbcalibrate.py` //Indiquer la commande

Bien maintenant le copier c'est bien mais comprendre ce qu'il y a dedans c'est mieux.

Un apprenti sorcier digne de ce nom s'empressera d'aller jeter un oeil sur le contenue du fichier example qui se trouve [ici](howto-pi-led-apa102/example/rgbcalibrate).

Une fois que tu as fini tu peux quitter l'éditeur de texte avec ctrl+x, sauvegarder en appuyant sur o puis valider en appuyant sur enter.

Tu peux maintenant exécuter le script en utilisant la commande suivante,

`python3 ~/rgbcalibrate.py`

Si tout ce passe bien, le bandeau LED devrait s'allumer avec les paramètre que tu as choisi.

Par défaut 50 pixels dont les 10 premiers en rouge et le reste éteint. Ensuite, après 5 secondes le tout s'éteint.
