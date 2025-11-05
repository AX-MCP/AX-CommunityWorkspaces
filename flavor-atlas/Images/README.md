# Images

This folder contains all photography and visual assets for Flavor Atlas recipes. Images are organized by recipe slug for easy reference and maintenance.

## Folder Structure

Each recipe has its own subfolder named after the recipe slug:

```
/Images/
  {dish-slug}/
    hero.jpg           - Main featured image of finished dish
    step-01.jpg        - First process/technique photo
    step-02.jpg        - Second process/technique photo
    ...                - Additional step photos as needed
    ingredient-layout.jpg  - Optional: ingredient mise en place
```

### Example Structure
```
/Images/
  chicago-deep-dish-pizza/
    hero.jpg
    step-01.jpg
    step-02.jpg
    step-03.jpg
  pad-thai/
    hero.jpg
    step-01.jpg
    step-02.jpg
```

## Image Requirements

### Hero Images (Required)
- **Purpose:** Main showcase of the finished dish
- **Dimensions:** Minimum 1600px width
- **Aspect Ratio:** 3:2 or 4:3 preferred
- **Format:** JPEG (compressed for web)
- **File Size:** Target 200-500KB (balance quality and load time)
- **Composition:** Well-lit, appetizing presentation
- **Alt Text Required:** 1-2 sentence description for accessibility

### Process/Step Images (Recommended)
- **Quantity:** Maximum 6 per recipe
- **Dimensions:** Minimum 1200px width
- **Naming:** Sequential `step-01.jpg`, `step-02.jpg`, etc.
- **Purpose:** Show key techniques, visual cues, or critical steps
- **Alt Text Required:** Brief description of what's shown

### Optional Images
- `ingredient-layout.jpg` - Mise en place or ingredient arrangement
- `plating-alt.jpg` - Alternative plating or serving suggestion
- `cross-section.jpg` - Interior view of dish when relevant

## Photography Guidelines

### Lighting
- Natural light preferred when possible
- Avoid harsh shadows or overexposure
- Consistent white balance across all images for a recipe

### Styling
- Clean, uncluttered backgrounds
- Props should enhance, not distract
- Show dish as home cooks would realistically create it
- Authentic cultural presentation when applicable

### Technical Standards
- Sharp focus on main subject
- Proper exposure (not too dark or blown out)
- Color accurate (food should look appetizing)
- Minimal post-processing (enhance, don't transform)

## Accessibility Requirements

Every image MUST include alt text in the recipe markdown:
```markdown
![Hero image of Chicago deep dish pizza](../Images/chicago-deep-dish-pizza/hero.jpg)
*Alt text: Thick Chicago-style deep dish pizza with golden crust, layers of cheese and tomato sauce visible in cross-section, served on white plate*
```

Alt text should:
- Be 1-2 descriptive sentences
- Include relevant visual details (colors, textures, composition)
- Help vision-impaired users understand the image content
- Not use phrases like "image of" or "picture of"

## File Naming Conventions

- **Slug format:** Lowercase, hyphens between words
- **Match recipe filename:** If recipe is `midwest-us_chicago-deep-dish-pizza_v1.md`, folder is `chicago-deep-dish-pizza`
- **No spaces or special characters:** Only letters, numbers, hyphens
- **Descriptive but concise:** `hero.jpg`, `step-01.jpg`, not `IMG_1234.jpg`

## Image Sources & Credits

### Original Photography
- Credit photographer in recipe metadata
- Ensure permissions for publication
- Link to photographer's portfolio if desired

### Licensed/Stock Images
- Only use images with proper licensing
- Include attribution if required by license
- Keep license documentation on file

### User Contributions
- Verify contributor owns rights to image
- Get explicit permission for publication
- Credit contributor in recipe

## Compression & Optimization

Before uploading:
- Compress images using tools like ImageOptim, TinyPNG, or similar
- Target file sizes: Hero 200-500KB, Steps 150-300KB
- Maintain quality while reducing file size
- Use progressive JPEG format for web

## Reference Images (Not for Recipes)

Store reference materials in:
```
/Images/_reference/
  technique-guides/
  equipment-photos/
  ingredient-identification/
```

These are for documentation and educational purposes, not tied to specific recipes.

---

**Coordinator:** @flavor_atlas_coordinator

For questions about image requirements or to contribute photography, visit: https://paxai.app/messages/flavor-atlas
