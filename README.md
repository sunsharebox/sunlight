# une ampoule connectée de couleur pour la boxenergie

## objectifs
On souhaite montrer avec la boxenergie la consommation d'une maison avec une lampe qui change de couleur.
On veut donc piloter une ampoule de couleur avec un raspberry pi et nodered.

## matériel
L'ampoule vient de conforama, de marque beewii (devenu OTIO)
C'est une ampoule qui se connecte a un smartphone en bluetooth low energy (BLE) avec l'application smartpad

## étapes du projet

### 1- tester la lampe avec un smartphone

### 2- rechercher des tutos pour piloter des ampoules BLE avec raspberry

2b - decoder l'appli beewii smartpad

2c - decoder le bluetooth qui est transmis à la lampe

2d - tutos divers

Pour des ampoules wifi : https://gladysassistant.com/fr/article/controler-des-ampoules-connectees <br>
Pour connexion filaire au GPIO : https://raspberry-pi.developpez.com/cours-tutoriels/projets-ido/cheerlights/


### 3 - portrer le code sous nodered
exemple sur ampoule très proche ici : <br>
https://developer.ibm.com/recipes/tutorials/interact-with-a-connected-awox-bulb-using-vocal-commands/

tuto nodered pour debutants :
http://silanus.fr/sin/?p=984
nodered est proposé dans les applications du raspberry ou en ligne de commande : <br>
```bash <(curl -sL https://raw.githubusercontent.com/node-red/linux-installers/master/deb/update-nodejs-and-nodered)```


## inspirations
https://github.com/delkk0/BeewiPy et https://github.com/Leiaz/python-awox-mesh-light <br>
http://domo-attitude.fr/tuto-lampe-de-chevet-yeelight-bluetooth-domoticz/ <br>
Elle ressemble aussi beaucoup aux ampoules AWOX https://www.awox.com/awox_product/smartlight-mesh-w9w/

https://github.com/jimmckeeth/BeeMiniCtrl.git <br><br>

<img src="http://www.bee-wi.com/wp-content/uploads/2016/09/BLR11.png" width="250"/> <img src="http://www.bee-wi.com/wp-content/uploads/2017/06/BLH04-U1E.png" width="250"/> <img src="http://actu-smartphones.com/wp-content/uploads/2015/02/boite.jpg" width="180"/> <br>
<img src=https://i.pinimg.com/236x/c1/d5/04/c1d504a513c66ceb0d76fcadc991d631.jpg width="160"/>  <img src=https://mir-s3-cdn-cf.behance.net/project_modules/disp/0bb82849055337.56084b140b852.jpg width="300" /><br>

## license

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />

licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.

Raspberry Pi is a trademark of the Raspberry Pi Foundation

## Questions - problemes soulevés
Récupérer l'adresse MAC de l'ampoule sur le raspberry ?
Appli en python BeewiPy a transferer sous nodered ?


## Tentative en python

Sur la base d'un tuto en anglais qui controle ces lampe avec python.

<code>

sudo apt-get install python3-pip libglib2.0-dev

sudo pip install bluepy

sudo <b>-H</b> pip install pexpect

</code>

recopier le code sur cette page et suivre ce post : https://www.raspberrypi.org/forums/viewtopic.php?t=117729#p1446633

recopier le code MAC visible sur l'appli smartphone en déconnectant la lampe
Lancer la commande :
<code>sudo python beewibulb.py 92:A6:76:XX:XX:XX status</code>
