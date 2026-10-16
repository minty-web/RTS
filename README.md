# БАЛТИКА — RTS

Top-down / 2.5D real-time strategy: Estonia & NATO allies vs Russian forces around the Gulf of Finland. Single self-contained HTML file — no dependencies, no build step.

## Run

Open `baltika-rts.html` in any modern browser (double-click works), or serve the folder:

```sh
python3 -m http.server 8000
# -> http://localhost:8000/baltika-rts.html
```

## Play

- Tap a unit to select, tap ground to order. Drag to pan, wheel / pinch to zoom.
- Capture and hold cities: they heal troops and spawn reinforcements.
- Aviation flies by **flight plan**: route + strike points («План» → taps → «Пуск»).
- UAVs recon and designate targets (+30% damage).
- SAMs (Mistral / Pantsir-S1) cover troops from aviation.
- Neutral cities (Helsinki, Kotka, Hamina, Vyborg): whoever captures first keeps them.
- Bridges and causeways are the only Gulf crossings.

## Tech notes

- Procedural map (Gulf of Finland theater, 4300×3200): heightfield terrain, Google-style cartography baked to an offscreen canvas.
- Units are tiny procedural 3D models rendered with a software 2.5D projector (tilted camera, painter's algorithm) onto the map texture.
- Game balance: `TY` table (costs/speeds/damage), `DIFF` curves, `ruAI` enemy logic — all in the single `<script>` block.
