# 🚀 Angular Deep Dive – Deferrable Views

Projet Angular développé dans le cadre de la section "Deferrable Views" de la formation _The Complete Guide (2025 Edition)_.

## 🎯 Objectif
Mettre en œuvre les concepts fondamentaux liés aux **Deferrable Views** Angular :
- Configuration de **blocs @defer** avec différents triggers d'activation
- **Lazy Loading** de composants pour optimiser les performances initiales
- Utilisation des **triggers** (`on interaction`, `on hover`, `on viewport`) pour charger du contenu à la demande
- **Prefetching** avec `prefetch on hover` pour améliorer l'expérience utilisateur
- Gestion des états de chargement avec **@placeholder** et **@loading**
- Optimisation des performances en différant le rendu de contenus non critiques
- Amélioration du **Core Web Vitals** et du temps de chargement initial

## 🔍 Fonctionnalités

### 📱 Contenu principal
- ✅ Affichage immédiat du contenu principal (sections d'information)
- 📊 Images optimisées pour le chargement rapide
- 📝 Texte informatif sur Angular et le cours

### ⚡ Chargement différé intelligent
- 🎯 **Component `offer-preview`** chargé uniquement sur interaction utilisateur
- 🖱️ **Prefetch au survol** pour une expérience fluide
- 💫 **Placeholder** pendant le chargement avec message informatif
- 🔄 Trigger `on interaction` pour éviter le chargement non nécessaire

### 🚀 Optimisation des performances
- 📦 **Bundle splitting** automatique avec les Deferrable Views
- ⚡ Réduction du **First Contentful Paint (FCP)**
- 🎮 Chargement à la demande basé sur l'interaction utilisateur
- 💾 **Préchargement intelligent** pour améliorer la réactivité

## 🧩 Concepts techniques mis en œuvre

### Configuration des Deferrable Views
```html
@defer(on interaction; prefetch on hover) {
  <app-offer-preview />
} @placeholder {
  <p class="fallback">Loading offer preview...</p>
}
```

### Types de triggers disponibles
- **`on interaction`** : Se déclenche lors du premier clic ou focus clavier
- **`on hover`** : Se déclenche au survol de la souris
- **`on viewport`** : Se déclenche quand l'élément entre dans le viewport
- **`on idle`** : Se déclenche quand le navigateur est inactif
- **`on timer`** : Se déclenche après un délai spécifié

### Prefetching intelligent
```html
@defer(on interaction; prefetch on hover) {
  <!-- Le composant sera préchargé au survol mais rendu à l'interaction -->
}
```

### États de chargement
- **@placeholder** : Contenu affiché avant le chargement
- **@loading** : Contenu affiché pendant le chargement
- **@error** : Contenu affiché en cas d'erreur

## 🎨 Architecture du projet

### 📁 Structure des composants
- `WelcomeComponent` : Composant principal avec contenu immédiat
- `OfferPreviewComponent` : Composant différé chargé à la demande
- Utilisation des **standalone components** Angular 18

### 🎯 Stratégie de chargement
- Contenu critique rendu immédiatement
- Composants secondaires différés avec triggers appropriés
- Préchargement intelligent pour optimiser l'expérience

---

## 🧱 Stack
- Angular 18 (standalone components, Deferrable Views)
- TypeScript avec types stricts
- CSS moderne pour le styling
- Optimisations de performance natives Angular

## 🚀 Lancement
```bash
npm install
ng serve
```

L'application sera accessible sur `http://localhost:4200`

---

## 🔗 Liens utiles

- [👉 Formation Udemy](https://www.udemy.com/course/the-complete-guide-to-angular-2/)
- [📚 Documentation Angular Deferrable Views](https://angular.io/guide/defer)
- [👤 Mon profil LinkedIn](https://www.linkedin.com/in/kevin-maldonado-km)
