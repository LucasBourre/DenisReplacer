# DenisReplacer

## Bien commencer votre TP.

<img src="https://upload.wikimedia.org/wikipedia/en/thumb/6/6c/Troymcclure.png/200px-Troymcclure.png" width="100" height="200">

Bonjour, je suis Troy McClure. 
Vous m'avez sûrement déjà vu dans des films tels que 'Alerte dans la baie des cochons' ,' A la recherche d'un taco nommé Juanita','Le retour du jeudi' ..  :sunglasses:
<br />
<br />
Aujourd'hui, nous allons apprendre à développer des extensions pour votre navigateur Chrome.
L'objectif de ce TP est d'injecter du Javascript dans votre code afin de modifier les images affichées sur vos pages webs.
Nous allons donc créer une extension qui remplace toutes les images de votre navigateur par notre héros national, Denis Brogniart ! <img src="https://img8.androidappsapk.co/300/4/b/4/denis.brogniart.ah.png" width="20" height="20">


Pour ce TP, vous aurez besoin de connaitre les bases de Javascript.

## Etape 1 : Remplir votre Manifest

Nous allons commencer par remplir notre fichier [Manifest.JSON](https://developer.chrome.com/extensions/manifest), qui est le fichier phare de notre application.
Ce fichier permettra d'indiquer à notre navigateur les informations importantes, ainsi que les scripts à éxecuter lorsque nous solliciterons l'extension. <br /> <br />

Ici, les champs intéressants sont les suivants :<br />
  *name, version, description, icons, browser_action, permissions, background, manifest_version* <br />
Attention ! la manifest_version est obligatoirement **2** : 
La version 1 devient obsolète et ne sera plus supporté par le futur.<br /> Je vous invite à cliquer [ici](https://developer.chrome.com/extensions/manifest/manifest_version)  pour plus d'informations : <br />
  
Remplissez donc vos champs, n'hésitez pas à nous demander en cas de problème  :thumbsup:

## Etape 2 : Installer le plugin sur le navigateur

Afin de pouvoir tester votre plugin, veuillez passer votre navigateur Chrome en mode Developpeur. <br />
Rendez-vous sur chrome://extensions/ , puis chargez votre dossier non empaquetté. <br /> <br />
C'est fait ? Bien ! :+1: <br /> Si aucune erreur n'est déclarée et qu'une icône d'extension est présente à coté de votre navigateur, votre Manifest.JSON est bien configuré. <br />
Lorsque vous voulez tester votre code dans les fichiers background.js et denisReplacer.js , retournez sur votre page d'extension et actualisez-la . <br />
Vous êtes prêt à écrire quelques lignes de code ? Passez à l'étape 3 !  :laughing:

## Etape 3 : Ecrire le code

2 fichiers sont à compléter. <br /><br />
### background.js<br />
 Nous  souhaitons que le background lance le script "denisReplacer.js" lorsque l'on clique sur le navigateur.<br />
On va donc ajouter un listener qui executera le script du fichier "denisReplacer.js" . <br />
Faites le nécessaire pour ajouter l'évènement dans le fichier.<br />
Indice :point_right: [event-onClicked](https://developer.chrome.com/extensions/browserAction#event-onClicked)
<br />
C'est fini ! Pas besoin d'aller plus loin pour ce fichier. Le script que nous souhaitons executer sera dans le fichier suivant.
<br />
<br />
### denisReplacer.js <br />
Vous pouvez voir que des variables sont déjà implémentées dans le fichier. Nous avons préféré vous donner celles-ci afin que vous ne perdiez pas de temps à aller chercher les différentes photos de Denis. <br />
Si vous souhaitez en ajouter, ou même mettre d'autres images à la place, n'hesitez pas ! <br/>
 Il reste 3 fonctions à écrire dans ce document. <br />
 - function Denis(imageurl) : Cette fonction va assigner à un "Denis" une url. <br/>
 - function Randomize(numberDenis) : Cette fonction va retourner un nombre entier aléatoire entre 0 et le nombre de denis. Elle servira à prendre une image parmis les différentes images de la variable "myDenis". <br/>
  - (function (document) { ... })(document)  : C'est ce script qui sera lancé lorsque vous cliquerez sur l'icône.
    Commencez par récupérer dans une variable "images" toutes les images du site (utilisez "getElementsByTagName" ). récupérez également le nombre d'images dans une variable "length" . <br />
    Bouclez ensuite sur le nombre d'images du document : <br />
    Prenez un nombre aléatoire, l'image [aleatoire] de la variable myDenis, et remplacez la source de l'image actuelle par l'url de myDenis choisi aléatoirement.
    

## Etape 4 : Testez !
Rendez-vous sur Google Images pour tester votre extension.<br />
Actualisez votre application dans chrome://extension , puis cliquez sur l'icone pour voir si les images de votre navigateur changent. <br />
Ca ne marche pas ? Tant pis ! Persévérez :trollface:

## Etape 5 ( bonus ) 
Votre plugin marche en cliquant. Nous pouvons faire en sorte que ça marche sans cliquer sur l'extension, que les images se changent à chaque fois qu'une image apparait. <br />
Modifier votre code pour que ce changement s'opère.
<br /><br />
(Indice : Il ne faut modifier que le _manifest.JSON_ . Plus besoin du bloc Background, ni du fichier background.js d'ailleurs ! 
Essayez de vous renseigner sur le bloc "content_scripts" ).
<br /> <br />
Vous pouvez également ajouter un son qui sera joué au  clic sur votre extension ( Par exemple, [celui-ci](https://www.cjoint.com/doc/17_04/GDBo22CpPLB_Denis-Brogniart-AH.mp3) )
