# Spécification fonctionnelle — Module de remboursement des frais de santé

Version 0.3 — Mutuelle Horizon

## 1. Périmètre

Le module permet à un adhérent de demander le remboursement d'une dépense de santé non prise en charge automatiquement, et au gestionnaire de traiter la demande.

Inclus : dépôt de la demande, contrôle, validation, paiement.
Exclu : la télétransmission automatique avec l'Assurance Maladie (traitée par le module Flux Noémie).

## 2. Acteurs

- Adhérent : dépose les demandes depuis l'espace adhérent.
- Gestionnaire : contrôle et valide les demandes.
- Système de paiement : exécute les virements.

## 3. Règles de gestion

- **RG-01** : Une demande doit comporter au moins un justificatif (PDF, JPG ou PNG, 5 Mo maximum).
- **RG-02** : Une demande ne peut être déposée que dans les 2 ans suivant la date des soins.
- **RG-03** : SI le montant demandé est supérieur à 500 €, ALORS la demande est soumise à validation manuelle par un gestionnaire.
- **RG-04** : Le montant remboursé est égal au montant de la dépense multiplié par le taux de garantie du contrat.
- **RG-05** : Le plafond annuel par adhérent est appliqué conformément à RG-12.
- **RG-06** : Une demande rejetée peut être corrigée et redéposée par l'adhérent.
- **RG-07** : Les demandes d'un montant inférieur ou égal à 1 000 € sont validées automatiquement si le justificatif est lisible.

Le gestionnaire traite les demandes dans un délai raisonnable.

## 4. Modèle de données

**DEMANDE_REMBOURSEMENT**

| Champ | Type | Obligatoire |
|---|---|---|
| id_demande | UUID | Oui |
| id_adherent | UUID | Oui |
| date_soins | Date | Oui |
| montant_demande | Décimal (10,2) | Oui |
| montant_rembourse | Décimal (10,2) | Non |
| type_soin | | Oui |
| statut | Liste : BROUILLON, SOUMISE, VALIDEE, PAYEE | Oui |
| motif_rejet | Texte (500) | Non |

## 5. Workflow

1. L'adhérent crée la demande (statut BROUILLON).
2. L'adhérent soumet la demande (statut SOUMISE).
3. La demande est contrôlée (statut EN_CONTROLE).
4. La demande est validée (statut VALIDEE) ou rejetée (statut REJETEE).
5. Le système de paiement effectue le virement (statut PAYEE).

## 6. Exigences fonctionnelles

- **EF-01** : L'adhérent peut créer, enregistrer en brouillon et soumettre une demande.
- **EF-02** : L'adhérent peut joindre un ou plusieurs justificatifs conformes à RG-01.
- **EF-03** : Le gestionnaire dispose d'une liste des demandes à valider, triée par date de soumission.
- **EF-04** : Le gestionnaire peut valider ou rejeter une demande en saisissant un motif de rejet.
- **EF-05** : L'adhérent est informé de l'avancement de sa demande.
- **EF-06** : L'adhérent consulte l'historique de ses demandes.
