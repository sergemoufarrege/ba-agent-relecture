# Corrigé — 01 User Story « Notifications »

**Verdict attendu : Non prêt** (au moins 3 bloquants : taille, plusieurs fonctionnalités, critère non testable / temps réel).

## Défauts plantés

| # | Point de contrôle | Défaut | Preuve | Sévérité attendue |
|---|---|---|---|---|
| D1 | US-S1 | 10 critères d'acceptation : c'est une épopée. | Critères 1 à 10 | Bloquant |
| D2 | US-S2 | Plusieurs fonctionnalités indépendantes : in-app, email, SMS, préférences, historique, push. | CA 1, 2, 3, 4, 6, 8 | Bloquant (peut être fusionné avec D1, accepté) |
| D3 | US-V1 | Persona générique. | « En tant qu'utilisateur » | Majeur |
| D4 | US-V3 | La valeur reformule l'objectif. | « afin d'être notifié » | Majeur |
| D5 | US-T1 / TR-2 | Critère subjectif, non testable. | « intuitive » (CA 10) | Majeur ou Bloquant |
| D6 | US-E1 / TR-2 | « Temps réel » non défini. | CA 7 | Majeur ou Bloquant |
| D7 | TR-1 | « Urgent » et « si nécessaire » non définis. | CA 3, CA 9 | Majeur |

**Attendu en plus :** une proposition de découpage en plusieurs stories (in-app, email, SMS, préférences, historique, push).

## Pièges — ne doivent pas être signalés

- Absence de modèle de données ou de format de notification.
- Absence de choix technique (fournisseur SMS, service push).
- Absence de règles détaillées en SI/ALORS.
