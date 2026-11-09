# Guide de Contribution — Gitrunner

> Ce guide explique comment proposer du code sur ce repo **sans avoir besoin d'être collaborateur**.
> Tu vas utiliser le workflow standard de l'open source : le **Fork**.

---

## 1. Fork le repo

1. Va sur la page du repo : `https://github.com/MetaphorSuit/Gitrunner`
2. Clique sur le bouton **Fork** (coin supérieur droit)
3. GitHub crée une copie du repo sur **ton compte** : `github.com/TON-USERNAME/Gitrunner`

---

## 2. Clone ton fork (pas le repo original)

```bash
# Remplace TON-USERNAME par ton pseudo GitHub
git clone git@github.com:TON-USERNAME/Gitrunner.git
cd Gitrunner
```

---

## 3. Ajouter le repo original comme "upstream" (optionnel mais recommandé)

Cela permet de récupérer les mises à jour du professeur plus tard.

```bash
git remote add upstream git@github.com:MetaphorSuit/Gitrunner.git
git fetch upstream
```

Vérifie :
```bash
git remote -v
```
Tu dois voir :
- `origin` → ton fork
- `upstream` → le repo original

---

## 4. Créer une branche pour ton travail

**Ne travaille jamais sur `main`.** Crée une branche dédiée :

```bash
git checkout -b feature/ton-prenom-nom-exercice
```

Exemples de noms de branches :
- `feature/jean-dupont-atelier-1`
- `fix/marie-curie-correction-readme`

---

## 5. Faire tes modifications et committer

```bash
# Voir ce qui a changé
git status

# Ajouter tes fichiers
git add .

# Committer avec un message clair
git commit -m "feat: description de ce que tu as fait"
```

### Convention de messages de commit (optionnel mais pro)

| Préfixe | Usage |
|---------|-------|
| `feat:` | Nouvelle fonctionnalité |
| `fix:` | Correction de bug |
| `docs:` | Documentation |
| `style:` | Mise en forme (indentation, espaces...) |
| `refactor:` | Refactorisation sans changement de comportement |
| `test:` | Ajout de tests |

---

## 6. Pousser ta branche sur ton fork

```bash
git push -u origin feature/ton-prenom-nom-exercice
```

> Si tu as fait plusieurs commits et que tu veux "nettoyer" ton historique avant de pousser, demande au professeur. Ne fais pas de `force push` sans savoir ce que tu fais.

---

## 7. Ouvrir une Pull Request (PR)

1. Retourne sur **ton fork** GitHub (`github.com/TON-USERNAME/Gitrunner`)
2. GitHub affiche un bandeau jaune : **"Compare & pull request"**
3. Clique dessus
4. Vérifie les infos :
   - **base repository** : `MetaphorSuit/Gitrunner`
   - **base** : `main`
   - **head repository** : `TON-USERNAME/Gitrunner`
   - **compare** : `feature/ton-prenom-nom-exercice`
5. Donne un titre clair à ta PR
6. Décris brièvement ce que tu as fait dans la description
7. Clique sur **Create pull request**

---

## 8. Après la PR

- Le professeur va **review** ton code
- Il peut demander des modifications : tu les fais sur ta branche locale, tu commit, tu push → la PR se met à jour automatiquement
- Quand tout est bon, il merge ta PR dans le repo original
- Tu peux ensuite supprimer ta branche

```bash
git checkout main
git branch -d feature/ton-prenom-nom-exercice
```

---

## 9. Synchroniser ton fork (plus tard)

Si le repo original a évolué et que tu veux récupérer les dernières mises à jour :

```bash
git fetch upstream
git checkout main
git rebase upstream/main
# OU si tu préfères merger :
# git merge upstream/main

git push origin main
```

---

## Récap en un schéma

```
┌─────────────────────┐         Fork          ┌─────────────────────┐
│   MetaphorSuit      │  ─────────────────►   │      TOI            │
│    /Gitrunner       │                       │   /Gitrunner        │
│    main (protégée)  │ ◄────────────────────   │   main              │
└─────────────────────┘     Pull Request      │   feature/xxx       │
       ▲                                      └─────────────────────┘
       │                                               │
       └────────── Le prof merge ta PR ────────────────┘
```

---

## En cas de problème

| Erreur | Solution |
|--------|----------|
| `Permission denied (publickey)` | Ta clé SSH n'est pas configurée. Vérifie `~/.ssh/id_ed25519.pub` sur GitHub. |
| `403 Forbidden` | Tu essaies de push sur le repo original. Vérifie que `origin` pointe bien sur **ton fork** (`git remote -v`). |
| `merge conflict` | Rebase ta branche sur `upstream/main` ou demande de l'aide au professeur. |

---

Bon courage ! 🚀
