# BA Agent — Relecture de specs

Un relecteur senior pour vos documents fonctionnels, avant qu'ils partent chez les développeurs, les testeurs ou un prestataire. Il repère ce qui obligera le destinataire à deviner, à revenir poser des questions ou à refaire du travail.

*English: a senior reviewer for functional documents (user stories, functional specifications, use cases, requirements documents). It reports evidence-based findings, a rule-based readiness verdict and the questions to ask the business. Grids and output are in French; documents in other languages are reviewed in their own language.*

## Ce que fait le plugin

Joignez un document et demandez simplement « relis cette spec ». Le plugin :

1. **Reconstitue le contexte** à partir du document (type, secteur, acteurs, destinataire) et affiche ses hypothèses, sans vous imposer un formulaire.
2. **Applique la grille adaptée au type de document** : INVEST pour les user stories, éléments structurels et points de contrôle pour les spécifications fonctionnelles, les use cases et les cahiers des charges, plus des contrôles transverses (termes non définis, contradictions, références orphelines, qualificatifs non mesurables).
3. **Cite le passage concerné pour chaque constat**, ou indique qu'un élément est absent. Aucun constat sans preuve.
4. **Sépare les constats certains des constats conditionnels**, qui dépendent d'une information de contexte non confirmée.
5. **Calcule un verdict par règle fixe** (Prêt / À clarifier / Non prêt) à partir du nombre de constats bloquants et majeurs, et non une note sur 100 estimée par le modèle.
6. **Rédige les questions à poser au métier**, priorisées et reliées aux constats.

Le rapport est livré sous forme de document. Si vous fournissez un fichier Word et le demandez, les constats peuvent être ajoutés en commentaires dans une copie du fichier.

## Adapter à votre organisation

- `skills/relecture-spec-ba/fiche-projet-modele.md` : le contexte d'un projet (glossaire, acteurs, systèmes, décisions), pour ne pas le redonner à chaque relecture.
- `skills/relecture-spec-ba/referentiel-organisation.md` : vos modèles, conventions et règles internes, qui s'ajoutent aux grilles et priment sur elles.

## Mesurer la qualité

Le dossier `evals/` contient trois documents avec des défauts volontairement plantés, leurs corrigés et un protocole de test. Rejouez-les après toute modification des grilles.

## Données et fonctionnement

Le plugin ne contient que des instructions et des grilles en texte. Il n'exécute aucun script, n'appelle aucun service externe et n'envoie aucune donnée ailleurs que dans votre conversation avec Claude. Les points réglementaires sont un aide-mémoire et ne constituent pas un avis juridique.

## Licence

Creative Commons BY-NC-SA 4.0 : utilisation, adaptation et partage libres à des fins non commerciales, avec attribution et partage dans les mêmes conditions. Pour un usage commercial, une adaptation à votre organisation ou un accompagnement, contactez l'auteur.
