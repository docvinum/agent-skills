# agent-skills

Skills génériques et réutilisables pour agents IA (Claude Code, etc.), sans dépendance à un projet ou à un contexte matériel particulier.

Extraites du dépôt `ai-skills` (qui conserve en plus les skills spécifiques à des projets).

## Contenu

- `skills/docx` — création / lecture / édition de documents Word (.docx, .dotx)
- `skills/pdf` — lecture, fusion, découpe, formulaires, OCR de PDF
- `skills/pptx` — création / lecture / édition de présentations PowerPoint
- `skills/xlsx` — création / lecture / édition de feuilles de calcul
- `skills/skill-creator` — création, amélioration et évaluation de skills
- `skills/consolidate-memory` — passe de consolidation de la mémoire de l'agent
- `skills/schedule` — création / mise à jour de tâches planifiées
- `skills/morning` — brief matinal rendu en artefact HTML
- `skills/setup-cowork` — configuration guidée de Cowork

## Installation sur une nouvelle machine

```bash
git clone <remote-url> ~/git/agent-skills
mv ~/.claude/skills ~/.claude/skills.bak 2>/dev/null  # si un dossier existant gêne
ln -s ~/git/agent-skills/skills ~/.claude/skills
```

## Synchronisation

La branche `main` est protégée : pas de push direct, tout changement passe par une pull request.

```bash
cd ~/git/agent-skills
git switch -c update-skills
git add -A
git commit -m "chore: update skills"
git push -u origin update-skills
gh pr create --fill
gh pr merge --squash --delete-branch   # bypass admin si aucune review disponible
```

Puis sur les autres machines :

```bash
cd ~/git/agent-skills
git switch main
git pull
```
