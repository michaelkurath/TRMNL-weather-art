# Weather Art

*Local weather in the style of famous artists.* A concept for the TRMNL Frame that displays full-screen artwork without weather icons, numbers, or forecasts.

| Setting | Controls |
| --- | --- |
| Artist | The visual treatment |
| Scene | The place depicted in the artwork |
| Weather location | The location used to retrieve current conditions |

The weather location and the depicted scene are independent. Russikon's weather can drive either the village or the city scene.

## Composition proofs

Each sheet contains clear daylight on top, fog in the middle, and windy rain at the bottom. Each row is a landscape composition. The Warhol-inspired rows contain two repetitions of the scene in different inks.

| Scene | Neutral reference | Van Gogh–inspired | Warhol-inspired |
| --- | --- | --- | --- |
| Small village | [Neutral](artwork/neutral/village.jpg) | [Study](artwork/studies/village-van-gogh.jpg) | [Study](artwork/studies/village-warhol.jpg) |
| Big city | [Neutral](artwork/neutral/city.jpg) | [Study](artwork/studies/city-van-gogh.jpg) | [Study](artwork/studies/city-warhol.jpg) |
| Mountain lake | [Neutral](artwork/neutral/mountain-lake.jpg) | — | — |

The neutral sheets establish the viewpoint, landmarks, and visual cues for the weather. The artist studies reinterpret those same compositions. The sheets are AI-generated visual proofs intended for comparison before preparing individual Frame assets.

## Prototype

Open [the procedural village experiment](prototype/procedural-village.html) locally in a browser. It renders four sample conditions deterministically and exports 2560 × 1440 PNGs. It was an earlier experiment in mapping weather inputs to individual strokes and scene elements.

The planned recipe will map live conditions to a small set of weather states and select a finished, pre-rendered image by artist, scene, and display orientation. Live weather integration, production artwork, and TRMNL packaging are pending.
