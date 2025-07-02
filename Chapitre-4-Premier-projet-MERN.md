
# 📦 Chapitre 4 – Premier projet MERN (React + Node.js + Express + MongoDB) : Pas à pas

---

## 🎯 Objectif du chapitre

Créer une application web simple de gestion d’utilisateurs (CRUD) en utilisant la **stack MERN** :

- **MongoDB** : Base de données
- **Express.js** : Serveur backend
- **React.js** : Interface utilisateur
- **Node.js** : Environnement d'exécution JS

---

## 🧱 Étape 1 – Créer le backend avec Node.js + Express

### 📁 Structure recommandée :

```
backend/
├── models/
│   └── User.js
├── routes/
│   └── users.js
├── .env
├── server.js
├── package.json
```

### ✅ Étapes :

1. Créer un dossier `backend`
2. Initialiser le projet :
   ```bash
   npm init -y
   ```
3. Installer les dépendances :
   ```bash
   npm install express mongoose cors dotenv
   npm install --save-dev nodemon
   ```
4. Créer un fichier `server.js` :
   ```js
   const express = require('express');
   const mongoose = require('mongoose');
   const cors = require('cors');
   require('dotenv').config();

   const app = express();
   app.use(cors());
   app.use(express.json());

   mongoose.connect(process.env.MONGO_URI)
     .then(() => console.log('MongoDB connecté'))
     .catch((err) => console.error(err));

   app.use('/api/users', require('./routes/users'));

   const PORT = process.env.PORT || 5000;
   app.listen(PORT, () => console.log(`Serveur en écoute sur le port ${PORT}`));
   ```

5. Créer un modèle `models/User.js` :
   ```js
   const mongoose = require('mongoose');

   const UserSchema = new mongoose.Schema({
     name: String,
     email: String
   });

   module.exports = mongoose.model('User', UserSchema);
   ```

6. Créer les routes CRUD dans `routes/users.js` :
   ```js
   const express = require('express');
   const router = express.Router();
   const User = require('../models/User');

   router.get('/', async (req, res) => {
     const users = await User.find();
     res.json(users);
   });

   router.post('/', async (req, res) => {
     const newUser = new User(req.body);
     const savedUser = await newUser.save();
     res.json(savedUser);
   });

   router.put('/:id', async (req, res) => {
     const updatedUser = await User.findByIdAndUpdate(req.params.id, req.body, { new: true });
     res.json(updatedUser);
   });

   router.delete('/:id', async (req, res) => {
     await User.findByIdAndDelete(req.params.id);
     res.json({ message: 'Utilisateur supprimé' });
   });

   module.exports = router;
   ```

7. Fichier `.env` :
   ```
   MONGO_URI=mongodb://localhost:27017/mern-users
   ```

8. Ajouter un script dans `package.json` :
   ```json
   "scripts": {
     "start": "nodemon server.js"
   }
   ```

9. Lancer le backend :
   ```bash
   npm start
   ```

---

## 🎨 Étape 2 – Créer le frontend avec React.js

1. Créer un dossier `frontend` :
   ```bash
   npx create-react-app frontend
   cd frontend
   npm install axios
   ```

2. Créer un composant `UserList.js` :
   ```js
   import axios from 'axios';
   import { useEffect, useState } from 'react';

   export default function UserList() {
     const [users, setUsers] = useState([]);

     useEffect(() => {
       axios.get('http://localhost:5000/api/users')
         .then(res => setUsers(res.data));
     }, []);

     return (
       <div>
         <h2>Liste des utilisateurs</h2>
         <ul>
           {users.map(user => (
             <li key={user._id}>{user.name} - {user.email}</li>
           ))}
         </ul>
       </div>
     );
   }
   ```

3. Ajouter ce composant dans `App.js` :
   ```js
   import './App.css';
   import UserList from './UserList';

   function App() {
     return (
       <div className="App">
         <h1>Mon premier projet MERN</h1>
         <UserList />
       </div>
     );
   }

   export default App;
   ```

4. Lancer le frontend :
   ```bash
   npm start
   ```

---

## 🔁 Étape 3 – Tester l’application

- Lancer MongoDB localement
- Lancer le backend :
  ```bash
  cd backend
  npm start
  ```
- Lancer le frontend :
  ```bash
  cd frontend
  npm start
  ```
- Ouvrir [http://localhost:3000](http://localhost:3000)

---

## 📌 Résumé

✔ Backend avec Node.js + Express + MongoDB  
✔ Frontend React.js qui appelle l’API  
✔ Connexion Axios vers le backend  
✔ Affichage des données MongoDB dans React

---

## 🎥 Vidéos recommandées

- [Projet MERN complet étape par étape (FR)](https://www.youtube.com/watch?v=7CqJlxBYj-M)
- [Créer une API Node.js avec Express et MongoDB (FR)](https://www.youtube.com/watch?v=fgTGADljAeg)

---

## 🧪 Exercice pour la stagiaire

- Ajouter un formulaire pour créer un utilisateur
- Ajouter un bouton pour supprimer un utilisateur
- Ajouter une fonction de mise à jour

---

*Ce projet est un excellent point de départ pour comprendre le fonctionnement de la stack MERN.*

