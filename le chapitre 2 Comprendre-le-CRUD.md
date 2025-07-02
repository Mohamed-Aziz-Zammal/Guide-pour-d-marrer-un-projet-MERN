
# 📚 Comprendre le CRUD – Base de tout projet web

---

## 🧠 1. Qu’est-ce que CRUD ?

**CRUD** est un acronyme pour les **4 opérations de base** qu'on peut faire sur des données :

| Lettre | Signification | Action            | Exemple (utilisateur) |
|--------|---------------|-------------------|------------------------|
| C      | Create        | Ajouter            | Ajouter un utilisateur |
| R      | Read          | Lire / Consulter   | Afficher la liste des utilisateurs |
| U      | Update        | Modifier           | Modifier le profil     |
| D      | Delete        | Supprimer          | Supprimer un compte    |

---

## 💾 2. Exemple simple avec MongoDB

Imaginons une **collection "users"** dans une base de données MongoDB.

| Opération | Requête en pseudo-code |
|-----------|-------------------------|
| Create    | `db.users.insert({name: "Sara"})` |
| Read      | `db.users.find({})` |
| Update    | `db.users.updateOne({name: "Sara"}, {$set: {name: "Sonia"}})` |
| Delete    | `db.users.deleteOne({name: "Sonia"})` |

---

## 🌐 3. Exemple REST API avec Express.js

### 🛠️ Routes typiques d’un CRUD

| Méthode HTTP | Route          | Fonction        |
|--------------|----------------|-----------------|
| POST         | `/users`       | Créer un user   |
| GET          | `/users`       | Lire tous les users |
| GET          | `/users/:id`   | Lire un seul user |
| PUT          | `/users/:id`   | Modifier un user |
| DELETE       | `/users/:id`   | Supprimer un user |

---

### ✍️ Exemple Express.js

```js
const express = require('express');
const router = express.Router();
const User = require('../models/User');

// Create
router.post('/', async (req, res) => {
  const user = new User(req.body);
  await user.save();
  res.json(user);
});

// Read All
router.get('/', async (req, res) => {
  const users = await User.find();
  res.json(users);
});

// Update
router.put('/:id', async (req, res) => {
  const updated = await User.findByIdAndUpdate(req.params.id, req.body, { new: true });
  res.json(updated);
});

// Delete
router.delete('/:id', async (req, res) => {
  await User.findByIdAndDelete(req.params.id);
  res.json({ message: 'Supprimé' });
});

module.exports = router;
```

---

## 📌 4. Pourquoi comprendre CRUD est important ?

🎯 Parce que **toutes les apps** font ça :
- Une app de notes ? → ajouter/modifier/supprimer une note
- Une boutique ? → gérer les produits (CRUD)
- Une plateforme d’apprentissage ? → gérer les cours et utilisateurs (CRUD)

Donc avant même d’apprendre React ou MongoDB, il faut bien **maîtriser CRUD**.
