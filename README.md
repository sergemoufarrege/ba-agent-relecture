# BA Agent — Spec Review / Relecture de specs

**English** · [Français](#français)

A senior business analyst reviewer for your functional documents, before they go to developers, testers or a vendor. It flags whatever would force the reader to guess, come back with questions or redo work.

Works in **English and French**: the report follows the language of your request.

## What it does

Attach a document and simply ask "review this spec". The plugin:

1. **Infers the context** from the document (type, industry, actors, audience) and states its assumptions, without making you fill in a form.
2. **Applies the checklist for the document type**: INVEST for user stories; structural elements and control points for functional specifications, use cases and requirements documents (BRD, RFP); plus cross-cutting checks (undefined terms, contradictions, broken references, unmeasurable wording).
3. **Quotes the passage for every finding**, or states that an element is missing. No finding without evidence.
4. **Separates certain findings from conditional ones**, which depend on context that isn't confirmed.
5. **Computes the verdict with a fixed rule** (Ready / Needs clarification / Not ready) from the number of blocking and major findings, instead of a score out of 100 guessed by the model.
6. **Writes the questions to ask the business**, prioritised and linked to the findings.

The report is delivered as a document. If you provide a Word file and ask for it, findings can be added as comments in a copy of the file.

## Installation

- **Claude app**: add the plugin from the plugin directory by searching for "BA Agent".
- **Skill only**: [download `relecture-spec-ba.zip`](https://github.com/sergemoufarrege/ba-agent-relecture/raw/main/download/relecture-spec-ba.zip) and upload it in the Claude app settings, Skills section. Then attach a spec and ask "review this spec".
- **Claude Code**: clone this repository and run `claude --plugin-dir ./ba-agent-relecture`.

### Other tools

- **Coding agents that support the open Agent Skills standard** (OpenAI Codex, GitHub Copilot in VS Code, Gemini CLI, Cursor…): copy the `skills/relecture-spec-ba` folder into the tool's skills folder (often `.agents/skills/`; check your tool's documentation).
- **Microsoft 365 Copilot, ChatGPT, Gemini**: use the [portable version](portable/): instructions to paste and knowledge files to upload, with setup steps. [Download all files as a zip](https://github.com/sergemoufarrege/ba-agent-relecture/raw/main/download/ba-agent-portable.zip).

## Tailor it to your organisation

- `skills/relecture-spec-ba/fiche-projet-modele.md`: project context (glossary, actors, systems, decisions), so you don't repeat it for every review.
- `skills/relecture-spec-ba/referentiel-organisation.md`: your templates, conventions and internal rules, which are added to the checklists and take precedence over them.

The instructions and checklists are written in French; they apply equally to English documents.

## Measuring quality

The `evals/` folder contains four documents (three in French, one in English) with deliberately planted defects, their answer keys and a test protocol. Re-run them after any change to the checklists.

## Data handling

The plugin contains only text instructions and checklists. It runs no scripts, calls no external service and sends no data anywhere other than your conversation with Claude. Regulatory points are a reminder, not legal advice. See the [privacy policy](https://github.com/sergemoufarrege/ba-agent-relecture/blob/main/PRIVACY.md).

## Licence

Creative Commons BY-NC-SA 4.0: free to use, adapt and share for non-commercial purposes, with attribution and under the same terms. For commercial use, tailoring to your organisation or support, contact the author.

---

## Français

Un relecteur senior pour vos documents fonctionnels, avant qu'ils partent chez les développeurs, les testeurs ou un prestataire. Il repère ce qui obligera le destinataire à deviner, à revenir poser des questions ou à refaire du travail.

Fonctionne en **français et en anglais** : le rapport suit la langue de votre demande.

### Ce que fait le plugin

Joignez un document et demandez simplement « relis cette spec ». Le plugin :

1. **Reconstitue le contexte** à partir du document (type, secteur, acteurs, destinataire) et affiche ses hypothèses, sans vous imposer un formulaire.
2. **Applique la grille adaptée au type de document** : INVEST pour les user stories, éléments structurels et points de contrôle pour les spécifications fonctionnelles, les use cases et les cahiers des charges, plus des contrôles transverses (termes non définis, contradictions, références orphelines, qualificatifs non mesurables).
3. **Cite le passage concerné pour chaque constat**, ou indique qu'un élément est absent. Aucun constat sans preuve.
4. **Sépare les constats certains des constats conditionnels**, qui dépendent d'une information de contexte non confirmée.
5. **Calcule un verdict par règle fixe** (Prêt / À clarifier / Non prêt) à partir du nombre de constats bloquants et majeurs, et non une note sur 100 estimée par le modèle.
6. **Rédige les questions à poser au métier**, priorisées et reliées aux constats.

Le rapport est livré sous forme de document. Si vous fournissez un fichier Word et le demandez, les constats peuvent être ajoutés en commentaires dans une copie du fichier.

### Installation

- **Dans l'app Claude** : ajoutez le plugin depuis le répertoire des plugins, en cherchant « BA Agent ».
- **Skill seule** : [téléchargez `relecture-spec-ba.zip`](https://github.com/sergemoufarrege/ba-agent-relecture/raw/main/download/relecture-spec-ba.zip) et importez-le dans les paramètres de l'app Claude, section Skills. Joignez ensuite une spec et demandez « relis cette spec ».
- **Claude Code** : clonez ce dépôt et lancez `claude --plugin-dir ./ba-agent-relecture`.

#### Autres outils

- **Agents de code compatibles avec le standard ouvert Agent Skills** (OpenAI Codex, GitHub Copilot dans VS Code, Gemini CLI, Cursor…) : copiez le dossier `skills/relecture-spec-ba` dans le dossier de skills de l'outil (souvent `.agents/skills/` ; vérifiez la documentation de votre outil).
- **Microsoft 365 Copilot, ChatGPT, Gemini** : utilisez la [version portable](portable/), avec les instructions à coller, les fichiers de connaissance à téléverser et la procédure d'installation. [Téléchargez tous les fichiers en un zip](https://github.com/sergemoufarrege/ba-agent-relecture/raw/main/download/ba-agent-portable.zip).

### Adapter à votre organisation

- `skills/relecture-spec-ba/fiche-projet-modele.md` : le contexte d'un projet (glossaire, acteurs, systèmes, décisions), pour ne pas le redonner à chaque relecture.
- `skills/relecture-spec-ba/referentiel-organisation.md` : vos modèles, conventions et règles internes, qui s'ajoutent aux grilles et priment sur elles.

### Mesurer la qualité

Le dossier `evals/` contient quatre documents (trois en français, un en anglais) avec des défauts volontairement plantés, leurs corrigés et un protocole de test. Rejouez-les après toute modification des grilles.

### Données et fonctionnement

Le plugin ne contient que des instructions et des grilles en texte. Il n'exécute aucun script, n'appelle aucun service externe et n'envoie aucune donnée ailleurs que dans votre conversation avec Claude. Les points réglementaires sont un aide-mémoire et ne constituent pas un avis juridique.

**Privacy / Confidentialité :** [politique de confidentialité](https://github.com/sergemoufarrege/ba-agent-relecture/blob/main/PRIVACY.md)

### Licence

Creative Commons BY-NC-SA 4.0 : utilisation, adaptation et partage libres à des fins non commerciales, avec attribution et partage dans les mêmes conditions. Pour un usage commercial, une adaptation à votre organisation ou un accompagnement, contactez l'auteur.
