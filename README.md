# 🧠 Dashboard Power BI – Analyse des ventes et qualité des données

Ce projet a été réalisé dans le cadre d'un atelier de modélisation et de visualisation de données avec **Power BI Desktop**.  
Il illustre la création d'un tableau de bord complet, depuis l'importation des données brutes jusqu'à la construction d'un modèle de données propre et normalisé.

---

## 📂 Structure du projet

- **data/** : fichiers CSV utilisés pour l'analyse (`sales_2.csv`)
- **screenshots/** : captures du tableau de bord final
- **powerbi-dashboard.pbix** : fichier Power BI complet
- **README.md** : documentation du projet

---

## ⚙️ Étapes principales du projet

### 1️⃣ Importation et nettoyage des données
- Import du fichier `sales_2.csv` dans Power Query  
- Analyse de la qualité et du type de données  
- Renommage des colonnes pour une meilleure lisibilité :
  - `OrderID` → *Id commande*
  - `CustomerID` → *Id client*
  - `ProductName` → *Nom produit*, etc.

### 2️⃣ Normalisation du modèle
Création de tables de référence :
- **Clients** : regroupement par Id et Nom client  
- **Produits** : regroupement par Id, Nom et Catégorie  
- **Régions** : regroupement par Id et Nom région  
- **Ventes** : table principale issue de la table brute

### 3️⃣ Modélisation des relations
- Vérification des relations automatiques entre les tables  
- Création manuelle de relations si nécessaire  
- Test de cohérence entre Id commande et nom de produit

### 4️⃣ Création du tableau de bord
- Thème personnalisé : *Loomy Lime Theme*  
- Couleurs : fond `#1E2D38`, briques `#232448`

#### Mesures DAX principales
```DAX
Total ventes = SUM(Ventes[Prix total])
Nombre de commandes = DISTINCTCOUNT(Ventes[Id commande])
Quantité vendue = SUM(Ventes[Quantité])
Commande moyenne = DIVIDE([Total ventes], [Nombre de commandes])
```

#### Visuels

- 4 KPI : Total ventes, Nombre de commandes, Quantité vendue, Commande moyenne
- Courbe d'évolution du chiffre d'affaires
- Barres horizontales par région
- Donut par catégorie de produit
- Tableau détaillé des commandes

### 5️⃣ Filtres et interactions

- Filtre de plage de dates
- Filtre sur le statut de commande
- Filtre sur la région

### 6️⃣ Onglet "Commandes annulées"

- Duplication du premier onglet
- Nouvelles mesures :
- Total commandes annulées
- Montant commandes annulées
- Pourcentage commandes annulées
- KPI, courbes et treemap dédiées

### 7️⃣ Info-bulles (tooltips)
Info-bulle pour histogramme par région

Info-bulle pour donut par catégorie de produit

## 🧩 Technologies utilisées

- Power BI Desktop
- Power Query
- DAX
- Excel / CSV

## 👨‍🎓 Auteur
**Yessir Arèmou Akorede ALI**  
Élève ingénieur à **JUNIA ISEN Lille**, spécialisation Data & Intelligence Artificielle  
Projet réalisé dans le cadre d'un atelier de modélisation et d'analyse de données.
