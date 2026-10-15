# Contrôles transverses (tous types de documents)

Ces points s'appliquent à tout document fonctionnel, en plus de la grille spécifique au type.

| ID | Point de contrôle | Sévérité par défaut | Catégorie |
|---|---|---|---|
| TR-1 | Chaque terme métier important est défini, dans le document ou dans un glossaire référencé. | Majeur (Bloquant s'il conditionne une règle ou un calcul) | Ambiguïtés |
| TR-2 | Aucun qualificatif non mesurable sur une exigence : « rapide », « intuitif », « simple », « temps réel », « sécurisé », « performant », « raisonnable », « si possible », « etc. ». | Majeur (Bloquant si l'exigence doit être testée à la recette) | Ambiguïtés |
| TR-3 | Aucune mention « à définir », « TBD », « à confirmer », « en attente » sur un élément nécessaire à l'implémentation. | Bloquant si l'élément est nécessaire pour implémenter ou chiffrer, sinon Majeur | Manques |
| TR-4 | Toute référence interne (RG-012, EF-04, §3.2, « voir annexe ») pointe vers un élément qui existe dans le document. | Majeur | Contradictions |
| TR-5 | Aucune affirmation n'en contredit une autre : valeurs, seuils, statuts, acteurs, périmètre. | Bloquant si la contradiction porte sur un comportement attendu, sinon Majeur | Contradictions |
| TR-6 | Les chiffres sont cohérents entre eux (totaux, seuils, durées, volumes). | Majeur | Contradictions |
| TR-7 | Chaque acteur ou système qui agit est identifié ; les phrases au passif ne cachent pas l'acteur (« la demande est validée » : par qui ?). | Majeur | Ambiguïtés |
| TR-8 | Chaque système externe cité (API, ERP, partenaire) a son rôle précisé : ce qu'on lui envoie, ce qu'on en reçoit. | Majeur | Manques |
| TR-9 | Le comportement en cas d'échec d'un système externe est précisé, si le document en dépend. | Majeur | Cas non couverts |
| TR-10 | Le traitement des données personnelles est évoqué si le document en collecte ou en affiche (finalité, conservation, droits). | Majeur (Bloquant pour des données de santé ou sensibles) — conditionnel seulement si rien n'indique que l'organisation est dans l'UE | Manques |

## Comment appliquer

- TR-2 ne s'applique qu'aux **exigences** (ce que le système doit faire). Un qualificatif flou dans une phrase de contexte (« l'objectif est de rendre le parcours plus simple ») n'est pas un défaut si une exigence mesurable le traduit ailleurs.
- Pour TR-4, cite la référence orpheline exactement : « RG-12 citée en RG-05, absente du document ».
- Pour TR-5, cite **les deux** passages qui se contredisent.
- Un même mot flou qui revient plusieurs fois donne **un seul** constat, qui liste les occurrences principales.
