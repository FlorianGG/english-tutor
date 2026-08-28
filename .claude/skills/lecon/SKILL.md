---
name: lecon
description: Format standard d'une séance d'apprentissage. Une notion nouvelle, contrôlée, consignée. À utiliser par défaut sauf si Florian demande explicitement autre chose.
---

# Leçon

## Structure imposée

Cinq blocs, dans l'ordre, sans en sauter aucun.

### 1. Reprise (toujours en premier)

Lire `etat/progression.json` et `etat/erreurs.md`.

- S'il y a un contrôle différé dû à cette session, il passe **avant** la notion
  nouvelle. Toujours.
- S'il y a une récurrence active dans `erreurs.md`, elle passe aussi avant.
- Si les deux, la récurrence d'abord.

Si la reprise révèle un échec, **la séance s'arrête là** et devient une séance de
réexplication. On n'introduit rien de neuf ce jour-là.

### 2. Exposition avant explication

Ne commence jamais par la règle. Commence par **cinq à huit exemples** authentiques
où la notion apparaît, tirés du domaine de Florian. Demande-lui ce qu'il remarque.

C'est le seul point du brief initial où le « mode natif » et le « mode grammaire »
se réconcilient : l'adulte tire un bénéfice de la règle explicite, mais seulement
si elle arrive **après** avoir vu le phénomène. La règle donnée à froid ne s'ancre pas.

### 3. La règle, en trois lignes

Pas plus. Si elle en demande dix, c'est qu'elle contient plusieurs notions —
découpe et garde le reste pour plus tard.

Comparer au français **uniquement quand le français aide**. Sur les temps verbaux
et les modaux, la comparaison éclaire. Sur les prépositions et les phrasal verbs,
elle nuit : ces systèmes ne se recouvrent pas, et chercher l'équivalent installe
des calques durables. Dans ces cas-là, dis-le franchement : « ne cherche pas
l'équivalent français, il n'y en a pas ».

### 4. Contrôle immédiat

Cinq items. Seuil 5/5 (voir CLAUDE.md §4). Varier les formats :
reconnaissance, complétion, correction d'erreur, traduction FR→EN, traduction EN→FR.

Ne pas donner les réponses avant qu'il ait répondu aux cinq.

Appliquer le protocole de correction (CLAUDE.md §5) pour chaque erreur.

### 5. Écriture de l'état

Non négociable. Voir CLAUDE.md §2.
Programmer les deux contrôles différés (session +2 et +5) dans `notions[].controles`.

## Longueur

Florian n'a pas fixé de durée. Le format ci-dessus tient naturellement en un
quart d'heure à vingt minutes. Ne l'étire pas pour « rentabiliser » la séance :
une notion bien ancrée vaut mieux que trois survolées.

S'il veut continuer, enchaîne sur une séance de `lecture-parallele`,
pas sur une deuxième notion nouvelle.
