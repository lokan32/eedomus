## Synchroniser l'état du doorbird

### Eedomus
- Créer un Actionneur avec deux états : ON/OFF
	- Ajouter une macro ON -> 3s -> OFF
	- Ajouter une règle : si devient ON -> Portail : passer
- Aller dans Configuration > Mon Compte > Consulter vos identifiants
	- Créé l'URL pour SET la macro précédente
		- Cloud
		- SET
		- periph.macro
		- Ouverture App Doorbird Dehors / Passer
	- S'envoyer l'URL sur son portable
### Application Doorbird
#### Ajouter une serrure intelligente
- Aller dans Paramètres ⚙ > APPAREILS > Portail  > SERRURES INTELLIGENTES > Ajouter un apple URL personnalisé
	- Nom : Passer Eedomus
	- URL : https://api.eedomus.com/set?api_user=xxxxxxxxx&api_secret=xxxxxxxxxxxxx&action=periph.macro&macro=5747292
- Enregistrer la serrure
- Enregistrer les paramètres


## Définir l'IP dans Eedomus
Lors de coupure, il est possible qu'il soit nécessaire de remettre l'IP du Doorbird dans Eedomus (dans ma configuration avec le répéteur wifi, il n'est pas possible de fixer l'IP sur la box internet).

Aller sur https://www.doorbird.com/checkonline pour récupérer l'IP actuelle du Doorbird. L'adresse MAC et le mot de passe sont sur les documentation d'origine du Doorbird (stockée dans Digiposte).

Aller dans Configuration > Périphériques > Doorbird > Configurer et mettre à jour VAR1.

Il est ensuite nécessaire d'enregistrer les identifiants pour cette IP. Pour cela il faut utiliser le endpoint de test : 
- Aller dans Paramètres Experts > Tester
- Remplacer l'IP et l'action par "test"
- Ajouter les paramètres d'authentification : `&doorbird_user=<user>&doorbird_pass=<password>`

Le retour doit être le suivant

`<b>Connexion réussie !</b><br><br>Informations sur votre portier Doorbird : <br>{"BHA": { "RETURNCODE": "1", "VERSION": [{"FIRMWARE": "000140","BUILD_NUMBER": "16750642","WIFI_MAC_ADDR": "XXXXXXXXX","RELAYS":["1"],"DEVICE-TYPE": "DoorBird D1101V-S"}]}}`

### Mise à jour auto de l'IP
Il est possible d'utiliser la fonction sdk_get_ip_from_ip_or_mac('1C:CA:E3:7A:33:BF'); pour récupérer l'IP d'un périphérique.
Récupérer la MAC du doorbird sur 
- https://secure.eedomus.com/box_http_query.php?from=script_proxy&controller_id=16257&command_sent_id=18903647&url=http%3A%2F%2F192.168.1.69%2Fconfig%2Fnetscan.php&XPATH=&convert=&radio_source= 
- http://ip_box_eedomus/config/netscan.php
- https://doc.eedomus.com/view/Superviser_son_r%C3%A9seau_local
Modifier ensuite la ligne suivante du script doorbird
```
//$doorbird_ip = getArg('doorbird_ip');
$doorbird_ip = sdk_get_ip_from_ip_or_mac(getArg('doorbird_ip'));
```
Et remplacer l'IP de VAR1 par l'adresse MAC


