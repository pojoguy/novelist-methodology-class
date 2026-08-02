# Production Setup — Recording & Edit

## Terms in this document

**For non-technical readers:** recording and editing vocabulary used below.

| Term | Plain language |
|------|----------------|
| **HDMI** | Cable that carries **video** from the camera to the computer capture card. |
| **DeckLink / capture card** | Hardware that lets the computer **receive live camera video**. |
| **OBS** | Free software to **preview, record, and optionally stream** camera + microphone. |
| **A-roll** | **You talking to camera** — main footage. |
| **B-roll** | **Cutaway footage** (phone screen, stock clips) over your voice. |
| **VO / voiceover** | **Narration** recorded without camera — often over B-roll. |
| **MKV / MP4** | **Video file formats** — MKV is safer if recording crashes; MP4 is easy to edit. |
| **Remux** | **Repackage** a file without re-encoding — OBS can turn MKV into MP4 quickly. |
| **DaVinci Resolve** | Free/pro **video editor** — cut, color, audio, titles, export. |
| **Fairlight** | The **audio page** inside Resolve — levels, noise reduction, loudness. |
| **LUFS** | **Loudness unit** — YouTube expects about **−14 LUFS** for consistent volume. |
| **Teleprompter** | **Scrolling script** on a screen you read while looking near the lens. |
| **End card** | **Last seconds** of video — subscribe, next episode, links. |
| **Chapters** | **Timestamp links** in the YouTube description so viewers can jump to sections. |
| **Lower third** | **Text bar** at the bottom of frame — name, term, or cue line. |
| **Chroma key** | **Color removal** (e.g. blue screen) so only the text bar composites over camera. |
| **Jump cut** | **Edit** that removes dead air or flubs — shortens the clip; live-burned text can fall out of sync. |

---

Gear and workflow for the **LLM Methodology** YouTube series.

---

## Hardware inventory

| Role | Device | Notes |
|------|--------|-------|
| **Camera** | Canon **HF G20** | 1080 AVCHD camcorder; **mini HDMI** live output |
| **Capture** | Blackmagic **DeckLink** (HDMI ingest) | Camera → DeckLink → PC; low-latency monitoring in OBS |
| **Capture / record** | **OBS Studio** | Scene switching, recording, optional teleprompter monitor |
| **Audio I/O** | **Logitech G733** headset | Mic + monitoring; wireless — mind latency and RF noise |
| **Edit** | **DaVinci Resolve** | Cut, color, Fairlight audio, Fusion titles, deliver |

---

## Signal flow

```text
Canon HF G20 (mini HDMI out)
        │
        ▼
Blackmagic DeckLink (HDMI in)
        │
        ▼
OBS Studio ──► record (.mkv / .mp4) ──► DaVinci Resolve
        ▲
Logitech G733 (mic + headphones)
```

**Optional parallel path:** Record AVCHD to the G20's SD card as **backup**. If OBS or DeckLink fails mid-session, you still have camera-native footage (sync in Resolve by clap or waveform).

---

## Canon HF G20 — camera settings

| Setting | Recommendation | Why |
|---------|----------------|-----|
| **Resolution / fps** | **1920×1080 · 24p** or **30p** | Match OBS project rate; 24p reads more "documentary," 30p safer for YouTube |
| **HDMI output** | **On** while recording | Feed DeckLink; confirm output is **clean** (no on-screen menus in HDMI — check G20 HDMI menu options) |
| **Focus** | **Manual** (or face lock if solo) | Prevents hunting mid-sentence |
| **Exposure** | Manual or locked auto | Lock before rolling — flicker reads amateur |
| **White balance** | Preset or manual gray card | Consistent skin tone across beats |
| **Audio on camera** | Off or low | **G733 → OBS** is primary audio; disable cam mic in OBS mix |

**Lens / framing:** Talking head — eyes upper third; leave headroom for on-screen titles (`YOU ALREADY USE AI` sits above or below face, not on it).

**Light:** Window or key light at 45°; HF G20 needs reasonable light — noisy gain in dim rooms.

---

## DeckLink + OBS

### OBS — video

| Setting | Value |
|---------|-------|
| **Base / output canvas** | 1920×1080 |
| **FPS** | Match camera (24 or 30) |
| **Source** | Video Capture Device → DeckLink input |
| **Format** | UYVY or default; if banding, test alternatives in BM utilities |

### OBS — audio

| Source | Device | Filters (suggested) |
|--------|--------|---------------------|
| **Mic** | G733 (Logitech G HUB device) | **Noise suppression** (light), **Compressor** (−12 dB threshold, 3:1), **Limiter** (−1 dB ceiling) |
| **Desktop** | Off unless capturing UI | — |

**Monitor:** G733 headphones via OBS **Advanced Audio** → Monitor and Output on mic, so you hear yourself without latency pile-up.

### OBS — recording

| Setting | Value |
|---------|-------|
| **Format** | **MKV** (crash-safe) — remux to MP4 after session if needed (OBS File → Remux) |
| **Encoder** | NVENC / QuickSync / x264 — whatever is stable on your PC |
| **Bitrate** | 15–25 Mbps @ 1080p talking head |
| **Separate audio track** | Enable if available — isolates mic for Fairlight |

