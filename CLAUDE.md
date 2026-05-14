# CLAUDE.md — Solution Logistral

Contexte complet du projet pour les sessions Claude Code.

## Vue d'ensemble

Logistral est une plateforme SaaS de planification logistique pour le Maroc. Trois modules principaux :

- **Beacon** — Pipeline d'ingestion de données (CSV/XLSX → commandes normalisées)
- **Nex** — Solveur VRP cross-docking multi-dépôts (2 phases : collecte + distribution)
- **Driver Portal** — Application mobile Capacitor PWA pour conducteurs sur le terrain

## Module Beacon (Ingestion)

Pipeline en 5 étapes :

1. **Loader** — Détecte type fichier (CSV/XLSX), encodage (chardet), séparateur
2. **Schema Matcher** — LLM Mistral mappe colonnes raw → champs canoniques Pydantic
3. **Normalizer** — Reconstruit adresses fragmentées, cast types, injecte defaults
4. **Geocoder** — Google Geocoding API pour lat/lon ramassage et livraison
5. **Validator** — Statut par ligne : valid / warning / rejected

## Module Nex (Solveur VRP)

Architecture cross-docking :

- **Phase Collecte** : Dépôt le plus proche → Ramassages → Dépôt
- **Phase Distribution** : Dépôt de distribution → Livraisons → Dépôt

Flux solver (`nex.py`) :

1. Charger commandes + camions depuis Supabase
2. Assigner pickups aux dépôts (distance Haversine)
3. Appeler ORS `/matrix` pour matrices durées/distances
4. Résoudre collecte (VROOM) par dépôt en parallèle
5. Résoudre distribution (VROOM)
6. Retourner résultats (ou persister en DB pour solve-and-save)

Scaling capacité VROOM :

- Poids : ×10 (float → int)
- Volume : ×1000 (float → int)
