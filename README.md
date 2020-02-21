Dans ce repo, on trouve les fichiers Vagrant et Ansible pour le deploiement de l'infrastructure

Le fichier Vagrant_Master_Jenkins configure la machine master Jenkins

Le fichier Vagrant_Slave_Jenkins configure la machine slave Jenkins, accessible via le port 9000 en ssh.

Le fichier Vagrant_Server_Test configure la machine de test, accessible via le port 9100 en ssh.

Le fichier Vagrant_Server_Prod configure la machine de prod, accessible via le port 9200 en ssh.

Le Serveur Master_Jenkins contient (java jdk, git , maven, jenkins, ansible et docker).

Le Serveur Slave_Jenkins contient (java jdk, git , maven, ansible et docker).

Le Serveur Test contient (java jdk et git).

Le Serveur Prod contient (java jdk  et git ).

L' approvisionnement des deux serveurs Test et Prod se fait avec ansible via le serveur Slave_Jenkins
, via les roles Ansible docker_prod et docker_test.
 Ces roles contiendront les informations pour l'installation de :
 
  Pour la docker_prod:
  - repo de docker
  - python-pip
 

 Pour la docker_test:
  - repo de docker
  - python-pip 


La branche 'develop' sera utilisée par le serveur Test  (test) au cours des 
changements de codes, tandis que la branche master sera utilisée pour la mise en production (déploiement). 