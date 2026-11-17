# Atelier PC Booster Pro — v5.1.0

Boîte à outils gratuite, portable et tout-en-un pour remettre un PC Windows en forme.
Disponible en français, anglais, allemand, espagnol et italien.

## Pourquoi ce dépôt ?

Ce code source est publié par transparence : certains antivirus signalent l'exécutable
comme suspect à cause de son comportement (droits administrateur, modifications du
registre, etc.), alors qu'il ne contient aucun code malveillant. Ce dépôt permet à
quiconque de vérifier le code par soi-même, ou de le recompiler.

## Fonctionnalités principales

- Optimisation système (nettoyage, réparation SFC/DISM, cache DNS)
- Informations système complètes
- Désinstallation de bloatwares
- Surveillance de la santé des disques (S.M.A.R.T.)
- Configuration DNS prête à l'emploi
- Récupération de comptes et réinitialisation de mot de passe local
- Lanceur d'utilitaires portables pour atelier
- Installation groupée de runtimes pour jeux PC
- Diagnostic complet avec rapport client, export et import des pilotes

## Lancer depuis le code source

- Windows 10 / 11 et Python 3.14
- Dépendance : `pip install customtkinter`
- Lancer en administrateur : `python booster_atelier_5.py`

Les droits administrateur sont nécessaires pour les outils système de Windows (SFC, DISM, pnputil…).
Le logiciel ne collecte ni n'envoie aucune donnée.

## Compiler (facultatif)

```
pyinstaller --onedir --windowed booster_atelier_5.py
```

Les exécutables compilés ne sont pas publiés dans ce dépôt, seul le code source y est hébergé.

## Licence

Distribué sous licence MIT — voir le fichier LICENSE.
