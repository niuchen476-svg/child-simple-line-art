---
name: child-simple-line-art
description: Convert supplied images into stable, friendly children's simple line drawings with recognizable silhouettes, slightly richer picture-book detail, and optional flat pastel colors. Use when the user asks for 儿童简笔画、幼儿画、简单线稿、绘本线稿、童真童趣风, or a cute simplified redraw of an image.
---

# Child Simple Line Art

Turn an attached or supplied image into a simple children's drawing while keeping the main subject recognizable.

For every conversion, read [references/style-guide.md](references/style-guide.md) and use it as the fixed style contract. Keep the style rules stable; only adapt the subject, composition, palette, and a small amount of detail to the supplied image.

## Visual direction

- Use a clean white, warm-white, or very light pastel background with a gentle picture-book feeling.
- Draw with medium-weight dark charcoal lines, rounded joins, smooth contours, and a controlled hand-drawn feel. Lines may have tiny natural variation, but must not become messy or shaky.
- Keep the image simple but not empty: use a clear outer contour, a few important interior lines, and limited childlike details that support recognition.
- Use flat fills in two to five soft pastel colors, plus the paper background. Prefer one gentle warm accent such as butter yellow, peach, coral, or ochre; avoid rainbow coloring.
- Make it mildly playful by using rounded shapes, friendly proportions, soft highlights, and small organic details such as simple leaves, clouds, or flower marks only when they are implied by the source.
- Keep shading flat or very lightly textured. Do not use gradients, glossy effects, photorealistic rendering, or dense crosshatching.
- Preserve the main silhouette, pose, object count, landmark features, and overall composition unless the user asks for a new arrangement.
- Simplify texture, small background objects, reflections, facial detail, and architectural detail into a few readable marks.

## Stability rules

- Before writing the image prompt, classify the source as people, animal, object, building, landscape, or collage/split layout.
- Identify three to six invariants that must survive the conversion, such as subject count, pose, silhouette, landmark shape, horizon, roofline, or panel arrangement.
- Keep the same style block for every image. Only change the subject description, preserved invariants, palette, and the amount of optional detail.
- Preserve the source orientation and composition by default. If the source is a collage or contains a before/after layout, keep the panel structure unless the user explicitly asks for a new layout.
- Use a mild playful treatment by default. Increase the childlike feeling through rounded contours and gentle color accents, not through random stickers, extra characters, or invented scenery.
- After generation, apply the quality gate in the style guide. If it fails, regenerate at most once with one targeted correction instead of changing the whole style.

## Subject handling

- For people, preserve pose, gesture, hairstyle or head shape, clothing blocks, and the number of people; do not turn them into unrelated mascots.
- For animals and objects, preserve the recognizable outline and defining features.
- For buildings and landscapes, preserve the horizon, major rooflines, landmark shapes, and foreground/background separation.
- Do not add characters, props, scenery, logos, captions, decorative stickers, or invented details that are not implied by the source.

## Text and source marks

- Do not add a title, caption, signature, seal, logo, or readable text by default.
- Preserve source text only when the user explicitly asks for it; otherwise simplify or omit incidental signs and labels.
- Do not invent text or watermarks.

## Workflow

1. Inspect the supplied image before editing and identify the main subject, orientation, composition, and important visible features.
2. Classify the source and write down three to six invariants before prompting.
3. Use the supplied image as the edit target and pass it to the built-in image-generation tool.
4. Apply the fixed style contract, explicitly stating what must remain recognizable, what may be simplified, and which childlike details are allowed.
5. Inspect the result at full size and thumbnail size using the quality gate. If one criterion fails, regenerate once with that criterion as the only targeted correction.
6. Return the finished raster image and a short note describing the preserved subject and chosen line/color treatment.

## Default prompt shape

Use a prompt like this, adapting the subject to the actual image:

```text
Convert the supplied image into a stable, clean children's picture-book line drawing with a mildly playful, childlike feeling. Keep the main subject, silhouette, pose, object count, orientation, composition, and key identifying features recognizable. Use medium-weight rounded dark charcoal outlines, smooth friendly contours, a few purposeful interior lines, simple flat shapes, and two to five soft pastel colors on a clean white or warm-white paper background. Add only subtle childlike cues such as rounded forms, soft highlights, or small organic marks already implied by the source. Simplify secondary details and background clutter. No extra characters, props, stickers, scenery, invented text, logo, or watermark; no photorealism, gradients, glossy effects, dense shading, or messy sketching.
```

When the user asks for “更童真”“更童趣” or similar, keep the same stable style contract and use the playful variation in the style guide: slightly rounder shapes, warmer accent colors, and a few more readable details, while retaining the original subject and layout.

## Output

Return the generated image, the saved file path when available, and one sentence confirming which subject features were preserved. Do not claim that source details were preserved if the generated image materially changes them.
