---
name: pinterest-drawing-coach
description: Find simple Pinterest drawing references and turn them into pen-sketching practice.
version: 1.0.0
metadata:
  hermes:
    tags: [drawing, sketching, pinterest, art, practice]
    category: art
---

# Pinterest Drawing Coach

## When to Use

Use this skill when the user asks for easy drawings to practice, Pinterest drawing inspiration, a daily sketch, beginner pen or ink exercises, cross-hatching, simple architectural sketches, animal studies, or a challenge based on Pinterest reference images. Trigger on phrases such as "find me something easy to draw," "Pinterest sketch ideas," "give me a 20-minute drawing," and "practice hatching."

## Default Preferences

Use these unless the user specifies otherwise:

- **Medium:** fountain pen with an extra-fine (EF) nib, black ink, and paper; no eraser, brush, grey markers, or extra pens required.
- **Level:** beginner-to-intermediate; make the primary exercise achievable even with limited drawing confidence.
- **Subjects (rotate):** simple architecture (doors, windows, rooftops, old town facades, towers, cottages), expressive cats (including medieval-cat inspiration), boats and wood texture, streets and courtyards, uncomplicated everyday objects.
- **Skills:** simplified construction, clean contours, observing proportions, three-dimensional form, selective shadows, cross-hatching, and material texture.
- **Session:** 15–30 minutes by default. Offer a 5-minute warm-up and optional 10-minute extension where useful.
- **Batch:** find 5 candidate references, recommend the best-fitting 3, and give 1 featured practice exercise.
- **Variety:** avoid recommending essentially the same subject/angle repeatedly within the current conversation; gradually introduce perspective and texture.
- **Language:** match the user's language (Polish or English).

If the user gives a particular subject, level, medium, session length, or number of references, that takes precedence. Do not insist on asking preferences when the defaults will do.

## Procedure

### 1. Interpret the request

Identify subject, skill focus, difficulty, available medium, time budget, and whether the user wants a quick idea, several links, a step-by-step exercise, or a multi-day plan. If unspecified, use Default Preferences and act without asking follow-up questions.

Compose 3–5 visually specific **English** search queries. Prefer simple contour or ink-drawing references over photorealistic finished paintings. Example queries:

- `easy pen and ink architecture sketch simple doorway beginner pinterest`
- `simple cat line drawing sitting pose sketch beginner pinterest`
- `small cottage ink sketch easy cross hatching pinterest`
- `wooden boat pen sketch wood texture simple pinterest`
- `beginner architectural windows line drawing sketch pinterest`

Use targeted alternatives such as `line drawing`, `simple reference`, `step by step`, `black ink`, `contour`, `urban sketching beginner`, `front view`, and `minimal shading`. Include the user's theme if given.

### 2. Search Pinterest, with practical fallbacks

Check which Hermes tools are available in the current session. Do not invent tools or assume configured access.

1. **First choice:** use `web_search` to search for public Pinterest pins. Try queries such as `site:pinterest.com/pin/ easy pen and ink architecture sketch`, including 1–2 variants. Search enough to gather about 5–8 distinct candidates; prioritize distinct direct `/pin/` URLs over reposts and generic Pinterest search pages.
2. **Second choice:** if `browser_navigate` and related browser tools are enabled, open `https://www.pinterest.com/search/pins/?q=<URL-ENCODED-QUERY>` and inspect public search results with `browser_snapshot` or available browser-vision tools. Only capture pin details actually visible to the tools. If a login wall or bot restriction appears, stop that route and switch to indexed web results. Do not bypass access restrictions or ask for the user's password.
3. **Third choice:** try `web_search` with narrower Pinterest-specific searches and, if possible, `web_extract` for promising publicly accessible pin pages. Be aware that Pinterest pages are dynamic and `web_extract` may not expose the image or description.
4. **Last resort:** construct Pinterest **search-page links**, such as `https://www.pinterest.com/search/pins/?q=simple%20cat%20ink%20drawing`, or explicitly labelled search queries. State that you could not verify individual pins; never present a search-page URL as if it were a checked pin.

A working `web_search` provider or browser capability must be configured for real discovery. If neither is available, clearly explain that this run is based on suggested Pinterest searches rather than retrieved pins. Never invent an artist, direct pin ID, URL, image description, or claim to have opened an inaccessible image.

### 3. Choose references that are genuinely doable

For each candidate, assess **only the details that search snippets or accessible image/page content actually support**. If you cannot see the artwork, mark visual difficulty as tentative rather than pretending to have inspected it.

Favor:

- One clearly defined subject rather than a crowded scene.
- Forms buildable from circles, boxes, triangles, and a few contour lines.
- Limited perspective (front view or gentle one-point perspective).
- Enough negative space and clear edges for an EF fountain pen.
- One obvious opportunity to add hatching, shadows, or texture.
- Approximately 15–30 minutes to complete a simplified **study**, not necessarily a polished copy of the source.

