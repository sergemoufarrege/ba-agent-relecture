# Grille — Cahier des charges

## Niveau d'exigence attendu

Un cahier des charges dit **quoi** construire et **pourquoi**, pas **comment**. Il sert de base contractuelle ou de pilotage : consultation de prestataires, validation budgétaire, cadrage.

**Ne pas pénaliser** :
- l'absence de règles de gestion détaillées (IF/THEN), de formules ou de règles de validation de champs ;
- l'absence de modèle de données typé ;
- l'absence de workflows détaillés, de maquettes ou d'architecture technique ;
- l'absence de cas limites applicatifs (« double clic », « erreur 404 ») : ils relèvent de la spécification.

Les cas non couverts d'un cahier des charges sont **au niveau projet** : dépassement de capacité, reprise après sinistre, changement de périmètre, retard d'un fournisseur, refus de recette.

## Éléments structurels

| Élément | Absent si… |
|---|---|
| Périmètre (inclus / exclu) | Aucune délimitation du périmètre |
| Objectifs métier mesurables | Aucun objectif, ou objectifs sans aucun indicateur |
| Exigences fonctionnelles identifiées et priorisées | Pas de liste d'exigences identifiables |
| Exigences non fonctionnelles | Aucune exigence de performance, sécurité ou disponibilité |

Un élément est **partiel** si, par exemple, les inclusions sont listées mais pas les exclusions, ou si les exigences sont numérotées sans priorité.

## Points de contrôle

### Cadrage
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| CDC-C1 | Les exclusions de périmètre sont explicites. | Majeur |
| CDC-C2 | Chaque objectif a un indicateur et une cible (« réduire les appels de 30 % en 12 mois »). | Majeur |
| CDC-C3 | Les parties prenantes et leurs rôles sont identifiés, dont qui valide. | Majeur |
| CDC-C4 | Le budget et le calendrier sont indiqués. | **Bloquant** dans un appel d'offres, une consultation de prestataires ou toute mise en concurrence, ou avant validation budgétaire ; sinon Majeur (conditionnel si le contexte est inconnu) |

### Exigences
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| CDC-E1 | Chaque exigence a un identifiant unique. | Majeur |
| CDC-E2 | Les exigences sont priorisées (MoSCoW, P1/P2/P3 ou équivalent). | Majeur |
| CDC-E3 | Chaque exigence est vérifiable à la livraison (pas « interface conviviale »). | Majeur par exigence ; Bloquant si la majorité ne l'est pas |
| CDC-E4 | Les exigences se rattachent aux objectifs. | Mineur |
| CDC-E5 | Les intégrations avec les systèmes existants sont listées (quels systèmes, quels échanges). | Majeur |
| CDC-E6 | Chaque élément inclus dans le périmètre est couvert par au moins une exigence. | Majeur (Bloquant si l'élément est un processus central du projet) |

### Exigences non fonctionnelles et données
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| CDC-N1 | La performance est chiffrée (temps de réponse, volumes, utilisateurs simultanés). | Majeur |
| CDC-N2 | La disponibilité est chiffrée (taux, plages, RTO/RPO si critique). | Majeur |
| CDC-N3 | Les exigences de sécurité sont précisées (authentification, habilitations, chiffrement, traçabilité). | Majeur |
| CDC-N4 | Les données clés, leurs volumes et leur durée de conservation sont identifiés. | Majeur |
| CDC-N5 | Les obligations de conformité applicables sont citées (RGPD, normes sectorielles). | Majeur — conditionnel si le secteur est inconnu |

### Pilotage
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| CDC-G1 | Les critères de recette du projet sont définis. | Majeur |
| CDC-G2 | Les principaux risques sont identifiés, avec une mesure de mitigation. | Mineur |
| CDC-G3 | Le processus de gestion des changements de périmètre est indiqué. | Mineur |
| CDC-G4 | Les livrables attendus sont listés (documentation, formation, réversibilité). | Mineur (Majeur en appel d'offres ou consultation de prestataires) |

## Contradictions fréquentes à vérifier

- Un élément exclu du périmètre est requis par une exigence (mobile exclu, notifications push exigées).
- Le budget ou le délai est manifestement incompatible avec le volume d'exigences. Signale-le comme **conditionnel** et sans chiffrer de coût de marché, sauf si le document fournit les éléments de comparaison.
- Une exigence de disponibilité élevée sans aucune exigence de sauvegarde ou de reprise.
- Une conformité annoncée (RGPD) sans les exigences qui la rendent possible (suppression, consentement, conservation).
- Un validateur cité dans les critères de recette mais absent des parties prenantes.
- Une exigence prioritaire qui dépend d'une exigence moins prioritaire.

## Repères de calibration

- **Cahier des charges solide** : plateforme e-commerce, objectifs chiffrés, inclusions et exclusions, 45 exigences numérotées en MoSCoW, exigences non fonctionnelles chiffrées, budget et calendrier, critères de recette, registre des risques. → Prêt.
- **Partiel** : portail client, objectifs sans indicateurs, exclusions absentes, exigences numérotées pour moitié, performance « rapide ». → À clarifier ou Non prêt selon le nombre de bloquants.
- **Liste de souhaits** : « interface conviviale, rapide, sécurisée, évolutive », budget « à définir », délai « au plus vite ». → Non prêt.
