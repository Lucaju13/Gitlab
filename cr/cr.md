# Build automatisé d’images Docker avec Gitlab
## Installation dockerfile sur ma machine

![Alt_text](../images/1.png)

## 2 Installation d’un runner Gitlab sur ma machine

![Alt_text](../images/2.png)

## 3 Accès au daemon Docker par une socket TLS

**1 - Installez mkcert pour pouvoir générer des certificats TLS pour Docker**

![Alt_text](../images/3.png)

**2 - Générez un certificat pour votre machine**

![Alt_text](../images/4.png)

**3 - Modifs le daemon Docker**

![Alt_text](../images/5.png)

![Alt_text](../images/6.png)

![Alt_text](../images/7.png)

![Alt_text](../images/8.png)

![Alt_text](../images/9.png)

![Alt_text](../images/10.png)

![Alt_text](../images/11.png)

## 4 Création de runners Gitlab sur gitlab.com ou gitlab.iutbeziers.fr
```cmd
gitlab-runner register -n \
--url "https://gitlab.iutbeziers.fr/" \
--registration-token glrt-5ANxYhW4XhYSb7rrioz- \
--executor shell \
--description "runner shell portainer1"
```
![Alt_text](../images/12.png)

## 4.1 Variables d’environnement pour le runner

![Alt_text](../images/16.png)

## 4.2 Création d’un runner Gitlab shell sur votre machine

![Alt_text](../images/13.png)

![Alt_text](../images/14.png)

## 4.3 Création d’un runner Gitlab D.I.N.D (Docker in Docker)
```cmd
sudo gitlab-runner register -n \
--url "https://gitlab.iutbeziers.fr/" \
--registration-token glrt-5ANxYhW4XhYSb7rrioz- \
--executor docker \
--description "docker runner dind portainer1" \
--docker-image "docker:24.0.5" \
--docker-privileged
```
![Alt_text](../images/15.png)

**5. Faites une modification sur ce projet pour arrêter le deploiement de l’image sur le registry de l’IUT.**

- [../script/.gitlab-ci.yml](voici le script)

![Alt_text](../images/17.png)


![Alt_text](../images/18.png)



