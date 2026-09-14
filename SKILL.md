---
name: child-simple-line-art
description: Convert supplied images into clean, friendly children's simple line drawings with recognizable silhouettes, minimal detail, and optional flat pastel colors. Use when the user asks for 儿童简笔画、幼儿画、简单线稿、绘本线稿, or a cute simplified redraw of an image.
---

# Child Simple Line Art

Turn an attached or supplied image into a simple children's drawing while keeping the main subject recognizable.

## Visual direction

- Use a clean white, warm-white, or very light pastel background.
- Draw with smooth dark charcoal or black lines, rounded joins, simple contours, and a friendly hand-drawn feel.
- Keep the image low-complexity: use only the lines needed to identify the subject.
- Use flat fills in no more than five soft colors when color is helpful; otherwise use line art only.
- Preserve the main silhouette, pose, object count, landmark features, and overall composition unless the user asks for a new arrangement.
- Simplify texture, small background objects, reflections, facial detail, and architectural detail into a few readable marks.

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
2. Use the supplied image as the edit target and pass it to the built-in image-generation tool.
3. Apply the visual direction above, explicitly stating what must remain recognizable and what may be simplified.
4. Inspect the result at full size and thumbnail size. If the subject is unclear or the drawing is too detailed, regenerate once with simpler contours and fewer colors.
5. Return the finished raster image and a short note describing the preserved subject and chosen line/color treatment.

## Default prompt shape

Use a prompt like this, adapting the subject to the actual image:

```text
Convert the supplied image into a clean children's simple line drawing. Keep the main subject, silhouette, pose, object count, and key identifying features recognizable. Use smooth rounded dark outlines, very few interior lines, simple flat shapes, and at most five soft pastel colors on a clean white or warm-white background. Simplify secondary details and background clutter. Keep the original composition unless a new layout is requested. No extra objects, no realistic rendering, no gradients, no complex shading, no decorative text, no logo, no watermark.
```

## Output

Return the generated image, the saved file path when available, and one sentence confirming which subject features were preserved. Do not claim that source details were preserved if the generated image materially changes them.
