---
name: visual-thinking
description: Generate and inspect image or motion concepts for new UI, maps, game spaces, and grounded presentations of existing products.
---

# Visual Thinking

Use an image generation model as a visual sketching partner. Turn the user's idea into an image, inspect the actual result, and let what is visible guide the next focused revision.

## Workflow

1. Infer the artifact, purpose, viewpoint, required content, and constraints from the request. Ask only when missing information would materially change the result.
2. Use the user's chosen image model and provider. If none is chosen, use an available image generation tool suited to the task.
3. Generate one concept or a small coherent set. For multiple screens, define a shared visual language, setting, and named characters before describing each screen's distinct state.
4. Inspect every generated image. Report concrete strengths, errors, inconsistencies, and uncertain details that are actually visible.
5. Make authorized small corrections when inspection exposes a clear miss. Invite user feedback when the next change involves a meaningful creative choice.
6. Regenerate only what the change requires. Use an existing image as a reference for local revisions or continuity. If the reference preserves an unwanted composition, consider fresh text generation.
7. Repeat until the concept answers the user's design question. Record the result and lessons without claiming more than the images demonstrate.

## Existing products

Inspect the public product and any authorized signed-in state before planning its presentation. Treat source screenshots as truth, preserve the brand, and state when an authenticated surface was unavailable. Do not invent controls, features, results, or unseen account behavior. Preserve material qualifications such as stated processing times. Published workflow diagrams explain a product; they do not prove that you ran those jobs.

Capture observed start, action, and result states when demonstrating a real interaction. Reuse a source screenshot directly when it needs no edit. When exact UI text or state matters, retain or composite the corresponding real UI pixels and ask the model for surrounding motion. Keep original captures, edited presentation frames, and generated motion distinct in the working notes and final claims.

Before uploading a capture to a model provider, inspect it and crop or redact keys, tokens, private account data, and other sensitive content.

## Prompt guidance

State the purpose and viewing context before visual style. Describe the viewpoint, main regions, hierarchy, interaction state, and details that must remain consistent. Give each screen one clear job.

Keep visible copy short and believable. Supply exact labels when wording matters. Do not invent pricing, guarantees, customer claims, capabilities, or other business facts.

Avoid broad demands such as "make it beautiful" when a concrete direction would work better. Preserve room for the image model to contribute ideas and preserve the user's control over the concept.

### Reusable base prompt

```text
Create a visual concept for [artifact] used by [audience] to [purpose].

View: [screen, camera angle, scale, or spatial viewpoint].
Required content: [regions, objects, controls, characters, or states].
Visual direction: [specific mood, materials, color, typography, illustration, or game style].
Continuity: [shared characters, setting, proportions, and visual rules].
Constraints: [exact labels, counts, relationships, exclusions, and facts that must not be invented].

Make the composition readable at a glance. Keep visible copy concise and internally consistent.
```

For a multi-screen set, append a short block for each screen describing its purpose and state. Do not ask every screen to show every feature.

## Inspect the result

- Check spelling, legibility, counts, duplicates, names, and identity.
- Compare state across screens, including timers, player status, selected items, and menu behavior.
- Check whether the composition communicates the requested scale and navigation relationships.
- Check that controls and copy fit the product context. In an online game, a local menu should not imply that the whole match has paused.
- Describe only what is visible. Treat the image as a concept, not proof of working software, accessible interaction, accurate geography, or a valid game level.
- Separate observed problems from optional design preferences.

## Revise with intent

Use a reference image when the goal is to preserve visual identity, product shell, or local composition while changing labels, elements, or screen state. References can also preserve unwanted framing and layout. When the reference anchors a composition the user wants to replace, restate the shared style in text and generate a fresh image.

Prefer one or two explicit corrections per revision. If the image contains many unrelated errors, decide with the user whether to correct the current direction or explore a new one.

## Add motion when it answers the question

For a functional demo, design matched empty, input-only, and result keyframes with the same camera and layout. State which action causes each change, such as drawing, clicking, loading, and revealing. Hold the result long enough to read. The ending state must not appear before the action that creates it.

Use first-frame and last-frame endpoints when the model supports them, then inspect intermediate frames for cause before effect. Endpoints constrain states but do not guarantee timing. A readable hold settles the camera and composition while natural subject motion continues. If a beat lands late, trim contiguous motion or regenerate a short shot. Do not pad it by cloning, freezing, or looping still frames unless the user intends a freeze effect.

Treat functional demo shots and expressive promotional beats as separate goals. Choose pacing and transitions for the product and audience. Distinguish subject motion from camera motion. Motion applied to an already complete interface shows camera movement, not proof that the interface created the result.

Inspect the rendered video. Generated interface motion is concept footage, not pixel-stable production UI, and intermediate text may warp even when landing frames recover.

For a complete launch-film example with staged keyframes, read [references/seam-studio.md](references/seam-studio.md).

