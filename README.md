# 3D Shadow Sculptures — Inspired by the GEB Cover

Interactive 3D sculptures that cast different letters as shadows on three perpendicular walls, recreating the concept from the cover of Douglas Hofstadter's *Godel, Escher, Bach*.

A voxel exists only if all three shadow bitmaps agree at that point in space — a boolean AND across three orthogonal projections.

## Part 1: R, A, G (Latin)

A 9x9 grid sculpture casting the letters R, A, G. Built in a single conversation with Claude, where a constraint-propagation bug in the R shadow led to an unexpectedly revealing discussion about how LLMs reason.

- **[re-creating-GEB-sculpture.html](re-creating-GEB-sculpture.html)** — Article: *Compressed Deliberation*
- **[geb-cover.html](geb-cover.html)** — Interactive 3D renderer (Three.js)

## Part 2: த, மி, ழ் (Tamil)

A 19x19 grid sculpture casting Tamil letters. Tamil's curved, thin strokes (~15-20% fill) make constraint satisfaction far harder than Latin's thick strokes (~55% fill). Solved by rectangularizing the curves into angular Bauhaus-style forms and building a bitmap editor for iterative human-AI co-design.

- **[sculpting-tamil-3d.html](sculpting-tamil-3d.html)** — Article: *Sculpting Tamil in 3D*
- **[tamil-shadow.html](tamil-shadow.html)** — Interactive 3D renderer (Three.js)
- **[bitmap-editor.html](bitmap-editor.html)** — Bitmap editor with real-time constraint verification

## How It Works

Each letter is defined as an NxN bitmap. For every point (x, y, z) in 3D space:

```
voxel(x, y, z) = front[N-1-y][x] AND right[N-1-y][z] AND top[z][x]
```

The sculptures are rendered with Three.js using directional lights and shadow mapping so the actual cast shadows match the bitmap definitions.

## Built With

Claude (Anthropic) + Three.js + a lot of constraint debugging

## Author

Ravi Annaswamy — March 2026
