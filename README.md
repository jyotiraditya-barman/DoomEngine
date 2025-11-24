# FastDoom JS – Web-Based Doom-Style Engine & Level Editor

A high-performance, single-file JavaScript/HTML5 port of **3D Sage’s open-source Doom-style raycasting engine** (originally written in C). This implementation faithfully recreates the classic pseudo-3D rendering technique popularized by id Software’s 1993 game *Doom*, while adding a fully functional top-down level editor — all running directly in the browser with zero dependencies.

- **Rendering resolution**: 320×200 (authentic retro feel)
- **Performance**: 60+ FPS on modern devices using Uint32Array direct pixel manipulation
- **Features**: Play mode + real-time map editor, mobile touch controls, level export
- **File size**: One self-contained HTML file (~500 LOC of JavaScript)

Live demo: Just open the HTML file in any modern browser.

## Features

| Feature                     | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| Raycasted 3D rendering     | Perspective-correct walls, variable sector heights, floor/ceiling shading   |
| Distance-based sector sorting | Proper visibility of overlapping sectors                                   |
| Built-in level editor      | Top-down view, grid snapping (32-unit), click-and-drag wall creation       |
| Mobile-ready controls      | On-screen D-pad for movement and strafing                                 |
| Export functionality      | Dump wall data to console for reuse or further processing                  |
| No external dependencies  | Pure vanilla JavaScript + HTML5 Canvas                                     |

## Quick Start

1. Save the provided code as `fastdoom-js.html`
2. Open the file in any modern browser (Chrome, Firefox, Edge, Safari)
3. Start playing immediately — a small E1M1-style map is preloaded

## Controls

### Play Mode (First-Person)
| Action               | Keyboard                  | Mobile               |
|----------------------|---------------------------|----------------------|
| Move forward / back  | W / S                     | ↑ / ↓ buttons        |
| Strafe left / right  | Q / E  or  hold Shift+A/D | ← / → buttons        |
| Turn left / right    | A / D                     | ← / → (short tap)    |
| Look up / down       | Shift + A / D             | —                    |
| Fly up / down        | Shift + W / S             | —                    |
| Toggle Edit / Play   | E                         | Edit Mode button     |

### Edit Mode (Top-Down Map Editor)
| Action               | Input                     |
|----------------------|---------------------------|
| Pan view             | WASD                      |
| Zoom                 | Mouse wheel (or pinch)    |
| Draw wall            | Click & drag (snaps to 32-unit grid) |
| Toggle mode          | E or “Edit Mode” button   |
| Export walls         | “Export Data” button → console |

## Technical Highlights

- Pre-computed sine/cosine tables (360° lookup)
- Direct `Uint32Array` buffer manipulation for maximum speed
- Perspective projection with proper behind-player clipping
- Dynamic sector and wall arrays (easy to extend)
- Bresenham line drawing for the editor
- World ↔ screen coordinate conversion with zoom/pan support

## Credits & Attribution

- **Original engine concept**: John Carmack / id Software (*Doom*, 1993)
- **C implementation & tutorial series**: [3D Sage](https://www.youtube.com/@3DSage)  
  Source: https://github.com/3DSage/OpenGL-Doom_tutorial_part_2

## License

```
MIT License

Copyright (c) 2025 [Jyotiraditya Barman] (JavaScript port)
Copyright (c) 3D Sage (original C implementation)

Permission is hereby granted, free of charge, to any person obtaining a copy...
```

Feel free to fork, enhance (sprites, textures, sound, multiplayer, etc.), and share your creations. Happy fragging!
