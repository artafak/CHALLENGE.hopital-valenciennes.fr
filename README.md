![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/7610fe24-a1ea-4186-a969-e6ad0caed020)

Le challenge **Cyberdream2021** est basé sur un scénario d’actualité, dans lequel le « joueur » devra se mettre dans la peau d’un auditeur travaillant dans une société spécialisée dans la cybersécurité. Celui-ci devra recueillir des informations, et scanner les sites Internet définis pour rechercher les vulnérabilités exploitables à l’aide des outils présentés précédemment.
Dans la seconde phase du scénario, l’exploitation de ces vulnérabilités permet de tester la sécurité du système d’information, et de montrer ses faiblesses.

**hopital-valenciennes.fr** est une simulation d'infrastructure simple inspirée de celle d'un hôpital français. (_dans le cas présent, le site Internet fourni est inspiré de celui de l'hôpital de Valenciennes_).
Fourni dans un cadre purement pédagogique, et réalisé comme support de _lab_ pour des formations, les machines virtuelles permettent d'entraîner les OSINTers et les Pentesters sur plusieurs outils différents, et les oblige à réfléchir à des scénarios d'intrusion.

Ce scénario a été conçu pour suivre les phases classiques d’un audit de sécurité (phase de reconnaissance, exploitation, rapport…), en lien avec la cybersécurité.
Il a été conçu pour être évolutif.
Voici ce qui peut être joué dans sa phase 1 :
-	Reconnaissance (recueil de renseignements)
-	Scan de réseaux, de ports. Identification des ports ouverts et des versions/protocoles utilisés)
-	Exploitation de vulnérabilités Wordpress, gain d’accès sur Wordpress.
-	Analyse de trames réseau et récupération des mots de passe à la volée

Dans sa phase 2, il est également possible de jouer :
-	Gain d’accès via contournement des « htaccess » sur le serveur de fichiers
-	Vulnérabilités sur Debian 9 (non à jour)
-	Stéganographie (recueil d’informations cachées dans des médias)
-	Gain d’accès via SSH et MySQL (bruteforce)
-	…

![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/bd42cb16-f947-4bcd-80e7-b68ede21eadb)

![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/8a3935d3-4ffd-4437-83c6-3471011505d6)



# Scénario (d’un point de vue technique global)

Le principe étant de faire manipuler les participants sur des sites Internet fictifs, de type Wordpress, hébergés dans des machines virtuelles (déconnectées d’Internet).
Il s’agit d’une plate-forme virtuelle composée de 2 machines virtuelles, simulant les sites Internet de l’hôpital de Valenciennes.
Afin d’être au plus près de l’actualité, ces sites représenteront l’hôpital de Valenciennes, ses services et ses contacts - tous fictifs -  s’inspirant de l’attaque cyber récente sur l’hôpital de Dax en février 2021.
Une première machine virtuelle, contenant 3 services WEB (2 sites Internet + base de données) et un serveur de fichier, permettra d’effectuer tout le travail de recueil d’information.
La deuxième machine virtuelle qui simule le principal point d'entrée dans le réseau est un Windows vulnérable à une attaque « EternalBlue ».
Dans un premier temps, les « joueurs » doivent travailler ensemble, de manière collaborative, afin de rechercher tous les renseignements nécessaires à l’analyse de l’environnement technique de « la cible » et chercher les vulnérabilités exploitables.
Dans un deuxième temps, des équipes seront formées dans un scénario « BLUE TEAM » et « RED TEAM ». La RED TEAM devra exploiter les vulnérabilités afin d’éprouver la sécurité de l’infrastructure virtuelle, la BLUE TEAM devra quant-à elle analyser les traces, et suivre en direct les différentes attaques, afin d’éditer un rapport sur les corrections à apporter sur la sécurité.



# Détail des phases du scénario
## La phase Ciblage – Recueil de renseignements

