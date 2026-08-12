# Fabrica Configs & Distribution Migration Plan

> Companion to `STRATEGY/VisualPalette-migration_plan.md`. This document covers **everything that is NOT visual/palette**: metadata, packaging/distribution config, auto-updater & release channels, the deep-link scheme, backend/telemetry endpoints, CLI command names & data directories, CI/CD, Homebrew, and user-visible product-name strings.
>
> All file:line references are against the current `orca/` tree (pre-rebrand). Don't touch `mission-control/`, `old-fabrica/`, `_BACKUP - orca/`.

---

## 1. Rebrand scope (from strategy)

From `STRATEGY/Fabrica-ADE Strategy.md`, the non-visual rebrand goals are:

- **Metadata & Distribution Config** — `package.json`, `electron-builder`, `Fabrica.exe`, build channels.
- **Telemetry Sanitization** — replace `stablyai` analytics with Fabrica-owned servers.
- **Auto-Updater & Releases** — point at `Auto-Skiller/Fabrica-ADE` (and dev-channel repos).
- **Deep Linking Scheme** — `orca://` → `fabrica://`.

---

## 2. Metadata & Distribution Configs

### 2.1 `orca/package.json`

| Field | Current | Target |
| --- | --- | --- |
| `name` | `orca` | `fabrica` |
| `description` | "Next-gen IDE for parallel agentic development" | align to Fabrica positioning |
| `homepage` | `https://github.com/stablyai/orca` | `https://github.com/Auto-Skiller/Fabrica-ADE` |
| `author` | `stablyai` | `Auto-Skiller` (or Fabrica entity) |
| `bin.orca` / `bin.orca-dev` | `orca` / `orca-dev` | `fabrica` / `fabrica-dev` |
| `repository` (if present) | `stablyai/orca` | `Auto-Skiller/Fabrica-ADE` |

### 2.2 `orca/config/electron-builder.config.cjs`

| What | Line | Current | Target |
| --- | --- | --- | --- |
| `appId` | `49` | `com.stablyai.orca` | `com.fabrica.app` (or `com.autoskiller.fabrica`) |
| `productName` | `94` | `'Orca'` | `'Fabrica'` |
| `win.executableName` | `287` | `'Orca'` | `'Fabrica'` |
| `win.nsis.artifactName` | `317` | `orca-windows-setup.${ext}` | `fabrica-windows-setup.${ext}` |
| `win.nsis.shortcutName` / `uninstallDisplayName` | `318-319` | `${productName}` | (auto via productName) |
| `win.extraResources` | `298-303` | `resources/win32/bin/orca.cmd → bin/orca.cmd`, `native/.../.build/orca.exe → bin/orca.exe` | `fabrica.cmd` / `fabrica.exe` (rename source + target) |
| `mac.icon` / `entitlements` | `327-329` | `resources/build/icon.icns` | Fabrica `.icns` (visual task, but path stays) |
| `mac.extendInfo` permission strings | `330-344` | `'Orca allows …'` | `'Fabrica allows …'` |
| `mac.extraResources` | `369-370`, `383-384` | `resources/darwin/bin/orca → bin/orca`, `Orca Computer Use.app` | `fabrica` / `Fabrica Computer Use.app` |
| `mac.extraFiles` | `393` | `orca-notification-status` | `fabrica-notification-status` |
| `dmg.artifactName` | `412` | `orca-macos-${arch}.${ext}` | `fabrica-macos-${arch}.${ext}` |
| `linux.executableName` | `417` | `orca-ide` | `fabrica` (GNOME `orca` conflict no longer applies; verify) |
| `linux.desktop.entry.StartupWMClass` | `425` | `orca` | `fabrica` |
| `linux.extraResources` | `433-434` | `resources/linux/bin/orca-ide → bin/orca-ide` | `fabrica` |
| `linux.maintainer` | `447` | `stablyai` | `Auto-Skiller` |
| `linux.category` | `448` | `Utility` | (keep) |
| `appImage.artifactName` | `451` | `orca-linux(-arm64).${ext}` | `fabrica-linux(-arm64).${ext}` |
| `deb.packageName` / `artifactName` | `454-455` | `orca-ide` | `fabrica` |
| `rpm.packageName` / `artifactName` | `476-477` | `orca-ide` | `fabrica` |
| `publish` | `500-504` | `owner:'stablyai'`, `repo: devChannelRepo ?? 'orca'` | `owner:'Auto-Skiller'`, `repo:'Fabrica-ADE'` (+ dev channels) |
| `devChannelRepo` | `42-48` | `orca-hourly` / `orca-daily` / `orca-adhoc` | `fabrica-hourly` / `fabrica-daily` / `fabrica-adhoc` |
| `chmodUnixCliLaunchers` list | `512` | `['orca','orca-ide']` | `['fabrica']` |
| `afterPack` / signing helpers | `208,279,281,393,543,552,570` | `Orca Computer Use.app`, `orca-notification-status`, `ORCA_COMPUTER_MACOS_SIGN_IDENTITY` | `Fabrica Computer Use.app`, `fabrica-notification-status`, `FABRICA_…_SIGN_IDENTITY` |

