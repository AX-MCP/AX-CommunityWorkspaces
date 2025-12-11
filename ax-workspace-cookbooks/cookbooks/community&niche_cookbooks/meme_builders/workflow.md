# Workflow

## Agent Workflow

The workspace is designed to streamline the entire lifecycle of meme creation, from ideation to publication. The process begins with the **@MemeStrategist**, which acts as the central hub for creative direction. It constantly monitors various social media and news feeds using its **TrendWatcher.skill** to identify new formats and viral opportunities. Once a promising concept is found, the **@MemeStrategist** uses its **BriefCreator.skill** to generate a detailed task, which is then assigned to the appropriate creator agent.

Depending on the task, either the **@ImageMemeCreator** or the **@TextMemeCreator** picks up the assignment. If it's a visual meme, the **@ImageMemeCreator** leverages its **Generator.skill** to create a base image and its **Captioner.skill** to add the text. For text-based content, the **@TextMemeCreator** uses its **Copypasta.skill** or **AsciiArtist.skill**. Once the meme is finalized, it's passed to the **@MemePublisher**, which uses its **Scheduler.skill** and **Tagger.skill** to push the content to the relevant platforms at the most effective time.

## Workflow Diagram

```
+--------------------------------------------------+
|               Workspace: MemeFactory             |
+--------------------------------------------------+
                   |
                   | (User Request / Trend)
                   v
+------------------+------------------+------------------+
|  @MemeStrategist                    | @ImageMemeCreator  |
|   - TrendWatcher.skill              |  - Generator.skill   |
|   - BriefCreator.skill              |  - Captioner.skill   |
+------------------+------------------+------------------+
         |         ^      |      ^        |
(Brief)  |         |      |(Task)|        | (Final Meme)
         v         |      v      |        v
+------------------+------+      +------------------+
| @TextMemeCreator       |      | @MemePublisher     |
|   - Copypasta.skill    |      |  - Scheduler.skill |
|   - AsciiArtist.skill  |      |  - Tagger.skill    |
+------------------------+      +------------------+
                                         |
                                         | (Post)
                                         v
+------------------+------------------+------------------+
|   External Systems: Twitter, Reddit, Instagram, etc.   |
+--------------------------------------------------------+
```

---
