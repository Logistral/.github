<div align="center">

# 🚚 Logistral

### *Optimize your logistics. Simplify your routes.*

**La plateforme IA qui transforme la logistique fragmentée en execution intelligente et coordonnee.**

🌍 Maroc · Afrique · MENA &nbsp;&nbsp;|&nbsp;&nbsp; 🌐 [logistral.dev](https://www.logistral.dev)


</div>

---

## 🎯 Notre Mission

Le secteur logistique marocain est encore largement manuel — plannings sur Excel, coordination par WhatsApp, visibilite nulle une fois les camions sur route.
Resultat : **30% des livraisons echouent**, 45% a cause d'erreurs d'adresses, et chaque echec coute en moyenne **80 DH** en carburant et main-d'oeuvre.

Logistral est la pour changer ca.

> *"We turn fragmented logistics data into coordinated, intelligent execution."*

---

## Ce qu'on construit

Une plateforme unifiee, batie autour de **trois modules complementaires** qui couvrent l'integralite du cycle logistique :

---

### Beacon — La couche donnees

Fichier client brut ──► Beacon ──► Donnees propres & structurees ──► Nex

Beacon est le **moteur d'ingestion et de nettoyage de donnees** de Logistral.
Il accepte n'importe quel fichier client — peu importe son format, son encodage ou la qualite de ses colonnes — et le transforme en un jeu de donnees fiable et exploitable.

- 📥 **Chargement intelligent** de fichiers heterogenes (CSV, Excel, adresses fragmentees, colonnes mal nommees)
- 🧠 **Matching semantique par IA** (MistralAI) pour identifier automatiquement les colonnes, meme avec des noms ambigus ou en arabe translittere
- 🔧 **Normalisation et reconstruction** des adresses incompletes par concatenation de fragments geographiques
- ✅ **Validation ligne par ligne** avec rapport de qualite detaille (lignes valides, warnings, rejets)

Beacon garantit que **Nex ne recoit jamais de donnees sales**.

---

### Nex — Le solveur de tournees intelligent

Nex est le **cerveau de planification** de Logistral. Il implemente un modele de resolution de tournees avance (**VRP cross-docking multi-depots a deux phases**) :

Phase 1 — Collecte 🏭 Depot ──► Points de ramassage ──► Depot
Phase 2 — Distribution 🏭 Hub ──► Points de livraison ──► Depot

- 🗺️ **Calcul sur reseau routier reel** grace a OpenRouteService, pas a vol d'oiseau
- ⚡ **Optimisation parallele** des phases de collecte et de distribution pour des plans en quelques secondes
- 🎚️ **Parametrable** : duree max de route, priorites commandes, fenetres horaires, temps d'arret par stop
- 💰 **Estimation automatique des couts** par tournee (carburant, maintenance) selon le type de vehicule
- 📊 **Dashboard KPIs** en temps reel : couverture, distance totale, cout, diagramme de Gantt des tournees

La ou les equipes passaient **2 a 3 heures** a planifier des tournees sur Excel, Nex produit des plans optimises **en moins de 5 minutes**.

---

### Sophos — Le copilote de l'operateur

Sophos est l'**assistant IA conversationnel** integre directement dans la plateforme. Il permet a n'importe quel dispatcher d'interroger ses donnees operationnelles en francais, sans effort.

- 💬 **Questions en langage naturel** — *"Combien de commandes ont ete livrees aujourd'hui ?"*, *"Quel camion a le plus de retard ?"*
- 🔄 **Memoire de conversation** — Sophos se souvient du contexte et comprend les questions de suivi
- 🔒 **Isolation multi-tenant** — Chaque utilisateur ne voit que ses propres donnees, de maniere inviolable
- 🛡️ **Auto-correction** — Si Sophos genere une requete incorrecte, il detecte l'erreur et se corrige automatiquement (jusqu'a 5 tentatives)
- 🎨 **Interface Glassmorphism** — Panneau lateral elegant, accessible d'un clic, sans quitter son espace de travail

---

## 🗺️ Le flux de bout en bout

📂 Donnees brutes du client
│
▼
🔦 BEACON — Nettoyage & structuration
│
▼
🧭 NEX — Optimisation des tournees
│
▼
🚚 Chauffeurs sur la route
│
▼
🤖 SOPHOS — Visibilite & aide a la decision en continu

---

## 🗂️ Les depots de cette organisation

| Depot | Description |
|---|---|
| 🔦 `beacon` | Pipeline d'ingestion et de nettoyage des donnees |
| 🧭 `nex` | Solveur VRP de planification de tournees |
| 🤖 `sophos` | Copilote IA conversationnel pour les operateurs |
| 🖥️ `frontend` | Interface planification, carte, Gantt & gestion flotte |
| ⚙️ `backend` | API FastAPI, authentification Supabase, services metier |

---