
# 👩‍💻 Introduction au développement web – Pour les débutants (en français)

---

## 🌐 1. Qu'est-ce que le développement web ?

Le développement web consiste à créer des **sites web** et des **applications web**.  
Il existe deux grandes parties :

| Partie           | Rôle                                                                 |
|------------------|----------------------------------------------------------------------|
| **Frontend**     | Ce que voit l'utilisateur (interface, design, boutons, etc.)        |
| **Backend**      | Ce qui se passe derrière (base de données, logique, authentification) |

---

## 🧭 2. Comment fonctionne un site web ?

1. L'utilisateur ouvre un site (comme www.google.com)
2. Le **frontend** s'affiche (fait en HTML, CSS, JS)
3. Le frontend demande des données (par exemple : les mails)
4. Le **backend** répond avec ces données
5. Ces données sont affichées à l’utilisateur

---

## 🧱 3. Les langages de base

| Langage | Utilisation                     |
|---------|----------------------------------|
| **HTML** | Structure de la page web         |
| **CSS**  | Apparence (couleurs, position, design) |
| **JavaScript** | Dynamisme, interaction, logique |

📌 Exemple simple :

```html
<!DOCTYPE html>
<html>
  <head><title>Ma première page</title></head>
  <body>
    <h1>Bienvenue !</h1>
    <p>Ceci est mon premier site web.</p>
  </body>
</html>
```

---

## ⚒️ 4. C’est quoi un framework ?

Un **framework** est un outil qui aide le développeur à coder plus vite, avec des structures prêtes.

| Framework     | Utilisé pour          |
|---------------|------------------------|
| **React.js**  | Frontend (interface)   |
| **Express.js**| Backend (serveur)      |

---

## 💾 5. C’est quoi une base de données ?

Une base de données (comme **MongoDB**) permet de **stocker des informations**.  
Exemples de données qu'on peut stocker :
- Liste des utilisateurs
- Produits d’un site e-commerce
- Messages dans un chat

---

## 🛠️ 6. C’est quoi Visual Studio Code (VS Code) ?

C’est un **éditeur de code** (comme Word mais pour les développeurs). Il permet :
- D’écrire du code
- D’organiser ses projets
- D’ajouter des extensions utiles
- De voir les erreurs

---

## 🔄 7. Qu’est-ce que le terminal / console ?

Le **terminal** est un outil pour écrire des commandes (au lieu de cliquer).

📌 Exemple :
```bash
npm start
```
→ Lance un projet.

---

## 🔗 8. Comment les technologies travaillent ensemble ?

Voici un **exemple complet** d’une application :

```
[Utilisateur] → [Frontend - React] → [API - Express] → [Base de données - MongoDB]
```

- React affiche une interface jolie
- Express gère les requêtes (ajouter utilisateur, etc.)
- MongoDB stocke les données

---

## 🔐 9. C’est quoi une API ?

Une API (Application Programming Interface) permet à deux logiciels de **communiquer entre eux**.  
Exemple :
- Frontend demande : "Donne-moi la liste des utilisateurs"
- Backend (API) répond : "Voilà les utilisateurs"

---

## 🎓 10. Résumé visuel (mind map simple)

```
Développement Web
│
├── Frontend (React.js)
│   ├── HTML
│   ├── CSS
│   └── JS
│
├── Backend (Node.js + Express)
│   └── Gère les données, sécurité, logique
│
└── Base de données (MongoDB)
    └── Stocke les informations
```

---

## 🔄 11. C’est quoi Git et GitHub ?

### 🧠 Git : un système de version

**Git** est un outil qui permet de :

- Sauvegarder les versions de ton projet à chaque étape
- Revenir en arrière si tu fais une erreur
- Travailler en équipe sans écraser le code des autres

📌 **Git fonctionne en local** (sur ton ordinateur).

---

### ☁️ GitHub : un espace de stockage en ligne

**GitHub** est un site web qui :

- Stocke ton projet Git **en ligne**
- Te permet de **collaborer** avec d'autres développeurs
- Sert comme **portfolio** (tu peux partager ton code avec une entreprise)

---

## 🛠️ Commandes Git de base

| Commande                | Description |
|-------------------------|-------------|
| `git init`              | Créer un projet Git local |
| `git status`            | Voir les fichiers modifiés |
| `git add .`             | Préparer tous les fichiers pour commit |
| `git commit -m "msg"`   | Sauvegarder une version avec un message |
| `git remote add origin URL` | Lier ton projet local à GitHub |
| `git push -u origin main` | Envoyer le code vers GitHub |

---

## 🧪 Exemple de scénario

```bash
cd mon-projet
git init
git add .
git commit -m "Premier commit"
git branch -M main
git remote add origin https://github.com/ton-nom-utilisateur/mon-projet.git
git push -u origin main
```

---

## 🎥 Recommandation vidéo pour Git & GitHub

- [Git & GitHub expliqué simplement (FR)](https://www.youtube.com/watch?v=2ReR1YJrNOM)

---

## ✅ Résumé des rôles

| Outil     | Rôle |
|-----------|------|
| Git       | Sauvegarde les versions localement |
| GitHub    | Héberge ton code en ligne |
| VS Code   | Éditeur de code |
| Terminal  | Interface pour écrire des commandes |
