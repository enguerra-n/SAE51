# monitoring de logs
Ce Dockerfile utilise Grafana, Loki, Promtail pour surveiller les journaux du serveur nginx. Grafana fournit un tableau de bord convivial, Loki agrège les journaux, Promtail scrape les journaux.

## Composants
- **Grafana** : Une plateforme open-source pour la surveillance et l'observabilité. Elle permet d'interroger, de visualiser, d'alerter et de comprendre les métriques.
- **Loki** : Un système d'agrégation de logs inspiré de Prometheus.
- **Promtail** : Un agent qui envoie le contenu des logs vers une instance privée de Loki.

## Exécution de l'application
Pour lancer l'application, utilisez la commande suivante : `docker compose up -d`
Cette commande utilise Docker Compose pour démarrer l'application.

## Vérifier l'état des services
Vous pouvez vérifier l'état des services en visitant les URL suivantes :
- `localhost:3100/metrics` : Cette page affiche diverses métriques relatives à l'application.
- `localhost:3100/ready` : Cette page indique si l'application est prête. Si elle n'indique pas « ready », essayez d'actualiser la page, sinon pentientez quelque instants.
- `localhost:3000` : Accéder à Grafana.

*Merci de prendre en compte que ses url fonctionne si les applications sont sur votre machine, si elles sont sur une autre machine spécifier l'adresse IP de celle-ci au lieu de localhost*

## Créer un nouveau Dashboard
Importez un nouveau Dashboard pour la surveillance de Loki, comme celui qui porte l'identifiant **13639**, ou créez-en un nouveau.
<a href="https://grafana.com/grafana/dashboards/13639-logs-app/">Documentation de celui-ci</a>
