# ⚔️ CastleFight — Interface Graphique JavaFX

> Jeu de combat au tour par tour développé en Java avec JavaFX, dans le cadre de l'épreuve E6 du BTS SIO option SLAM.

---

## 📋 Description

CastleFight est un jeu de combat 1v1 en local. Deux joueurs choisissent chacun leur personnage parmi 4 classes disponibles, puis s'affrontent en se frappant à tour de rôle. Le jeu intègre des mécaniques de coups critiques, d'esquives et d'animations JavaFX pour rendre les combats dynamiques.

---

## 🧙 Personnages disponibles

| Personnage | Points de vie | Caractéristique |
|------------|:------------:|-----------------|
| 🧝 Elfe     | 20 PV        | Équilibré        |
| 🪓 Nain     | 30 PV        | Le plus résistant |
| ⚔️ Guerrier | 20 PV        | Équilibré        |
| 🧙 Sorcière  | 15 PV        | Fragile mais puissante |

---

## ⚙️ Mécaniques de combat

- 🛡️ **15% de chance** d'**esquiver** une attaque (dégâts = 0)
- 🔥 **15% de chance** de porter un **coup critique** (dégâts × 2)
- 💬 Log de combat en temps réel avec messages variés (9 verbes d'action aléatoires)
- 🎨 Barre de vie colorée dynamique :
  - 🟢 Bonne santé (> 10 PV)
  - 🟠 Danger (≤ 10 PV)
  - 🔴 Critique (≤ 5 PV)

---

## 🏆 Système de score

Un `ScoreManager` enregistre le nombre de victoires de chaque personnage tout au long de la session. Le classement est affiché à la fin de chaque combat et persiste jusqu'à la fermeture de l'application.

---

## 🎬 Animations JavaFX

| Événement          | Animation                          |
|--------------------|------------------------------------|
| Coup normal        | Shake horizontal (ImageView)       |
| Coup critique      | Shake amplifié                     |
| Victoire (gagnant) | Zoom × 1.3                         |
| Défaite (perdant)  | Rotation 360° + Fade out           |

---

## 🗂️ Structure du projet

```
Castlefight-epreuve-E6/
├── pom.xml
├── nbactions.xml
└── src/
    └── main/
        ├── java/
        │   ├── module-info.java
        │   └── com/btssio66/oarboux/graphiquecastlefight/
        │       ├── App.java                        # Point d'entrée JavaFX
        │       ├── controllers/
        │       │   ├── PrimaryController.java       # Sélection des personnages
        │       │   └── GameSceneController.java     # Scène de combat
        │       └── model/
        │           ├── Personnage.java              # Classe abstraite de base
        │           ├── Combattant.java              # Implémentation générique
        │           ├── Elfe.java
        │           ├── Guerrier.java
        │           ├── Nain.java
        │           ├── Sorciere.java
        │           └── ScoreManager.java            # Gestion des victoires
        └── resources/
            ├── css/
            │   └── GraphiqueCastleFight.css
            ├── images/
            │   └── (sprites pixel art des personnages)
            └── com/btssio66/oarboux/graphiquecastlefight/
                ├── primary.fxml                     # Vue sélection
                └── gameScene.fxml                   # Vue combat
```

---

## 🛠️ Technologies utilisées

| Technologie      | Version | Rôle                        |
|------------------|---------|-----------------------------|
| Java             | 11      | Langage principal            |
| JavaFX Controls  | 13      | Interface graphique          |
| JavaFX FXML      | 13      | Déclaration des vues         |
| Maven            | 3.x     | Gestion des dépendances      |
| CSS              | —       | Style personnalisé           |

---

## 🚀 Installation & Lancement

### Prérequis

- ☑️ Java JDK 11+
- ☑️ Maven installé et configuré dans le PATH

### Cloner et lancer

```bash
git clone https://github.com/Oliviez1/Castlefight-epreuve-E6.git
cd Castlefight-epreuve-E6
mvn clean javafx:run
```

### Mode debug

```bash
mvn clean javafx:run@debug
```

> Le serveur d'écoute se lance sur `localhost:8000`.

---

## 🕹️ Comment jouer

1. **Joueur 1** clique sur son personnage dans la grille de sélection
2. **Joueur 2** clique sur un personnage différent
3. Cliquer sur **"Jouer"** pour lancer le combat
4. Cliquer sur **"Attaquer"** à chaque tour pour résoudre le round
5. Le combat se termine quand un personnage tombe à 0 PV
6. Le classement des victoires s'affiche, puis on peut rejouer

---

## 👤 Auteur

**O. Arboux** — BTS SIO option SLAM, 2ème année  
Projet réalisé dans le cadre de l'**épreuve E6 — Conception et développement d'applications**

[![GitHub](https://img.shields.io/badge/GitHub-Oliviez1-181717?style=flat&logo=github)](https://github.com/Oliviez1)
