# Undertow

A game on the [Ashes of Eden](https://github.com/Saaayurii/ashes-of-eden) engine: its combat, its
code and its tools, with this repository's own story, places and pictures laid over them.

- `data/game.json` — what makes the game this game: rooms in play order, the menu, the
  three paths' colours, which of the engine's collections it takes (`inherit`).
- `data/` — the game's own entries; one with the same id as the engine's replaces it.
  A one-document file (`hero.json`, `projectiles.json`, …) changes only the keys it names.
- `data/hero.json` — the fight, only what differs from the engine's: the hero's `stats` and
  `feel`, which special `moves` he has, and how enemies keep their distance (`enemy_ai`).
- `rooms/rooms.json` — rooms made from the engine's (`base`) with the game's own enemies,
  weather and light; `rooms/composed_rooms.json` — rooms stitched from several paintings;
  `rooms/studio_rooms.json` — what the studio adds. The scenes in `scenes/rooms/` are
  written from them (`tools/rooms/generate_rooms.py --pack`, and by CI on a push): edit
  the tables, not the scenes.
- `assets/fonts/NotoSerifSC-Subset.ttf` — the Chinese the game's words use
  (`tools/art/make_cjk_font.py --pack`), when it has words of its own.
- `localization/strings.csv` — keys the game adds or retells (`GAME_TITLE`, …).
- `assets/`, `scenes/` — the game's pictures and rooms, named `res://content/...`.

Play it locally from an engine checkout:

    python3 tools/packs/apply_pack.py ../undertow
    make import && make room ROOM=0

Open it in the art studio: https://saaayurii.github.io/undertow/studio/ (or the engine's studio,
«▣ → Открыть игру» → `Saaayurii/undertow`). Play it: https://saaayurii.github.io/undertow/

The tide is in. The rooms are the swamp, the crypt and the catacombs of Ashes, flooded:
bubbles and drips, a cold blue night, the drowned, tide cultists, brine wraiths and the
Tide Knight in the hall. The hero is lighter in the water (less gravity) and finds no grip
on the wet walls (no wall jump); the tide comes three abreast.
