# Identifier Rename Review — "Orca" leftovers

> Companion to `STRATEGY/infra-migration_plan.md` and `STRATEGY/VisualPalette-migration_plan.md`.
> Decides what to do with the **non-visible "Orca" identifiers** that the display-string sweep deliberately left alone.
> One file per item. Written for a Product Manager, not an engineer.

## The big fact that shapes all of this

**We have 0 users right now.** That means every warning about "users lose data / get logged out / lose their session" is **moot** —
those only happen when a *current* user upgrades an already-installed app. With zero installs there is:

- no saved logins to lose,
- no data folders to migrate,
- no installed firewall rules / TLS certs / helper apps to orphan.

So almost every item below is **safe to rename now**. The only remaining reasons to keep "Orca" are:
1. It's **invisible to users** (so a rename gives zero brand value, only engineering cost/risk).
2. Two parts of **our own product** must be renamed *together* or they stop talking to each other.

## Quick-decision table

| Item | Visible to users? | Recommendation (0 users) | File |
| --- | --- | --- | --- |
| 1. Wire tokens (`orca_server_ready`, `orca:serve-ready`) | No | **✅ Renamed** to `fabrica_*` (both sides ship together) | [01-wire-tokens.md](01-wire-tokens.md) |
| 2. Environment variables (`ORCA_*`) | No | **Keep** (or rename later, low priority) | [02-environment-variables.md](02-environment-variables.md) |
| 3. Plugin `engines.orca` field | No | **Keep "orca"** — tied to plugin trust system | [03-plugin-engines-field.md](03-plugin-engines-field.md) |
| 4. Keychain service name | No (macOS Keychain) | **Rename now** — nothing stored yet | [04-keychain-service.md](04-keychain-service.md) |
| 5. Data folders / `.orca` paths | No | **Rename now** — nothing in them yet | [05-data-directories.md](05-data-directories.md) |
| 6. `Co-authored-by: Orca` git trailer | Yes (git history) | **Rename now** — cosmetic | [06-git-coauthor-trailer.md](06-git-coauthor-trailer.md) |
| 7. App name / About / app menu / productName | **Yes** | **Rename now** — this IS the brand | [07-app-name-and-menu.md](07-app-name-and-menu.md) |
| 8. Windows firewall rule `Orca Mobile Pairing` | Yes (Windows Settings) | **Rename now** | [08-firewall-rule.md](08-firewall-rule.md) |
| 9. TLS certificate `CN=Orca Runtime` | Yes (security prompts) | **Rename now** | [09-tls-certificate.md](09-tls-certificate.md) |
| 10. Windows install path `Program Files\Orca Dev` | Yes (user's disk) | **Rename now** | [10-install-path.md](10-install-path.md) |
| 11. `orca` CLI command | Yes (terminal) | **Keep `orca` + add `fabrica` alias** | [11-cli-command.md](11-cli-command.md) |
| 12. `Orca Computer Use.app` helper (macOS) | Mostly no | **Rename in lockstep** with the app | [12-computer-use-app.md](12-computer-use-app.md) |

## The one real risk (internal wiring, not users)

Even with 0 users, some identifiers are used by **two halves of our own product at once**:

- Desktop app ↔ mobile app pairing (bundle ids, firewall rule, relay pairing),
- Desktop app ↔ macOS "Computer Use" helper (helper app name + permission prompts),
- Desktop app ↔ remote/headless server (wire tokens).

If we rename one half and not the other, pairing / permissions / handshake break. So the rule is simple:

> **Rename everything user-visible now; keep invisible wire/plugin tokens as "orca"; and for anything two products share, rename both sides in the same release.**

Nothing in this folder requires a data migration because we have 0 users.
