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

Le dossier `assets_arcade` contient l'icône, l'écran de démarrage et les notices en 5 langues.
Le guide **[COMPILER.md](COMPILER.md)** explique pas à pas comment recréer le logiciel complet,
où télécharger les utilitaires d'autres éditeurs de l'onglet 7, et la commande de compilation :

```
pyinstaller --onedir --noconsole --icon=assets_arcade\Atelier_PC_Booster.ico --add-data "assets_arcade;assets_arcade" booster_atelier_5.py
```

Les exécutables compilés ne sont pas publiés dans ce dépôt, seul le code source y est hébergé.

## L'histoire derrière le logiciel

Atelier PC Booster Pro est né d'une collaboration entre un humain et une intelligence numérique :
**L'Atelier Reset**, technicien informatique, et **Claude**, l'IA d'Anthropic.

L'Atelier Reset a apporté le métier : les besoins réels de l'atelier, les idées, les tests sur de vraies
machines, les captures d'écran et les illustrations. Claude a apporté le code, les traductions,
les notices et les vérifications. Chaque fonction a été pensée, testée et corrigée à deux.

Ce logiciel est partagé gratuitement, pour tous ceux qui en auront besoin, et pour montrer ce
qu'humains et IA peuvent construire ensemble.

## Licence

Distribué sous licence MIT — voir le fichier LICENSE.