### 2.3 Homebrew Casks — `orca/Casks/orca.rb`, `orca@rc.rb`

| Field | Current | Target |
| --- | --- | --- |
| `name` | `"Orca"` / `"Orca RC"` | `"Fabrica"` / `"Fabrica RC"` |
| `app` | `"Orca.app"` | `"Fabrica.app"` |
| `binary` | `#{appdir}/Orca.app/.../bin/orca` | `.../bin/fabrica` |
| data dir | `~/Library/Application Support/Orca` | `~/Library/Application Support/Fabrica` |
| tap | `stablyai/homebrew-orca` | `Auto-Skiller/homebrew-fabrica` |

### 2.4 CLI launchers / packaged resources

| File | Current | Target |
| --- | --- | --- |
| `resources/linux/bin/orca-ide` | `orca-ide` | `fabrica` |
| `resources/darwin/bin/orca` | `orca` | `fabrica` |
| `resources/win32/bin/orca.cmd` | `orca.cmd` | `fabrica.cmd` |
| `native/windows-cli-launcher/.build/orca.exe` | `orca.exe` | `fabrica.exe` |
| `resources/linux/packaging/after-install.sh`, `after-remove.sh` | reference `orca-ide` | `fabrica` |

### 2.5 Bundled plugin publisher — `resources/plugins/launch/`

- `stablyai.orca-portuguese/orca-plugin.json`: `publisher:"stablyai"` → `fabrica`; `repository` → Fabrica repo.
- `stablyai.orca-navigation-shortcuts`, `stablyai.orca-multipass-recipes`: rename plugin dirs + `publisher` fields.
- `bundled-plugins.json` / `orca-marketplace.json`: update any `stablyai.*` references.

---

## 3. Runtime CLI command names & data directories (migration-sensitive)

These ship to user machines and carry **user data** — renaming needs a migration path (keep legacy-symlink/relocation logic).

| Concern | File:line | Current | Target |
| --- | --- | --- | --- |
| Dev CLI command | `src/main/cli/cli-installer.ts:31` | `orca-dev` | `fabrica-dev` |
| Linux CLI command | `:32` | `orca-ide` | `fabrica` |
| Legacy linux command | `:33` | `orca` | (drop / migrate) |
| Default command (mac/win) | `:91` | `orca` | `fabrica` |
| Install paths | `:340,343,354` | `~/.local/bin/orca-dev`, `Programs/Orca Dev/bin/orca-dev.cmd`, `~/.local/bin/orca-ide` | `~/.local/bin/fabrica-dev`, `Programs/Fabrica Dev/bin/fabrica-dev.cmd`, `~/.local/bin/fabrica` |
| WSL command | `src/main/cli/wsl-cli-installer.ts:24,25` | `orca-ide` / `orca` | `fabrica` |
| WSL bridge script | `src/main/cli/wsl-cli-scripts.ts:77` | `~/.local/share/orca/orca-wsl-bridge.ps1` | `~/.local/share/fabrica/...` |
| Linux shim | `src/main/cli/linux-terminal-orca-cli-shim.ts:48` | `~/.local/bin/orca` (execs `orca-ide`) | `~/.local/bin/fabrica` (execs `fabrica`) |
| Linux dispatcher | `src/main/cli/linux-bare-orca-dispatcher.ts:43` | `~/.local/bin/orca` (execs `orca-ide`) | `~/.local/bin/fabrica` |
| App config/data dir (mac) | `src/main/codex/codex-home-paths.ts:61` | `~/Library/Application Support/orca` | `.../Fabrica` |
| App config/data dir (win) | `:64` | `%APPDATA%/orca` | `%APPDATA%/Fabrica` |
| App config/data dir (linux) | `:66` | `~/.config/orca` | `~/.config/fabrica` |
| Agent runtime home | many (`~/.local/share/orca/...`) | `orca` | `fabrica` |

