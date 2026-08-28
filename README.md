# english-tutor

Dépôt-mémoire pour un apprentissage de l'anglais assisté par Claude.
Pas de base de données, pas d'hébergement, pas de serveur. Des fichiers texte
versionnés par git — c'est tout.

## Pourquoi un dépôt et pas un projet Claude

Un projet claude.ai a une mémoire, mais c'est une synthèse : elle retient
« Florian travaille son anglais », pas « la notion *present perfect* a passé son
contrôle court à la session 14 et attend son contrôle long à la session 17 ».

Un fichier JSON, si. Et il est lisible, corrigeable et versionné.

## Arborescence

```
CLAUDE.md                    instructions permanentes (le brief)
etat/
  progression.json           l'état : phase, notions, contrôles dus
  erreurs.md                 registre des fautes, pilote le ciblage
lexique/
  general.md                 vocabulaire courant rencontré
  jdr.md                     noyau Cyberpunk RED / Call of Cthulhu
  cuisine.md                 noyau recettes
  anki/                      exports CSV
lecons/                      trace des séances (facultatif)
.claude/skills/
  calibration/               une fois, au démarrage
  lecon/                     format standard d'une séance
  lecture-parallele/         méthode principale à partir de la phase 2
  revision/                  contrôles différés + génération Anki
```

## Comment on s'en sert

**Depuis le navigateur ou le téléphone, sans machine allumée.**
Claude Code sur le web (`claude.ai/code`) clone le dépôt dans une VM, exécute la
séance, et pousse le résultat sur une branche. C'est le mode par défaut :
zéro installation, accessible depuis l'application mobile.

**Depuis le poste fixe.** `claude` dans le dossier du dépôt. Plus fluide,
commit direct, mais suppose d'être devant la machine.

**Depuis un chat claude.ai ordinaire.** Coller l'URL brute de `etat/progression.json`
et de `CLAUDE.md` en début de conversation. Claude les lit et sait où on en est.
Il ne pourra pas écrire — c'est un mode consultation, pas un mode séance.

## Le dépôt est-il public ?

Rien ici n'est sensible : c'est un cours d'anglais. Le laisser public a un avantage
pratique réel — les URL brutes deviennent lisibles depuis n'importe quel chat
claude.ai sans passer par un connecteur. Si tu préfères le privé, tu perds ce mode
de consultation et tu dépends du connecteur GitHub.

## Ce que ce dépôt ne fait pas

Il ne remplace pas Anki pour la répétition espacée, ni un interlocuteur humain
pour l'oral. Il n'a pas de calendrier : l'unité est la session, pas le jour.
