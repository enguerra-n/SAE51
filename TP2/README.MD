# SAE51-TP2
-LELOUP Quentin
-LECOQ Enguerran

Ce document présente la réalisation de notre travail sur la SAE51 (TP2), 
le but de ce travail est de collecter les données d'un serveur WEB. 

<!-- Pour sauter une ligne sur le rendu markdown il faut faire 2 espaces et appuyer sur entrer -->




## Partie 1 : Les différentes plateforme permettant de collecter les données

* ### Rsyslog : 

<img src="https://www.rsyslog.com/logo7-2/" alt="Description" width="300" height="200">

Créé en 2004 par Rainer Gerhards, Rsyslog est un système de gestion des journaux (logs) pour Linux et Unix. Il est conçu pour collecter, filtrer et stocker les messages de log provenant du système et des applications.  

Rsyslog permet de :

* Centraliser les logs en les envoyant vers un serveur distant.
* Filtrer et classer les logs en fonction de leur priorité ou de leur source.
* Analyser et stocker les logs dans différents formats (fichiers, bases de données). 

Il est souvent utilisé pour la surveillance, le débogage, et la gestion de la sécurité. L'installation se fait uniquement sur l'environement LINUX.  
Lien vers le site de l'application : https://www.rsyslog.com/


* ### Graphana LOKI  :  
<br>
<br>

<img src="https://www.netways.de/wp-content/uploads/2023/12/logo_product_loki.png" alt="Description" width="300" height="120">

<br>
<br>


Grafana Loki, lancé en 2018 par Grafana Labs, est un outil open-source conçu pour collecter, analyser et visualiser des logs. Contrairement à d'autres solutions, Loki n'indexe pas le contenu des logs, mais se concentre sur les métadonnées, ce qui le rend plus léger et moins coûteux en termes de stockage.

Graphana LOKI permet de : 

* Collecter des logs : Loki peut ingérer des logs à partir de diverses sources.
 * Rechercher rapidement : Grâce à l'utilisation des métadonnées, la recherche dans les logs est rapide et efficace.
* Integrer avec Grafana : Loki s'intègre parfaitement avec Grafana, permettant de visualiser et d'explorer les logs aux côtés des métriques.

Graphana loki présente un large avantage en therme de documentation technique en ligne car il est utilisé par plus de 66 000 utilisateurs.  
Lien vers le site de l'application : https://grafana.com/oss/loki/

* ### Graylog :
 
 <br>
<br>

<img src="\graylog_logo.png" alt="logo graylog" width="300" height="120">

<br>
<br>

Graylog, créé en 2009, est un outil qui centralise et analyse les journaux d'événements (logs) de différents systèmes.

Graylog permet de :

* Collectee et centraliser des logs : Regroupe tous les logs en un seul endroit.
* Rechercher rapidement : Permet de trouver facilement des informations spécifiques dans les logs.
* Creer des alertes automatiques : Envoie des notifications en cas de problèmes.
* Donne accès à un tableaux de bord : Affiche les données sous forme de graphiques pour une meilleure visualisation.
  
Lien vers le site de l'application : https://graylog.org/


## Partie 2 : Choix et mise en oeuvre de la solution

### Graphique de fonctionement de l'infrastructure : 

<img src="\usage-graphic.png" alt="schéma du fonctionnement applicatif" width="300">

## Monitoring de logs
Ce Dockerfile utilise Grafana, Loki, Promtail pour surveiller les journaux du serveur nginx. Grafana fournit un tableau de bord convivial, Loki agrège les journaux, Promtail scrape les journaux.

## Composants
- **Grafana** : Une plateforme open-source pour la surveillance et l'observabilité. Elle permet d'interroger, de visualiser, d'alerter et de comprendre les métriques.
- **Loki** : Un système d'agrégation de logs inspiré de Prometheus.
- **Promtail** : Un agent qui envoie le contenu des logs vers une instance privée de Loki.
- **Nginx** : serveur web permettant de générer des logs

## Exécution de l'application
Pour lancer l'application, utilisez la commande suivante : `docker compose up -d`
Cette commande utilise Docker Compose pour démarrer l'application.

## Vérifier l'état des services
Vous pouvez vérifier l'état des services en visitant les URL suivantes :
- `localhost:3100/metrics` : Cette page affiche diverses métriques relatives à l'application.
- `localhost:3100/ready` : Cette page indique si l'application est prête. Si elle n'indique pas « ready », essayez d'actualiser la page, sinon pentientez quelque instants.
- `localhost:3000` : Accéder à Grafana.
- `localhost:8080` : Accéder à nginx.

*Merci de prendre en compte que ses url fonctionne si les applications sont sur votre machine, si elles sont sur une autre machine spécifier l'adresse IP de celle-ci au lieu de localhost*

## Créer un nouveau Dashboard
Importez un nouveau Dashboard pour la surveillance de Loki, comme celui qui porte l'identifiant **13639**, ou créez-en un nouveau.
<a href="https://grafana.com/grafana/dashboards/13639-logs-app/">Documentation de celui-ci</a>


