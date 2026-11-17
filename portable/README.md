# BA Agent — Portable version / Version portable

**English** · [Français](#français)

Use BA Agent in AI assistants that don't read Claude skills: **Microsoft 365 Copilot**, **ChatGPT** (custom GPTs), **Google Gemini** (Gems) and any assistant that accepts custom instructions plus knowledge files.

Coding agents that support the open Agent Skills standard (Claude Code, OpenAI Codex, GitHub Copilot in VS Code, Gemini CLI, Cursor…) can use the skill folder `skills/relecture-spec-ba` directly instead.

## What's in this folder

| File | Where it goes |
|---|---|
| `BA-Agent-instructions.txt` | Paste its content into the assistant's **Instructions** field (about 6,800 characters). |
| `knowledge/BA-Agent-grilles.txt` | Upload as a knowledge file: all review checklists. |
| `knowledge/BA-Agent-exemple.txt` | Upload as a knowledge file: a full example review. |
| `knowledge/BA-Agent-referentiel-organisation.txt` | Upload as a knowledge file; fill it in with your organisation's rules first (optional). |
| `knowledge/BA-Agent-fiche-projet-modele.txt` | Upload as a knowledge file: the project sheet template. |

## Setup

Menus change often; labels below are indicative.

**Microsoft 365 Copilot (agent)**
1. In Microsoft 365 Copilot, open **Agents → Create agent → Configure**.
2. Name: BA Agent. Paste the instructions.
3. Under **Knowledge**, upload the four files (or point to a SharePoint folder containing them).
4. Test with a document, then share the agent with your team.

**ChatGPT (custom GPT)**
1. **GPTs → Create → Configure**.
2. Paste the instructions and upload the four files under **Knowledge**.
3. Enable data analysis (code) if you want reports as Word files; web browsing and image generation are not needed.
4. In a company workspace, keep the GPT visible to your workspace only.

**Google Gemini (Gem)**
1. **Gems → New Gem**.
2. Paste the instructions and add the four files.
3. Save and test.

## Good to know

- The method, checklists and verdict rule work the same everywhere. Producing a Word report or comments in your file depends on what the assistant can do with files; otherwise the report appears in the chat.
- Results can vary between assistants. Check with the test documents in `evals/` (document 04 is in English) before rolling out to a team.
- Only submit documents your organisation allows you to process with that assistant.

---

## Français

Pour utiliser BA Agent dans des assistants qui ne lisent pas les skills Claude : **Microsoft 365 Copilot**, **ChatGPT** (GPT personnalisés), **Google Gemini** (Gems) et tout assistant qui accepte des instructions personnalisées et des fichiers de connaissance.

Les agents de code compatibles avec le standard ouvert Agent Skills (Claude Code, OpenAI Codex, GitHub Copilot dans VS Code, Gemini CLI, Cursor…) peuvent utiliser directement le dossier `skills/relecture-spec-ba`.

### Contenu du dossier

| Fichier | Où il va |
|---|---|
| `BA-Agent-instructions.txt` | À coller dans le champ **Instructions** de l'assistant (environ 6 800 caractères). |
| `knowledge/BA-Agent-grilles.txt` | Fichier de connaissance : toutes les grilles de relecture. |
| `knowledge/BA-Agent-exemple.txt` | Fichier de connaissance : un exemple de relecture complète. |
| `knowledge/BA-Agent-referentiel-organisation.txt` | Fichier de connaissance, à remplir d'abord avec les règles de votre organisation (facultatif). |
| `knowledge/BA-Agent-fiche-projet-modele.txt` | Fichier de connaissance : le modèle de fiche projet. |

### Installation

Les menus changent souvent : les intitulés ci-dessous sont indicatifs.

**Microsoft 365 Copilot (agent)**
1. Dans Microsoft 365 Copilot, ouvrez **Agents → Créer un agent → Configurer**.
2. Nom : BA Agent. Collez les instructions.
3. Dans **Connaissances**, téléversez les quatre fichiers (ou indiquez un dossier SharePoint qui les contient).
4. Testez sur un document, puis partagez l'agent avec votre équipe.

**ChatGPT (GPT personnalisé)**
1. **GPT → Créer → Configurer**.
2. Collez les instructions et téléversez les quatre fichiers dans **Connaissances**.
3. Activez l'analyse de données (code) si vous voulez des rapports en fichier Word ; la navigation web et la génération d'images sont inutiles.
4. Dans un espace d'entreprise, limitez la visibilité du GPT à votre espace de travail.

**Google Gemini (Gem)**
1. **Gems → Nouveau Gem**.
2. Collez les instructions et ajoutez les quatre fichiers.
3. Enregistrez et testez.

### Bon à savoir

- La méthode, les grilles et la règle de verdict fonctionnent partout. La production d'un rapport Word ou de commentaires dans votre fichier dépend de ce que l'assistant sait faire avec les fichiers ; sinon, le rapport s'affiche dans la conversation.
- Les résultats peuvent varier d'un assistant à l'autre. Vérifiez avec les documents de test du dossier `evals/` (le document 04 est en anglais) avant de déployer à une équipe.
- Ne soumettez que des documents que votre organisation autorise à traiter avec cet assistant.