### OBS — scenes (minimum)

| Scene | Contents |
|-------|----------|
| **A-Roll** | DeckLink full frame (default record) |
| **A-Roll + Lower Third** | DeckLink + blue-chroma Slides bar (optional — see § On-screen text) |
| **B-Roll / Screen** | Display Capture or Window Capture for phone UI, maps, banking |
| **End card** | Static PNG or Resolve-only (easier in Resolve) |

**Teleprompter:** Second monitor or tablet with teleprompter block from script file; OBS records camera only — prompter out of frame.

**Slides on monitor 2 (no chroma):** Use as **presenter clock** — which card should be up — even when recording clean A-Roll only.

---

## Logitech G733 — audio notes

**Strengths:** Consistent level, fine for explainers, already owned.

**Limits:** Wireless headset mics are not lavaliers — room tone, plosives, and "headset voice" are real. Mitigate in Fairlight, not by shouting.

| Mitigation | Where |
|------------|--------|
| Mic 15–20 cm from mouth, boom slightly off-axis | Physical |
| Pop filter or foam windscreen | Physical |
| Light noise reduction | OBS filter → Fairlight if needed |
| EQ: high-pass **80–100 Hz**, gentle presence **3–5 kHz** if muddy | Fairlight |
| Normalize to **−14 LUFS** integrated (YouTube) | Fairlight → Deliver |

**Beat 3 VO option:** Record montage voiceover in OBS **Audio-only** scene (black video) or record in Resolve Fairlight after picture lock — same G733 chain.

---

## Session plan — Episode 0

Record in this order to minimize setup churn:

| Order | Content | Mode | Script ref |
|-------|---------|------|------------|
| **1** | Full A-roll: Beats 1, 2, 4, 5, Close | `[CAM]` single OBS scene | Teleprompter block — pause at `[/]` |
| **2** | Beat 3 voiceover only | OBS record audio + black, or VO in Resolve | Montage VO paragraph |
| **3** | B-roll inserts | Phone screen record **or** OBS Display Capture | Shot list § Beat 3 |
| **4** | Safety pickup | Re-read any flubbed sentences | Per-beat |

**Do not** stop camera between Beats 1–2–4–5 if you can sustain energy — cut on jump cuts in Resolve. Beat 3 is assembly edit over B-roll.

### B-roll capture (phone / screen)

| Shot | Capture method |
|------|----------------|
| Autocomplete, captions, check deposit | Phone screen record → AirDrop / cable → Resolve |
| Night photo, portrait mode | Phone camera → import stills or short clips |
| Video call UI | OBS window capture (blur account info) |

---

## On-screen text — hybrid workflow

**Default:** Build lower thirds and labels in **DaVinci Resolve** (Edit → Titles or Fusion Text+). Reuse one template per series — retime on the **cut** timeline after jump cuts.

**Optional live path:** **Google Slides or PowerPoint** on a **blue** background, chroma-keyed in OBS — works well for this rig (less skin spill than green on talking-head footage).

### Why hybrid (not all-live)

Jump-cut editing removes breaths and false starts **after** record. Text burned into the camera take is locked to **wall-clock time** — a 4 s cut makes the slide early or wrong. Resolve overlays sit on the edited timeline.

| Text type | Where | Method |
|-----------|--------|--------|
| Cold open title (`YOU ALREADY USE AI`) | 0:00–0:08 | **Resolve** — full-frame title + fade |
| Beat 1 timed cues + icons | Over cuts / B-roll | **Resolve** |
| Beat 2 timeline + stochastic labels | Graphics + lower thirds | **Resolve** (timeline is not a live slide) |
| Beat 3 montage labels | Full-screen B-roll | **Resolve** only |
| Beat 4 craft-panic list | Steady cam | **Resolve** or **live blue chroma** |
| Beat 5 authority cards | Steady cam | **Resolve** or **live blue chroma** |
| Close — repo URL, end card | 4:55+ | **Resolve** |

**Slides as presenter notes:** Always OK on monitor 2 — advance to your voice; do not require burning into the program feed.

### Blue chroma (preferred over green for this series)

| | Blue screen | Green screen |
|---|-------------|--------------|
| **Skin spill** | Usually less on forehead/neck | Common on talking-head footage |
| **This rig** | **Preferred** for live composite | Use only if blue wardrobe conflict |
| **Avoid on camera** | Blue shirt, tie, cool LED-only key | Green clothing |

**Slide deck setup (Slides or PowerPoint):**

- Background: **one flat blue** — e.g. `#0047AB` or broadcast blue; no gradients.
- Layout: **lower-third bar** only (text on blue bar; or full slide keyed with crop so only the bar composites).
- Typography: high contrast (white on blue bar); test at 1080p before session.

**OBS — A-Roll + Lower Third scene:**

