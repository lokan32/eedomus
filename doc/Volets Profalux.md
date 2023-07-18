# Liens et notices
Site de dépannage des volets profalux : https://www.profalux-pro.com/depannage/
Thread intéressant sur le sujet : https://www.forumconstruire.com/construire/topic-434641-probleme-telecommande-calyps-home.php
Ma Calyps'home : https://ma.calypshome.com/
Notices : 
![](Notice%20SAV%20Moteur%20Zigbee%203.0%20-%20A%20partir%20de%20Septembre%202021%20-%20NSAV061.pdf)
![](Notice%20SAV%20Telecommande%20Zigbee%20-%20A%20partir%20de%20septembre%202021%20-%20NSAV062.pdf)
# Solaires radio
Todo
# Filaire zigbee
## Ajouter de nouveaux volets sur la Calyps'home
Sur 1 télécommande du réseau : R puis ⏹️ (ouvre le réseau)
Si le volet ne bouge pas, il n'est pas dans le réseau
Sur nouvelle télécommande : R puis (🔼 + 🔽) : (supprime le réseau du nouveau volet)
Sur 1 télécommande du réseau : R puis ⏹️ (ouvre le réseau)
Sur la nouvelle télécommande : R puis 🔼 (entre dans le réseau)
Tester que le nouveau volet est bien dans le réseau avec R puis ⏹️

⚠️ **Attendre 3 minutes que le réseau se ferme avant tout autre manipulation (tous les volet du réseau font un mouvement)**

Aucune manipulation nécessaire sur la Calyps'home excepté le renommage des volets. Une ouverture réseau, une manipulation des volets ou un redémarrage de la box permet parfois la détection.
La box ne peut ajouter qu'un seul réseau de volet zigbee (celui auquel appartient le dongle)
Il semblerait que la fonctionnalité d'ajout d'équipement depuis la box ouvre le réseau. Cependant, le retour de succès de l'opération ne marche pas toujours.

La suppression d'un volet de la box provoque ça désassociation de la télécommande et nécessite ensuite un reset du moteur pour la réassocier : 
- Reset de la télécommande (5 fois sur R)
- Reset du volet (Mettre le fil noir sur la phase pendant 5 secondes). Pendant que le volet fait des mouvements, ⏹️ sur la télécommande
- Remettre le fil noir avec le neutre