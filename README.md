[README.md](https://github.com/user-attachments/files/33288340/README.md)
# NUKEMAP

An educational, client-side nuclear effects visualizer using Leaflet and OpenStreetMap tiles.

## Run it

Serve this folder from a local web server (Google Maps will not load reliably from `file://`):

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`. No API key, account, or billing setup is required.

The app loads Leaflet from a CDN and uses the standard OpenStreetMap tile server plus the OpenStreetMap HOT style. Keep the required attribution visible, and review the [OpenStreetMap tile usage policy](https://operations.osmfoundation.org/policies/tiles/) before deploying at scale. These are street-map layers, not satellite imagery.

## Model note

The rings are deliberately approximate educational visualizations. They use a cube-root yield scaling model and should not be used for prediction, emergency response, or decision-making. The fallout corridor is represented as a contextual length readout only; it is not a meteorological dispersion model.

The impact report is also illustrative: it applies broad, hard-coded population-density and replacement-value assumptions to the modeled rings. It is not live census, insurance, infrastructure, or casualty data.

The app can retain multiple impact points on one map. Choose an effect preset (nuclear device, non-nuclear ICBM, rods from God, particle accelerator beam, or hypersonic missile), click the map to position it, and press “Add impact + run totals.” The non-nuclear presets are abstract visualization presets, not engineering or performance models.

The per-weapon settings are intentionally high-level visual controls. They do not expose physical weapon-design inputs such as rod dimensions, material density, guidance, or construction parameters.

Each added impact now plays a short expanding blast-wave animation and leaves a persistent crater/impact-scar marker on the map until impacts are cleared.

The map also includes an abstract first-person replay overlay for every weapon preset. It uses a weapon-specific stylized horizon, flash, camera shake, and aftermath text; it is intentionally not a realistic training or targeting view. The POV overlay is opt-in so it does not block map clicks or prevent adding another impact.