1. **Video Capture Device** — DeckLink (bottom layer).
2. **Window Capture** — Slides in presentation mode (top layer); crop to lower-third region if possible.
3. **Filter on Slides source:** Chroma Key — key color = slide blue; **Similarity** low; **Smoothness** modest; **Spill Reduction** toward blue.
4. **Key light:** Slight warm (amber) on face — separates skin from blue spill.
5. **Wardrobe:** No blue on camera.

**Parallel safety:** Screen-record the Slides window (no key) in a second OBS scene or separate track. If jump cuts break live timing, re-key or replace the bar in Resolve without re-shooting A-roll.

### Resolve — reusable lower-third template

Build once; duplicate per episode:

| Spec | Value |
|------|-------|
| **Safe area** | Bar within lower **15%** of frame; clear of face in standard framing |
| **Font** | One sans-serif; **36–48 px** @ 1080p for terms; **56–72 px** for cold open |
| **Duration** | Term cards **3–5 s**; montage labels **2–3 s** (per script) |
| **Transition** | **8–12 frame** fade in/out |
| **Tracks** | Titles above A-roll; montage labels on B-roll track only |

Episode 0 script on-screen tables are the cue sheet — place titles after picture lock, not from script timestamps alone (timestamps shift after cuts).

### B-roll: full frame, not PIP

Proof footage (phone UI, check deposit, night mode) stays **full-screen** on cuts. Lower thirds on face only during A-roll thesis lines — not over B-roll proof shots. See script shot lists per beat.

---

## DaVinci Resolve — workflow

### Project setup

| Setting | Value |
|---------|-------|
| **Timeline resolution** | 1920×1080 |
| **Timeline fps** | Match OBS (24 or 30) |
| **Color management** | DaVinci YRGB (default fine for talking head) |

### Edit page — assembly

1. Import OBS MKV/MP4 + B-roll + end card PNG.
2. **A-roll base:** Place full take; blade on script beat timestamps (chapter markers in script).
3. **Beat 3:** Lay VO on audio track 1; B-roll on V1, no camera.
4. **Jump cuts:** Remove breaths and false starts; 2–4 frame cross-dissolve optional if jump feels harsh.
5. **On-screen text:** Per § On-screen text — Resolve templates for most cues; optional blue-chroma bars only on steady-cam beats (4–5).

### Fairlight — audio

1. **Sync:** If using SD backup, sync by clap or PluralEyes/manual waveform.
2. **Voice:** Noise reduction (mild), EQ, compressor, limiter.
3. **Music:** Optional bed under intro/end card only — **−18 dB** under voice if used.
4. **Loudness:** Loudness meter → target **−14 LUFS** integrated, **−1 dBTP** true peak (YouTube).

### Color — optional

HF G20 + room light: slight contrast and saturation bump in Color page; match B-roll phone footage so montage doesn't flash warm/cool.

### Deliver — YouTube

| Setting | Value |
|---------|-------|
| **Preset** | YouTube 1080p |
| **Format** | MP4, H.264 or H.265 |
| **Upload** | Direct or via YouTube Studio |

### Chapters

Paste from script into YouTube description (YouTube auto-chapters if timestamps formatted):

```text
0:00 You already use AI
0:08 The 2022 myth
0:55 What stochastic means
2:20 AI you already use
3:50 Craft panic
4:20 Why this series
4:55 What's next
```

---

## Pre-flight checklist (day of record)

- [ ] G733 charged; G HUB recognizes mic
- [ ] DeckLink seen in OBS (preview live)
- [ ] HF G20 HDMI out live; focus / WB / exposure locked
- [ ] OBS test record 10 s — play back audio + video
- [ ] Teleprompter script loaded (`00-history-and-authority.md` → teleprompter block)
- [ ] Lower thirds: Resolve template ready **or** blue Slides deck + OBS chroma test (10 s)
- [ ] No blue clothing if using live chroma lower thirds
- [ ] Room quiet — HVAC, notifications off
- [ ] Water; script beats marked

---

## Post-flight checklist

- [ ] Remux MKV → MP4 if needed
- [ ] Backup raw to second drive
- [ ] Resolve project saved with date `Ep00_YYYY-MM-DD`
- [ ] Captions: Resolve auto-caption or YouTube → correct `Erlang`, `Gaines`, `Whisper`, `Chirp`, `stochastic`
- [ ] Blur banking PII in check-deposit shots
- [ ] On-screen text retimed to **cut** timeline (not raw record timestamps)
- [ ] Description + tags from script file
- [ ] End screen: Subscribe, playlist, Ep. 1

---

## Future upgrades (optional, not required)

| Gap | Upgrade | Priority |
|-----|---------|----------|
| Headset mic quality | USB condenser (e.g. Samson Q2U) or lav + interface | Medium |
| Teleprompter | Pad + remote scroll app | Low |
| Key light | LED panel | Medium — biggest visual lift for HF G20 |
| B-roll only | Phone on tripod for consistent screen shots | Low |

---

## Changelog

| Date | Change |
|------|--------|
| 2026-08-02 | On-screen text: hybrid Resolve + optional blue-chroma Slides; B-roll full-frame rule |
| 2026-08-02 | Initial rig doc: HF G20, DeckLink, OBS, G733, Resolve |
