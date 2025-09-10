# 🚴‍♂️ STYX Analyse

**STYX Analyse** est une application de bureau développée en **Python + PyQt6**, destinée à analyser et visualiser les données de trajets dans le cadre du projet **Styx**.

---

## ✨ Fonctionnalités

- Import et gestion de sessions de trajets (`.csv`)
- Visualisation interactive avec **matplotlib**
- Statistiques et rapports automatiques
- Interface graphique en **PyQt6**
- Export et stockage de commentaires liés aux sessions
- Pour toutes vos quesitons : (lien vers [styx-projet.fr](https://styx-projet.fr/styx-analyse))

## 💻 Version macOS (fonctionnelle mais destiné a évoluer)

Une version compilée est disponible dans les **[Releases](https://github.com/Axel-Ladaique/Styx-Analyse/releases/tag/v0.1.0)**.

### Installation
- Télécharger le fichier `.zip` correspondant à la version macOS
- Décompresser et lancer `STYX Analyse.app`

⚠️ Sur macOS, si Gatekeeper bloque l’ouverture :
1. Clic droit sur `STYX Analyse.app` → **Ouvrir**  
2. Confirmer l’ouverture  
3. L’application se lancera normalement par la suite  

---

## 🛠️ Librairies (pas encore complet)

- [Python 3.9+](https://www.python.org/)
- [PyQt6](https://pypi.org/project/PyQt6/) (interface graphique)
- [PyQt6-WebEngine](https://pypi.org/project/PyQt6-WebEngine/) (affichage web)
- [Matplotlib](https://matplotlib.org/) (graphiques)
- [Pandas](https://pandas.pydata.org/) et [NumPy](https://numpy.org/) (analyse de données)



## 📄 Licence

Projet développé dans le cadre du projet **Styx**.  
Licence a définir.

---

## 🆘 Support

👉 Pour toute question ou bug : [Page support STYX Analyse](https://styx-projet.fr/styx-analyse)

---

# User Guide : STYX Analyse  

Lors du premier lancement, des **trajets d’exemple** sont déjà enregistrés : vous pouvez les utiliser pour prendre en main le logiciel. Ils resteront dans le logiciel sauf si vous les supprimez.
Si vous les supprimez par erreur, re-téléchargez le logiciel pour les récuperer.

## Page d’accueil  

Lorsque vous lancez l’application, vous arrivez sur la **page d’accueil**.  
Celle-ci se compose de deux parties principales :  

<img width="2032" height="1167" alt="Capture d’écran 2025-09-10 à 21 49 45 copie" src="https://github.com/user-attachments/assets/60ba3ed8-f6d7-41e7-a732-d9fd0513d511" />

### 📌 Panneau gauche   
- Affiche les **performances cumulées** de tous les fichiers déjà sauvegardés dans le logiciel (encadré rouge).   
- En dessous, vous trouverez le **bouton Support** (encadré jaune), qui renvoie vers la page [STYX Support](https://styx-projet.fr/styx-analyse#styx-analyse-pc) en cas de questions ou de problème.  
- Enfin, la **version du logiciel** est affichée en bas du panneau.  

### 📌 Partie droite  
- Liste tous les **trajets stockés** dans l’application (encadré bleu) .  
- Ajout d'un nouveau trajet avec le bouton **Nouveau trajet** (encadré vert).  
  - Ce bouton vous demandera de sélectionner un fichier CSV.  
  - ⚠️ Ce fichier doit obligatoirement être **généré par le vélo STYX** (conforme au format défini dans le code). Sinon, l’importation échouera.  

- Lorsqu’un trajet est sélectionné (surbrillance en bleu), deux actions sont possibles en bas de la page (encadré noir) :  
  - **Analyser** → ouvre la page d’analyse du trajet.  
  - **Supprimer** → efface définitivement le fichier du stockage de l’application.  
    ⚠️ Attention : une fois confirmé, le fichier est perdu et **ne peut pas être récupéré**.  


## Page d’analyse  

La **page d’analyse** est composée de trois grandes parties :  

<img width="1988" height="1123" alt="Capture d’écran 2025-09-10 à 21 49 59" src="https://github.com/user-attachments/assets/11c6b7a6-aaac-4228-8878-e3c371501176" />

### 📌 Partie gauche  

- **Résumé du trajet** *(encadré vert)*  
  Donne les informations générales du trajet : distance, durée, bilan énergétique, altitudes, etc.  

- **Sélection de plage** *(encadré bleu clair)*  
  Permet de sélectionner la portion de données affichées.  
  Très utile pour couper le début et/ou la fin d’un trajet, par exemple pour masquer les données GPS de départ/arrivée.  

- **Informations instantanées** *(encadré bleu foncé)*  
  Affiche les informations précises au point sélectionné sur le graphique ou sur la carte.  
  Déplacez le curseur sur le graphique ou la carte pour que les informations se mettent à jour en temps réel.  

- **Commentaires** *(encadré rouge)*  
  Permet de commenter le trajet.
  
  <img width="459" height="245" alt="Capture d’écran 2025-09-10 à 22 45 18" src="https://github.com/user-attachments/assets/84760835-30d9-469a-ab91-263a2cfa81a7" />
  
  - Les commentaires sont sauvegardés via le bouton **Enregistrer les commentaires**.  
  - Ils sont inclus dans les rapports générés.  
  - Vous pouvez y noter un instant ou un comportement anormal du vélo (utile pour signaler un bug).  
  - Peut aussi servir à garder un souvenir ou un contexte pour un trajet.  


---

### 📌 Partie droite  

- **Affichage des graphiques** *(encadré gris)*  
  - Bouton **Ajouter** → ajoute un graphique (jusqu’à 6 maximum).  
  - Bouton **Supprimer** → supprime le dernier graphique affiché.  
  - Bouton **Mode normal / Mode avancé** → active ou désactive le mode avancé.  
    - En **mode avancé**, plus de données sont disponibles dans la liste déroulante au-dessus de chaque graphe.  
    - Vous pouvez également **zoomer manuellement** sur les graphiques.  
  - Les graphiques sont **synchronisés** : lorsque vous déplacez le curseur sur l’un d’eux, il se déplace aussi sur les autres.  
  - Cliquez pour **bloquer le curseur** à un instant donné, et cliquez à nouveau pour le libérer.  

- **Carte interactive** *(encadré marron)*  
  - La carte se met à jour automatiquement lors des changements de plage.  
  - Lorsque le curseur se déplace sur un graphique, un **point orange** apparaît sur le tracé à l’endroit correspondant.  
  - Inversement, si vous déplacez le curseur sur la carte, celui-ci se déplace aussi sur les graphiques.  

<img width="1411" height="914" alt="Capture d’écran 2025-09-10 à 22 48 37" src="https://github.com/user-attachments/assets/e7ca86d4-c2f5-4a3d-806b-1aff4ae11861" />

Exemple avec un point séléctioné sur la carte avec 6 graphiques affiché en mode expert


### 📌 Partie basse  

- **Génération de rapports** *(encadré orange)*

<img width="562" height="390" alt="Capture d’écran 2025-09-10 à 22 50 23" src="https://github.com/user-attachments/assets/fbcb38c6-f348-4049-893d-7eeeda5b82be" />

  - Permet de générer et sauvegarder des rapports.  
  - Vous pouvez donner un **nom** au rapport.  
  - Les rapports sont stockés dans :  
    ```
    /STYX Analyse.app/Contents/Resources/rapports
    ```
  - Option **Inclure le fichier CSV de base complet** :  
    - Si cochée → le rapport contiendra le fichier initial *et* le fichier tronqué (après sélection de plage).  
    - Si décochée → seules les données tronquées seront incluses (utile si vous ne voulez pas partager les coordonnées de départ et d’arrivée).  
  - 💡 Astuce : si vous voulez signaler un comportement anormal du vélo, sélectionnez la plage temporelle où ce comportement apparaît.  
    Inclure le fichier complet peut aider à comprendre l’erreur plus facilement.  

- **Bouton Retour** *(encadré jaune)*  
  - Renvoie directement à la **page d’accueil** de l’application.  