> **Migration note:** existing users have worktrees/agent state under `~/.config/orca`, `~/.local/share/orca`, `~/Library/Application Support/orca`. The first Fabrica release should relocate (or symlink) these dirs, or users lose local worktree/agent history.

---

## 4. Auto-Updater & Release Channels

The feed URLs are derived from repo constants — **this is the core of the Auto-Updater goal**.

| What | File:line | Current | Target |
| --- | --- | --- | --- |
| Main release repo | `src/shared/release-channel.ts:27` (`MAIN_RELEASE_REPO`) | `stablyai/orca` | `Auto-Skiller/Fabrica-ADE` |
| Hourly repo | `:24` | `stablyai/orca-hourly` | `Auto-Skiller/Fabrica-ADE-hourly` |
| Daily repo | `:25` | `stablyai/orca-daily` | `Auto-Skiller/Fabrica-ADE-daily` |
| Adhoc repo | `:26` | `stablyai/orca-adhoc` | `Auto-Skiller/Fabrica-ADE-adhoc` |
| Channel→repo resolver | `:73` (`getReleaseRepoForChannel`) | reads above | (auto via constants) |
| Feed URL builder | `src/main/updater-release-builds.ts:19-21` (`getReleaseDownloadUrlForRepo`) | `https://github.com/${repo}/releases/download/...` | (auto via repo constants) |
| Releases API URL | `:15-17` (`getReleasesApiUrl`) | `https://api.github.com/repos/${repo}/releases` | (auto via repo constants) |
| Updater fallback feed | `src/main/updater.ts:1440,2205` | `https://github.com/stablyai/orca/releases/latest/download` | `.../Auto-Skiller/Fabrica-ADE/...` |
| electron-builder publish | `config/electron-builder.config.cjs:500-504` | `owner:'stablyai'`, `repo:'orca'` | `owner:'Auto-Skiller'`, `repo:'Fabrica-ADE'` |

> The GitHub release **tags** themselves (e.g. `v1.4.178-rc.2`) stay semver; only the *owner/repo* changes. Dev-channel builds still need matching `fabrica-hourly`/`fabrica-daily`/`fabrica-adhoc` repos on GitHub.

---

## 5. Deep-link scheme `orca://` → `fabrica://`

Pairing / handoff URLs are generated and parsed as `orca://pair?…` / `orca://pair#…` / `orca://worktree/serve`. **Every literal must change**, plus the OS registration.

