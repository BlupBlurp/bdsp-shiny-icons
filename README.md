# BDSP Shiny Icons

A collection of Pokémon icons in BDSP (Brilliant Diamond & Shining Pearl) style (128x128), recolored to match their shiny variants.

## Overview

This repository contains all original BDSP Pokémon icons and some additional ones that have been recolored to display their shiny forms. The collection includes a total of **1554 icons** covering:

- **All Pokémon generations** (1-9)
- **Alternative forms** and regional variants
- **Mega Evolutions**
- **Pokémon GO exclusive forms**
- **Additional special forms**

## Repository Structure

### `shiny_icons/`

Contains the main collection of shiny Pokémon icons **without the shiny indicator star**. Icons are organized by generation:

- `Generation1_0001-0151/` - Kanto Pokémon
- `Generation2_0152-251/` - Johto Pokémon
- `Generation3_0252-0386/` - Hoenn Pokémon
- `Generation4_0387-0493/` - Sinnoh Pokémon
- `Generation5_0494-0649/` - Unova Pokémon
- `Generation6_0650-0721/` - Kalos Pokémon
- `Generation7_0722-0809/` - Alola Pokémon
- `Generation8_0810-0905/` - Galar Pokémon
- `Generation9_0906-1025/` - Paldea Pokémon

### `star_templates/`

Contains shiny indicator star templates that can be applied to any icon using [ImageMagick](https://imagemagick.org/) commands. Includes multiple star designs:

![Star template 1](star_templates/star1.png)
![Star template 1.2](star_templates/star1_2.png)
![Star template 2](star_templates/star2.png)
![Star template 3](star_templates/star3.png)

### `reference_textures/`

Contains the original BDSP icons, textures, and Pokémon Home icons used as reference material for creating the shiny variants. This folder includes both normal and shiny texture references that were essential for the recoloring process.

## Examples

### Without Shiny Star (`shiny_icons/`)

![Shiny Charizard without star](shiny_icons/Generation1_0001-0151/pm0006_00_01.png)
![Shiny Pikachu without star](shiny_icons/Generation1_0001-0151/pm0025_03_11.png)
![Shiny Gengar without star](shiny_icons/Generation1_0001-0151/pm0094_01_01.png)
![Shiny Moltres without star](shiny_icons/Generation1_0001-0151/pm0146_01_21.png)
![Shiny Magikarp without star](shiny_icons/Generation1_0001-0151/pm0129_00_11_28.png)

### With Shiny Star (`star_templates/examples/`)

![Politoed with star template 1](star_templates/examples/pm0186_00_01_star1.png)
![Politoed with star template 1.2](star_templates/examples/pm0186_00_01_star1_2.png)
![Politoed with star template 2](star_templates/examples/pm0186_00_01_star2.png)
![Politoed with star template 3](star_templates/examples/pm0186_00_01_star3.png)

## Adding Shiny Stars

To add a shiny star to any icon, use [ImageMagick](https://imagemagick.org/)'s composite command. The star templates are already sized to match the icons (128x128), so they can be placed directly with center gravity:

```bash
# Add a star to a single image
magick composite -gravity center star_templates/star1.png shiny_icons/Generation2_0152-251/pm0186_00_01.png output_with_star.png
```

### Batch Processing All Icons

**Windows (PowerShell):**

```powershell
# Create an output folder and process all icons
New-Item -ItemType Directory -Force -Path "shiny_icons_with_star"
Get-ChildItem -Recurse -Path "shiny_icons" -Filter "*.png" | ForEach-Object { magick composite -gravity center "star_templates/star1.png" $_.FullName "shiny_icons_with_star/$($_.Name)" }
```

**Mac/Linux (Bash):**

```bash
# Create output folder and process all icons
mkdir -p shiny_icons_with_star
find shiny_icons -name "*.png" -exec sh -c 'magick composite -gravity center star_templates/star1.png "$1" "shiny_icons_with_star/$(basename "$1")"' _ {} \;
```

## Creation Process

The majority of these shiny icons were created using our custom [Sprite Recolor Tool](https://github.com/BlupBlurp/sprite-recolor-tool). This tool takes:

- An original sprite/icon
- A normal Pokémon texture reference
- A shiny Pokémon texture reference

The tool then recolors the sprite to match the shiny color palette.

## Usage

These icons are **free to use** for personal and community projects.

No attribution required, though it's always appreciated!

Attribution is required, so please credit the contributors in your projects.

## Credits

This project was made possible through the collaborative efforts of:

- **ttin**
- **Blup**
- **darth_pokemon**
- **Heavenly_Experience**
- **realmadrid1809**
- **puningtilde**
- **profblack**
- **dahnidandypants**
