# Commandes utiles

## Commandes utiles à connaître pour gérer et diagnostiquer un serveur ISC DHCP :

1. **Vérifier les baux DHCP attribués** :
   - Affiche les baux DHCP actuellement attribués.

   ```bash
   cat /var/lib/dhcp/dhcpd.leases
   ```

2. **Redémarrer le service DHCP** :
   - Redémarre le service DHCP pour appliquer les modifications.

   ```bash
   sudo systemctl restart isc-dhcp-server
   ```

3. **Vérifier le statut du service DHCP** :
   - Affiche le statut actuel du service DHCP.

   ```bash
   sudo systemctl status isc-dhcp-server
   ```

4. **Consulter les journaux du service DHCP** :
   - Affiche les journaux pour diagnostiquer les problèmes.

   ```bash
   sudo journalctl -xeu isc-dhcp-server
   ```

5. **Vérifier la configuration du serveur DHCP** :
   - Vérifie la syntaxe du fichier de configuration du serveur DHCP.

   ```bash
   sudo dhcpd -t -cf /etc/dhcp/dhcpd.conf
   ```

6. **Libérer et renouveler l'adresse IP sur un client Linux** :
   - Libère et renouvelle l'adresse IP sur un client Linux.

   ```bash
   sudo dhclient -r
   sudo dhclient
   ```

7. **Modifier manuellement un bail DHCP** :
   - Ouvre le fichier des baux DHCP pour modification.

   ```bash
   sudo nano /var/lib/dhcp/dhcpd.leases
   ```

8. **Supprimer tous les baux et recréer un fichier vide** :
   - Supprime tous les baux DHCP et recrée un fichier vide.

   ```bash
   sudo rm /var/lib/dhcp/dhcpd.leases
   sudo systemctl restart isc-dhcp-server
   ```

9. **Afficher les interfaces réseau écoutées par le serveur DHCP** :
   - Affiche les interfaces réseau sur lesquelles le serveur DHCP écoute.

   ```bash
   sudo netstat -uap | grep dhcpd
   ```

10. **Tester la configuration du serveur DHCP** :
    - Teste la configuration du serveur DHCP sans démarrer le service.

    ```bash
    sudo dhcpd -t
    ```

## Commandes utiles à connaître pour gérer et diagnostiquer un serveur DNS BIND9 :

1. **Vérifier la configuration de BIND9** :
   - Vérifie la syntaxe des fichiers de configuration de BIND9.

   ```bash
   sudo named-checkconf
   ```

2. **Vérifier les fichiers de zone DNS** :
   - Vérifie la syntaxe et la cohérence des fichiers de zone DNS.

   ```bash
   sudo named-checkzone example.com /etc/bind/db.example.com
   ```

3. **Redémarrer le service BIND9** :
   - Redémarre le service BIND9 pour appliquer les modifications.

   ```bash
   sudo systemctl restart bind9
   ```

4. **Vérifier le statut du service BIND9** :
   - Affiche le statut actuel du service BIND9.

   ```bash
   sudo systemctl status bind9
   ```

5. **Consulter les journaux de BIND9** :
   - Affiche les journaux pour diagnostiquer les problèmes.

   ```bash
   sudo journalctl -xeu bind9
   ```

6. **Tester la résolution DNS** :
   - Utilise `dig` pour tester la résolution DNS.

   ```bash
   dig @localhost example.com
   ```

7. **Recharger les fichiers de zone sans redémarrer BIND9** :
   - Recharge les fichiers de zone sans redémarrer le service.

   ```bash
   sudo rndc reload
   ```

8. **Vérifier les statistiques de BIND9** :
   - Affiche les statistiques de BIND9.

   ```bash
   sudo rndc stats
   ```

9. **Afficher la configuration de BIND9** :
   - Affiche la configuration actuelle de BIND9.

   ```bash
   sudo rndc dumpdb -zones
   ```

10. **Vérifier les clés DNSSEC** :
    - Vérifie les clés DNSSEC.

    ```bash
    sudo named-checkzone -D example.com /etc/bind/db.example.com
    ```