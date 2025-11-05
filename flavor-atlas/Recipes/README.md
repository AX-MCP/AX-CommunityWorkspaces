# Recipes

This folder contains all original recipes developed within the Flavor Atlas workspace. Recipes are organized by regional cuisine and follow the standardized format defined in [FlavorAtlas_Recipe_Template.md](../FlavorAtlas_Recipe_Template.md).

## Regional Collections

Each subfolder represents a distinct culinary tradition or regional cuisine:

- **[midwest-us/](./midwest-us/)** - Midwest United States: Heartland comfort food and farm-to-table traditions
- **[new-orleans/](./new-orleans/)** - New Orleans: Cajun, Creole, and Louisiana cuisine
- **[west-coast-us/](./west-coast-us/)** - West Coast United States: Pacific fusion and California cuisine
- **[mexican/](./mexican/)** - Mexican: Traditional and regional Mexican dishes
- **[thai/](./thai/)** - Thai: Cuisine from all regions of Thailand
- **[mediterranean/](./mediterranean/)** - Mediterranean: Greek, Italian, Spanish, and Middle Eastern
- **[east-asian/](./east-asian/)** - East Asian: Chinese, Japanese, Korean, and Vietnamese
- **[south-asian/](./south-asian/)** - South Asian: Indian, Pakistani, Bangladeshi, and Sri Lankan

## Recipe Status Workflow

Recipes progress through these stages:
1. **Idea** - Concept proposed
2. **Draft** - Initial recipe written
3. **Test-Cooked** - Recipe tested by specialist agent
4. **Verified** - Reviewed and approved by @Coordinator
5. **Published** - Final recipe ready for use

## Naming Convention

Recipe files must follow this format:
```
{region}_{dish-slug}_v{version}.md
```

Examples:
- `midwest-us_chicago-deep-dish-pizza_v1.md`
- `thai_pad-thai_v2.md`
- `mexican_mole-poblano_v1.md`

## Image Storage

All recipe images are stored in the `/Images/` folder at the root level, organized by dish slug:
```
/Images/{dish-slug}/hero.jpg
/Images/{dish-slug}/step-01.jpg
```

## Quality Requirements

Every recipe must include:
- ✅ Valid YAML front matter
- ✅ Dual units (metric and imperial) for all measurements
- ✅ Cultural context and background (2-4 lines)
- ✅ Step-by-step instructions with sensory cues
- ✅ Food safety temperatures and storage guidance
- ✅ High-quality images with alt text
- ✅ Allergen information and substitutions

---

For detailed formatting guidelines, see [FlavorAtlas_Recipe_Template.md](../FlavorAtlas_Recipe_Template.md)
