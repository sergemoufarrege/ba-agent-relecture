# Exemple de relecture complète — User Story

Cet exemple montre le format et le niveau d'exigence attendus. Il sert de calibrage, pas de modèle à recopier mot pour mot.

## Document relu

> **US-142 — Tableau de bord des opportunités**
> En tant que commercial, je veux voir un résumé automatique de mes opportunités avec leur probabilité de signature, afin de prioriser mes actions.
>
> Critères d'acceptation :
> 1. Le tableau affiche les opportunités triées par score.
> 2. Chaque ligne affiche le nom du client, le montant, la date de clôture et la dernière interaction.
> 3. Un filtre permet d'afficher 7, 30 ou 90 jours.
> 4. Le tableau se met à jour en temps réel grâce à l'API Perplexity.
> 5. Si aucune opportunité, un message s'affiche.

## Sortie attendue

## Contexte retenu
User story agile pour un outil CRM interne destiné aux commerciaux ; destinataire probable : équipe de développement interne, en refinement avant sprint.
Hypothèses : l'API Perplexity est un service externe qui n'est pas encore intégré.

## Verdict : À clarifier
Story bien formée et de bonne taille, mais « temps réel » et l'origine du score empêchent d'estimer et de tester. Constats : 1 bloquant, 5 majeurs, 1 mineur.

## Éléments structurels
| Élément | État | Preuve |
|---|---|---|
| Formule persona / objectif / valeur | ✅ Présent | « En tant que commercial, je veux… afin de prioriser mes actions » |
| Critères d'acceptation | ✅ Présent | 5 critères numérotés |

## Constats
### Manques
| # | Sévérité | Constat | Preuve | Impact |
|---|---|---|---|---|
| M1 | Majeur | L'origine du score de probabilité n'est pas précisée (champ existant, calcul interne ou service externe). (US-E2) | « triées par score » (CA 1) | L'effort varie de quelques heures à plusieurs jours selon la source. |
| M2 | Majeur | La dépendance à l'API Perplexity n'est pas qualifiée : accès, contrat, données envoyées. (US-I1, TR-8) | « grâce à l'API Perplexity » (CA 4) | La story risque d'être bloquée en cours de sprint. |

### Contradictions
Aucun constat.

### Ambiguïtés
| # | Sévérité | Constat | Preuve | Impact |
|---|---|---|---|---|
| A1 | Bloquant | « Temps réel » n'est pas défini : notification immédiate, rafraîchissement périodique ou action manuelle. (US-E1, TR-2) | « se met à jour en temps réel » (CA 4) | Estimation incertaine (1 à 4 jours) et critère impossible à valider en recette. |
| A2 | Majeur | « Dernière interaction » peut désigner un email, un appel ou toute activité CRM. (TR-1) | « la dernière interaction » (CA 2) | Le développeur choisira une interprétation qui ne sera peut-être pas celle attendue. |
| A3 | Majeur | La période du filtre ne précise pas la date de référence (création, clôture prévue, dernière activité). (US-T1) | « afficher 7, 30 ou 90 jours » (CA 3) | Le critère ne peut pas être testé sans connaître la date filtrée. |
| A4 | Mineur | « Date de clôture » : date prévisionnelle saisie ou date effective. (TR-1) | « la date de clôture » (CA 2) | Clarification d'affichage. |

### Cas non couverts
| # | Sévérité | Constat | Preuve | Impact |
|---|---|---|---|---|
| N1 | Majeur | Le comportement en cas d'indisponibilité de l'API n'est pas décrit. (TR-9) | Absent du document | Tableau vide ou erreur affichée au commercial, sans décision prise. |

## Constats conditionnels
- Si le score est calculé par un service externe à partir de données clients, alors l'envoi de ces données hors du système d'information doit être encadré (contrat, protection des données). — Preuve : « grâce à l'API Perplexity » — Changerait le verdict : non.

## Questions au métier
🔴 Que signifie « temps réel » : mise à jour immédiate, rafraîchissement toutes les X secondes, ou bouton d'actualisation ? Quel délai est acceptable en recette ? (→ A1)
🟠 Le score de probabilité est-il un champ existant du CRM, un calcul interne ou une donnée fournie par Perplexity ? Si c'est Perplexity, l'accès est-il déjà ouvert, et que se passe-t-il s'il ne répond pas ? (→ M1, M2, N1)
🟠 Qu'entend-on par « dernière interaction » : dernier email, dernier appel, ou toute activité enregistrée ? (→ A2)
🟠 Le filtre 7/30/90 jours porte-t-il sur la date de clôture prévue, la date de création ou la dernière activité ? (→ A3)
🟢 La date de clôture affichée est-elle la date prévisionnelle ou la date effective ? (→ A4)

## Pourquoi cette sortie est correcte

- La story n'est pas pénalisée pour l'absence de modèle de données ou de règles détaillées : ce n'est pas attendu dans une user story.
- Chaque constat cite le critère concerné.
- « Temps réel » n'apparaît qu'une fois (A1), même s'il touche à la fois l'estimation et la testabilité.
- Les questions sur le score, l'API et la panne sont fusionnées, car elles portent sur le même sujet.
- Le verdict suit la règle : 1 bloquant et plus de 3 majeurs → À clarifier.
