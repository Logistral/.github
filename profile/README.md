<div align="center">

# 🚚 Logistral

### *Optimize your logistics. Simplify your routes.*

**La plateforme IA qui transforme la logistique fragmentée en exécution intelligente et coordonnée.**

🌍 Maroc · Afrique · MENA &nbsp;&nbsp;|&nbsp;&nbsp; 🌐 [logistral.dev](https://www.logistral.dev)


</div>

---

## 🎯 Notre Mission

Le secteur logistique marocain est encore largement manuel — plannings sur Excel, coordination par WhatsApp, visibilité nulle une fois les camions sur route.
Résultat : **30% des livraisons échouent**, 45% à cause d'erreurs d'adresses, et chaque échec coûte en moyenne **80 DH** en carburant et main-d'œuvre.

Logistral est là pour changer ça.

> *"We turn fragmented logistics data into coordinated, intelligent execution."*

---

## Ce qu'on construit

Une plateforme unifiée, bâtie autour de **trois modules complémentaires** qui couvrent l'intégralité du cycle logistique :

---

### Beacon — La couche données

Fichier client brut ──► Beacon ──► Données propres & structurées ──► Nex

Beacon est le **moteur d'ingestion et de nettoyage de données** de Logistral.
Il accepte n'importe quel fichier client — peu importe son format, son encodage ou la qualité de ses colonnes — et le transforme en un jeu de données fiable et exploitable.

- 📥 **Chargement intelligent** de fichiers hétérogènes (CSV, Excel, adresses fragmentées, colonnes mal nommées)
- 🧠 **Matching sémantique par IA** (MistralAI) pour identifier automatiquement les colonnes, même avec des noms ambigus ou en arabe translittéré
- 🔧 **Normalisation et reconstruction** des adresses incomplètes par concaténation de fragments géographiques
- ✅ **Validation ligne par ligne** avec rapport de qualité détaillé (lignes valides, warnings, rejets)

Beacon garantit que **Nex ne reçoit jamais de données sales**.

---

### Nex — Le solveur de tournées intelligent

Nex est le **cerveau de planification** de Logistral. Il implémente un modèle de résolution de tournées avancé (**VRP cross-docking multi-dépôts à deux phases**) :

Phase 1 — Collecte 🏭 Dépôt ──► Points de ramassage ──► Dépôt
Phase 2 — Distribution 🏭 Hub ──► Points de livraison ──► Dépôt

- 🗺️ **Calcul sur réseau routier réel** grâce à OpenRouteService, pas à vol d'oiseau
- ⚡ **Optimisation parallèle** des phases de collecte et de distribution pour des plans en quelques secondes
- 🎚️ **Paramétrable** : durée max de route, priorités commandes, fenêtres horaires, temps d'arrêt par stop
- 💰 **Estimation automatique des coûts** par tournée (carburant, maintenance) selon le type de véhicule
- 📊 **Dashboard KPIs** en temps réel : couverture, distance totale, coût, diagramme de Gantt des tournées

Là où les équipes passaient **2 à 3 heures** à planifier des tournées sur Excel, Nex produit des plans optimisés **en moins de 5 minutes**.

---

### Sophos — Le copilote de l'opérateur

Sophos est l'**assistant IA conversationnel** intégré directement dans la plateforme. Il permet à n'importe quel dispatcher d'interroger ses données opérationnelles en français, sans effort.

- 💬 **Questions en langage naturel** — *"Combien de commandes ont été livrées aujourd'hui ?"*, *"Quel camion a le plus de retard ?"*
- 🔄 **Mémoire de conversation** — Sophos se souvient du contexte et comprend les questions de suivi
- 🔒 **Isolation multi-tenant** — Chaque utilisateur ne voit que ses propres données, de manière inviolable
- 🛡️ **Auto-correction** — Si Sophos génère une requête incorrecte, il détecte l'erreur et se corrige automatiquement (jusqu'à 5 tentatives)
- 🎨 **Interface Glassmorphism** — Panneau latéral élégant, accessible d'un clic, sans quitter son espace de travail

---

## 🗺️ Le flux de bout en bout

📂 Données brutes du client
│
▼
🔦 BEACON — Nettoyage & structuration
│
▼
🧭 NEX — Optimisation des tournées
│
▼
🚚 Chauffeurs sur la route
│
▼
🤖 SOPHOS — Visibilité & aide à la décision en continu

---

## 🗂️ Les dépôts de cette organisation

| Dépôt | Description |
|---|---|
| 🔦 `beacon` | Pipeline d'ingestion et de nettoyage des données |
| 🧭 `nex` | Solveur VRP de planification de tournées |
| 🤖 `sophos` | Copilote IA conversationnel pour les opérateurs |
| 🖥️ `frontend` | Interface planification, carte, Gantt & gestion flotte |
| ⚙️ `backend` | API FastAPI, authentification Supabase, services métier |

---