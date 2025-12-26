# Minecraft Bedrock Edition Addon JSON Schema

Comprehensive JSON schemas for Minecraft Bedrock Edition (MCBE) addon development, providing validation and IntelliSense support for behavior packs and resource packs.

## Overview

This project provides JSON schemas that enable:

- **Validation**: Catch errors in your addon JSON files before testing
- **IntelliSense**: Get autocomplete suggestions and documentation in VS Code
- **Type Safety**: Ensure your addons follow the correct structure

## Features

- ✅ Behavior pack schemas
- ✅ Resource pack schemas
- ✅ Manifest validation
- ✅ Component-based organization
- ✅ Common definitions for shared patterns

## Usage

Reference schemas in your addon JSON files using the `$schema` property:

```json
{
  "$schema": "https://raw.githubusercontent.com/YOUR_USERNAME/MCBE-Addon-JSON-Schema/main/behavior_packs/manifest.schema.json",
  "format_version": 2,
  "header": {
    "name": "My Behavior Pack",
    "description": "A custom behavior pack",
    "uuid": "...",
    "version": [1, 0, 0],
    "min_engine_version": [1, 21, 0]
  },
  "modules": []
}
```

## Schema Structure

```
behavior_packs/     # Behavior pack schemas
resource_packs/     # Resource pack schemas
common/             # Shared definitions and patterns
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
