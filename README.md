# Cloud Configuration Firecracker

## Description

Ce répertoire contient les fichiers de configuration centralisés pour l'infrastructure Tsore IaaS basée sur Firecracker. Ces configurations sont utilisées par les différents microservices de la plateforme pour assurer une configuration cohérente et faciliter la gestion des paramètres dans les différents environnements.

## Structure du répertoire

Le répertoire contient les fichiers de configuration suivants :

- `application.properties` : Configuration commune partagée par tous les services
- `auth-service.properties` : Configuration spécifique au service d'authentification
- `service-registry.properties` : Configuration du service de découverte Eureka
- `service-proxy.properties` : Configuration du service de routage/API Gateway
- `service-ssh-key.properties` : Configuration du service de gestion des clés SSH
- `service-vm-offers.properties` : Configuration du service de gestion des offres de machines virtuelles

## Utilisation

Ces fichiers de configuration sont chargés par le serveur de configuration Spring Cloud Config et distribués aux différents microservices. Chaque service récupère sa configuration spécifique en fonction de son nom et de son profil d'environnement.

### Paramètres principaux

#### Service Registry (Eureka)
- Port : 8761
- Configuration du serveur Eureka pour la découverte de services

#### Service VM Offers
- Port : 8083
- Connexion à la base de données MySQL
- Configuration Hibernate pour la persistance des données

#### Autres services
- Configuration des connexions à RabbitMQ (commentée)
- Configuration des endpoints Actuator pour la surveillance
- Paramètres de retry pour la résilience

## Développement

Pour modifier les configurations :

1. Effectuez les changements nécessaires dans les fichiers de propriétés
2. Validez que les modifications sont compatibles avec les services concernés
3. Redémarrez le serveur de configuration pour appliquer les changements

## Intégration

Ces configurations sont utilisées dans l'architecture microservices de la plateforme Tsore IaaS Firecracker, qui comprend :

- Service d'authentification et de gestion des utilisateurs
- Service de gestion des offres de machines virtuelles
- Service de gestion des clés SSH
- Service de découverte (Eureka)
- Service de routage (API Gateway)

## Remarques

Certaines configurations comme les connexions à RabbitMQ sont commentées et doivent être activées selon les besoins de l'environnement de déploiement.
