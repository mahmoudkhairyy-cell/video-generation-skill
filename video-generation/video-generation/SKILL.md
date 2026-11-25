---
name: video-generation
description: Create a finished vertical (9:16) motion-graphics video from a one-line idea, using only a phone and free tools. Claude writes the script and voice-over text, then outputs the whole video as ONE self-contained animated HTML file that plays full-screen in the phone browser; the user screen-records it, adds free Arabic TTS voice-over, and finishes in the CapCut app. Use when the user wants to generate, make, or produce a video, reel, TikTok, or Short from scratch — especially flat motion-graphics/typography style — without a computer, paid tools, or editing skills. A secondary route covers realistic AI footage via free generators.
---

# Video Generation from a One-Line Idea (phone-only, free)

Turn one line into a finished 9:16 reel. Everything below works from the free Claude app on a phone plus free mobile tools. No computer, no paid plan.

## The two routes

| Route | Look | When |
|---|---|---|
| **A — Motion reel (default)** | Flat design, big Arabic typography, mockups, waveforms — the viral "motion" style | Default. Fast, reliable, fully free, no quotas |
| **B — AI footage** | Realistic or stylized generated clips | Only if the user explicitly wants realistic footage; daily credit limits apply |

Route A is the default. Read `references/motion-reel-html.md` before building the HTML reel. Read `references/free-tools.md` for route B and for the TTS options.

## Honest capabilities (always be straight with the user)

- Claude **writes** the video: hook, script, scene designs, voice-over text, and the animated HTML reel. Claude does **not** render or export an mp4.
- The "render" is a **screen recording** of the HTML reel playing in the phone browser (built into iOS and Android).
- Voice-over is free TTS (or the user's own voice recorded in CapCut).
- Final assembly (recording + voice + captions + music) happens in the **CapCut app** — free.

## Route A workflow

1. **Idea → script.** Write a hook-first Arabic (or user's language) script: 6–10 short lines, 30–60 seconds total. See `references/script-storyboard.md`.
2. **Storyboard → scene plan.** One scene per 1–2 lines; assign each scene a duration in seconds. Vary the palette between videos (pick a fresh bg/ink/accent set each time) so the user's videos never look identical.
3. **Build the reel HTML.** Output ONE artifact: a single self-contained HTML file that plays the whole video automatically (all scenes, animations, timing) at 9:16. No external assets except Google Fonts. Spec in `references/motion-reel-html.md`.
4. **Voice-over text.** Output the VO lines separately (plain text) for the TTS step, matching the scene order. See `references/voice-captions.md`.
5. **Tell the user exactly what to do** (short numbered steps, their language):
   - Open the HTML on the phone (tap the artifact → "open in browser" / download and open).
   - Start the phone's screen recorder, play the reel full-screen, stop at the end.
   - Generate the VO mp3 on a free Arabic TTS site (see `references/free-tools.md`).
   - In CapCut: new project → import the recording → add the VO audio → align, trim silence, auto-captions (Arabic) → optional background music → export 1080p.
   Assembly details in `references/assembly.md`.
6. **Iterate.** When the user gives feedback ("make the hook stronger", "change the colors"), edit the script/HTML and output the updated reel. Small feedback = small edit, not a rebuild.

## Route B workflow (AI footage)

Script and storyboard as above, then write one generation prompt per scene (see `references/prompts.md` — prompt formula, negative prompts, vertical settings, Egyptian-availability notes in `references/free-tools.md`). The user generates clips in the free tier of a generator, then assembles in CapCut with the same VO/captions path as Route A.

## Rules

- Vertical 9:16, 30–60 seconds. Hook in the first 2 seconds.
- Arabic-first: RTL text, Arabic fonts (Tajawal, Cairo), Egyptian-friendly wording unless the user wants MSA or another dialect.
- Never claim the AI generated a real person, real results, or earnings. No fake testimonials.
- Keep every output copy-paste-simple: the user is on a phone.
- If a step fails on the user's phone, offer the simplest fallback (e.g. own-voice recording instead of TTS) instead of adding tools.
