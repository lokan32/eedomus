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
AutoInput est une application de la suite AutoApps. Elle dispose d'une période d'essaie. Elle peut ensuite être acheter en une fois via l'application AutoApps (L'application AutoApps propose un abonnement donnant accès à l'ensemble des plugins. Il n'est pas obligatoire)

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
		1. Titre : Eedomus
		1. Message : verisure-nuit
	1. Tâche : Mode Nuit Verisure

## Pushover (web)
1. Copier la User Key
2. Enregistrer la tablette centrale sur pushover 
3. Créer une application Eedomus et copier son API Token
## Eedomus
1. Installer un périphérique Pushover et renseigner les User key et API Token
2. Plutot que d'installer un periphérique Pushover par notification, nous allons lui ajouter des valeurs
3. Ajouter des valeurs et modifier le message de notification dans l'URL pour :
	1. verisure-nuit
	2. verisure-off
	3. verisure-total
4. Aller dans Configuration > Box > Configurer > Amazon Echo/Alexa 🔧
	1. Activer le partage du périphérique Verisure pushover avec Alexa
	2. Cocher les cases des états à partager et renommer les valeurs
		1. Désactive l'alarme
		2. Active l'alarme en mode nuit
		3. Active l'alarme en mode total

## Alexa
1. Aller dans Appareils > Tous les appareils > + > Essayer de détecter de nouveaux appareils
2. Cliquer sur "Configurer" pour chacun des appareils détectés
3. Créer des routines pour surcharger les commandes si besoin
	1. Ecrire "vérissure" dans les commandes vocales