# Weather Art

*Local weather in the style of famous artists.* A concept for the TRMNL Frame that displays full-screen artwork without weather icons, numbers, or forecasts.

| Setting | Controls |
| --- | --- |
| Artist | The visual treatment |
| Scene | The place depicted in the artwork |
| Weather location | The location used to retrieve current conditions |

The weather location and the depicted scene are independent. Russikon's weather can drive either the village or the city scene.

## Composition proofs

The neutral sheets establish the viewpoint, landmarks, and weather cues for each scene. Read each sheet from top to bottom. All eight daytime conditions have a reference for all three scenes.

| Scene | Clear · Fog · Windy rain | Overcast · Calm rain · Snow | Dry wind · Thunderstorm |
| --- | --- | --- | --- |
| Small village | [Sheet](artwork/neutral/village.jpg) | [Sheet](artwork/neutral/village-overcast-rain-snow.jpg) | [Sheet](artwork/neutral/village-dry-wind-thunderstorm.jpg) |
| Big city | [Sheet](artwork/neutral/city.jpg) | [Sheet](artwork/neutral/city-overcast-rain-snow.jpg) | [Sheet](artwork/neutral/city-dry-wind-thunderstorm.jpg) |
| Mountain lake | [Sheet](artwork/neutral/mountain-lake.jpg) | [Sheet](artwork/neutral/mountain-lake-overcast-rain-snow.jpg) | [Sheet](artwork/neutral/mountain-lake-dry-wind-thunderstorm.jpg) |

The artist studies reinterpret the clear, fog, and windy-rain compositions. Each Warhol-inspired row repeats the scene in two ink palettes. The sheets are AI-generated visual references.

| Scene | Van Gogh–inspired | Warhol-inspired |
| --- | --- | --- |
| Small village | [Study](artwork/studies/village-van-gogh.jpg) | [Study](artwork/studies/village-warhol.jpg) |
| Big city | [Study](artwork/studies/city-van-gogh.jpg) | [Study](artwork/studies/city-warhol.jpg) |

## Prototype

Open [the procedural village experiment](prototype/procedural-village.html) locally in a browser. It renders four sample conditions deterministically and exports 2560 × 1440 PNGs. It was an earlier experiment in mapping weather inputs to individual strokes and scene elements.

## Install on TRMNL

Download [Weather Art.zip](dist/Weather_Art.zip) and use **Plugins → Private Plugin → Import new** in TRMNL. Set **Artist**, **Scene**, and **Weather location**, then save and force refresh if you want to see the new selection immediately. Weather location defaults to Zürich.

The recipe polls [Open-Meteo](https://open-meteo.com/) hourly for the current weather code and 10 m wind speed. Weather data is provided under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Neutral, Van Gogh and Warhol each cover all eight daytime weather states for the village and city. Thunderstorm, snowfall and fog codes select their own scenes. Rain and drizzle use windy-rain art at 30 km/h or above and calm-rain art below that speed. Dry conditions at 30 km/h or above use dry-wind art. Otherwise, overcast has its own scene and clear to partly cloudy conditions use clear art. Missing or unknown weather codes use clear art, and missing wind speed leaves the wind variant off.

All four layouts preserve the artwork's aspect ratio. The Frame switches automatically between landscape and dedicated 1440 × 2560 portrait artwork. Each weather state has separate portrait and landscape compositions. The portrait Warhol compositions stack their two ink treatments vertically. Differently shaped layouts can have margins.

The GitHub Sync source lives in `src/` at the repository root. When the plugin is linked to this repository in TRMNL, leave its folder setting blank. Use `trmnlp serve` for local preview. After editing the recipe, rebuild the import ZIP from the repository root with `zip -j dist/Weather_Art.zip src/*.liquid src/settings.yml`.
