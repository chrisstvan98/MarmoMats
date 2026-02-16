# MarmoMats - Texture Importer for Marmoset Toolbag 5

Automatically sets up materials with textures based on a simple naming convention. This plugin processes all materials in your scene and automatically assigns matching texture files.

## Features

- Automatically detects all materials in the scene
- Matches textures to materials based on naming convention
- Configures material properties (Gloss/Roughness mode, Specular mode, etc.)
- Sets proper sRGB settings for each texture type
- Supports multiple texture formats (PNG, JPG, TGA, TIFF, EXR, DDS)

## Installation

1. Copy the `MarmoMats` folder to your Marmoset Toolbag 5 plugins directory:
   - **Windows**: `%LOCALAPPDATA%\Marmoset Toolbag 5\plugins\`
   - **macOS**: `~/Library/Application Support/Marmoset Toolbag 5/plugins/`
   - **Linux**: `~/.local/share/Marmoset Toolbag 5/plugins/`

2. Restart Marmoset Toolbag 5

3. The plugin will appear in the Plugins menu

## Usage

1. Import your 3D model into Marmoset Toolbag 5
2. Open the plugin from the Plugins menu
3. Click the `...` button to browse for your texture folder
4. Click `Begin Import` to process all materials

The plugin will automatically:
- Find matching textures for each material
- Set up material properties (Gloss/Roughness, Specular, Emissive, etc.)
- Apply textures with correct sRGB settings

## Texture Naming Convention

Textures must follow this naming pattern: `material_name_suffix.ext`

Where:
- `material_name` matches the material name in Marmoset
- `suffix` indicates the texture type (see below)
- `ext` is the file extension (.png, .jpg, .tga, etc.)

### Supported Texture Types

| Suffix | Texture Type | Description |
|--------|-------------|-------------|
| `_n` | Normal Map | Surface normals |
| `_c` | Albedo Map | Base color/diffuse |
| `_g` | Gloss Map | Sets microsurface to Gloss mode |
| `_r` | Roughness Map | Sets microsurface to Roughness mode |
| `_s` | Specular Map | Sets reflectivity to Specular mode |
| `_o` | Occlusion Map | Ambient occlusion |
| `_e` | Emissive Map | Sets emission to Emissive mode |

### Example

For a material named `wood_plank`, the following textures would be recognized:
- `wood_plank_n.png` - Normal map
- `wood_plank_c.png` - Albedo map
- `wood_plank_g.png` - Gloss map
- `wood_plank_s.png` - Specular map
- `wood_plank_o.png` - Occlusion map
- `wood_plank_e.png` - Emissive map

## Material Property Changes

The plugin automatically configures material properties based on texture types:

- **Gloss Maps** (`_g`): Changes microsurface from Roughness to Gloss mode
- **Roughness Maps** (`_r`): Changes microsurface to Roughness mode
- **Specular Maps** (`_s`): Changes reflectivity to Specular mode and sets channel
- **Emissive Maps** (`_e`): Enables Emissive mode
- **Normal Maps** (`_n`): Enables "Flip Y" option
- **Occlusion Maps** (`_o`): Automatically enables occlusion

## Requirements

- Marmoset Toolbag 5
- Python 3.x (included with Marmoset Toolbag 5)

## License

This plugin is provided as-is for use with Marmoset Toolbag 5.

## Support

For issues or questions, please open an issue on the GitHub repository.
