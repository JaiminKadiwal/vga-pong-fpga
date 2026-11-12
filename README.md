# VGA Pong

Two player Pong on the Digilent Cmod A7 35T, shown on a VGA monitor at 640 x 480, 60 Hz.
Written in VHDL with Vivado 2026.1.

Team: Jaimin Kadiwal, Farren Martinus

## Folders

| Folder | Holds |
|---|---|
| `shared/` | constants and types both halves use |
| `platform/` | clocks, button input, board specific parts |
| `display/` | everything that becomes pixels on the monitor |
| `physics/` | ball, paddles, bounces, serve |
| `game/` | modes, scoring, menu, computer opponent |
| `top/` | top level wiring only |
| `extensions/` | optional features (BLE, high scores, NN) |
| `verify/` | testbenches and sim helpers |
| `build/` | constraints and Tcl scripts |
| `docs/` | interfaces, physics notes, pinout, test plan |

## Ground rules

- Anything that crosses between folders is written down in `docs/` first.
- `display` only reads game state, it never changes it.
- Game state updates once per frame tick.
- The Vivado project is never committed. Rebuild it from `build/`.
- A module merges into `main` only after its testbench passes.
