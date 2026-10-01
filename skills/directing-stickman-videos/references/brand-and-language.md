# Brand Packs and Narration Language

Read this only when the user or a calling skill supplies a narration language other than English, a brand pack, or both.

## Narration language

- Write the VO in the requested language and keep the reference translation in the user's language (skip it when both are the same).
- Word budget for about sixty seconds:

  | Language | Words across six clips | Per clip |
  |---|---|---|
  | English | 130–150 | 21–25 |
  | Spanish (Cuba / Latin America) | 140–160 | 23–27 |
  | Portuguese (Brazil) | 135–155 | 22–26 |

- Spanish for Cuba: neutral Caribbean Spanish, *tú* form, short sentences, no Spain-specific slang (*vale*, *mola*), local terms only when the brand pack allows them (for example *fula*, *saldo*, *tarjeta*).
- Dialogue stays audio-only and must be quoted exactly inside every prompt. Name the language and accent in the narrator lock, for example: "a warm young adult narrator speaking Caribbean Spanish with a soft Cuban accent".
- Most video models drift on non-English speech. Always add the stitching note: generate clips with SFX, then lay one continuous external VO track (recorded or TTS) during assembly.

## Brand pack

A brand pack is a JSON with `name`, `palette` (each color has `describe`), `video.stickman` (`theme`, `accents`), `tone`, `avoid`, `video.signature`, and `feature_topics`.

Apply it like this:

1. **Theme**: propose `video.stickman.theme` and ask the user to confirm it in the setup gate. Do not choose it silently.
2. **Accents**: use exactly the three words in `video.stickman.accents` as the palette. They are already descriptive; never convert them to color codes.
3. **Tone and claims**: follow `tone`; never write anything in `avoid`; do not invent product features beyond `feature_topics` or the user's source.
4. **Signature**: close the final clip with the brand idea in `video.signature`, staged as a visual (no visible logo text inside generation prompts; logos are composited in post-production).
5. **Post-production note**: list the brand overlays to add after generation: logo lockup, CTA and URL from the brand pack, captions in the narration language.

Never put real customer data, prices, or rates on screen unless the user's source provides them with a date and source.
