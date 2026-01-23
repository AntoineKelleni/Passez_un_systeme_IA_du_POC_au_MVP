![Python](https://img.shields.io/badge/Python-3.11-blue)
![RAG](https://img.shields.io/badge/RAG-Retrieval--Augmented--Generation-blueviolet)
![FAISS](https://img.shields.io/badge/FAISS-Vector%20Index-green)
![Mistral](https://img.shields.io/badge/Mistral-LLM%20API-orange)
![OpenAgenda](https://img.shields.io/badge/OpenAgenda-Event%20API-success)
![Docker](https://img.shields.io/badge/Docker-Containerization-2496ED)
![Azure](https://img.shields.io/badge/Microsoft%20Azure-Cloud-0078D4)
![Status](https://img.shields.io/badge/Project-POC%20to%20MVP-brightgreen)

<p align="center">
  <img src="logo_OCR.jpg" alt="Logo OpenClassrooms" width="200">
</p>

# Puls-Events – Chatbot RAG (POC → MVP)
<p align="center">
  <img src="img/phase du projet.png" alt="Logo OpenClassrooms" width="750">
</p>
<p align="center">
  <img src="img/architecture MVP.png" alt="Logo OpenClassrooms" width="750">
</p>

Chatbot de recommandation d’événements culturels basé sur une approche **Retrieval-Augmented Generation (RAG)**.  
Ce projet illustre le passage progressif d’un **Proof of Concept (POC)** vers un **Minimum Viable Product (MVP)**, avec une réflexion complète sur l’architecture, l’infrastructure cloud et la gestion des coûts.

---

##  Objectifs du projet
```
- Concevoir un chatbot capable de recommander des événements culturels pertinents
- Exploiter des données publiques issues d’OpenAgenda
- Valider la faisabilité technique via un POC
- Transformer le POC en MVP exploitable et scalable
- Mettre en place une architecture modulaire, orientée production
- Anticiper les contraintes de coûts, de déploiement et de monitoring
```
---

## Principe de l’approche RAG

L’architecture repose sur le principe de **Retrieval-Augmented Generation** :
```
1. Recherche sémantique dans une base vectorielle
2. Récupération de documents pertinents
3. Injection du contexte dans un modèle de langage
4. Génération d’une réponse contextualisée et contrôlée
```
Cette approche permet de :
```
- réduire les hallucinations,
- s’appuyer sur des données réelles,
- améliorer la pertinence des réponses.
```
---

## Phase 1 – Proof of Concept (POC)

### Objectifs du POC
```
- Valider la faisabilité technique du chatbot RAG
- Tester la recherche sémantique sur des données événementielles
- Vérifier la qualité des réponses générées
```
### Fonctionnalités du POC
```
- Pipeline Python local
- Ingestion des données OpenAgenda
- Nettoyage et normalisation
- Vectorisation NLP (embeddings)
- Indexation via FAISS
- Chatbot conversationnel simple
```
### Limites identifiées
```
- Quotas et crédits API (modèles d’embeddings)
- Erreurs liées aux limites de taux (API)
- Architecture locale non scalable
- Absence de déploiement cloud
- Pas de monitoring ni d’interface utilisateur avancée
```
Ces limites ont motivé le passage vers une approche MVP.

---

## Phase 2 – Passage au MVP

### Objectifs du MVP
```
- Industrialiser le pipeline existant
- Séparer clairement les responsabilités
- Déployer la solution sur le cloud
- Maîtriser les coûts BUILD et OPEX
- Préparer les évolutions futures
```
---

## Architecture MVP
<p align="center">
  <img src="img/architecture MVP.png" alt="Logo OpenClassrooms" width="1000">
</p>
L’architecture MVP est organisée en trois couches principales :

### 1. Data & Indexation
```
- Sources : OpenAgenda (événements)
- Ingestion et nettoyage automatisés
- Vectorisation NLP
- Base relationnelle :
  - métadonnées structurées (date, lieu, catégorie…)
- Base vectorielle :
  - recherche par similarité sémantique
```
### 2. Application & Orchestration
```
- API Backend comme point d’entrée unique
- Orchestration des requêtes
- Règles métier :
  - filtres
  - priorisation
  - ranking
  - cache
- Monitoring & KPI :
  - latence
  - erreurs
  - usage
  - satisfaction
```
### 3. Expérience Utilisateur
```
- Interface chatbot conversationnelle
- Mémoire conversationnelle (court terme)
- Contexte géographique
- Moteur RAG :
  - retrieval
  - génération de réponse
- Réponse personnalisée
```
---

## Choix de l’infrastructure cloud

Le MVP est déployé sur ```Microsoft Azure.```

### Justifications du choix
```
- Déploiement rapide
- Scalabilité progressive
- Services managés
- Observabilité intégrée
- Modèle de coûts pay-as-you-go
- Adapté à une démarche MVP
```
L’architecture reste volontairement modulaire et portable.

---

## Déploiement & conteneurisation

Les composants applicatifs sont conteneurisés à l’aide de Docker afin de :
```
- faciliter le déploiement,
- garantir la reproductibilité,
- préparer la montée en charge.
```
##  Macro backlog du MVP

### Must-Have
```
- Pipeline data automatisé  
- API Backend  
- Recherche vectorielle  
- Moteur RAG  
- Déploiement cloud  
- Monitoring & logs  
```
### Nice-to-Have
```
- Interface utilisateur avancée  
- Historique conversationnel persistant  
- Enrichissement des sources de données  
```
---

## 💰 Estimation des coûts

### BUILD
```
- Conception de l’architecture  
- Développement du pipeline data  
- API Backend  
- Mise en place cloud et déploiement  
```
### OPEX
```
- Hébergement cloud  
- Appels aux modèles de langage  
- Stockage et monitoring  
```
### Optimisations envisagées
```
- Cache des réponses  
- Limitation des volumes vectorisés  
- Montée en charge progressive  
```
---

## Monitoring & observabilité

Le MVP intègre une approche orientée observabilité :
```
- Suivi des performances  
- Gestion des erreurs  
- Analyse de l’usage  
- Indicateurs de satisfaction  
```
Ces éléments permettent d’itérer rapidement et de sécuriser la production.

---

##  Perspectives d’évolution
```
- Amélioration de l’expérience utilisateur  
- Optimisation des coûts NLP  
- Enrichissement fonctionnel  
- Extension à de nouvelles sources de données  
- Déploiement à plus grande échelle  
``` 

---

## Conclusion

Ce projet illustre une démarche complète de **Data Engineering**, depuis la validation technique d’un **POC** jusqu’à la conception d’un **MVP structuré, scalable et orienté production**.  
Il met en évidence la capacité à prendre en compte les contraintes techniques, métier et infrastructure dans une logique de création de valeur.



