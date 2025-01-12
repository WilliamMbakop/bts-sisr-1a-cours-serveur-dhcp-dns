Commandes utiles à connaître pour gérer et diagnostiquer un serveur ISC DHCP :

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