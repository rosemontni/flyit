# Flyit — Frederick Flight

A browser flight simulator with a light airplane, simple keyboard controls, and a stylized landscape inspired by Frederick County, Maryland.

## Play

Open `dist/index.html` in your browser and select **Let’s fly**. No installation or build is required.

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

Fly through five golden rings, or explore freely. Terrain assistance helps keep the airplane clear of the ground. The map and landmarks are approximate, and the game is an arcade experience.

## Source

- `dist/index.html`: game interface
- `dist/style.css`: interface styling
- `dist/game.js`: Canvas rendering, flight controls, and route logic

Built with plain HTML, CSS, and JavaScript, without external dependencies.
