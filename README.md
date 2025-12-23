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

<img width="319" height="374" alt="image" src="https://github.com/user-attachments/assets/3b8c4258-d9e3-436f-b55b-d165ecc2a555" />



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

<img width="1919" height="1012" alt="image" src="https://github.com/user-attachments/assets/2aabea76-5865-42a9-ba68-69cddd72d546" />



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
En conclusion ce TP a permis de mettre en place un **pipeline CI/CD fonctionnel** avec Jenkins et Docker.  
Le projet Java est désormais **automatiquement compilé et testé**, ce qui garantit une intégration continue efficace.

---

## 🔗 Lien du dépôt GitHub
👉 https://github.com/aalaeg1/TPJavaPipeLine-AalaeGoudal
