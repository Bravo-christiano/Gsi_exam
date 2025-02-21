    Tâche2 : Test de compétences Ansible

    Nom de la tâche
   Test de compétences Ansible

    Préparation de la tâche
   - Installation du serveur SSH avec `apt install openssh-server`.
   - Activation du service SSH avec `systemctl enable ssh` et `systemctl start ssh`.
   - Configuration de l'inventaire Ansible dans `/etc/ansible/hosts` avec :
     
     [gsi_machines]
     gsi_machine ansible_host=<IP_DU_SERVEUR>
     
   - Vérification de la configuration avec `ansible all --list-hosts`.

    Mise en œuvre de la tâche
   - Exécution du module ping pour tester la connectivité :
     
     ansible gsi_machines -m ping -i /etc/ansible/hosts
     
   - Création d’un playbook `install_apache.yml` pour :
     - Installer Apache avec le module `apt`.
     - Vérifier que le service Apache est démarré.
     - Modifier le fichier `/etc/apache2/ports.conf` pour écouter sur le port 8081.
     - Redémarrer Apache pour appliquer la modification.
   - Exécution du playbook avec :
     
     ansible-playbook -i /etc/ansible/hosts install_apache.yml --ask-become-pass
     

    Vérification
   - Réussite de la commande `ansible gsi_machines -m ping` avec réponse « pong ».
   - Confirmation dans la sortie du playbook que Apache est installé, que le port a été modifié et que le service a redémarré correctement.
   

 Enregistrement et intégration du fichier dans mon dépôt Git
   Depuis la racine du dépôt :
   
   cd Gsi_exam
   git add Ansible/install_apache.yml Ansible/README_Ansible.md
   git commit -m "Tache 2: ajout du playbook et de la documentation pour la Tâche 2 Ansible"
   git push
   

 Ajout d'une balise pour marquer l’étape Ansible :
   
   git tag -a Ansible_Task -m "Balise pour la Tâche Ansible"
   git push origin --tags
   
