# Compiler Atelier PC Booster Pro soi-même

Ce dépôt contient tout ce qu'il faut pour recréer le logiciel : le script, l'icône, l'écran de
démarrage et les notices en 5 langues. Les seuls éléments absents sont les **utilitaires d'autres
éditeurs** (onglet 7) : ils ne nous appartiennent pas, leur licence interdit souvent de les
redistribuer, et ce sont des exécutables. Chacun se télécharge gratuitement sur le site officiel
de son éditeur (liste plus bas).

> Le logiciel fonctionne sans ces utilitaires : seul le bouton correspondant de l'onglet 7
> signalera que le fichier est introuvable.

## 1. Préparer Windows

1. Installer **Python 3.14** depuis [python.org](https://www.python.org/downloads/windows/)
   en cochant **« Add python.exe to PATH »**.
2. Ouvrir une invite de commandes et installer les dépendances :
   ```
   pip install customtkinter pillow pyinstaller
   ```

## 2. Récupérer le dépôt

Bouton vert **Code → Download ZIP** sur GitHub, puis extraire l'archive. On obtient :

```
booster_atelier_5.py
assets_arcade\
    Atelier_PC_Booster.ico
    splashscreen.jpg
    Notice_FR.pdf  Notice_EN.pdf  Notice_DE.pdf  Notice_ES.pdf  Notice_IT.pdf
```

## 3. Les utilitaires de l'onglet 7 (facultatif)

**Le plus simple : ne rien faire.** Dans l'onglet 7, chaque outil indique son état :
✅ en vert s'il est présent, bouton orange **📥 Télécharger** si le logiciel peut le récupérer
tout seul, bouton gris **🌐 Page officielle** sinon. Au premier clic, le logiciel télécharge la
dernière version depuis le site officiel de l'éditeur (après votre accord), la range dans
`assets_arcade` et la lance. Pour les éditeurs sans lien direct, il ouvre la page officielle et
indique où placer le fichier. Le nom exact du dossier ou de la version n'a pas d'importance.

Pour un exécutable complet dès la compilation, on peut aussi placer les outils à l'avance dans
`assets_arcade` (colonne « Au premier clic » : 📥 = téléchargement automatique, 🌐 = page officielle) :

| Outil | Chemin attendu dans `assets_arcade` | Au premier clic | Site officiel |
|---|---|---|---|
| Malwarebytes AdwCleaner | `Malwarebytes AdwCleaner.exe` | 📥 | [malwarebytes.com/adwcleaner](https://www.malwarebytes.com/adwcleaner) |
| CrystalDiskInfo | `CrystalDiskInfo\DiskInfo64.exe` | 📥 | [crystalmark.info](https://crystalmark.info/en/download/#CrystalDiskInfo) |
| BleachBit Portable | `BleachBit\bleachbit.exe` | 📥 | [bleachbit.org](https://www.bleachbit.org/download/windows) |
| Autoruns (Sysinternals) | `Autoruns\Autoruns64.exe` | 📥 | [learn.microsoft.com](https://learn.microsoft.com/sysinternals/downloads/autoruns) |
| HWMonitor (CPUID) | `HWMonitor\HWMonitor_x64.exe` | 📥 | [cpuid.com](https://www.cpuid.com/softwares/hwmonitor.html) |
| CPU-Z (CPUID) | `cpuz\cpuz_x64.exe` | 📥 | [cpuid.com](https://www.cpuid.com/softwares/cpu-z.html) |
| GPU-Z | `GPU-Z.2.71.0.exe` | 🌐 | [techpowerup.com](https://www.techpowerup.com/gpuz/) |
| Display Driver Uninstaller | `Display Driver Uninstaller\DDU v18.1.6.1\Display Driver Uninstaller.exe` | 📥 | [wagnardsoft.com](https://www.wagnardsoft.com/display-driver-uninstaller-DDU-) |
| WirelessKeyView (NirSoft) | `WirelessKeyView\WirelessKeyView.exe` | 🌐 | [nirsoft.net](https://www.nirsoft.net/utils/wireless_key.html) |
| Process Explorer (Sysinternals) | `ProcessExplorer\procexp64.exe` | 📥 | [learn.microsoft.com](https://learn.microsoft.com/sysinternals/downloads/process-explorer) |
| TCPView (Sysinternals) | `tcpview\tcpview64.exe` | 📥 | [learn.microsoft.com](https://learn.microsoft.com/sysinternals/downloads/tcpview) |
| MiniTool Partition Wizard (portable) | `MiniTool Partition Magic\partitionwizard.exe` | 📥 | [partitionwizard.com](https://www.partitionwizard.com/free-partition-manager.html) |
| BlueScreenView (NirSoft) | `BlueScreenView\BlueScreenView.exe` | 📥 | [nirsoft.net](https://www.nirsoft.net/utils/blue_screen_view.html) |

Onglet 8 : tous les runtimes et lanceurs, Epic Games Launcher compris, s'installent
automatiquement par winget. Rien à placer dans `assets_arcade`.

> Une version plus récente (autre numéro de version, autre nom de dossier) est reconnue
> automatiquement : inutile de renommer.
> Certains antivirus signalent à tort WirelessKeyView (outil de récupération de mots de passe Wi-Fi) :
> c'est pourquoi il n'est volontairement pas téléchargé automatiquement.
> Les téléchargements automatiques viennent uniquement des sites des éditeurs ; pour DDU, l'empreinte
> SHA-256 publiée par Wagnardsoft est vérifiée avant toute décompression.
> MiniTool : utilisez la version portable ; l'installateur ajoute MiniTool ShadowMaker et des services Windows.

## 4. Compiler

Dans le dossier qui contient `booster_atelier_5.py` :

```
pyinstaller --onedir --noconsole --icon=assets_arcade\Atelier_PC_Booster.ico --add-data "assets_arcade;assets_arcade" booster_atelier_5.py
```

Le logiciel se trouve ensuite dans `dist\booster_atelier_5\` : lancer
`booster_atelier_5.exe` **en tant qu'administrateur**. Tout le dossier doit rester ensemble.

> Votre antivirus peut signaler l'exécutable compilé : c'est une fausse alerte fréquente avec
> PyInstaller et les logiciels qui utilisent les outils d'administration de Windows. Le code
> source complet est dans ce dépôt, chacun peut le vérifier.

---

## Building it yourself (English summary)

1. Install Python 3.14 (tick "Add python.exe to PATH"), then `pip install customtkinter pillow pyinstaller`.
2. Download this repository (Code → Download ZIP) and extract it.
3. Optional: nothing to do — in tab 7, the software downloads 11 of the 13 tools from their official
   websites on first click (with your consent) and opens the official page for the others.
   You can also place them in `assets_arcade` beforehand, using the paths shown in the table.
4. Build with the `pyinstaller` command above, then run `dist\booster_atelier_5\booster_atelier_5.exe` as administrator.
