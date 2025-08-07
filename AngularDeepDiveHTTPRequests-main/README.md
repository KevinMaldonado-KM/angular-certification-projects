
# 📦 Angular Deep Dive – HTTP Requests & Error Handling

Projet Angular développé dans le cadre de la section "Sending HTTP Requests & Handling Responses" de la formation _The Complete Guide (2025 Edition)_.

## 🎯 Objectif
Mettre en œuvre les concepts fondamentaux liés aux requêtes HTTP avec Angular :
- Communication avec un backend (Node/Express mocké)
- Chargement dynamique des données via `HttpClient`
- Ajout et suppression optimiste avec rollback en cas d’erreur
- Gestion des erreurs centralisée avec un `ErrorService`
- Utilisation des signaux (`signal`, `inject`) pour stocker localement les données
- Architecture modulaire avec services dédiés (`PlacesService`)

## 🔍 Fonctionnalités
- 📥 **GET** des lieux disponibles et des lieux favoris utilisateur
- ➕ **PUT** pour ajouter un lieu aux favoris (optimistic update)
- 🗑️ **DELETE** pour retirer un lieu des favoris (optimistic update + rollback)
- ⚠️ Gestion des erreurs via interception des requêtes échouées
- ⏳ Fallback de chargement pendant les appels HTTP
- 🔁 Rechargement dynamique via `pipe`, `tap`, `catchError` de RxJS

---

## 🖼️ Aperçu de l’application

![Aperçu du projet](public/screenshot.png)

---

## 🧱 Stack
- Angular 18 (standalone components, signal, inject)
- RxJS (`tap`, `catchError`, `throwError`)
- HttpClientModule
- Node.js pour mocker une API REST

## 🚀 Lancement
```bash
npm install
npm run start
```
⚠️ Le backend doit être démarré séparément dans `/backend`.

---

## 🔗 Liens utiles

- [👉 Formation Udemy](https://www.udemy.com/course/the-complete-guide-to-angular-2/)
- [👤 Mon profil LinkedIn](https://www.linkedin.com/in/kevin-maldonado-km)
