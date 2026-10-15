# Corrigé — 03 Cahier des charges « Portail adhérents »

**Verdict attendu : Non prêt.** Les exigences non fonctionnelles ne sont pas quantifiées (élément structurel au mieux partiel) et plusieurs bloquants existent dans un contexte de consultation de prestataires, explicite dans l'en-tête.

Variante : si l'évaluateur considère que le contexte « consultation de prestataires » n'implique pas un appel d'offres formel, le budget passe en Majeur ; le verdict reste Non prêt ou À clarifier selon le décompte. Les deux sont acceptables à condition que le raisonnement soit affiché.

## Défauts plantés

| # | Point de contrôle | Défaut | Preuve | Sévérité attendue |
|---|---|---|---|---|
| D1 | CDC-C2 | Objectifs sans indicateur ni cible. | §2 | Majeur (élément structurel « objectifs mesurables » partiel ou absent) |
| D2 | TR-5 | Contradiction : mobile natif exclu, mais notifications push sur téléphone exigées. | §3 vs EX-08 | Bloquant |
| D3 | CDC-E1 | Deux exigences sans identifiant. | §4, 4e et 5e puces | Majeur |
| D4 | CDC-E2 | Aucune priorisation des exigences. | §4 | Majeur |
| D5 | CDC-N1/N2/N3 / TR-2 | Exigences non fonctionnelles non quantifiées. | « rapide et disponible », « sécurisé » (§5) | Bloquant (élément structurel partiel) |
| D6 | CDC-C4 | Budget non indiqué alors que le document sert à consulter des prestataires ; date de mise en service imprécise. | §6 | Bloquant |
| D7 | CDC-N4/N5 / TR-10 | Données personnelles et de santé (certificat médical) sans exigence de conservation, confidentialité ou RGPD. | EX-01 | Majeur ou Bloquant |
| D8 | CDC-C3 / TR-5 | Le comité directeur valide la recette mais n'est pas identifié comme partie prenante ; aucun rôle n'est défini. | §7 | Majeur |

## Constats acceptés en plus

- Exclusions de périmètre incomplètes (une seule exclusion).
- Reprise des données existantes (adhérents actuels) non évoquée.
- Intégration avec le système de la fédération sportive non évoquée (constat **conditionnel**).
- Critères de recette non définis (CDC-G1).
- Volumes (12 000 adhérents, pic de renouvellement en début de saison) non traduits en exigence de performance.

## Pièges — ne doivent pas être signalés

- Absence de règles de gestion détaillées, de modèle de données typé ou de workflow : ce n'est pas attendu dans un cahier des charges.
- Absence de cas limites applicatifs (double paiement, double clic).
- Absence d'architecture technique.
- Une estimation chiffrée du coût du projet par la skill : elle ne doit pas inventer de coût de marché.
