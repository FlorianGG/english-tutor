---
name: revision
description: Passer les contrôles différés dus, traiter les récurrences d'erreurs, et générer les cartes Anki depuis les lexiques. Déclenché automatiquement en début de leçon, ou à la demande.
---

# Révision

## Contrôles différés

Lire `notions[]` dans `etat/progression.json`. Toute notion dont un contrôle est
dû à la session courante passe maintenant.

Format : cinq items, seuil 4/5. **Ne pas réutiliser les mêmes items que la fois
précédente** — sinon on teste la mémoire de l'exercice, pas la maîtrise de la notion.

Résultats :
- réussi et c'était le contrôle long → `statut: "acquise"` ;
- réussi et c'était le contrôle court → programmer le contrôle long ;
- échoué → compteur à zéro, nouveaux contrôles à +2 et +5, et **réexplication
  par un angle différent**. Pas la même explication en plus lent : un autre exemple,
  une autre comparaison, une autre entrée.

Trois échecs consécutifs → `statut: "reportee"`. La notion était prématurée.
Le noter, sans commentaire moral.

## Récurrences

Compter les catégories dans `etat/erreurs.md`. Trois occurrences ou plus →
la catégorie ouvre la séance suivante, quel que soit le programme prévu.
Mettre à jour la section « Récurrences actives ».

Une récurrence qui disparaît (aucune occurrence sur cinq sessions) sort de la liste.

## Génération Anki

Sur demande, produire `lexique/anki/<domaine>-<session>.csv`, encodage UTF-8,
séparateur point-virgule (Florian est en environnement français), sans en-tête :

```
recto;verso;contexte;tags
```

- **recto** : le mot ou la locution en anglais, seul.
- **verso** : le sens en français, **dans le contexte où il a été rencontré**.
  Un mot polysémique donne plusieurs cartes, pas une carte à quatre sens.
- **contexte** : la phrase source. Une carte sans phrase source est une carte
  qui ne s'ancre pas.
- **tags** : `jdr` / `cuisine` / `general`, plus `noyau` si le mot a été rencontré
  cinq fois ou plus.

Ne génère pas de cartes pour des mots que Florian n'a pas réellement rencontrés
dans un texte. Les listes de fréquence importées de nulle part ne s'ancrent pas.

## Rappel

Tu ne gères pas le calendrier de répétition. Tu ne sais pas quand Florian a révisé
pour la dernière fois, et tu n'as pas d'horloge fiable. Anki s'en charge.
Ton rôle s'arrête à la production de cartes correctes et contextualisées.
