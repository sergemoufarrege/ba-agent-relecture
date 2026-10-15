# Corrigé — 02 Spécification « Remboursements »

**Verdict attendu : Non prêt** (au moins 3 bloquants : D1, D2, D3, D4).

## Défauts plantés

| # | Point de contrôle | Défaut | Preuve | Sévérité attendue |
|---|---|---|---|---|
| D1 | TR-5 | Contradiction de seuils : au-dessus de 500 € validation manuelle, mais validation automatique jusqu'à 1 000 €. Une demande de 700 € a deux comportements. | RG-03 vs RG-07 | Bloquant |
| D2 | SF-D4 / TR-5 | Statuts incohérents : EN_CONTROLE et REJETEE apparaissent dans le workflow mais pas dans la liste du modèle de données. | §4 statut vs §5 étapes 3–4 | Bloquant |
| D3 | TR-4 | Référence orpheline : RG-12 n'existe pas, donc le plafond annuel est indéfini. | RG-05 | Bloquant |
| D4 | SF-RG3 | Formule incomplète : pas d'arrondi, pas de prise en compte du remboursement déjà versé par l'Assurance Maladie, pas d'application du plafond. | RG-04 | Bloquant ou Majeur |
| D5 | SF-D1 | Le champ type_soin n'a ni type ni liste de valeurs. | §4 | Majeur |
| D6 | TR-2 / SF-W5 | Délai non chiffré. | « délai raisonnable » (§3) | Majeur |
| D7 | SF-W3 / TR-9 | Échec du virement non traité (RIB invalide, rejet bancaire). | Absent du document (§5 étape 5) | Majeur |
| D8 | TR-7 / SF-W1 | Acteur du contrôle non précisé (gestionnaire ou contrôle automatique). | « La demande est contrôlée » (§5 étape 3) | Majeur |
| D9 | SF-T1 | Exigence non vérifiable : canal et moments d'information non précisés. | EF-05 | Majeur |

## Constats acceptés en plus (non plantés mais légitimes)

- Absence de règle sur les doublons (même soin déposé deux fois).
- Workflow de redépôt après rejet (RG-06) non décrit dans le §5.
- Données de santé : hébergement et confidentialité (constat **conditionnel** ou Majeur, le secteur étant explicite).

## Pièges — ne doivent pas être signalés

- Absence de choix technique (outil de GED, prestataire de paiement).
- Absence de maquettes.
- Le périmètre et les exclusions : ils sont présents (§1).
