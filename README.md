# RAG - Questions/Réponses sur la prise en charge des pneumopathies aiguës communautaires (PAC)

## Description

Ce projet propose un système de **Retrieval-Augmented Generation (RAG)** permettant d'interroger un document médical sur la prise en charge des **pneumopathies aiguës communautaires (PAC)** supposées d'origine bactérienne.
Le système utilise un modèle de langage (LLM) associé à une base de connaissances construite à partir du document fourni, afin de répondre à des questions en langage naturel.

## Fonctionnalités

- Chargement et traitement du document source (.docx)
- Découpage en passages pour faciliter la recherche
- Création d’index vectoriel (embeddings) pour la recherche rapide des passages pertinents
- Questionnement en langage naturel avec génération de réponses contextualisées
- Affichage des sources des extraits utilisés pour la réponse

## 🧪 Test du modèle


| **Question**                                         | **Réponse générée**                                             | **Commentaire**                                                  |
|------------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|
| Quelles sont les recommandations d'antibiotiques pour un adulte atteint d'une PAC non grave sans commorbidités ? | Les recommandations d'antibiotiques pour un adulte atteint d'une Pneumonie non grave sans comorbidités sont l'Amoxicilline à une dose de 1-2g par 8 heures par voie orale ou intraveineuse, comme indiqué dans les recommandations thérapeutiques de la Commission des Médicaments Anti-Infectieux (COMAI) réalisées et validées le 20/06/2025. | Bonne réponse générale sur une question simple, même si le dernier commentaire peut être hors de propos. |
| Quels examens ne sont pas recommandés pour une PAC et pourquoi ?         | Les examens de dosage de la CRP (C-réactive protéine) et PCT (Procalcitonine) ne sont pas systématiquement recommandés pour un diagnostic et/ou suivi de pneumonie aiguë (PAC). Cela est dû au fait qu'ils ne sont pas spécifiques pour la détection de la bactérie comme cause de la PAC et peuvent être altérés par d'autres processus inflammatoires ou infections non respiratoires. Dans le contexte de PAC graves, un diagnostic différentiel doit être effectué et les examens doivent être choisis en fonction de la suspicion clinique, du contexte de l'hospitalisation et de la gravité de la maladie. | Bonne réponse encore une fois mais des commentaires qui semblent avoir été ajoutés par le modèle de base car non présents dans le document : à contrôler     |
| Dans quels cas puis-je prescrire de l'amoxicilline-acide clavulanique ?   | L'amoxicilline-acide clavulanique peut être prescrite en cas de comorbidité, car elle possède une activité antibiotique plus large que l'amoxicilline seule, en particulier contre les bactéries productrices d'enzymes β-lactamases résistantes aux β-lactamines. Par ailleurs, elle est également utilisée dans le traitement de la pneumopathie d'inhalation, pour sa bonne pénétration pulmonaire. | Question plus complexe car le médicament est indiqué dans plusieurs parties différentes du document : le modèle détecte bien le cas de pneumopathie d'inhalation et la prise en compte des comorbidités. Cependant, il semble extrapoler de connaissances préalables et extérieures au document en ce qui concerne les bactéries productrices d'enzymes β-lactamases résistantes aux β-lactamines, ce qui peut être préjudiciable dans la recommandation.|


## Structure du projet
- `Test_technique_CHU_Montpellier.ipynb` : Notebook principal avec le code et les démonstrations
- `data/` : Dossier contenant les documents sources (**non versionné**)
  - `Prise en charge des Pneumopathies aigues communautaires V2.docx` : document médical sur les pneumopathies
- `.gitignore` : Fichier pour exclure les fichiers sensibles ou inutiles du dépôt
- `README.md` : Ce fichier de présentation
