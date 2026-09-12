# Fieldstar add-in releases

Signed release packages for the Fieldstar SOLIDWORKS add-in. **No source lives here** —
the source is in `fieldstar-solidworks-addin`.

Each release carries two assets:

- `SwCostingAddin-<version>.zip` — the add-in
- `manifest.json` — version, SHA-256, and the release signature

Workstations read the latest release through the GitHub API on SOLIDWORKS startup, verify
the package's hash **and** its RSA signature against the public key compiled into the
add-in, and stage it. The updater re-verifies and applies it when SOLIDWORKS next closes.

The signature is what makes a package trustworthy, not this repository. Anything not
signed by the Fieldstar release key is refused, whatever it was downloaded from.

Publishing: `scripts\publish-update.ps1` in the source repo.
Provisioning a workstation: `scripts\set-release-token.ps1`.
