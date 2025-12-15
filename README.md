# TP Java Pipeline Jenkins

## 👤 Étudiant
**Nom Prénom :** Aalae Goudal  
**Dépôt GitHub :** TPJavaPipeLine-AalaeGoudal

---

## 🎯 Objectif du TP
Mettre en place un **pipeline CI/CD Jenkins** pour un projet **Java Maven** en utilisant **Docker**, afin d’automatiser :
- le téléchargement du code source
- la compilation
- l’exécution des tests
- la génération du fichier JAR

---

## 🛠️ Technologies utilisées
- **Java**
- **Maven**
- **Jenkins**
- **Docker**
- **Git & GitHub**

---

## 📁 Structure du projet

![alt text](image.png)


---

## 🐳 Image Docker Maven

Une image Docker personnalisée a été construite à partir du fichier `Dockerfile` :



Cette image contient :
- Java
- Maven
- Git

Elle est utilisée par Jenkins comme **agent Docker** pour exécuter le pipeline.

---

## ⚙️ Pipeline Jenkins

Le pipeline Jenkins est défini dans le fichier `Jenkinsfile`.

### 🔄 Étapes du pipeline :
1. **Checkout**
   - Récupération du code source depuis GitHub

2. **Build**
   - Compilation du projet
   - Exécution des tests
   - Génération du fichier JAR

Commande Maven utilisée :


---

## ✅ Résultat du Pipeline Jenkins

Le pipeline s’exécute avec succès (statut **SUCCESS**).

### 📸 Capture 1 — Pipeline Jenkins en succès (vert)
*(Dashboard Jenkins)*

![alt text](image-1.png)


---

## ⚠️ Problèmes rencontrés et solutions

### 🔴 Problème rencontré
Lors de l’exécution du pipeline, Jenkins ne pouvait pas accéder à Docker :

permission denied while trying to connect to the docker API


### ✅ Solution appliquée
- Montage du socket Docker :
- Ajout de l’utilisateur `jenkins` au groupe `docker`
- Attribution des permissions nécessaires

Après correction, le pipeline s’exécute correctement.

---

## 🧾 Conclusion
Ce TP a permis de mettre en place un **pipeline CI/CD fonctionnel** avec Jenkins et Docker.  
Le projet Java est désormais **automatiquement compilé et testé**, ce qui garantit une intégration continue efficace.

---

## 🔗 Lien du dépôt GitHub
👉 https://github.com/aalaeg1/TPJavaPipeLine-AalaeGoudal
