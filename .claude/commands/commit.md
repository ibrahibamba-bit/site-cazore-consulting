# /commit

> Commande pour sauvegarder l'état du workspace dans Git.

---

## Mission

Quand je lance `/commit`, exécute la séquence suivante :

### Étape 1 : Vérifier que Git est initialisé

Vérifie si le dossier courant est un dépôt Git.

- Si ce n'est pas le cas, initialise Git : `git init`
- Si le `.gitignore` est présent, il sera respecté automatiquement

### Étape 2 : Voir ce qui a changé

Lance `git status` pour lister tous les fichiers modifiés, ajoutés ou supprimés.

Présente-moi un résumé lisible :

```
Voici ce qui va être sauvegardé :

Nouveaux fichiers :
- [liste]

Fichiers modifiés :
- [liste]

Fichiers supprimés :
- [liste]
```

Si aucun changement n'est détecté, annonce-le et arrête la commande.

### Étape 3 : Proposer un message de commit

Analyse les changements et propose un message de commit clair et en français.

Format du message :
```
[type] : [description courte de ce qui a changé]
```

Types possibles :
- `init` : première mise en place
- `feat` : nouvelle fonctionnalité ou nouveau contenu
- `update` : mise à jour d'un fichier existant
- `fix` : correction d'une erreur
- `structure` : réorganisation, renommage, déplacement

Exemple :
```
Message de commit proposé :
"feat : ajout des dossiers livrables et gestion des secrets"

Tu valides, ou tu veux modifier le message ?
```

### Étape 4 : Exécuter le commit

Une fois le message validé :

1. `git add .` pour stager tous les fichiers (hors exclusions `.gitignore`)
2. `git commit -m "[message validé]"`

### Étape 5 : Confirmer

Annonce le résultat :

```
Sauvegarde effectuée.

Commit : "[message]"
Fichiers sauvegardés : [nombre]

Ton workspace est sauvegardé localement.
```

---

## Règles importantes

- Ne jamais commiter `.env` (il est dans `.gitignore`, mais le vérifier visuellement avant)
- Si un fichier sensible apparaît dans `git status`, alerter immédiatement avant de continuer
- Toujours présenter le résumé des changements et le message proposé avant d'exécuter
- Communication en français systématique
- Pas de tirets longs (em dashes) dans les réponses
