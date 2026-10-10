# Flyit — Frederick Flight

A browser flight simulator with a light airplane, simple keyboard controls, and real-world 3D geography around Frederick County, Maryland.

## Play

Play at https://rosemontni.github.io/flyit/. No installation or build is required. Internet access and a WebGL-capable browser are required to load Cesium and geographic services.

For a local HTTP preview, run `python -m http.server 4173 --directory dist`, then visit http://localhost:4173.

## Controls

| Key | Action |
| --- | --- |
| Up / Down arrows | Climb / descend |
| Left / Right arrows | Turn |
| W / S | Increase / decrease throttle |
| Space | Level wings and pitch |
| P | Pause / resume |
| R | Restart the scenic route |

Fly through five golden rings, or explore freely. Terrain assistance helps keep the airplane above loaded ground elevation. Flight uses WGS84 longitude, latitude, altitude and an assisted arcade flight model. Building collision is not simulated.

## Real-world data

- **Renderer:** CesiumJS 1.146, streamed from the official Cesium CDN.
- **Terrain:** Esri WorldElevation3D Terrain3D, using Cesium's ArcGIS tiled elevation provider.
- **Satellite/aerial imagery:** Esri World Imagery. Source attributions remain visible in Cesium's credit display.
- **Buildings:** [Frederick County Building Footprints](https://fcgis.frederickcountymd.gov/server_pub/rest/services/Tiled/BuildingFootprints_Tiled/MapServer/0). Footprints are extruded using measured soffit heights, converted from feet to meters. Missing heights use an estimated 6 meters. These are solid, flat-roof GIS models, not photogrammetric or photo-textured buildings. Ground elevation uses loaded terrain where available, with county ground elevations as fallback; source datums and differing survey dates may cause local offsets.
- **Streets:** [Frederick County road centerlines](https://fcgis.frederickcountymd.gov/server_pub/rest/services/Tiled/BaseMap/MapServer/33), draped over the terrain. Detailed street surfaces also appear in the aerial imagery.

Buildings and streets stream in nearby geographic cells as you fly; distant cells are removed to limit memory. Geometry and imagery availability, dates and accuracy depend on the source services. Service failures are shown in the map status. No API keys or account credentials are embedded.

## Source

- `dist/index.html`: game interface
- `dist/style.css`: interface styling
- `dist/game.js`: Canvas rendering, flight controls, and route logic

Built with HTML, CSS, JavaScript and CesiumJS. The GitHub Pages workflow deploys `dist` on pushes to `main`.
