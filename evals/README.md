# Jeu de test — relecture-spec-ba

Ce dossier n'est pas chargé par la skill. Il sert à vérifier que la skill trouve les bons défauts, sans fausses alertes, et de façon stable.

## Contenu

| Document | Type | Défauts plantés | Verdict attendu |
|---|---|---|---|
| `01-user-story-notifications.md` | User Story | 7 | Non prêt |
| `02-spec-remboursements.md` | Spécification fonctionnelle | 9 | Non prêt |
| `03-cdc-portail-adherents.md` | Cahier des charges | 8 | Non prêt (À clarifier si le contexte n'est pas un appel d'offres) |

Chaque document a un corrigé (`*-corrige.md`) : liste des défauts plantés, sévérité attendue, et **pièges** (ce qui ne doit pas être signalé).

## Protocole

1. Ouvre une **conversation neuve** avec la skill activée (pour éviter que le contexte de création influence le résultat).
2. Colle le document avec une demande simple : « Relis cette spec avant que je l'envoie. »
3. Compare la sortie au corrigé et note :
   - **Détection** : nombre de défauts plantés trouvés / nombre de défauts plantés ;
   - **Fausses alertes** : constats qui figurent dans les pièges, ou qui n'ont pas de preuve dans le document ;
   - **Verdict** : identique ou non au verdict attendu ;
   - **Format** : sections présentes, citations, numérotation, questions renvoyant aux constats.
4. Relance **3 fois** le même document dans 3 conversations neuves. Le verdict doit être identique et les défauts bloquants toujours trouvés ; une variation sur les constats mineurs est acceptable.
5. Pour tester le contexte : relance le document 03 une fois sans rien préciser, une fois en ajoutant « C'est pour un appel d'offres ». Le budget manquant doit passer de constat conditionnel ou majeur à bloquant.

## Seuils indicatifs

- Détection des défauts bloquants : 100 %.
- Détection globale : au moins 80 %.
- Fausses alertes : 0 sur les pièges, au plus 2 constats discutables par document.
- Verdict stable sur les 3 exécutions.

Refais ce protocole après chaque modification de `SKILL.md` ou d'une grille. Ajoute tes propres documents réels (anonymisés) avec leur corrigé au fil du temps : c'est ce qui rendra la skill fiable sur ton terrain.

## Suivi

| Date | Version modifiée | Doc 01 (détection / fausses alertes / verdict) | Doc 02 | Doc 03 | Remarques |
|---|---|---|---|---|---|
| | | | | | |
