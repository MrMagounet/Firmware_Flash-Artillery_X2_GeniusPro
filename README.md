# Comment flasher les Artillery SideWinder X2 &Genius Pro. Firmware Marlin 2.0.9.2 Mr.Magoo avec nouvelles fonctions et ajustement / How to Flash Artillery 32bits SideWinder X2 & Genius Pro. Marlin Firmware with new features.

## French Version / English Down of this page

Si vous souhaitez me payer un café ou me soutenir : [Paypalme/MrMagounet](https://www.paypal.com/paypalme/MrMagounet) 
Cela me permettra de continué à aider la communauté.

Liens vers le topic original : [lesimprimantes3d.fr](https://www.lesimprimantes3d.fr/forum/topic/44697-tuto-comment-flasher-le-firmware-des-x2-genius-pro-hornet/)

Vidéo Youtube sur ce Tuto avec Flash Artillery X2 : [3DK Maker](https://www.youtube.com/watch?v=SnRNQQoOKaw&t=99s)

## Comment Flasher la carte mère Artillery Ruby
Pour pouvoir activé de nouvelle fonction sur les nouvelle imprimante 32bits Artillery, il sera nécessaire d'effectuer un Flash d'un nouveau Firmware Marlin avec les fonctions souhaité activé sur la carte Ruby.

J'ai réaliser un petit Tutoriel au format PDF expliquant en détail comment réussir à Flasher votre imprimante 3D Artillery équipé de la Carte Mère Ruby.

**-------------------------------------------------------------------------**
**je tiens à rappeler qu'il y a toujours un risque potentiel de bloquer votre carte mère, si un coupure de courant ou une erreur de manipulation est éffectué.**
**Je ne peux être tenu responsable de tous dommage occasionné, même si  il y a peu de risque.**
**-------------------------------------------------------------------------**

Il sera nécessaire d'utilise un soft de chez STM (programmateur), et un soft de contrôle pour imprimante 3D comme Repetier Host ou Pronterface par exemple.  

Je vous laisse prendre connaissance du tutoriel : [Tuto PDF](Firmware_Flash-Artillery_X2_GeniusPro/Compiled Firmware/X2/Marlin 2.0.9.2-Stock)

## Marlin 2.0.9.2 MrMagoo Fonctions et améliorations
Voici la liste des optimisations et ajouts :
- Passage à Marlin 2.0.9.2 (Après mise à jour le mode DFU devrait pouvoir être activé sans ouvrir l'imprimante, si vous aviez une X2 qui le nécessitait)
- Passage des baudrate en 250000 au lieu de 115200.
- Ajustements des valeurs sur la sécurité et la prévention d'incidents thermiques.
- Ajustements des Feedrates (X / Y / Z / E) de la X2.
- Ajustements des accélérations (principalement l'accélération de rétraction qui était excessive).
- Remplacement des fonctions "Junction Deviation" & "S-Curve" par le "Classic Jerk" (les Jonction Déviation et S-Curve sont encore capricieuse sous Marlin pour le moment).
- Ajustement Feedrate du Z-Prob pour une plus grande efficacité du relevé de mesure du 3DTouch (Probing Fans Off).
- Activation de la fonction M48 (Test de répétabilité du capteur de nivellement automatique).
- Activation de la fonction "Restore Leveling After G28" (dès que un G28 est effectué les valeurs du dernier relevé sous automatiquement rechargé), plus besoin de G29 ou M420 S1 après le G28 dans le start Gcode 😉.
- Activation de la fonction G26 Mesh Validation.
- ABL Relevé de Mesure en 49 points au lieux de 25 points (c'est qu'un avis perso mais cela apporte plus de précision sur le relevé et donc sur la première couche).
- Activation du "Nozzle Park Feature" et "Advanced Pause Feature" (support M600 et parcage automatique de la tête en pause).
- Activation de la fonction "Adaptative Step Smoothing" (Augmentation de la résolution des mouvements multi axe, surtout a certaine fréquence de fonctionnement des moteurs).
- Prise en compte du BabyStepping tout le temps et pas uniquement en cours de mouvement.
- Activation du "Linear Advance" avec valeur "K à 0" (ce qui vous permet de le laisser inactif a 0 ou d'effectué un test de calibration Linear Advance et d'ajuster sa valeur), le Linear Advance permet de garder un flux de matière constant sortant de la buse lors des accélérations et décélérations. Vidéo explication du Linear - - Advance & Outils de génération du Gcode de calibration pour Linear Advance.
- Ajustement de la fonction "ARC Welder" avec une résolution bien plus importante.
- Activation de la fonction M486 pour les utilisateur de PrusaSlicer & SuperSlicer (object cancelation)

# Firmware TFT pour le MKS TFT28
Je proposerais des firmware TFT pré-configuré, mais **attention les portages de Firmware TFT issue du portage BTT (comme ceux de Digant & Molise) ont des Bug de messages d'erreur M21 et de pause aléatoire M1** depuis les versions Patch 6 & Patch 7. 
