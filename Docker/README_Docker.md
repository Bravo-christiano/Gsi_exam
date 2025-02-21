 Tâche 3 : Docker 

 Objectif
Ce document décrit la configuration et l'exécution de la Tâche Docker, qui consiste à :
- Créer une image Docker basée sur un Dockerfile inspiré du playbook Ansible.
- Démarrer un conteneur à l'aide d'un script bash.
- Fournir un playbook Ansible (docker.play.yml) pour installer et configurer Nginx sur un hôte (pour comparaison ou validation).

 1. Contenu de la Tâche

 1.1. Dockerfile
Le fichier **Dockerfile** construit une image basée sur Ubuntu, installe Nginx, copie une page HTML simple, expose le port 80 et démarre Nginx en mode premier plan.


 1.2. Script Bash (bash.sh)
Le script *bash.sh* est utilisé pour :
- Construire l'image Docker (nommée my-nginx-image).
- Démarrer un conteneur nommé my-nginx-container en mappant le port 80 du conteneur sur le port 8080 de l'hôte.
- Afficher un message de confirmation.


 1.3. Playbook Ansible (docker.play.yml)
Ce playbook installe Nginx, copie une page HTML et démarre le service sur l'hôte cible. Il sert ici de comparaison/validation avec la solution Docker.