| Role | File |
| --- | --- |
| Pairing code builder / parser | `src/shared/pairing.ts:26,35,47,62,74` |
| Web pairing input parser | `src/renderer/src/web/web-pairing.ts:26,49,128` |
| Redaction of pairing URLs | `src/shared/ephemeral-vm-recipe-diagnostics.ts:42,62,69` |
| Fixture builder | `src/shared/mobile-relay-pairing-fixtures.ts:139` |
| CLI client error / help | `src/cli/runtime/client.ts:292`, `src/cli/help.ts:284`, `src/cli/specs/environment.ts:10` |
| Mobile IPC | `src/main/ipc/mobile.ts` (pairingUrl) |
| Serve readiness / argv | `src/main/server/serve-readiness.ts`, `src/main/startup/serve-mode-argv.ts` |
| CLI launch handler | `src/cli/runtime/launch.ts` / `client.ts` (orca://pair inputs) |

- **OS registration:** no `app.setAsDefaultProtocolClient('orca')` / `registerSchemesAsPrivileged` was found in `src/`. Locate the registration (likely `src/main/index.ts` bootstrap, or an electron-builder `protocols:` entry) and register `fabrica://`.
- **Tests assert the literal** `orca://…` in `web-pairing.test.ts`, `pairing.test.ts`, `serve-readiness.test.ts`, `serve-mode-argv.test.ts`, `mobile.test.ts`, `cli/index.test.ts`, `cli/runtime/launch.test.ts`, `ephemeral-vm-*.test.ts` — update fixtures to `fabrica://`.

---

## 6. Backend / Telemetry / Domain URLs (StablyAI infra → Fabrica)

These point at StablyAI servers and must be repointed or made configurable (covers **Telemetry Sanitization** + updater/feedback endpoints).

| Endpoint | File |
| --- | --- |
| PostHog apiKey `phc_3hhj3GZzKXUY3VvRyJZTiLmQ4jwPijCZsiT7V7w8pHY5` | `src/main/telemetry/posthog.ts` (replace with Fabrica analytics / disable) |
| `https://share.onorca.dev` | `src/main/artifacts/artifact-cloud-config.ts:3` (+ host allow-list `:21`) |
| `https://login.onorca.dev`, `https://relay.onorca.dev` | `src/main/orca-profiles/profile-cloud-auth-config.ts:19,21` |
| `https://www.onorca.dev/v1/feedback` | `src/main/ipc/feedback.ts:17` |
| `https://onorca.dev/changelog`, `/whats-new/*` | `src/main/updater-changelog.ts:13,45`, `updater-nudge.ts:12`, `updater-events.ts:196` |
| `https://relay.onorca.dev` (fixtures) | `src/shared/mobile-relay-pairing-fixtures.ts` |
| `https://onorca.dev/plugins/kill-list.json` | `src/main/plugins/plugin-kill-list-service.ts:10` |
| `https://www.onorca.dev/docs/…` | `src/shared/feature-wall-workflows.ts`, `feature-wall-tiles.ts` |
| `ORCA_DIAGNOSTICS_TOKEN_URL` / `https://www.onorca.dev/diagnostics/token` | referenced in `.github/workflows/release-cut.yml`, `hourly-mac-build.yml`, `daily-mac-build.yml`, `adhoc-mac-build.yml` (env var) + `src/main/…` diagnostics uploader |
| Product URL + attribution footer | `src/main/attribution/terminal-attribution.ts:12` (`ORCA_PRODUCT_URL`), `:572,606,1002,1033` ("Made with Orca 🐋" → "Made with Fabrica") |
| `github.com/stablyai/orca` | `terminal-attribution.ts`, `README.md`, `docs/readme/README.*.md`, `ORCA_WINDOWS_SETUP_GUIDE.md`, `CONTRIBUTING.md`, `Casks/*.rb` |

> Recommended: move all endpoints behind env vars / a config module so infra can change without a code release.

---

## 7. CI/CD — `.github/workflows`

| Concern | File | Current | Target |
| --- | --- | --- | --- |
| Repo guard | `release-cut.yml:68`, `hourly/daily/adhoc-mac-build.yml`, `readme-downloads-badge.yml:23`, `homebrew-bump.yml` | `github.repository == 'stablyai/orca'` | `'Auto-Skiller/Fabrica-ADE'` |
| Dev release repos | `hourly:58`, `daily:66`, `adhoc:77` (`*_REPO`) | `stablyai/orca-hourly|daily|adhoc` | `Auto-Skiller/Fabrica-ADE-hourly|daily|adhoc` |
| Homebrew tap | `homebrew-bump.yml:10,137,147,152` | `stablyai/homebrew-orca` | `Auto-Skiller/homebrew-fabrica` |
| Cask bump | `homebrew-bump.yml:73-77,104-108` | `orca`/`orca@rc` tokens, `orca-macos-*.dmg` | `fabrica`/`fabrica@rc`, `fabrica-macos-*.dmg` |
| SignPath project-slug | `release-cut.yml:1278,1489` | `orca` | `fabrica` |
| Diagnostics token URL | `release-cut.yml`, mac builds | `https://www.onorca.dev/diagnostics/token` | Fabrica diagnostics endpoint |
| Windows signing | `release-cut.yml` | signs `Orca.exe`, `orca-windows-setup.exe`, `orca-windows-inner-*` | `Fabrica.exe`, `fabrica-windows-setup.exe` |
| macOS helper signing | mac builds | `Orca Computer Use.app` | `Fabrica Computer Use.app` |
| Release repo scripts | `config/scripts/setup-hourly-release-repo.sh`, `setup-daily-release-repo.sh`, `setup-adhoc-release-repo.sh` | reference `orca-*` repos | `fabrica-*` repos |
| Mobile builds | `mobile-android-release.yml:76,109`, `mobile-ios-release.yml:106,109,140` | `orca-mobile-apk`, `orca-signing.keychain-db`, `orca-dist-cert.p12`, title "Orca Mobile Android" | `fabrica-mobile-*` etc. |

---

## 8. User-visible product-name strings (i18n)

These are the strings a user reads — rename the **English default** to `Fabrica` (keep i18n keys unchanged):

- `src/renderer/src/App.tsx:2094,2097` `translate('auto.App.5096cbbc86','Orca')` (titlebar/sidebar wordmark)
- `src/renderer/src/web/web-preload-api.ts:551` `name:'Orca'`
- `src/renderer/src/components/crash-report/CrashReportDialogSurface.tsx`, `onboarding/OnboardingFlow.tsx:213`, `mobile/slides/HomeSlide.tsx:12`, `status-bar/ResourceUsageStatusSegment.tsx:267`, `lib/remote-pairing-copy.ts:62,88` (`endpoint:'Orca'`), `automations/*` panes, `components/plugin-catalog/plugin-display-name.ts:8` (special-cases `'orca'` casing).
- **Test fixtures**: hundreds of `displayName:'Orca'` / `repo:'orca'` / `'StablyAI'` strings in `*.test.ts(x)` are test data — leave unless they assert user-facing copy.

---

## 9. Scope / risk notes

- This is a **large** surface (100s of references). Keep edits surgical; do not rewrite working logic.
- Respect Orca's cross-platform + remote-wire-compat + Git-provider constraints (`orca/AGENTS.md`): renaming `appId`, deep-link scheme, and data dirs can break previously-paired clients, saved shortcuts, and local worktree/agent state — coordinate with a **major version bump** and ship data-dir migration.
- Many references are in tests; prefer global rename with care, then run `pnpm lint` / `vitest` in `orca/`.
- The deep-link OS-registration call was **not** found via the standard Electron APIs in `src/` — confirm its location before renaming the scheme, or the app won't receive `fabrica://` opens.

---

## 10. Ordered checklist (configs)

1. **Repo/package metadata:** `package.json` (name/author/homepage/bin/description) + `src/shared/release-channel.ts` repo constants (`Auto-Skiller/Fabrica-ADE` + dev repos).
2. **electron-builder:** `appId`, `productName`, `executableName`, `artifactName` (`fabrica-*`), permission strings, helper app names, `publish` owner/repo, `devChannelRepo` names, `chmodUnixCliLaunchers` list.
3. **CLI + data dirs:** `cli-installer.ts`, `wsl-cli-installer.ts`, shim/dispatcher, `codex-home-paths.ts`; rename resources bins (`fabrica`/`fabrica.cmd`/`fabrica.exe`); add data-dir migration.
4. **Deep link:** register `fabrica://`; rename all `orca://` literals + tests.
5. **Auto-updater feed:** `updater-release-builds.ts`, `updater.ts` fallback URLs (auto via repo constants).
6. **Backend/telemetry:** repoint or disable `onorca.dev` + PostHog to Fabrica infra (env-configurable); update `terminal-attribution.ts` product URL/footer; update docs/README links.
7. **CI/CD:** `.github/workflows` repo guards, dev repos, Homebrew tap/cask, SignPath slug, signing artifact names, `config/scripts/*-release-repo.sh`, mobile build names.
8. **Homebrew + plugins:** `Casks/orca.rb`/`orca@rc.rb`, plugin `publisher` fields.
9. **Display strings:** replace user-visible `'Orca'` defaults with `'Fabrica'`.
10. **Verify:** `pnpm lint` + `vitest` in `orca/`; cut a smoke release to `Auto-Skiller/Fabrica-ADE` and confirm updater feed + deep link resolve.
