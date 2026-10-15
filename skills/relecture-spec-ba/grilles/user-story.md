# Grille — User Story

## Niveau d'exigence attendu

Une user story est une **base de conversation**, pas une spécification. Format habituel : « En tant que [persona], je veux [objectif], afin de [valeur] » + 3 à 7 critères d'acceptation, soit 5 à 15 lignes.

**Ne pas pénaliser** (absence normale dans une user story) :
- les règles de gestion détaillées en IF/THEN ;
- les types et formats de champs ;
- la couverture exhaustive des cas limites ;
- les choix techniques et d'architecture.

Évalue la story sur sa capacité à entrer dans un sprint, selon INVEST.

## Éléments structurels

| Élément | Absent si… |
|---|---|
| Formule persona / objectif / valeur | Ni persona, ni objectif identifiables |
| Critères d'acceptation | Aucun critère d'acceptation |

## Points de contrôle

| ID | INVEST | Point de contrôle | Sévérité par défaut |
|---|---|---|---|
| US-I1 | Indépendante | Les dépendances bloquantes (autre story, API, donnée non disponible) sont absentes ou explicitement identifiées. | Majeur (Bloquant si la dépendance empêche de démarrer) |
| US-N1 | Négociable | Les critères décrivent un **résultat observable**, pas une implémentation (« via websocket », « composant React », « appel à /api/v2 »). | Mineur (Majeur si cela fige un choix contestable) |
| US-V1 | Valable | Le persona est spécifique (« conseiller clientèle », « gestionnaire sinistres »), pas « utilisateur » générique. | Majeur |
| US-V2 | Valable | L'objectif est explicite et compréhensible seul. | Bloquant |
| US-V3 | Valable | La valeur métier (« afin de… ») est énoncée et n'est pas une reformulation de l'objectif. | Majeur |
| US-E1 | Estimable | Aucun terme flou n'empêche l'estimation (« temps réel », « automatique », « intelligent »). | Bloquant si l'écart d'estimation est important, sinon Majeur |
| US-E2 | Estimable | L'origine des données affichées ou calculées est connue (champ existant, calcul, système externe). | Majeur |
| US-S1 | Petite | 3 à 7 critères d'acceptation. | 8–9 critères : Majeur ; 10 ou plus : Bloquant (épopée) |
| US-S2 | Petite | Une seule fonctionnalité (pas « notifications in-app, email et SMS + préférences »). | Majeur (Bloquant si plusieurs fonctionnalités indépendantes) |
| US-T1 | Testable | Chaque critère a un résultat observable et un critère de réussite clair. | Bloquant si aucun critère n'est testable ; Majeur par critère non testable |
| US-T2 | Testable | Le cas vide ou d'erreur principal est couvert (aucun résultat, saisie invalide, droit insuffisant). | Mineur |

## Règles spécifiques

- Si US-S1 ou US-S2 échoue, ajoute dans les constats une **proposition de découpage** : 2 à 6 stories avec un titre, 3 à 5 critères chacune et la valeur apportée.
- Les catégories de constats pour une user story : les termes flous vont en **Ambiguïtés**, les critères non testables en **Manques**, la taille excessive en **Manques**.
- Questions au métier : 3 à 6 au maximum. Une story qui en appelle plus de 8 n'est pas prête.

## Repères de calibration

- **Bonne story** : « En tant qu'agent support, je veux consulter l'historique de commandes d'un client afin de répondre rapidement à ses questions. » 5 critères Given/When/Then, dont client sans commande et identifiant invalide. → Prêt, aucun constat au-delà de Mineur.
- **Story correcte mais ambiguë** : tableau de bord commercial trié par probabilité de closing, « mis à jour en temps réel », score fourni par une API externe. → À clarifier : « temps réel » (US-E1) et origine du score (US-E2, US-I1).
- **Épopée** : « système de notifications complet » avec 10 critères (in-app, email, SMS, préférences, historique, push…). → Non prêt, proposer un découpage.
- **Story vide** : « En tant qu'utilisateur, je veux que le système soit mieux, afin que ce soit plus facile », critères « rapide », « moderne », « les utilisateurs aiment ». → Non prêt, réécriture complète.
