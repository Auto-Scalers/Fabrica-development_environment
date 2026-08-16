# Git Guide — Fabrica Repo Split

This guide documents how the Fabrica monorepo is split into three independent repositories, with **full commit history preserved** and **no files lost on disk**.

## Target layout

| Local folder | GitHub repo |
| --- | --- |
| `Fabrica-IDE/Fabrica-web` | `Auto-Scalers/Fabrica-web` |
| `Fabrica-IDE/orca` | `Auto-Scalers/Fabrica-app` |
| `Fabrica-IDE` (root) | `Auto-Scalers/Fabrica-development_environment` |

All three GitHub repos already exist. `Fabrica-web` is already its own git repo pointing at the correct remote; the work is finishing the push and splitting `orca` out of the root repo.

> Core rule: git never deletes files on disk — it only changes what it *tracks*. Everything below is safe.

---

## Phase 0 — Safety backup (recommended, ~1 min)

```powershell
Compress-Archive -Path "C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE\orca","C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE\STRATEGY","C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE\AGENTS.md" -DestinationPath "$HOME\Desktop\fabrica-backup.zip"
```

Insurance only. Even if something goes wrong, the files are recoverable.

---

## Phase 1 — Fabrica-web (already linked)

`Fabrica-web` is already its own repo pointing at `Auto-Scalers/Fabrica-web`. Just finish it:

```powershell
cd "C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE\Fabrica-web"
git add -A
git commit -m "Update globals.css"
git push -u origin main
```

---

## Phase 2 — orca → Fabrica-app (history preserved)

Run these in the **root** folder:

```powershell
cd "C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE"
# 1. Save current state (so the split includes any uncommitted work)
git add -A
git commit -m "Snapshot before splitting repos"

# 2. Extract orca's full commit history into its own branch
git subtree split -P orca -b fabrica-app-history

# 3. Push that branch as the main branch of Fabrica-app
git push --force https://github.com/Auto-Scalers/Fabrica-app.git fabrica-app-history:main
```

`--force` is safe because Fabrica-app is brand new/empty.

Then make the `orca` folder itself a real repo so you work on it independently:

```powershell
cd "C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE\orca"
git init -b main
git remote add origin https://github.com/Auto-Scalers/Fabrica-app.git
git fetch origin main
git reset --mixed origin/main
```

Your files stay untouched — this just attaches the history you pushed.

---

## Phase 3 — Root → Fabrica-development_environment

```powershell
cd "C:\Users\BAB AL SAFA\Desktop\Fabrica-IDE"
# 1. Stop tracking orca (files stay on disk, they just move to Fabrica-app)
git rm -r --cached orca
git commit -m "Remove orca from dev-environment repo"

# 2. Create .gitignore so backups and the app folders never get pushed
Set-Content .gitignore "orca/`nFabrica-web/`n.backup/`n_sources/`n*.log"
git add .gitignore
git commit -m "Add gitignore"

# 3. Point this repo at the new remote and push
git remote set-url origin https://github.com/Auto-Scalers/Fabrica-development_environment.git
git push -u origin main
```

---

## Verify

- `git remote -v` in each of the three folders should show the correct URL.
- `git status` in all three should be clean.
- Planning docs (`STRATEGY/`, `*.plans`, `AGENTS.md`, `README.md`) live in the development-environment repo.

## Optional cleanup

The old `Auto-Scalers/Fabrica` repo on GitHub is now orphaned — delete it or keep it as an archive.