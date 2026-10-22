# Source Record Snap for OBS Studio

<<<<<<< before updating
This snap delivers [Source Record](https://github.com/exeldro/obs-source-record) to the [OBS Studio snap](https://snapcraft.io/obs-studio). Source Record adds an individual record button to any source, letting you record sources independently from the main output.
=======
[![source-record-obs-studio](https://snapcraft.io/source-record-obs-studio/badge.svg)](https://snapcraft.io/source-record-obs-studio)

This snap delivers [source-record](https://github.com/exeldro/obs-source-record) to the
[OBS Studio snap](https://snapcraft.io/obs-studio).

Source Record lets you record any source in OBS Studio. This is a filter
that provides an individual record button for any source, allowing you to
record sources independently from the main output.
>>>>>>> after updating

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
