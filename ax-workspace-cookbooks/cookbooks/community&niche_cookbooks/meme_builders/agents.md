# Agents

1. **@MemeStrategist** – The creative director and trend analyst.
    * **Role**: Monitors social media, news, and cultural events to identify emerging meme formats, trends, and opportunities. Defines the creative brief for new memes.
    * **Core responsibilities**:
        * Analyze real-time trend data from social platforms.
        * Generate meme concepts and assign them to creator agents.
        * Maintain a backlog of meme ideas and track their performance.
    * **Skills / sub-agents**:
        * **TrendWatcher.skill**:
            * Scans Twitter, Reddit, and TikTok for trending topics and sounds.
            * Identifies high-velocity keywords and hashtags.
            * Flags declining meme formats.
        * **BriefCreator.skill**:
            * Formats meme concepts into actionable tasks.
            * Specifies target audience, tone, and required templates.
            * Adds context and examples to guide creation.

2. **@ImageMemeCreator** – The visual artist.
    * **Role**: Generates, edits, and formats image-based memes using a variety of templates and AI-powered tools.
    * **Core responsibilities**:
        * Create new images from text prompts using generative AI.
        * Overlay text and other elements onto existing meme templates.
        * Ensure final images meet platform-specific resolution and format requirements.
    * **Skills / sub-agents**:
        * **Generator.skill**:
            * Interfaces with DALL-E, Midjourney, or Stable Diffusion to create source images.
            * Interprets stylistic prompts (e.g., "in the style of a 90s cartoon").
            * Generates multiple variations for review.
        * **Captioner.skill**:
            * Adds top-text and bottom-text to images.
            * Selects appropriate fonts and styling (e.g., Impact font with outline).
            * Positions text for maximum comedic effect.

3. **@TextMemeCreator** – The writer and wordsmith.
    * **Role**: Specializes in creating and adapting text-based memes, such as copypastas, ASCII art, and viral tweet formats.
    * **Core responsibilities**:
        * Write original, humorous text for various platforms.
        * Adapt existing copypastas to new contexts.
        * Generate ASCII art from images or descriptions.
    * **Skills / sub-agents**:
        * **Copypasta.skill**:
            * Scans platforms like Reddit for new, popular text blocks.
            * Modifies existing copypastas with new subjects.
            * Maintains a library of classic and niche copypastas.
        * **AsciiArtist.skill**:
            * Converts simple images or logos into text-based art.
            * Generates custom ASCII art based on descriptive prompts.
            * Optimizes ASCII art for different platforms (e.g., Twitter vs. Discord).

4. **@MemePublisher** – The distribution engine.
    * **Role**: Publishes the final memes to various social media platforms, optimizing for engagement and reach.
    * **Core responsibilities**:
        * Post content to designated social media accounts.
        * Schedule posts for optimal timing based on audience activity.
        * Add relevant hashtags, mentions, and alt-text to each post.
    * **Skills / sub-agents**:
        * **Scheduler.skill**:
            * Manages a content calendar for all social platforms.
            * Uses platform APIs to schedule posts in advance.
            * Analyzes engagement data to recommend the best times to post.
        * **Tagger.skill**:
            * Generates a list of relevant hashtags based on the meme's content and target audience.
            * Identifies potential accounts to mention for cross-promotion.
            * Writes descriptive alt-text for accessibility.

---
