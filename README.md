# Stack Grafana - Loki - Promtail (Monitoring de Logs)
# Stack Grafana - Prometheus - Node-exporter (Monitoring de ressources)

## Introduction

La stack Grafana, Loki, Promtail permet de surveiller et d'analyser les logs systèmes ou d'applications. Son utilisation est légere et simple grâce à son déploiement via docker.

- **Promtail** est l’agent installé sur les serveurs cibles il permet de parser les logs entrants et d’y ajouter des tags afin de mieux trier les alertes. 
- **Prometheus** repose sur une base de données et agit comme un aggrégateur de metrics, comme la performances des serveurs (utilisation disque, charges CPU, bande passante utilisée...)
- **Loki** est repose également sur une base de données, mais cet outil permet d'aggréger tous types de logs (logs système, logs d'applications, logs de service...)
- **Grafana** va ensuite chercher dans cette base de données afin de les retranscrire sur son interface. Un panel assez large de filtres est disponible sur Grafana, mais permet aussi la customisation des intervalles des requêtes.

Toutes ces solution forment donc un ensemble puissant et grandement personnalisable afin de cybersurveiller entièrement un système d’informations. Une fois mises en place, ces solutions sont plutôt légères et peu gourmandes en ressources, ce qui permet de ne pas influer sur la qualité du réseau et des performances de nos services.

## Configuration

Ici, toute la configuration est basée sur docker, et sur des fichiers **docker-compose.yml**. Il suffit donc d'exécuter la commande :

```docker-compose up```

D'abord sur le serveur (afin d'initialiser Loki) puis sur le client, et l'infrastructure de monitoring est monté.

