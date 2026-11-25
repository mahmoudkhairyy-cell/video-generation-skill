# Motion reel as one HTML file (Route A spec)

The reel is ONE self-contained HTML file that, opened full-screen in a phone browser, plays the entire video automatically: every scene, animated, timed, at 9:16. The user screen-records the playback. That recording IS the video.

## Hard requirements

- Single file. No external images, no JS libraries, no fetch. Only allowed external: Google Fonts (`Tajawal`, `Cairo`, or `Almarai`). If offline fallback matters, add `font-family` fallbacks (`system-ui, sans-serif`).
- Stage: a fixed 9:16 canvas (`aspect-ratio: 9/16`, e.g. 405x720 CSS px scaled to fit screen, centered, black bars around it are fine — CapCut crops).
- `dir="rtl"` and `lang="ar"` for Arabic reels. All headline text as real HTML text (not SVG paths) so it renders crisp.
- Total runtime = sum of scene durations, 30–60s. Autoplay on load (with a 0.8s lead-in black/first frame so the recorder captures the start). End on a final frame that holds 1s (CTA / logo / end card), then stop — do not loop.
- Everything animated with CSS keyframes + a tiny JS scene scheduler (`setTimeout` chain or `requestAnimationFrame` clock). No video, no canvas recording, no WebGL.

## Scene grammar (the look)

- Flat solid background per scene (one bg + one ink + ONE accent color for the whole video; a single contrasting dark scene mid-video is allowed for emphasis).
- HUGE bold Arabic headline (font-weight 800/900, 60–90px equivalent), entering with a pop/slide + slight overshoot.
- Number chip: small filled box (accent color) with the step number, next to or above the headline.
- Small uppercase Latin sub-label under Arabic headlines (e.g. `STEP 02 / 06 · ONE LINE`) — this is part of the viral look.
- Progress indicator: dashes or a bar at the top that fills scene by scene; step label top corner.
- Simple flat shapes only: rounded rects, circles, phone/window mockups (rect + dots), folder/zip icons, waveform bars (animated divs), check marks. Draw with divs/borders, keep to a few elements per scene.
- Motion types: slide-in, pop with scale, highlight swipe (a colored box that wipes behind a keyword), waveform bounce, mockup tilt-in. Ease-out, snappy (150–400ms). Never slow fades.
- Watermark/handle: small, bottom or side, optional.

## Timing and sync with voice-over

- Write each scene's duration to match its VO line(s): roughly 1 second per 2–2.5 Arabic words, plus 0.3s breathing room. Put the duration map in an HTML comment at the top so it is easy to retime.
- The user aligns VO in CapCut; minor drift is fixed there by trimming/speeding. Design scenes as independent blocks so one scene can be shortened without breaking others.
- If the user reports the VO is longer than the reel, increase scene durations in the JS timing array — that is a one-line edit.

## Output checklist (verify before handing over)

1. Opens as a single file, plays start to finish without interaction, then stops on the end card.
2. All Arabic text renders RTL, bold, no tofu boxes (font loaded or fallback fine).
3. Scene count and durations match the script; total 30–60s.
4. No external assets besides fonts; works in a phone browser full-screen.
5. Colors: bg/ink/accent set named in an HTML comment, so palette swaps are one edit.
