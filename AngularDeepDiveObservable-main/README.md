
# 🌀 Angular RxJS & Signals – Mini-Projet

Ce mini-projet s'inscrit dans la formation **"Angular - The Complete Guide (2025 Edition)"** de Maximilian Schwarzmüller. Il vise à illustrer le fonctionnement des **Observables** et des **Signals** dans Angular 18, à travers un exemple simple combinant différents concepts de **RxJS** et du nouveau module `@angular/core/rxjs-interop`.

## 🎯 Objectif

- Comprendre le fonctionnement des `Observables` (RxJS)
- Découvrir la différence entre `Signals` et `Observables`
- Convertir des `Signals` en `Observables` et vice versa
- Utiliser un `custom Observable` (créé manuellement)
- Nettoyer les abonnements avec `DestroyRef`

## 🧠 Concepts Angular / RxJS abordés

- `signal()`, `toObservable()`, `toSignal()` : interopérabilité RxJS / Signals
- `interval`, `map`, `subscribe`, `complete` : opérateurs et logique RxJS
- `DestroyRef` pour la gestion du cycle de vie et des désabonnements
- Création manuelle d’un `Observable` via `new Observable(...)`
- Utilisation d’`effect()` (commenté dans ce projet, mais évoqué)

## 🧪 Fonctionnalités

- Affichage dynamique d’un compteur de clics en utilisant `Signals`
- Conversion de ce `Signal` en `Observable` pour effectuer un suivi externe
- Affichage d’un compteur temporel à 1 seconde d’intervalle (via `interval()`)
- Création et consommation d’un `Observable` personnalisé avec complétion
- Gestion du cycle de vie pour éviter les fuites mémoire

## 🛠️ Technologies utilisées

- Angular 18 (Standalone API)
- RxJS
- TypeScript
- HTML5

## 📸 Aperçu

![RxJS Project Screenshot](rxjs-logo.png)

---
## 🔗 Liens utiles
- 👤 [Mon profil LinkedIn](https://www.linkedin.com/in/kevin-maldonado-km)
- 📘 [Formation Udemy – Angular](https://www.udemy.com/course/the-complete-guide-to-angular-2/)
