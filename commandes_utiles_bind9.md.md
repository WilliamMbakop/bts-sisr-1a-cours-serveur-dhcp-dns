
Commandes utiles à connaître pour gérer et diagnostiquer un serveur DNS BIND9 :

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
