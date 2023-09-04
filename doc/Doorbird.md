## Définir l'IP dans Eedomus
Lors de coupure, il est possible qu'il soit nécessaire de remettre l'IP du Doorbird dans Eedomus (dans ma configuration avec le répéteur wifi, il n'est pas possible de fixer l'IP sur la box internet).

Aller sur https://www.doorbird.com/checkonline pour récupérer l'IP actuelle du Doorbird. L'adresse MAC et le mot de passe sont sur les documentation d'origine du Doorbird (stockée dans Digiposte).

Aller dans Configuration > Périphériques > Doorbird > Configurer et mettre à jour VAR1.

Il est ensuite nécessaire d'enregistrer les identifiants pour cette IP. Pour cela il faut utiliser le endpoint de test : 
- Aller dans Paramètres Experts > Tester
- Remplacer l'IP et l'action par "test"
- Ajouter les paramètres d'authentification : &doorbird_user=<user>&doorbird_pass=<password>

Le retour doit être le suivant
```
<b>Connexion réussie !</b><br><br>Informations sur votre portier Doorbird : <br>{"BHA": { "RETURNCODE": "1", "VERSION": [{"FIRMWARE": "000140","BUILD_NUMBER": "16750642","WIFI_MAC_ADDR": "XXXXXXXXX","RELAYS":["1"],"DEVICE-TYPE": "DoorBird D1101V-S"}]}}
```
