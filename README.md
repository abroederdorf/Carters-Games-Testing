# Carters-Games-Testing

Staging environment for [Carter's Games](https://github.com/abroederdorf/Carters-Games). Exports and deploys a branch of the main repo to GitHub Pages for testing before it goes public.

**Live testing URL:** https://testing.alpinealicia.com

---

## How it works

This repo contains no game code — it only has a deploy workflow. When triggered, it:

1. Checks out the specified branch from the main repo
2. Exports the project using Godot (headless)
3. Deploys the build to GitHub Pages at `testing.alpinealicia.com`

---

## Triggering a deploy

### From the main repo (normal flow)

In [Carter's Games](https://github.com/abroederdorf/Carters-Games) → **Actions** → **Export & Deploy** → **Run workflow** → pick `testing`.

This dispatches to this repo with the current branch name. The main repo workflow waits and reports success or failure.

### Manually from this repo

**Actions** → **Deploy** → **Run workflow** → enter the branch name to deploy (e.g. `feat/my-feature`).

---

## Required secrets

| Secret | Purpose |
|--------|---------|
| `PAT` | Personal access token with `repo` scope — used to check out the private main repo |

Set in repo **Settings → Secrets and variables → Actions**.

GitHub Pages deployment uses built-in GitHub Actions permissions — no extra secrets needed.
