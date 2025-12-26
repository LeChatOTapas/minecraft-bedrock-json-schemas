# Contributing to MCBE Addon JSON Schema

Thank you for your interest in contributing to this project! We welcome contributions that help improve the schemas for Minecraft Bedrock Edition addon development.

## Getting Started

1. Fork the repository
2. Clone your fork locally
3. Create a new branch for your changes
4. Make your changes following the guidelines below
5. Test your changes
6. Submit a pull request

## Schema Development Guidelines

### File Structure

- Organize schemas by pack type: `behavior_packs/` and `resource_packs/`
- Within each pack type, organize by component (e.g., `behavior_packs/entities/`, `resource_packs/blocks/`)
- Store common definitions in `common/` for shared patterns (identifiers, filters, ranges)
- Place manifest schemas at root of each pack type directory

### Naming Conventions

- **Schema files**: Use kebab-case (e.g., `entity-behavior.schema.json`)
- **Definitions**: Match official Minecraft documentation naming
- **No version suffixes**: Schemas target the latest MCBE version only
  - **Exception**: Manifest schemas support both V2 and V3 formats (V2 and V3 available separately) as V3 is still being finalized by Mojang

### Schema Design Patterns

#### Use `$ref` for Reusable Components

```json
{
  "$ref": "../common/identifier.schema.json#/definitions/identifier"
}
```

#### Define Strict Enums

```json
{
  "type": "string",
  "enum": ["peaceful", "easy", "normal", "hard"],
  "description": "Game difficulty level"
}
```

#### Include Descriptive Documentation

```json
{
  "description": "The entity's identifier. Example: 'minecraft:zombie'",
  "type": "string",
  "pattern": "^[a-z0-9_]+:[a-z0-9_]+$"
}
```

#### Set `additionalProperties: false`

This helps catch typos in addon JSON files:

```json
{
  "type": "object",
  "properties": {
    "format_version": { "type": "string" }
  },
  "additionalProperties": false
}
```

### Version Management

- Schemas target the **latest stable MCBE version** only
- Update schemas promptly when new MCBE versions introduce changes
- Document MCBE version compatibility in schema descriptions
- Reference official Minecraft changelogs in commit messages

### Testing Your Changes

1. **Validate against real examples**: Test schemas with actual MCBE addon JSON files
2. **Check IntelliSense**: Open a JSON file in VS Code and reference your schema
3. **Verify validation**: Introduce intentional errors to ensure they're caught
4. **Test across different scenarios**: Use various addon examples

### Commit Guidelines

- Write clear, descriptive commit messages
- Reference MCBE version if updating for new features
- Include links to official Minecraft documentation when relevant

Example:

```
Add entity behavior schema for MCBE 1.21

- Added minecraft:behavior.* component definitions
- Based on official documentation at https://...
- Tested with vanilla mob examples
```

### Pull Request Process

1. Ensure your PR description clearly describes the changes
2. Reference any related issues
3. Include examples of how the schema works
4. Update README.md if adding new major features
5. Wait for review and address any feedback

## What to Contribute

### High Priority

- New component schemas for recent MCBE updates
- Missing behavior pack schemas
- Missing resource pack schemas
- Improvements to existing schemas based on real-world usage

### Always Welcome

- Documentation improvements
- Bug fixes in existing schemas
- Additional examples
- Better descriptions and inline documentation

### Research Required

Before adding a schema, ensure you have:

1. Official Minecraft documentation reference
2. Real-world example from addons
3. Understanding of all valid property values
4. Knowledge of required vs optional properties

## Resources

- [Minecraft Bedrock Documentation](https://learn.microsoft.com/en-us/minecraft/creator/)
- [JSON Schema Specification](https://json-schema.org/)
- [JSON Schema Validation](https://json-schema.org/understanding-json-schema/reference/index.html)

## Code of Conduct

- Be respectful and constructive
- Focus on improving the schemas
- Help others learn
- Base contributions on official documentation

## Questions?

If you have questions about contributing:

1. Check existing schemas for examples
2. Review the project's [copilot instructions](.github/copilot-instructions.md)
3. Open an issue for discussion
4. Reference official Minecraft Bedrock documentation

---

Thank you for helping make MCBE addon development better! 🎮
