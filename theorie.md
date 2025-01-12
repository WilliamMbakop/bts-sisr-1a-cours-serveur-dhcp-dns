# Serveur DHCP & Serveur DNS - Théorie

## Informations

| Champ           | Détails                                      |
|-----------------|----------------------------------------------|
| **Auteur**      | William Mbakop                               |
| **Date**        | 9 janvier 2025                               |
| **Description** | Serveur DHCP & Serveur DNS - Théorie         |

## Serveur DHCP

### Rôle
Le serveur DHCP (Dynamic Host Configuration Protocol) est responsable de l'attribution automatique des adresses IP et d'autres paramètres réseau aux appareils sur un réseau. Cela simplifie la gestion des adresses IP et réduit les erreurs de configuration manuelle.

### Fonction
- **Attribution d'adresses IP** : Le serveur DHCP attribue des adresses IP dynamiques aux clients sur le réseau.
- **Configuration des paramètres réseau** : Il fournit également des informations telles que le masque de sous-réseau, la passerelle par défaut et les serveurs DNS.
- **Gestion des baux** : Le serveur gère les baux d'adresses IP, y compris l'expiration et le renouvellement des adresses IP attribuées.

### Processus DORA
Le processus DORA (Discover, Offer, Request, Acknowledge) est utilisé par le DHCP pour attribuer des adresses IP :
- **Discover** : Le client envoie une requête DHCP Discover pour trouver les serveurs DHCP disponibles.
- **Offer** : Les serveurs DHCP répondent avec une offre DHCP Offer contenant une adresse IP disponible.
- **Request** : Le client répond avec une requête DHCP Request pour accepter l'offre d'un serveur spécifique.
- **Acknowledge** : Le serveur DHCP confirme l'attribution de l'adresse IP avec un message DHCP Acknowledge.

### Ports
- **Port 67/UDP** : Utilisé par le serveur DHCP pour recevoir les requêtes des clients.
- **Port 68/UDP** : Utilisé par les clients DHCP pour recevoir les réponses du serveur.

## Serveur DNS

### Rôle
Le serveur DNS (Domain Name System) traduit les noms de domaine lisibles par l'homme (comme www.example.com) en adresses IP compréhensibles par les machines (comme 192.0.2.1). Cela permet aux utilisateurs d'accéder aux ressources réseau en utilisant des noms de domaine faciles à retenir.

### Fonction
- **Résolution de noms** : Convertit les noms de domaine en adresses IP.
- **Répartition de charge** : Peut distribuer le trafic réseau entre plusieurs serveurs pour équilibrer la charge.
- **Cache DNS** : Stocke les résultats des requêtes DNS pour accélérer les résolutions futures.

### Processus de résolution DNS
Le processus de résolution DNS suit plusieurs étapes :
- **Requête récursive** : Le client demande au résolveur DNS de trouver l'adresse IP correspondante à un nom de domaine.
- **Requête itérative** : Le résolveur DNS interroge plusieurs serveurs DNS, en commençant par le serveur racine, puis les serveurs de domaine de premier niveau (TLD), et enfin les serveurs DNS autoritaires pour obtenir la réponse.
- **Réponse** : Le résolveur DNS renvoie l'adresse IP trouvée au client.

### Ports
- **Port 53/UDP** : Utilisé pour la plupart des requêtes DNS.
- **Port 53/TCP** : Utilisé pour les requêtes DNS nécessitant une réponse plus longue ou pour les transferts de zone DNS.                              |
