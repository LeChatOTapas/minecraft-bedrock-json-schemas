# Minecraft Bedrock Edition Addon JSON Schema

Comprehensive JSON schemas for Minecraft Bedrock Edition (MCBE) addon development, providing validation and IntelliSense support for behavior packs and resource packs.

## Overview

This project provides JSON schemas that enable:

- **Validation**: Catch errors in your addon JSON files before testing
- **IntelliSense**: Get autocomplete suggestions and documentation in VS Code
- **Type Safety**: Ensure your addons follow the correct structure
- **UUID Generation**: Automatic UUID v4 generation with tiping UUID and press `TAB`

## Features

- ✅ **Manifest V2 & V3 schemas** for both behavior and resource packs
- ✅ Strict validation (semver strings, UUID patterns, namespace patterns)
- ✅ Automatic UUID generation via defaultSnippets
- ✅ Settings section support (V3 behavior packs only)
- ✅ Dual dependency format (UUID-based and module_name-based)
- ✅ Component-based organization (coming soon)
- ✅ Common definitions for shared patterns (coming soon)

## Quick Start - Visual Studio Code

### Option 1: Workspace Settings (Recommended)

1. Copy [vscode-settings.json](vscode-settings.json) into your workspace `.vscode` folder
2. Rename it to `settings.json`

**OR**

Copy the contents into your `.code-workspace` file:

```json
{
  "folders": [{ "path": "." }],
  "settings": {
    "json.schemas": [
      {
        "fileMatch": ["manifest.json", "manifest.jsonc", "manifest.json5"],
        "url": "https://raw.githubusercontent.com/LeChatOTapas/minecraft-bedrock-json-schemas/main/behavior_packs/manifest.schema.json"
      }
    ]
  }
}
```

The schemas will automatically apply to matching files in your workspace.

### Option 2: Per-File Reference

Add the `$schema` property directly in your JSON files:

```json
{
  "$schema": "https://raw.githubusercontent.com/LeChatOTapas/minecraft-bedrock-json-schemas/main/behavior_packs/manifest.schema.json",
  "format_version": 2,
  "header": {
    "name": "My Behavior Pack",
    "description": "A custom behavior pack",
    "uuid": "",
    "version": [1, 0, 0],
    "min_engine_version": [1, 21, 0]
  },
  "modules": []
}
```

**Tip**: Type `Ctrl+Space` in an empty UUID field and select "New UUID" to automatically generate a UUID v4.

## Available Schemas

### Behavior Packs

- [Manifest V2](behavior_packs/manifest.schema.json) - Format version 2 (stable)
- [Manifest V3](behavior_packs/manifest-v3.schema.json) - Format version 3 (experimental, with settings support)

### Resource Packs

- [Manifest V2](resource_packs/manifest.schema.json) - Format version 2 (stable)
- [Manifest V3](resource_packs/manifest-v3.schema.json) - Format version 3 (experimental)

## Schema Structure

```
behavior_packs/     # Behavior pack schemas
  ├── manifest.schema.json           # V2 manifest
  └── manifest-v3.schema.json        # V3 manifest with settings
resource_packs/     # Resource pack schemas
  ├── manifest.schema.json           # V2 manifest
  └── manifest-v3.schema.json        # V3 manifest
common/             # Shared definitions (coming soon)
vscode-settings.json  # VS Code configuration template
```

## Version Compatibility

These schemas target the **latest stable version** of Minecraft Bedrock Edition. They are updated regularly to reflect new features and changes.

## Contributing

Contributions are welcome! When adding or updating schemas:

1. Follow the [schema design guidelines](.github/copilot-instructions.md)
2. Test against real addon examples
3. Include descriptions and examples from official documentation
4. Reference Minecraft changelog entries in commits

## Resources

- [Official Minecraft Bedrock Documentation](https://learn.microsoft.com/en-us/minecraft/creator/)
- [JSON Schema Specification](https://json-schema.org/)
- [MCBE Addon Development Guide](https://learn.microsoft.com/en-us/minecraft/creator/documents/gettingstarted)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues or questions:

- Open an issue on GitHub
- Refer to official Minecraft Bedrock documentation
- Check existing schemas for examples

---

**Note**: This is an unofficial community project and is not affiliated with Mojang or Microsoft.
