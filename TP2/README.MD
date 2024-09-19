# SAE51-TP2
-LELOUP Quentin
-LECOQ Enguerran

Ce document présente la réalisation de notre travail sur la SAE51 (TP2), 
le but de ce travail est de collecter les données d'un serveur WEB. 

<!-- Pour sauter une ligne sur le rendu markdown il faut faire 2 espaecs et appuyer sur entrer -->




## Partie 1 : Les différentes plateforme permettant de collecter les données

* ### Rsyslog : 

Créé en 2004 par Rainer Gerhards, Rsyslog est un système de gestion des journaux (logs) pour Linux et Unix. Il est conçu pour collecter, filtrer et stocker les messages de log provenant du système et des applications.  

Rsyslog permet de :

* Centraliser les logs en les envoyant vers un serveur distant.
* Filtrer et classer les logs en fonction de leur priorité ou de leur source.
* Analyser et stocker les logs dans différents formats (fichiers, bases de données). 

Il est souvent utilisé pour la surveillance, le débogage, et la gestion de la sécurité.


* ### Graphana LOKI  :


Grafana Loki, lancé en 2018 par Grafana Labs, est un outil open-source conçu pour collecter, analyser et visualiser des logs. Contrairement à d'autres solutions, Loki n'indexe pas le contenu des logs, mais se concentre sur les métadonnées, ce qui le rend plus léger et moins coûteux en termes de stockage.

Les principales fonctionnalités de Loki incluent :

* Collecte de logs : Loki peut ingérer des logs à partir de diverses sources.
 * Recherche rapide : Grâce à l'utilisation des métadonnées, la recherche dans les logs est rapide et efficace.
* Intégration avec Grafana : Loki s'intègre parfaitement avec Grafana, permettant de visualiser et d'explorer les logs aux côtés des métriques.


## Partie 2 : Choix et mise en oeuvre de la solution

