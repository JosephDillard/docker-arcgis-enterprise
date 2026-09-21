# Agent guide: Docker ArcGIS Enterprise experiments

These instructions apply throughout this repository. Read [README.md](README.md), the relevant image README, and [COPYRIGHT.md](COPYRIGHT.md). Preserve upstream provenance and the existing MIT license.

## Scope and layout

This is an experimental container setup derived from Brian H Wilson's Wildsong project. The inherited README records historical environment results, not a current Esri support certification.

- `server/`, `portal/`, `datastore/`, and `ubuntu-server/`: image definitions and setup scripts.
- `web-adaptor/`: separate historical Web Adaptor setup.
- `Dockerfile.postgres` and `compose.yaml`: database image and root stack configuration.
- `sample.env` and `configurebasedeployment.properties.SAMPLE`: configuration templates.
- `Installers/` and `Licenses/`: instructions for user-provided proprietary prerequisites.

## Working rules

- Preserve Brian H Wilson/Wildsong attribution; do not replace upstream ownership notices with the repository owner's name.
- Do not commit Esri installers, license files, tokens, passwords, configured secret files, or data volumes. Inspect local configuration without printing secrets.
- Verify product versions, Linux prerequisites, license requirements, and official support guidance when changing deployment instructions. Keep historical claims dated.
- Separate image build checks from successful ArcGIS configuration, federation, or operational validation. A running container alone is insufficient evidence of a working site.
- Keep product/data volumes intact. Starting, federating, upgrading, or deleting a stack must be within the requested task scope; do not do it merely to validate documentation.

## Validation

For Compose edits, use `docker compose config --quiet` with the required local variables when Docker is available; do not print the resolved configuration containing secrets. For shell edits, use syntax checks before execution. Build affected images only when the necessary installers and licenses are available and relevant to the task. Report unavailable prerequisites and distinguish static checks, image builds, and actual ArcGIS workflow tests.

## Repository documentation and notices

- Keep [README.md](README.md) aligned with actual setup, commands, and limitations. Keep this `AGENTS.md` at the repository root and update relevant instructions when workflows change.
- Follow [COPYRIGHT.md](COPYRIGHT.md) and any applicable license files. Preserve existing copyright years, ownership, third-party attribution, and license scope; do not relicense material as part of routine maintenance.
- For documentation-only edits, verify added/changed local links and run `git diff --check`. Runtime suites are needed when behavior or executable examples change, not for a notice or wording-only edit.
- Before finishing, review the diff for unrelated changes, generated artifacts, and secrets. Report what changed, what was checked, and any checks that could not run.
