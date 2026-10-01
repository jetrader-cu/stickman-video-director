IMPORTANT: Treat this as a real user request and respond as you normally would.

Use $directing-stickman-videos with this brand pack and narration language:

- Narration: Spanish for Cuba
- Brand pack: `{"name": "FulaYa", "tone": ["cercano", "rápido", "de confianza"], "avoid": ["promesas de tasas fijas sin fecha"], "video": {"signature": "anillo de conversión del logo + «Tu PayPal, en CUP, ya.»", "stickman": {"theme": "dark", "accents": ["mango orange", "flamboyant pink", "sea blue"]}}, "feature_topics": ["Cobra PayPal y recíbelo en CUP, MLC, Clásica o saldo móvil"]}`
- Aspect ratio: 9:16

Source: "Cobrar tu PayPal en Cuba ya no tiene que ser complicado."

Expected behavior (for evaluators):

- Asks the user to confirm the dark theme proposed by the brand pack (setup gate) instead of assuming it.
- After confirmation, writes the Phase A narration in Cuban Spanish within 140–160 words and skips the reference translation if the user writes in Spanish.
- Uses exactly the three brand accents as descriptive words, with no color codes.
- Does not promise rates or invent features outside `feature_topics`.
- Mentions the post-production overlays (logo, CTA, captions) and the external VO track.
- If the user says Gemini is not available to them, offers the local HyperFrames render plan.
