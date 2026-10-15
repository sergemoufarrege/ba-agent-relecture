# Grille — Use Case

## Niveau d'exigence attendu

Un use case décrit une **interaction complète** entre un acteur et le système : plus détaillé qu'une user story, moins qu'une spécification fonctionnelle. Il couvre comment l'interaction se déroule, ses variantes et ce qui peut mal tourner.

**Ne pas pénaliser** :
- l'absence de règles de gestion détaillées : une simple référence (RG-023) suffit ;
- l'absence de modèle de données typé : les données échangées doivent être identifiées, pas typées ;
- l'absence de maquettes.

Repère de taille : un scénario nominal de 3 à 5 étapes sans variante est plutôt une user story ; au-delà de 50 étapes ou plusieurs fonctionnalités, il faut découper.

## Éléments structurels

| Élément | Absent si… |
|---|---|
| Objectif et acteur principal | Ni objectif ni acteur explicites |
| Préconditions et postconditions | Aucune des deux |
| Scénario nominal | Aucun scénario, ou moins de 5 étapes pour une interaction réelle |
| Scénarios alternatifs | Aucune variante décrite |
| Scénarios d'exception | Aucun cas d'erreur décrit |

## Points de contrôle

| ID | Point de contrôle | Sévérité par défaut |
|---|---|---|
| UC-A1 | Les acteurs secondaires (systèmes externes, autres rôles) sont identifiés. | Majeur |
| UC-A2 | Le déclencheur du use case est explicite. | Majeur |
| UC-A3 | Le périmètre est indiqué (ce que le use case ne couvre pas). | Mineur |
| UC-C1 | Les préconditions sont vérifiables (« client connecté, compte actif », pas « le client a un compte »). | Majeur |
| UC-C2 | Les postconditions sont décrites en cas de succès **et** en cas d'échec. | Majeur |
| UC-F1 | Chaque étape est atomique : une seule action. | Mineur par étape ; Majeur si fréquent |
| UC-F2 | Chaque étape système a un résultat observable (« affiche… », « crée la commande n°… »), pas « le système traite ». | Majeur |
| UC-F3 | La numérotation est cohérente : 1, 2, 3 ; alternatives 3a, 3a.1 ; exceptions 4E, 4E.1. | Mineur |
| UC-F4 | Chaque alternative ou exception a une condition de déclenchement, un point de départ et un point de retour (ou une fin explicite). | Bloquant si le point de retour manque, sinon Majeur |
| UC-F5 | Les données saisies et restituées à chaque étape sont identifiées. | Majeur |
| UC-F6 | Les règles de gestion utilisées sont référencées. | Mineur |
| UC-E1 | Les pannes ou délais d'un système externe sont couverts. | Majeur |
| UC-E2 | L'abandon par l'utilisateur et l'expiration de session sont traités quand c'est pertinent. | Mineur |

## Contradictions fréquentes à vérifier

- Une précondition est refaite dans le flux (« Pré : connecté » puis « 1. L'utilisateur se connecte »).
- Une postcondition de succès est contredite par une exception qui annule l'opération après coup.
- Deux alternatives ont des conditions qui se chevauchent sans règle de priorité.
- Une étape utilise une donnée produite plus loin dans le flux.
- Une alternative part d'une étape qui n'existe pas, ou une exception revient vers une étape ultérieure.
- Une étape requiert un rôle qui n'est pas listé parmi les acteurs.

## Repères de calibration

- **Use case solide** : passage de commande, 21 étapes nominales, 5 alternatives et 4 exceptions avec points de retour, pré/postconditions de succès et d'échec, règles référencées. → Prêt.
- **Use case partiel** : connexion client en 6 étapes, 1 alternative, 1 exception, préconditions vagues, étapes « valider » non observables. → À clarifier.
- **Liste d'étapes** : « 1. Aller au panier 2. Saisir la livraison 3. Payer 4. Confirmation ». → Non prêt.
