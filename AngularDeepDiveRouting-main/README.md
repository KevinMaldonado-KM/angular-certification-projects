# 🚀 Angular Deep Dive – Routing

Projet Angular développé dans le cadre de la section "Routing" de la formation _The Complete Guide (2025 Edition)_.

## 🎯 Objectif
Mettre en œuvre les concepts fondamentaux liés au routage Angular :
- Configuration de **routes principales et enfants** avec paramètres dynamiques
- **Lazy Loading** avec `loadChildren` pour optimiser les performances
- Utilisation des **guards** (`CanMatch`, `CanDeactivate`) pour protéger les routes
- **Resolvers** pour charger des données avant l'affichage des composants
- Navigation programmatique avec le service `Router`
- Gestion des **paramètres de route** et **query parameters**
- **Providers** au niveau des routes pour l'injection de services
- Composants dédiés (`UserTasksComponent`, `TasksComponent`, `NewTaskComponent`)
- Utilisation des signaux et de l'injection de dépendances Angular (`inject`)

## 🔍 Fonctionnalités

### 👥 Gestion des utilisateurs
- ✅ Liste d'utilisateurs avec navigation dynamique
- 🔄 Paramètres de route pour identifier l'utilisateur sélectionné
- 📊 Résolution du nom d'utilisateur via `resolveUserName`
- 🎭 Affichage conditionnel basé sur l'utilisateur actif

### 📋 Gestion des tâches
- 📝 Affichage des tâches par utilisateur avec `resolveUserTasks`
- ➕ Création de nouvelles tâches avec formulaire dédié
- 🛡️ Guard `canLeaveEditPage` pour éviter la perte de données
- 🔍 Navigation entre les différentes vues de tâches
- ⚠️ Composant "No Task" par défaut quand aucune tâche n'est sélectionnée

### 🛡️ Sécurité et navigation
- 🚦 Guard `dummyCanMatch` pour contrôler l'accès aux routes
- 🔀 Redirections automatiques vers des routes par défaut
- 🚫 Page "Not Found" pour les routes inexistantes
- 📊 Gestion des données via `data` et `resolve`

### ⚡ Optimisation des performances
- 🚀 **Lazy Loading** avec `loadChildren` pour charger les modules à la demande
- 📦 Injection de services au niveau des routes avec `providers`
- 🔄 Stratégie `runGuardsAndResolvers: 'always'` pour la réactivité

## 🧩 Concepts techniques mis en œuvre

### Configuration des routes
```typescript
export const routes: Routes = [
  {
    path: '', 
    component: NoTaskComponent,
    title: 'No task selected',
  },
  {
    path: 'users/:userId',
    component: UserTasksComponent,
    loadChildren: () =>
      import('./users/users.route').then((mod) => mod.routes),
    canMatch: [dummyCanMatch],
    resolve: {
      userName: resolveUserName
    },
    title: resolveTitle,
  },
  {
    path: '**',
    component: NotFoundComponent,
  },
];
```

### Lazy Loading et Providers
```typescript
// Routes enfants avec providers injectés
export const routes: Routes = [
  {
    path: '',
    providers: [TasksService], // Service disponible pour cette route et ses enfants
    children: [
      {
        path: 'tasks',
        component: TasksComponent,
        runGuardsAndResolvers: 'always',
        resolve: {
          userTasks: resolveUserTasks,
        },
      },
      // ...
    ],
  },
];
```

### Guards et Resolvers
```typescript
// Guard pour protéger l'accès aux routes
const dummyCanMatch: CanMatchFn = (route, segments) => {
  const router = inject(Router);
  const shouldGetAccess = Math.random();
  if(shouldGetAccess < 1){
    return true;
  }
  return new RedirectCommand(router.parseUrl('/unauthorized'));
}

// Guard pour éviter de quitter une page sans sauvegarder
export const canLeaveEditPage: CanDeactivateFn<NewTaskComponent> = (component) => {
  return component.submitted || confirm('Do you really want to leave?');
};
```

### Navigation et état
- 🔄 Navigation programmatique avec `Router.navigate()`
- 📊 Récupération des paramètres avec `ActivatedRoute`
- 🗂️ Services pour la gestion de l'état (`TasksService`, `UsersService`)
- ⚡ **Lazy Loading** pour optimiser le temps de chargement initial
- 🏪 Persistance des données dans `localStorage` avec signaux

---

## 🧱 Stack
- Angular 18 (standalone components, signals, inject)
- Angular Router (routes, guards, resolvers)
- RxJS pour la gestion asynchrone
- TypeScript avec types stricts

## 🚀 Lancement
```bash
npm install
npm start
```

L'application sera accessible sur `http://localhost:4200`

---

## 🔗 Liens utiles

- [👉 Formation Udemy](https://www.udemy.com/course/the-complete-guide-to-angular-2/)
- [👤 Mon profil LinkedIn](https://www.linkedin.com/in/kevin-maldonado-km)