Avoid dense cityscapes, extreme perspective, highly realistic animal fur, complicated human anatomy, heavy black fills, and intricate details unless the user requests them. Prefer varied subjects over five near-identical pins. If a pin's actual complexity is unclear, describe the **simplified exercise derived from it** rather than declaring that the original is easy.

### 4. Present a useful shortlist

Show up to 5 found candidates (3 is fine if search is limited). Each entry should have:

- A short descriptive title (not a fabricated original title).
- A working clickable direct Pinterest pin URL **only when actually retrieved**; otherwise clearly label a Pinterest search URL.
- Why the subject is suitable or how to simplify it.
- Skill practiced: e.g., straight-line control, perspective, wood grain, cat silhouette, cast shadows, or cross-hatching.
- Estimated practice time and difficulty (`easy` or `easy with simplification`).
- Artist/source credit where it is explicitly available; do not guess attribution.

Recommend **one** featured drawing, selected for the user's requested theme and current skill. Explain the choice in one sentence. Avoid dumping dozens of links without turning them into exercises.

### 5. Teach the featured exercise in 4 layers

Use the source as inspiration for an original practice sketch, not instructions to republish an exact replica. Give concrete, medium-appropriate steps:

1. **Gesture and big shapes (3–5 min):** decide framing; place 2–5 basic masses with very light, sparse pen lines or imagined construction lines.
2. **Outline and proportions (5–8 min):** add the key contour lines and correct proportion through observation; describe 1–2 shapes/angles to check.
3. **Volume and shadow (5–10 min):** choose a single light direction; add sparse, directional cross-hatching only to shadow-side planes and cast-shadow areas. Suggest a usable hatching direction and spacing; leave highlights white.
4. **Signature texture (3–5 min):** add just one chosen material texture (wood planks, bricks, roof tiles, foliage, cat fur clusters) without filling every surface.

Add:

- **What to observe:** 2–3 specific principles (perspective, light direction, edge hierarchy, texture following form, etc.).
- **Common beginner mistake:** one concrete issue and one correction.
- **2-minute self-check:** 3 yes/no checks suitable for the subject.
- **Optional stretch:** one small challenge, such as adding a cast shadow or a second, less-detailed object.

For cross-hatching specifically: use sparse, parallel strokes on shaded planes first; add a second angled layer only for darker regions; avoid making every area equally dark. Adapt instructions when the user uses pencil, tablet, or another medium.

### 6. Follow-ups without repetition

When the user says `another`, change the subject or camera angle and raise only one difficulty variable at a time. When they share a drawing image, evaluate the visible drawing itself: give 2 specific strengths, 1 high-impact improvement, and a small next exercise; do not assume they followed an unseen pin. For a `7-day challenge`, produce a progression (basic shape -> contour -> light/shadow -> one-point perspective -> texture -> combined sketch -> review), using verified Pinterest links when search works.

Do not schedule background searches or send reminders unless the user explicitly requests scheduling and scheduling tools are available.

## Response Format

**Today's drawing:** [clear subject]
**Recommended reference:** [verified Pinterest pin link, or labelled Pinterest search link]
**Time / difficulty / focus:** [time] / [difficulty] / [one key skill]
**Why this one:** [one sentence]

**Other suitable references:** [2–4 distinct candidates with source links, duration, and focus]

**Draw it in four layers:**
1. [big shapes]
2. [contours]
3. [volume and cross-hatching]
4. [texture]

**Notice:** [2–3 targeted observations]
**Avoid:** [one mistake + fix]
**Self-check:** [three short yes/no prompts]
**Optional extension:** [one realistic extra challenge]

If real pin links are inaccessible, lead with the limitation and use explicitly labelled Pinterest search links; the exercise itself should still be useful.

## Pitfalls

- **Pinterest login/dynamic page:** do not claim to have seen inaccessible imagery. Try indexed pin URLs or label search links honestly.
- **Search result description is sparse:** state that visual difficulty is tentative and give an easy simplified study instead of making visual claims.
- **Result is a photo or elaborate artwork:** simplify it into a single outline/shape study; avoid implying the original is a beginner tutorial.
- **Repeated/reposted pins:** deduplicate exact URLs and visually near-identical subjects when enough information is available.
- **Attribution:** link the original result and credit the artist if clearly identified. Do not claim ownership or encourage reposting artwork without permission.
- **Time estimates:** estimate your simplified exercise, not a complete recreation.
- **Unavailable web tools:** give usable Pinterest search links and exercises without fabricating real retrieved pins.

## Verification

Before responding, confirm that (a) any link described as a **verified direct pin** was actually retrieved this run, (b) an inaccessible page was not described as visually inspected, (c) recommended subjects meet the user's time and medium, (d) one exercise includes construction, contour, shadow, and texture layers, and (e) the user has at least one clickable reference link or clearly labelled fallback search link.

