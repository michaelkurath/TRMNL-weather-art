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

## Install on TRMNL

Download [Weather Art.zip](dist/Weather_Art.zip) and use **Plugins → Private Plugin → Import new** in TRMNL. Set **Artist**, **Scene**, and **Weather location**, then save and force refresh if you want to see the new selection immediately. Weather location defaults to Zürich.

The recipe polls [Open-Meteo](https://open-meteo.com/) hourly and displays one of twelve pre-rendered images. It uses three art states in this preview: clear for dry conditions, fog for fog or snowfall, and windy rain for drizzle, rain, or thunderstorms. When weather data is missing it shows the clear artwork. Weather data is provided under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

All four TRMNL layouts use the same full-color landscape assets and preserve the picture's aspect ratio. Landscape fills a 16:9 Frame. Portrait and differently shaped layouts show the centered artwork with margins. The source art comes from the composition proofs, so the images are preview resolution. Separate portrait artwork and additional artists and scenes are future work.

The GitHub Sync source lives in `src/` at the repository root. When the plugin is linked to this repository in TRMNL, leave its folder setting blank. Use `trmnlp serve` for local preview. After editing the recipe, rebuild the import ZIP from the repository root with `zip -j dist/Weather_Art.zip src/*.liquid src/settings.yml`.
