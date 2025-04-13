- Installer un server Apache + Activer PHP
- Cloner le repo dans /var/www/html/whatever et donner la propriété de whatever à son utilisateur
- Cloner son repo dans whatever
- Copier l'emulation des lib eedomus dans son repo : https://github.com/aussitot/eedomus.emulation.lib/blob/master/eedomus.lib.php 
	- TODO : Créer un git submodule pour completer la lib
- Ajouter les lignes suivantes dans le script

```
error_reporting(E_ALL);
ini_set("display_errors", 1);

require("eedomus.lib.php");
```

- Créer un fichier config.php avec les credentials de l'API eedomus
	- Configuration > Mon compte > Consulter mes identifiants
	- Ajouter le fichier au .gitignore
```
<?php
$api_user = "xxxxxx";
$api_secret = "yyyyyyyyy ";
?>
```
Accéder à http://localhost/deye/eedomus-deye/deye_cloud.php?action=verify