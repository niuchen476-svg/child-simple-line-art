# Children's Simple Line Art Style Guide

This reference is the stable visual contract for `$child-simple-line-art`. It is intentionally specific enough to make repeated conversions feel like one coherent personal style, while leaving the subject and composition open to the source image.

## Style identity

Aim for a warm children's picture-book drawing: simple, friendly, slightly imperfect, and easy to recognize at a glance. The result should feel like a careful child-friendly illustration made with a dark marker and a small box of pastel crayons.

Use:

- medium-weight dark charcoal or near-black outlines;
- rounded line caps and joins;
- smooth, confident contours with only mild hand-drawn variation;
- rounded corners and simplified organic shapes;
- a warm-white or very light pastel paper background;
- flat color areas with a faint paper grain only when it does not reduce clarity.

Avoid:

- photorealism, 3D rendering, glossy highlights, cinematic lighting, or airbrushed gradients;
- scratchy construction lines, excessive hatching, muddy shadows, or noisy detail;
- stickers, emoji, random decorative icons, invented characters, or a mascot treatment;
- scary, uncanny, overly sharp, or distorted faces.

## Color contract

Use two to five soft colors plus the paper background. Keep most of the image in one calm family and use at most one clear warm accent.

Good starting palettes:

- sky blue + leaf green + butter yellow + charcoal;
- dusty blue + peach + warm ochre + charcoal;
- sage green + coral + cream + charcoal;
- lavender blue + soft pink + muted yellow + charcoal.

Colors should be flat or nearly flat. A small amount of uneven crayon or risograph-like texture is acceptable, but the subject must remain readable. If the source is already colorful, simplify it into the closest two to five-color palette rather than preserving every hue.

## Childlike detail budget

The default is “mildly playful,” not maximally cute. Add charm through:

- rounder silhouettes and friendly proportions;
- a few simple interior marks for windows, leaves, ripples, fur, or clothing;
- tiny soft highlights or dots where the source already has lights or reflections;
- gentle repetition, such as a few leaves, clouds, waves, or windows;
- simple expressive features only when a face is already present in the source.

Do not add new people, animals, buildings, vehicles, signs, props, or scenery. A detail is allowed only when it is visible in, structurally implied by, or a direct simplification of the source.

## Subject routing

First choose one source type and preserve its invariants:

- **People:** keep the number of people, pose, gesture, head shape, hairstyle, and large clothing blocks. Use simple facial marks only if the face is visible.
- **Animals:** keep the body silhouette, head direction, ears, tail, and one or two defining markings.
- **Objects:** keep the outer contour, orientation, proportions, and the most distinctive functional parts.
- **Buildings:** keep the main massing, roofline, landmark tower or opening, and the foreground/background separation. Reduce windows to a few grouped marks.
- **Landscapes:** keep the horizon, major land/water/sky bands, one to three depth layers, and the strongest landmark shapes. Reduce reflections and foliage to readable patterns.
- **Collage or split layout:** keep the number, order, and approximate proportions of panels. Simplify each panel with the same line and color contract.

## Prompt assembly

Build the generation prompt in this order:

1. State the source type and the three to six invariants that must remain.
2. Paste the stable style identity: children's picture-book line drawing, rounded dark charcoal outlines, warm paper, two to five pastel colors, mildly playful.
3. State what may be simplified: texture, tiny objects, reflections, dense windows, or incidental background clutter.
4. State the composition rule: preserve orientation and original layout unless the user requests a change.
5. Add the negative constraints: no invented objects or text, no logo or watermark, no photorealism, gradients, glossy effects, or messy sketching.

Only vary the subject description, preserved invariants, palette, and detail budget between runs. This is the main stability mechanism.

## Quality gate

Inspect the result at full size and as a small thumbnail. It passes when:

- the main subject is recognizable in the thumbnail;
- the subject count, orientation, and major composition are correct;
- landmark contours survive while secondary detail is simplified;
- outlines are rounded, coherent, and not visibly tangled;
- color count stays within two to five soft colors plus paper;
- there are no invented objects, readable accidental text, logos, or watermarks;
- the mood is warm and child-friendly rather than dark, realistic, or uncanny.

If exactly one issue is found, retry once with a targeted instruction such as “restore the roofline,” “remove the extra object,” “reduce interior lines,” or “make the palette flatter.” Do not restart with a completely different style. If the second result still changes a source-critical detail, report that limitation honestly.
