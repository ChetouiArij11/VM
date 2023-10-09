# Outils a découvrir - déploiement continue

## Outils Cloud

### Github Action (cloud)

### Gitlab Ci (cloud)

### Travis CI (cloud)

### Jenkins (sys / docker / kubernetes)

## Penser a documenter tous le processus (documentation scientifique )

## Pour le module Disponibilite de Infra & Monitoring

### Nous allons creer des lab (devopslab)

    - Installer docker comme outil de deploiment
      + installe sur Windows 10/11 (WSL)
      + machine virtuelle avec docker

    - Tester kubernetes sous form 
      + minikube (docker / VM /sys)
      + k3s
      + k8s
      
    - Tester les diferents outils :
     + Jenkins 
     + Uptime
     + Prometheus / Grafana 
     + etc .

### mettre cntr+k ensuit v pour affiche le contenu de readme file sur le preview

## Outils du travail

- Cree une VM template -template-

 -> 2 GO RAM , 20GO disque
 -> execute le script reset-template (/code_template_sh)

- Cree VM devopsLabs
 -> 8 Go Ram, 40Go Disque, 4 coeurs
 -> wsl :
      ```
      wsl -l --online
      wsl --install -d Ubuntu22.04
       ```

 -> affectuer une adresse fixe a cette machine (VMWare DHCP)

      ```
        1- acceder (C:\ProgramData\VMware\vmnetdhcp.config)
        2- ajouter à la fin de page le code suivant 
                    host serverhost {
                             hardware ethernet 00:0C:29:74:46:2D;
                            fixed-address 192.168.114.131;
                                    }
                    host arij {
                            hardware ethernet 00:0C:29:F0:8B:4C;
                            fixed-address 192.168.114.132;
                                }


        ```

 -> generer une pair de cle ssh

        ```
    ssh-keygen
    ssh-copy-id @192.168.114.131
      ```

 ->Installer Docker

      ```
    sudo apt update
    sudo apt install docker-compose -y
    docker-compose --version
      ```
 ->Installer Ansible

      ```
        sudo apt install ansible
        ansible --version
      ```
  ->Installer Portainer

       ```
       - docker volume create portainer_data
       - docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
        - docker run -d -p 9000:9000 \
      ```

  ->Installer Python3

        ```
    sudo apt install python3
    python3 --version

        ```
-cree 2 VM (snapshots du template)
 ->affecter des adresses ip fixes