Les participants devront travailler en équipe pour 
-	Recueillir toutes les informations nécessaires à la création d’une « fiche d’identité » de la cible (un mini dossier de ciblage)
-	Scanner le site Internet et la machine virtuelle hébergeant le site, et relever toutes les vulnérabilités détectées.
-	Rechercher sur Internet grâce aux bases de données publiques, les CVE correspondant à ces vulnérabilités.
Pour cela, les participants devront pouvoir accéder librement à Internet (pour de la recherche uniquement), utiliser les outils qui leur auront été présentés, et remplir le document « modèle » qui leur sera fourni.

Ce scénario oblige les participants à travailler de manière collaborative, pour effectuer les recherches appropriées, grâce à l’instruction qu’ils auront suivie, et la manipulation des outils, avec une prise en main rapide.

Les recherches et les analyses du site Internet et de la machine virtuelle mettront en évidence plusieurs vulnérabilités, et une petite architecture réseau (crée pour le scénario par les intervenants) qu’ils devront exploiter par la suite des travaux pratiques.

Le Wordpress utilisé pour le site est vulnérable et l’authentification peut être contournée,
La machine virtuelle héberge un deuxième site Internet, qui contient l’architecture réseau de l’hôpital (l’accès à une autre machine virtuelle utile à la suite du scénario) détectable via un scan Nmap.



## La phase Exploitation des vulnérabilités

Une fois toutes les informations recueillies sur la cible (le site Internet fictif de l’hôpital de Valenciennes) lors de l’atelier précédent, les participants vont devoir travailler en équipe, mais cette fois dans un mode BLUE TEAM – RED TEAM.
La RED TEAM (équipe attaquante) va devoir exploiter les vulnérabilités détectées pendant la phase de ciblage, tandis que la BLUE TEAM (équipe défensive) va travailler comme un SOC et suivre les phases d’attaque en utilisant des outils d’analyse réseau (comme Wireshark), et devra émettre un rapport expliquant comment les attaquants se sont infiltrés sur le réseau, et comment ils sont parvenus à leurs fins.

![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/2ffd9661-d94e-4201-ae7f-d38a033ff854)
_Machine virtuelle des joueurs, avec les outils pré-installés_


![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/64ffcbb7-38df-49d6-a5dc-6a3da2ca4ac6)
_Message d’avertissement avant d’entrer sur les sites fictifs_


![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/506cf8ab-e3e8-4475-a82a-9e99f33ee987)
_Site Internet hopital-valenciennes.fr_



![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/5c6ad37f-5178-45ca-a045-819547c715f6)
_Site Internet du service informatique (sihv.hopital-valenciennes.fr)_



![image](https://github.com/artafak/CHALLENGE.hopital-valenciennes.fr/assets/38442391/55ddd31b-3177-4454-bdc7-8af0bfe3f88f)
_Serveur de fichiers du site hopital-valenciennes.fr:85_



# Matériel nécessaire

Les intervenants viendront avec 3 ordinateurs portables contenant les machines virtuelles et les présentations. Il sera nécessaire de les connecter au réseau existant.

Dans le cas où les ordinateurs portables ne pourraient pas être connectés au réseau existant, il sera nécessaire d’exporter les VM et de les configurer sur un poste existant. Cela, en plus de nécessiter un temps de vérification et de test, nécessite également des ordinateurs hôtes suffisamment performants pour accueillir une dizaine de VM démarrées simultanément (obligatoire pour la partie EternalBlue)

Une machine virtuelle en format OVA (VirtualBox) sera distribuée aux joueurs. Elle contient tous les outils et les configurations nécessaires à la formation et aux mises en pratique.


# Ressources

Pour télécharger les machines virtuelles et les documents ressources, suivez ce lien
Google Drive : https://drive.google.com/drive/folders/1jHMvBVt7RT5liDk4E4iPg2xKamDCjXjf?usp=sharing


Sur les ordinateurs hôtes, il sera nécessaire d’avoir un minimum de 8Go d’espace disque libre, ainsi que 4go de mémoire vive.

Les VM seront configurées pour fonctionner à travers le réseau, sur un adressage propre (le serveur Web embarquant son propre serveur DHCP avec un adressage en 192.168.5.0/24)
Les VM joueur sont configurées en DHCP.
