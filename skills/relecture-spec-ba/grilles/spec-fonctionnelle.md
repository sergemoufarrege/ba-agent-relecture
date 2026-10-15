# Grille — Spécification fonctionnelle

## Niveau d'exigence attendu

Une spécification fonctionnelle décrit **comment** une fonctionnalité ou un module se comporte, au niveau nécessaire pour développer et tester sans deviner. C'est le document le plus détaillé des quatre.

**Ne pas pénaliser** :
- l'absence de choix techniques (langage, framework, architecture) ;
- l'absence de maquettes, si le comportement est décrit ;
- l'absence de cas de test détaillés (ils relèvent du plan de test).

## Éléments structurels

| Élément | Absent si… |
|---|---|
| Règles de gestion identifiées (RG-001…) | Les règles ne sont qu'en texte narratif, sans identifiant |
| Modèle de données | Aucune liste d'entités ou de champs |
| Workflows / états | Aucun enchaînement d'étapes ou de statuts décrit |
| Exigences fonctionnelles identifiées (EF-001…) | Aucune exigence numérotée |

Un élément est **partiel** s'il existe mais de façon incomplète (ex. : règles numérotées pour moitié, champs listés sans types).

## Points de contrôle

### Périmètre
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| SF-P1 | Le périmètre est défini : ce qui est inclus et ce qui est explicitement exclu. | Majeur |
| SF-P2 | Le contexte métier et les acteurs sont identifiés. | Majeur |

### Règles de gestion
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| SF-RG1 | Chaque règle a un identifiant unique. | Majeur |
| SF-RG2 | Chaque règle précise sa condition et son résultat (SI… ALORS…), sans « en général » ou « selon le cas ». | Bloquant |
| SF-RG3 | Les formules et calculs sont exacts : opérandes, arrondis, unités, bornes. | Bloquant |
| SF-RG4 | Les seuils et valeurs limites sont chiffrés, avec le traitement de la valeur exacte du seuil (≥ ou >). | Majeur |

### Données
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| SF-D1 | Chaque champ a un type, un format ou une liste de valeurs. | Majeur |
| SF-D2 | Les champs obligatoires et facultatifs sont distingués. | Majeur |
| SF-D3 | Les règles de validation de saisie sont précisées, avec le message en cas d'erreur. | Majeur |
| SF-D4 | Les valeurs de statut sont identiques dans le modèle de données, les règles et les workflows. | Bloquant (Contradiction) |

### Workflows et cas limites
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| SF-W1 | Chaque transition d'état a un déclencheur et un acteur. | Majeur |
| SF-W2 | Les transitions interdites ou les états finaux sont identifiables. | Mineur |
| SF-W3 | Les cas d'erreur métier sont décrits (refus, données invalides, solde insuffisant…), avec le comportement attendu. | Bloquant si un cas fréquent est absent, sinon Majeur |
| SF-W4 | Les accès concurrents et doubles soumissions sont traités quand ils sont plausibles (deux validateurs, double clic). | Majeur |
| SF-W5 | Les délais, expirations et relances sont chiffrés. | Majeur |

### Testabilité
| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| SF-T1 | Chaque exigence est vérifiable : un testeur peut écrire un cas de test sans poser de question. | Majeur par exigence ; Bloquant si la majorité ne l'est pas |
| SF-T2 | Les exigences renvoient aux règles et aux données concernées (traçabilité). | Mineur |
| SF-T3 | Les droits et habilitations par profil sont précisés. | Majeur |

## Règles spécifiques

- Une contradiction entre deux règles, ou entre une règle et un workflow, est le défaut le plus coûteux d'une spec : vérifie systématiquement les seuils, statuts et rôles qui apparaissent à plusieurs endroits.
- Cas non couverts à chercher en priorité : valeurs aux bornes, concurrence, panne d'un système externe, données incomplètes ou en doublon, retour arrière dans un workflow, annulation.
- Si la spec fait moins de quelques pages pour un module complexe, mentionne-le dans le verdict : c'est souvent un document de cadrage, pas une spec.

## Repères de calibration

- **Spec solide** : prêt personnel, 45 pages, 18 RG numérotées en SI/ALORS, modèle de données typé, machines à états, traçabilité EF→RG. → Prêt, constats Mineurs.
- **Spec partielle** : gestion de factures, 12 RG dont 5 en narratif, types manquants sur certains champs, un workflow sur deux décrit. → À clarifier.
- **Document de cadrage présenté comme spec** : portail client, 8 pages, règles vagues, liste de champs sans types, pas de workflow. → Non prêt.
