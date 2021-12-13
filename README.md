<!DOCTYPE html>
<html>
  <head>
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">
    <title>README</title>
  </head>
  <body>
    <h1 dir="auto">Comment flasher les Artillery SideWinder X2 &amp;Genius Pro.
      Firmware Marlin 2.0.9.2 Mr.Magoo avec nouvelles fonctions et ajustement /
      How to Flash Artillery 32bits SideWinder X2 &amp; Genius Pro. Marlin
      Firmware with new features.</h1>
    &nbsp;&nbsp;
    <p></p>
    <h1 dir="auto">French Version / English Down of this page</h1>
    <p></p>
    <br>
    <table style="width: 1000px;" border="0">
      <tbody>
        <tr>
          <td>Si vous souhaitez me payer un café ou me soutenir : <a href="https://www.paypal.com/paypalme/MrMagounet"
              target="_blank"> Paypalme/MrMagounet<br>
            </a>
            <p><a target="_blank" rel="noopener noreferrer"><img src="https://www.lesimprimantes3d.fr/forum/uploads/monthly_2021_02/logo.png.7b007150fa09975916925b46c74c4133.png"
                  style="max-width: 100%;" width="175" align="right"></a></p>
            <p dir="auto">Cela me permettra de continué à aider la communauté.</p>
            <p dir="auto"><span style="color: #333399;"><span style="color: #330033;">Liens
                  vers le topic original : <a href="https://www.lesimprimantes3d.fr/forum/topic/44697-tuto-comment-flasher-le-firmware-des-x2-genius-pro-hornet/">lesimprimantes3d.fr</a><br>
                </span></span></p>
            <p dir="auto"><span style="color: #333399;"><span style="color: #330033;">Vidéo
                  Youtube sur ce Tuto avec Flash Artillery X2 : <a href="https://www.youtube.com/watch?v=SnRNQQoOKaw&amp;t=99s">3DK
                    Maker</a></span></span></p>
          </td>
        </tr>
      </tbody>
    </table>
    <br>
    <h2 dir="auto"><a id="user-content-marlin-20" class="anchor" href="#marlin-20"><svg
          class="octicon octicon-link" viewBox="0 0 16 16" width="16" height="16"></svg></a><u>Comment
        Flasher la carte mère Artillery Ruby</u></h2>
    <p dir="auto">Pour pouvoir activé de nouvelle fonction sur les nouvelle
      imprimante 32bits Artillery, il sera nécessaire d'effectuer un Flash d'un
      nouveau Firmware Marlin avec les fonctions souhaité activé sur la carte
      Ruby.</p>
    <p dir="auto">J'ai réaliser un petit Tutoriel au format PDF expliquant en
      détail comment réussir à Flasher votre imprimante 3D Artillery équipé de
      la Carte Mère Ruby.</p>
    <p dir="auto">-------------------------------------------------------------------------</p>
    <p dir="auto"><span style="box-sizing: border-box; color: rgb(231, 76, 60);">
        <b>je tiens à rappeler qu'il y a toujours un risque potentiel de bloquer
          votre carte mère, si un coupure de courant ou une erreur de
          manipulation est éffectué.</b></span></p>
    <b> </b>
    <p dir="auto"><b><span style="box-sizing: border-box; color: rgb(231, 76, 60);">Je
          ne peux être tenu responsable de tous dommage occasionné, même
          si&nbsp; il y a peu de risque.</span></b></p>
    <p dir="auto">-------------------------------------------------------------------------</p>
    <p dir="auto">Il sera nécessaire d'utilise un soft de chez STM
      (programmateur), et un soft de contrôle pour imprimante 3D comme Repetier
      Host ou Pronterface par exemple.&nbsp;&nbsp;</p>
    <p dir="auto">Je vous laisse prendre connaissance du tutoriel : <a href="https://github.com/MrMagounet/Frimware_Flash-Artillery_X2_GeniusPro/blob/main/TUTO-PDF_Comment_Flasher_son_Artillery-Ruby.pdf">Tuto
        PDF</a></p>
    <p dir="auto"></p>
    <p><br>
    </p>
    <p> </p>
    <h2 dir="auto"><a id="user-content-example-configurations" class="anchor" href="#example-configurations"><svg
          class="octicon octicon-link" viewBox="0 0 16 16" width="16" height="16"></svg></a><u>Marlin
        2.0.9.2 MrMagoo Fonctions et améliorations </u></h2>
    <p dir="auto"><u>Voici la liste des optimisations et ajouts :</u></p>
    <ul>
      <p dir="auto"> </p>
      <li>Passage à <b>Marlin 2.0.9.2</b> (Après mise à jour le mode <b>DFU </b>devrait
        pouvoir être activé sans ouvrir l'imprimante, si vous aviez une X2 qui
        le nécessitait)</li>
      <li>Passage des baudrate en <b>250000 </b>au lieu de <b> 115200</b>.</li>
      <li>Ajustements des valeurs sur la sécurité et la prévention d'incidents
        thermiques.</li>
      <li>Ajustements des Feedrates (X / Y / Z / E) de la X2.</li>
      <li>Ajustements des accélérations (principalement l'accélération de
        rétraction qui était excessive).</li>
      <li>Remplacement des fonctions "<b>Junction Deviation</b>" &amp; "<b>S-Curve</b>"
        par le "<b>Classic Jerk</b>" (les Jonction Déviation et S-Curve sont
        encore capricieuse sous Marlin pour le moment).</li>
      <li>Ajustement Feedrate du Z-Prob pour une plus grande efficacité du
        relevé de mesure du 3DTouch (Probing Fans Off).</li>
      <li>Activation de la fonction <b>M48 </b>(Test de répétabilité du
        capteur de nivellement automatique).</li>
      <li>Activation de la fonction "<b>Restore Leveling After G28</b>" (dès que
        un G28 est effectué les valeurs du dernier relevé sous automatiquement
        rechargé), plus besoin de G29 ou M420 S1 après le G28 dans le start
        Gcode 😉.</li>
      <li>Activation de la fonction <b>G26 </b>Mesh Validation.</li>
      <li><b>ABL </b>Relevé de Mesure en <b>49 </b>points au lieux de <b>25
        </b>points (c'est qu'un avis perso mais cela apporte plus de précision
        sur le relevé et donc sur la première couche).</li>
      <li>Activation du "<b>Nozzle Park Feature</b>" et "<b>Advanced Pause
          Feature</b>" (support M600 et parcage automatique de la tête en
        pause).</li>
      <li>Activation de la fonction "<b>Adaptative Step Smoothing</b>"
        (Augmentation de la résolution des mouvements multi axe, surtout a
        certaine fréquence de fonctionnement des moteurs).<br>
      </li>
      <li>Prise en compte du <b>BabyStepping</b> tout le temps et pas
        uniquement en cours de mouvement.</li>
      <li>Activation du "<b>Linear Advance</b>" avec valeur "K à 0" (ce qui vous
        permet de le laisser inactif a 0 ou d'effectué un test de calibration
        Linear Advance et d'ajuster sa valeur), le Linear Advance permet de
        garder un flux de matière constant sortant de la buse lors des
        accélérations et décélérations. Vidéo explication du Linear Advance
        &amp; Outils de génération du Gcode de calibration pour Linear Advance.</li>
      <li>Ajustement de la fonction "<b>ARC Welder</b>" avec une résolution bien
        plus importante.</li>
      <li>Activation de la fonction <b>M486 </b>pour les utilisateur de
        PrusaSlicer &amp; SuperSlicer (object cancelation)</li>
      <p></p>
    </ul>
    <h2 dir="auto"><a id="user-content-building-marlin-20" class="anchor" href="#building-marlin-20"><svg
          class="octicon octicon-link" viewBox="0 0 16 16" width="16" height="16"></svg></a><u>Firmware
        TFT pour le MKS TFT28</u></h2>
    <p dir="auto">Je proposerais des firmware TFT pré-configuré, mais<b>
        attention les portages de Firmware TFT issue du portage BTT (comme ceux
        de Digant &amp; Molise) ont des Bug de messages d'erreur M21 et de pause
        aléatoire M1 </b>depuis les versions Patch 6 &amp; Patch 7. <b><br>
      </b></p>
    <p dir="auto"><b><br>
      </b></p>
    <p></p>
  </body>
</html>
