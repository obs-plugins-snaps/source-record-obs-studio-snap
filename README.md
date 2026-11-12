# Source Record Snap for OBS Studio

[![source-record-obs-studio](https://snapcraft.io/source-record-obs-studio/badge.svg)](https://snapcraft.io/source-record-obs-studio)

This snap delivers [Source Record](https://github.com/exeldro/obs-source-record) to the [OBS Studio snap](https://snapcraft.io/obs-studio). Source Record adds an individual record button to any source, letting you record sources independently from the main output.

## Installation

### Install from the Store

```shell
sudo snap install source-record-obs-studio
```

### Connect to the OBS Studio snap

```shell
sudo snap connect obs-studio:obs-plugins source-record-obs-studio:obs-plugins
```

Once connected, Source Record will appear as a filter in OBS Studio. Right-click any source → **Filters** → **+** → **Source Record**.

## Development

```shell
snapcraft
```

The plugin is built against the libobs headers shipped in the
`obs-studio` snap, so no local OBS build is required.

The snap starts in `devel` grade; flip it to `stable` in
`snap/snapcraft.yaml` once the packaged plugin is verified to work.

## E2E tests

The repository ships a small pytest suite (`tests/e2e`) that starts a
headless Wayland session, drives OBS through the accessibility tree, and
checks that the plugin's module is actually loaded. CI runs it on every
pull request against the exact snap built in that run (non-blocking
while the suite soaks). Plugins extend the suite with tests for their
own UI surface.

To run it locally, install the snap and connect it as above, then run
the suite from the shared workflows checkout:

```shell
E2E_OBS_HOME="$PWD/e2e-home" \
  uv run --project /path/to/obs-plugins-snaps/workflows \
  pytest tests/e2e
```

Screenshots, logs and state are collected under `$E2E_OBS_HOME`
(`e2e-home/` above) for triage.
