# Minecraft Bedrock Edition Addon JSON Schema

## Project Overview

This project provides JSON schemas for Minecraft Bedrock Edition (MCBE) add-on development, specifically for **behavior packs** and **resource packs**. Schemas enable validation and IntelliSense when referenced via `$schema` URLs in addon JSON files.

## Schema Development Guidelines

### File Structure

- Organize schemas by pack type: `behavior/` and `resource/`
- Within each pack type, organize by component (e.g., `behavior/entities/`, `resource/blocks/`)
- Store common definitions in `common/` for shared patterns (identifiers, filters, ranges)
- Place manifest schemas at root: `manifest-behavior.schema.json`, `manifest-resource.schema.json`

### Schema Naming Conventions

- Use kebab-case for schema files: `entity-behavior.schema.json`
- Match official Minecraft documentation naming where possible
- No version suffixes - schemas target the latest MCBE version only

### Schema Design Patterns

- Use `$ref` for reusable components (identifiers, filters, ranges)
- Define strict `enum` values based on official Minecraft documentation
- Include `description` fields with examples from Minecraft docs
- Set `additionalProperties: false` to catch typos in addon JSON files

### Version Management

- Schemas target the **latest stable MCBE version** only
- Update schemas promptly when new MCBE versions introduce changes
- Document MCBE version compatibility in schema descriptions
- Reference official Minecraft changelogs in commit messages when updating

### Testing & Validation

- Validate schemas against real MCBE addon examples
- Test with popular addon projects as reference implementations
- Ensure schemas work with VS Code JSON validation
- Verify IntelliSense provides helpful suggestions

### Schema Usage

- Schemas are referenced via `$schema` URLs in addon JSON files
- Include `$id` field in each schema for proper referencing
- Provide usage examples showing `$schema` URL patterns
- Ensure schemas are hosted/accessible for direct URL consumption

### Documentation

- Include inline examples in schema descriptions
- Link to official Minecraft Bedrock documentation
- Document common addon patterns and best practices

## Key Resources

- [Minecraft Bedrock Documentation](https://learn.microsoft.com/en-us/minecraft/creator/)
- [JSON Schema Specification](https://json-schema.org/)
- MCBE addon format specifications and version history

## Development Workflow

1. Research new MCBE features from official changelogs
2. Create or update schemas matching the JSON structure
3. Validate against example addons
4. Test IntelliSense functionality in VS Code
5. Document changes and update version references
