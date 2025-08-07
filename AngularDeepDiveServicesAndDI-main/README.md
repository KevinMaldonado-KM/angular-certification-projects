
# 🧠 Mini-Projet Angular – Services & Injection de Dépendances

Projet réalisé dans le cadre de la section _"Services & Dependency Injection – Deep Dive"_ de la formation **Angular - The Complete Guide (2025 Edition)** de Maximilian Schwarzmüller (Udemy).

🎯 **Objectif** : comprendre comment externaliser et réutiliser la logique métier avec des services Angular, et maîtriser les différents mécanismes d’injection de dépendances.

---

## 🧠 Concepts Angular mis en œuvre

- Création de services Angular (`LoggerService`, `AuthService`, etc.)
- Injection de dépendances dans les composants (`@Injectable`, injection dans le constructeur)
- Fourniture de services via `providedIn`, `@Inject()`, ou `providers[]`
- Différences entre injecteurs (root vs élément)
- Réutilisation de logique partagée entre composants
- Injection de valeurs personnalisées (`InjectionToken`, objets statiques, non-classes)
- Composition de services : un service injecté dans un autre
- Analyse du comportement des injecteurs via les DevTools Angular
- Utilisation de `NgModule` vs Standalone API pour les providers

---

## 📂 Structure du projet

```
src/
├── app/
│   ├── services/
│   │   ├── logger.service.ts          # Service de log personnalisé
│   │   ├── auth.service.ts            # Simule une authentification
│   │   ├── config.token.ts            # InjectionToken pour la configuration
│   ├── components/
│   │   ├── login/
│   │   └── header/
│   ├── app.component.ts
│   └── app.config.ts
```

---

## 🧰 Technologies utilisées

- Angular 18
- TypeScript
- Standalone Components
- Angular CLI
- HTML/CSS

---

## 🚀 Lancer l’application

```bash
npm install
ng serve
```

Accès à l’application : [http://localhost:4200](http://localhost:4200)

---

## 📌 Remarques

> Ce projet est purement didactique et sert à illustrer les mécanismes fondamentaux de l’injection de dépendances dans Angular, ainsi que la structuration des services dans une application modulaire.

---

## 🔗 Liens utiles
- 👤 [Mon profil LinkedIn](https://www.linkedin.com/in/kevin-maldonado-km)
- 📘 [Formation Udemy – Angular](https://www.udemy.com/course/the-complete-guide-to-angular-2/)
- 🧠 [Documentation Angular – DI](https://angular.io/guide/dependency-injection)
