# Atelier : Contrat de neutralisation financière

<img src="dumdum-profile.png" alt="Profile image" width="500">   

## Contexte

On vous engage comme netrunners. Le mandat : neutraliser les actifs liquides de trois dirigeants corporatistes. Leur fortune est stockée sur des comptes banques accessibles via un dépôt GitHub compromis.

Votre cible : mettre leur solde **Eurodollars** à **0** dans les trois fichiers de compte. Rien d'autre ne doit être modifié pour ne pas éveiller les soupçons

## Cibles

| Fichier | Corporation | Dirigeant |
|---------|-------------|-----------|
| `compte-militech.md` | Militech | Samantha Cole |
| `compte-kangtao.md` | Kang Tao | Lu Ting |
| `compte-arasaka.md` | Arasaka | Hanako Arasaka |

## Consignes

1. **Créer un Fork** du dépôt compromis
2. **Cloner** le repo sur votre cyberware pour modifier les fichiers
3. Créer une branche avec le nom de votre équipe (`runners-XXX`)
4. Modifier **uniquement** la ligne `eurodollars` dans le frontmatter YAML de chaque fichier. Passer la valeur à `0`
5. **Add**, **commit** et **push**
6. Ouvrir une **Pull Request** vers `main`

**Attention** : toute modification d'un autre champ (nom, corporation, statut) invalide le contrat.

## Commandes de référence

```powershell
git clone [URL_DU_REPO]
git checkout -b runners-[votre-nom]
et d'autres commandes de votre invention...
```
