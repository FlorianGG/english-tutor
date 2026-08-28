---
name: calibration
description: Établir le niveau réel de départ avant toute leçon. À lancer une seule fois, quand progression.json est en phase 0. Produit une estimation par compétence, jamais un score certifié.
---

# Calibration

## Pourquoi

Florian se déclare débutant absolu. C'est très probablement faux : francophone
adulte, joueur de Cyberpunk 2077, lecteur de documentation technique. Il a
certainement un vocabulaire passif important et une grammaire résiduelle scolaire.
Commencer à zéro lui ferait perdre des mois sur des choses qu'il sait déjà.

À l'inverse, surestimer son niveau le mettrait en échec dès la deuxième séance.
L'objet de cette calibration est de trancher sur des preuves, pas sur une déclaration.

## Déroulé

Quatre blocs, dans cet ordre. Ne pas annoncer les niveaux visés.

**Bloc 1 — Reconnaissance passive.**
20 mots isolés, difficulté croissante, mélangeant vocabulaire général et
vocabulaire de domaine (JDR, cuisine). Demander la traduction ou « je ne sais pas ».
Compter les « je ne sais pas » comme information, pas comme échec.

**Bloc 2 — Déchiffrage.**
Trois phrases de longueur croissante, tirées de registres différents
(une phrase de règle de JDR, une instruction de recette, une phrase narrative).
Demander le sens global, pas une traduction mot à mot.

**Bloc 3 — Sensibilité grammaticale.**
Six paires de phrases dont une est agrammaticale. Lui demander laquelle sonne faux,
sans demander pourquoi. Cela teste l'intuition acquise, pas la règle apprise.

**Bloc 4 — Production minimale.**
Trois phrases françaises courtes à traduire. C'est le bloc le plus révélateur :
les calques du français y apparaissent immédiatement.

## Sortie

Écrire dans `etat/progression.json` :

- `niveau_estime.lecture`, `.vocabulaire_general`, `.grammaire` : une valeur sur
  l'échelle CEFR (A1 à C2), assortie d'une marge (`"A2, possiblement A2+"`).
- `niveau_estime.fiabilite` : toujours renseigné honnêtement. Une calibration de
  30 questions ne vaut pas un test certifié. Le dire à Florian explicitement.
- `phase` : passer à 1 ou 2 selon le résultat.
- Les erreurs du bloc 4 vont dans `etat/erreurs.md`.

Puis proposer à Florian de confirmer avec un test de positionnement externe
(gratuit, en ligne) s'il veut un point de repère indépendant du tien.
