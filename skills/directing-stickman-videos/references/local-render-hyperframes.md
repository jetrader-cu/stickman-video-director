# Local Render with HyperFrames (No Video-Model Access)

Use this when the target video model is unavailable to the user (regional restrictions, no card, no credits) or when the user asks for a deterministic, editable render.

HyperFrames (`heygen-com/hyperframes`, Apache-2.0) renders HTML + GSAP compositions to MP4 locally with headless Chrome and FFmpeg. Stick figures are drawn as SVG lines, so the approved Phase A storyboard maps directly to code.

## Mapping Phase A to a composition

| Phase A element | HyperFrames implementation |
|---|---|
| Six clips of ~10 s | Six timed scenes (`data-start`, `data-duration`) in one root composition, or six sub-compositions |
| Theme polarity | Root background and stroke color (`#FFFFFF` + black lines, or `#000000` + white lines) |
| Character lock | One reusable SVG stick figure (circle head, five line limbs, uniform stroke width) animated with GSAP |
| Three accent colors | CSS variables; take the hex values from the brand pack in code only (never in model prompts) |
| Three beats per clip | GSAP labels at 0, 3 and 7 s of each scene |
| Visual metaphors | Simple SVG props (arrows, coins, phones, charts) drawn with the same line weight |
| Camera moves | GSAP transforms on a scene wrapper (scale = push-in, x/y = pan) |
| Transitions | Match the final pose of clip *n* to the first pose of clip *n+1*; wipe or morph between scenes |
| VO | One continuous track: local TTS (`npx hyperframes tts --voice ef_dora -l es`) or a recorded/cloned voice |
| Captions | `npx hyperframes transcribe vo.wav --language es` then caption overlay |
| BGM / SFX | `<audio>` clips with `data-volume`; duck BGM under the VO |

## Deliverable

1. The approved Phase A (unchanged).
2. A scene-by-scene build list: SVG elements, GSAP moves per beat, and audio cues.
3. Commands: `npx hyperframes init <name> --resolution portrait --example blank`, author `index.html`, `npx hyperframes check`, `npx hyperframes render . -o video.mp4`.

Keep the same negative constraints: no on-screen words inside scenes except the optional post-production overlay.
