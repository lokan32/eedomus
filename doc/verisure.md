# Présentation des éléments

## Tablette centrale

### My Verisure
L'application Verisure ne dispose pas d'une API ouverte pouvant être appelée par un tiers. L'application MyVerisure (pour les système Verisure déployés en France) permet de modifier l'état de l'alarme depuis la tablette centrale.

### Tasker
Tasker est une application android payante (achat unique) : 
- https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en&gl=US&pli=1
- https://tasker.joaoapps.com/
Tasker permet de déclancher des suites d'actions (Task) suite à un stimuli (Profile)

### AutoInput
AutoInput est une application plugin de Tasker. Elle permet d'enregistrer des inputs utilisateurs sur une application puis de les reproduire comme Action dans Tasker.
### Pushover
Pushover est un service qui permet de créer des notifications sur les appareils android ayant l'application à partir d'un web service : 
- https://play.google.com/store/apps/details?id=net.superblock.pushover&hl=en&gl=US
- https://pushover.net/

## Eedomus

### Pushover
Le plugin Pushover sur Eedomus permet de créer un périphérique qui facilite les appels au web service Pushover
- https://secure.eedomus.com/pages/doc.php?type=pushover&file=readme_fr.md

# Mise en place
## Tablette-centrale

1. Installer Tasker
2. Installer AutoInput
3. Ouvrir AutoInput et aller dans _Manage Input Action_
4. Cliquer sur + pour ajouter une nouvelle _Input Action_
	1. Une notification apparait, elle permet de valider l'action que l'on vient de faire (ACCEPT) ou de recommencer la capture (RE-SELECT)
	1. Ouvrir l'application MyVerisure pour capture l'action 'AUTRES MODES'
	1. Recommencer l'étape 4 pour les actions 🏠, Suivant et DESACTIVER
5. Installer Pushover et enregistrer le device sous le nom _Tablette-centrale_
6. Ouvrir Tasker
7. Créer une Tâche Mode Nuit Verise avec les Actions suivantes
	1. App > Charger une appli > My Verisure
	1. Plugin > AutoInput > Action > Configuration > Stored Action > _AUTRES MODES_
	1. Plugin > AutoInput > Action > Configuration > Stored Action > _🏠_
	1. Plugin > AutoInput > Action > Configuration > Stored Action > _Suivant_
8. Créer un Profil Verisure Nuit avec la configuration suivante :
	1. Evenement > Plugin > Pushover
		1. Titre : Verisure
		1. Message : Nuit
	1. Tâche : Mode Nuit Verisure
## Eedomus
1. Installer un périphérique Pushover