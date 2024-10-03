# Examen final module DevOps IMDW280
## Consignes générales : 
Le but de cet exament est de mettre en pratique le contenu du cours DevOps que nous avons vu depuis le début du cours. 

Jusqu'à présent nous avons vu les principes de base pour utiliser git, créer des Githubs Actions et développer une REST API. Sur les autres cours nous avons vu Kubernetes, et comment déployer des applications dessus. 

La demande est la suivante, à partir des sources mises à dispositions et des supports de cours, déployez l'application python que nous avons développé dans le cluster Openshift mis à disposition pour l'occasion. 

Un document décrivant les différentes étapes de réalisation est attendu en livrable.

Pour travailler, créez un projet sur github que vous vous partagerez au besoin et mettez les ressources de ce projet dedans.

## Attendus sur la chaine CI/CD 

### Création de l'image Docker de l'application 
Afin de créer une image docker de manière automatique, le fichier Dockerfile est mis à disposition sur la racine. Celui-ci prends le contenu du dossier app-python et le met en place dans l'image du conteneur. 

L'image une fois construite avec la pipeline CI/CD, doit être envoyé dans la container registry harbor.kakor.ovh sous le nom harbor.kakor.ovh/ipi/groupeX:tag via l'utilisateur ipi.

Pour ce faire, renseignez-vous sur les solutions de Github Actions pour y parvenir. 

### Tests de sécurité 

A partir de l'application Trivy, scannez depuis la chaîne CI/CD l'image créé pour mettre en évidence les vulnérabilités. Faites en sorte qu'une erreur de ce job, ne résulte pas en un arrêt de la chaîne. 

### Déploiement de l'application 

L'image harbor.kakor.ovh/public/oc:latest, est mise à disposition pour déployer l'application sur Kubernetes. Adaptez les fichiers dans le dossier kubernetes-manifest afin de deployer dans le projet de vos groupes spécifiques les différents fichiers yaml. 

Par groupe, le namespace projet-gp-X vous sera mis en place.

Pour vous connecter, le compte que vous pouvez utiliser est ipi-gp-X et le mot de passe vous sera fourni à part. L'API à utiliser pour le cluster est https://api.openshift.kakor.ovh:6443

Vous pouvez vous connecter sur l'interface web sur l'adresse https://console-openshift-console.apps.openshift.kakor.ovh pour récupérer le token dans le menu login en haut à droite vous permettant de lancer les opérations.

### Testez le fonctionnement de l'application depuis l'url renseignée dans la route Openshift