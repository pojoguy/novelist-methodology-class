# Production Setup — Recording & Edit

## Terms in this document

**For non-technical readers:** recording and editing vocabulary used below.

| Term | Plain language |
|------|----------------|
| **HDMI** | Cable that carries **video** from the camera to the computer capture card. |
| **DeckLink / capture card** | **HDMI ingest (input)** — receives live signal from the camera into the PC; not a display output. |
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
| **Display** | **70" 4K monitor** (single) | Teleprompter + Slides as **windows** on same panel; OBS program = **camera via DeckLink ingest** unless compositing |

---

## Signal flow

```text
Canon HF G20 (mini HDMI out — 1080p)
        │
        ▼
Blackmagic DeckLink (HDMI in — capture input)
        │
        ▼
OBS Studio ──► record (.mkv / .mp4) ──► DaVinci Resolve
        ▲
Logitech G733 (mic + headphones)

70" 4K monitor ◄── GPU display out (teleprompter / Slides — not through DeckLink)
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

## DeckLink capture (HDMI in) + OBS

### OBS — video

| Setting | Value |
|---------|-------|
| **Base / output canvas** | 1920×1080 |
| **FPS** | Match camera (24 or 30) |
| **Source** | Video Capture Device → **DeckLink** (select the card's **HDMI input** / ingest device) |
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
| **A-Roll** | Camera via **DeckLink ingest** — full frame (default record) |
| **A-Roll + Lower Third** | DeckLink ingest + blue-chroma Slides bar (optional — see § On-screen text) |
| **B-Roll / Screen** | Display Capture or Window Capture for phone UI, maps, banking |
| **End card** | Static PNG or Resolve-only (easier in Resolve) |

**Teleprompter + Slides:** One **70" 4K** panel — prompter and deck as separate windows (see § Single-monitor layout). OBS **A-Roll** records **camera via DeckLink ingest** only; the monitor is a separate GPU output and is not in the program feed unless you explicitly composite (blue-chroma lower third).

---

## Single-monitor layout (70" 4K)

Teleprompter and Google Slides / PowerPoint both run as **windows on the same display**. The Canon stays on its tripod; the monitor is your **read surface**, not a second camera.

### Camera ↔ monitor placement

| Goal | Setup |
|------|--------|
| **Eye line** | Lens **centered on** or just below the monitor; prompter text in the **upper center** band (near lens height) |
| **Distance** | At 70", sit far enough back that you see prompter + slide clock without scanning — typically **1.5–2.5 m**; increase prompter font if you are closer |
| **Framing** | HF G20 on tripod — talking head; monitor is **behind or above** lens, not beside it (side placement reads as "looking off camera") |
| **Glare** | Slight tilt or bias light so the panel does not reflect into the lens |

### Recommended window zones (3840×2160)

```text
┌─────────────────────────────────────────────┐
│         TELEPROMPTER (upper center)         │  ← scroll script; largest window
│              near lens line                 │
├─────────────────────────────────────────────┤
│                                             │
│     (unused / dimmed desktop)               │
│                                             │
├──────────────────────┬──────────────────────┤
│  Slides presenter    │  OBS preview (small) │  ← slide clock; optional
│  or next-card strip  │  not recorded        │
└──────────────────────┴──────────────────────┘
```

| Window | Role | Notes |
|--------|------|--------|
| **Teleprompter** | Scroll `00-history-and-authority.md` teleprompter block | High contrast; **large type** (70" rewards 48–72 pt+); auto-scroll or foot pedal / hotkey |
| **Slides** | **Presenter clock** — current card, next cue | **Windowed** speaker view or narrow strip; avoid fullscreen deck over prompter mid-take |
| **OBS** | Preview + record control | Small corner; **do not** fullscreen OBS over prompter while rolling |

**Record session:** Windows **Focus assist / Do not disturb** — no toast notifications over prompter.

### 4K / Windows scaling

- OBS **Window Capture** crop coords follow **display scaling** (125%, 150%, etc.). After any scaling change, re-test chroma crop.
- Teleprompter app font size is independent of OS scale — set by eye at your seated distance, not by resolution number.
- Camera **HDMI out** → DeckLink **HDMI in** remains **1080p**; the 70" panel is **GPU display out** (4K UI only — teleprompter, Slides, OBS control).

### Slides on same monitor + blue chroma

Works if:

1. **Prompter** = separate window (upper) — **not** inside the captured Slides region.
2. **Slides** = resizable window; OBS **Window Capture** + crop to **lower-third bar only**; Chroma Key on blue.
3. Or record **clean A-Roll** (DeckLink ingest only) and add lower thirds in Resolve — avoids fighting window layout on one panel.

**Parallel safety:** Screen-record the Slides window (no key) while presenting — rescue sync in Resolve without re-shooting face.

### What does *not* go on this monitor

- **Phone B-roll** — screen record or Canon shooting the phone; not the 70" display (see B-roll table below).
- **Beat 3 montage labels** — added in Resolve on B-roll clips.

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

**Slides as presenter notes:** Window on the same 70" panel — advance to your voice; does not need to burn into the program feed (default: Resolve for on-screen text).

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

1. **Video Capture Device** — DeckLink **ingest** (bottom layer).
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
4:05 Craft panic
4:35 Why this series
5:10 What's next
```

---

## Pre-flight checklist (day of record)

- [ ] G733 charged; G HUB recognizes mic
- [ ] DeckLink **ingest** seen in OBS (preview live from camera HDMI)
- [ ] HF G20 HDMI out live; focus / WB / exposure locked
- [ ] OBS test record 10 s — play back audio + video
- [ ] Teleprompter script loaded (`00-history-and-authority.md` → teleprompter block)
- [ ] Teleprompter window upper-center; Slides clock windowed (not fullscreen over script)
- [ ] Prompter font readable at seated distance on 70" panel
- [ ] Focus assist / notifications off
- [ ] Lower thirds: Resolve template ready **or** blue Slides window + OBS chroma test (10 s)
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
| B-roll phone UI | Screen record, or Canon on tripod filming phone on desk — not the 70" monitor |

---

## Changelog

| Date | Change |
|------|--------|
| 2026-08-02 | DeckLink = HDMI ingest (input), not display output; signal-flow diagram |
| 2026-08-02 | Single 70" 4K monitor: teleprompter + Slides window layout; clarify phone B-roll |
| 2026-08-02 | On-screen text: hybrid Resolve + optional blue-chroma Slides; B-roll full-frame rule |
| 2026-08-02 | Initial rig doc: HF G20, DeckLink, OBS, G733, Resolve |
