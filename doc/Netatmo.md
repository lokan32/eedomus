## Accès aux logs

En ce qui concerne les changements d'état du Relais, vous avez à votre disposition les données historiques générées par le Thermostat et les Vannes, qui sont synchronisées pièce par pièce dans chaque Maison virtuelle de l’application Netatmo.

Pour télécharger les données d’une pièce, il suffit de suivre cette procédure :

1. Aller sur l'application web Energie ([https://my.netatmo.com](https://my.netatmo.com/)) depuis le navigateur internet d'un ordinateur.
2. Se connecter au compte Netatmo, et aller dans le menu Gérer ma maison (roue dentée dans la partie droite du bandeau supérieur).
3. Dans la colonne de gauche, cliquer sur le bouton menu (les 3 points verticaux) de la pièce souhaitée, puis sur le bouton Paramètres.
4. Dans la rubrique Gestion des données, cliquer sur Télécharger les données de votre pièce. Il est alors possible de sélectionner la fréquence des mesures, le type de données exportées et la période à analyser.

Dans le document téléchargé vous trouverez différentes colonnes :

• Timestamp : heure au format Unix. Le timestamp désigne le nombre de secondes écoulées depuis le 1er janvier 1970 à minuit UTC précise. Par exemple le timestamp 1465225760 correspond au 6/6/2016 à 17:09:20. Plus d'infos ici : [http://www.timestamp.fr/](http://www.timestamp.fr/)  
• Timezone : date et heure en fonction du fuseau horaire en vigueur.  
• Temperature : température ambiante mesurée.  
• Sp-Temperature : température de consigne (setpoint).  
• BoilerOn : nombre de secondes durant lesquelles le Thermostat a ordonné au chauffage de s'activer.  
• BoilerOff : nombre de secondes durant lesquelles le Thermostat a ordonné au chauffage de s'éteindre.  
• heating_power_request : pourcentage d’ouverture des Vannes.