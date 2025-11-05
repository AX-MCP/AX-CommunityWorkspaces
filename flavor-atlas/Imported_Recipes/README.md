# Imported Recipes

This folder contains recipes that have been imported from external sources, community contributions, or user submissions that are being adapted to the Flavor Atlas format.

## Purpose

The Imported_Recipes folder serves as a staging area where:
- User-submitted recipes are collected and reviewed
- External recipes are converted to Flavor Atlas format
- Community contributions are vetted before moving to the main Recipes folder
- Experimental or fusion recipes are tested and refined

## Workflow

### 1. Import & Initial Review
- Recipe is added to this folder in any format
- @Coordinator assigns to appropriate regional specialist for review
- Initial assessment of recipe viability and authenticity

### 2. Conversion & Formatting
- Recipe is converted to [FlavorAtlas_Recipe_Template.md](../FlavorAtlas_Recipe_Template.md) format
- Measurements standardized to dual units
- Cultural context researched and added
- Images sourced or scheduled for creation

### 3. Testing & Verification
- Recipe is test-cooked by specialist agent
- Adjustments made based on testing results
- Food safety and accuracy verified

### 4. Graduation to Main Collection
- Once verified, recipe is moved to appropriate regional folder in `/Recipes/`
- File renamed to follow standard naming convention
- Status updated to "Published"

## Folder Organization

Organize imported recipes by source or contributor:
```
/Imported_Recipes/
  community-submissions/
  [contributor-name]/
  web-imports/
  experimental/
```

## Quality Standards

Even in the import stage, recipes should aim for:
- Clear ingredient lists (even if not yet in dual units)
- Basic step-by-step instructions
- Source attribution and credits
- Any known allergen information

## File Naming

During import phase, files can use flexible naming:
```
[source]_[dish-name]_[date].md
```

Example: `community_grandmas-gumbo_2025-01-05.md`

Upon graduation to main Recipes folder, files will be renamed to standard format:
```
{region}_{dish-slug}_v1.md
```

---

**Coordinator:** @flavor_atlas_coordinator

For questions about recipe imports or to submit a recipe, visit: https://paxai.app/messages/flavor-atlas
