# Guide d'installation et de configuration d'Apache2 et Git sur Ubuntu

Ce guide vous montrera comment installer et configurer Apache2 sur un serveur Ubuntu, ainsi que comment cloner un dépôt Git et configurer un site web de base.

## Mise à jour et mise à niveau du système

Avant de commencer, assurez-vous que votre système est à jour en exécutant les commandes suivantes :

```bash
sudo apt update
sudo apt upgrade
```

## Installation de net-tools

Pour utiliser la commande `ifconfig`, installez le package `net-tools` :

```bash
sudo apt install net-tools
```

## Installation d'Apache2

Pour installer Apache2, utilisez la commande suivante :

```bash
sudo apt install apache2
```

## Démarrage d'Apache2

Démarrez le service Apache2 avec la commande suivante :

```bash
sudo systemctl start apache2
```

## Vérification du statut d'Apache2

Vous pouvez vérifier le statut d'Apache2 avec la commande suivante. Appuyez sur la touche "q" pour quitter la sortie détaillée :

```bash
sudo systemctl status apache2
```

## Activation du démarrage automatique d'Apache2

Pour que le service Apache2 démarre automatiquement au démarrage du système, exécutez la commande suivante :

```bash
sudo systemctl enable apache2
```

## Redémarrage d'Apache2

Pour appliquer les modifications de configuration, redémarrez Apache2 :

```bash
sudo systemctl restart apache2
```

## Clonage d'un dépôt Git

Utilisez la commande suivante pour cloner un dépôt Git (remplacez `<url>` par l'URL du dépôt Git que vous souhaitez cloner) :

```bash
git clone <url>
```

## Copie du dossier "nom-du-site" vers le répertoire Web d'Apache

Pour copier un dossier appelé "nom-du-site" dans le répertoire Web d'Apache ("/var/www"), utilisez la commande suivante :

```bash
sudo cp -r nom-du-site /var/www
```

## Création du fichier de configuration

Créez un fichier de configuration pour votre site (nom-du-site.conf) dans le répertoire "/etc/apache2/sites-available" à partir des paramètres par défaut en utilisant la commande suivante :

```bash
sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/nom-du-site.conf
```

## Configuration d'un site Apache2

Utiliser l'éditeur de texte Nano pour ouvrir le fichier et y ajouter la configuration nécessaire :

```bash
sudo nano /etc/apache2/sites-available/nom-du-site.conf
```

Assurez-vous de définir les directives `ServerName`, `ServerAdmin`, et `DocumentRoot` appropriées pour votre site.

## Activation du site Apache2

Activez le site Apache2 que vous venez de configurer en utilisant la commande suivante :

```bash
sudo a2ensite nom-du-site.conf
```

## Redémarrage d'Apache2

Pour que la configuration du site soit prise en compte, redémarrez Apache2 :

```bash
sudo systemctl restart apache2
```

Cela devrait vous permettre d'installer Apache2, de cloner un dépôt Git, de copier un dossier dans le répertoire Web d'Apache, de configurer un site web, et de redémarrer Apache2 pour rendre votre site accessible en ligne.
