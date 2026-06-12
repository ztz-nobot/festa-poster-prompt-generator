---
name: zdesign
description: "Generate optimized AI image prompts for felt-style festival posters — input variables, get a ready-to-use prompt for Midjourney/DALL-E/SD. Based on CITY FESTA STUDIO design system."
version: 2.0.0
author: Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [design, poster, prompt-engineering, felt, mascot, festival]
    related_skills: []
---

# ZDesign — Felt Festa Poster Prompt Generator

Use this skill when the user wants to create a festival/event poster in the **fluffy felt mascot style** and needs a **high-quality AI image generation prompt**. This skill outputs a structured, detailed prompt — it does NOT generate the image itself.

Source: "CITY FESTA STUDIO" tutorial series by @VigoCreativeAI.

## When To Use

- User needs a prompt for festival/market/event poster generation
- User wants the "cute needle-felt mascot + real city" aesthetic
- User asks for Midjourney / DALL-E / Stable Diffusion poster prompts
- User says "帮我生成海报提示词" or "设计一个海报prompt"

## When NOT To Use

- User wants the agent to directly generate or render an image
- User wants an HTML/CSS poster (use `claude-design` instead)

## The Design Formula: FIVE MOVES, ONE FEELING

| # | Move (CN) | Move (EN) | Prompt Keyword |
|---|-----------|-----------|----------------|
| 01 | 毛毡手作角色 | Needle-felt 3D mascots | `needle-felt, fluffy, textile, tactile, bean eyes, rosy cheeks` |
| 02 | 大圆体白标题 | Chunky white display type | `ultra-bold chunky rounded white bubble letters, filling frame` |
| 03 | 蓝天实景街景 | Real bright-sky backdrop | `bright sunny photorealistic [city/harbor/park], blue sky` |
| 04 | 一季一主色 | One seasonal accent color | See Season Palettes below |
| 05 | 信息块+图标行 | Info block + icon row | `white rounded info card, date+location, circular icon row` |

Core method: "Cute is the method" (可爱，是这套的方法论)

## Concrete Parameters

| Parameter | Value | Notes |
|-----------|-------|-------|
| Mascot height | 40-60% of frame height | Foreground, slightly oversized |
| Title font size | 15-20% of frame width | Must fill the horizontal span |
| Info card padding | 16-24px | Rounded corners 16-20px |
| Icon row | 4-5 icons | Diameter 36-44px each, gap 12-16px |
| CTA button | 12-16px radius, full width | Padding 12-16px vertical |
| Header bar height | 28-36px | Semi-transparent dark background |
| Tagline ribbon | 8-12px padding, 20-24px radius | Accent color, high contrast text |
| Color temperature | Warm (6000-7000K) | Bright daylight feel, never cold |
| Mascot eye size | 8-12px diameter | Bean-shaped black dots |
| Mascot cheek blush | 10-14px, 40% opacity pink | Below eyes, on both sides |
| Background blur | 0% (sharp) | Background must be photorealistic, not blurred |
| Prompt word count | MJ: ≤350, DALL-E: ≤400, SD: ≤150+tags, Flux: ≤300 | Per platform limits |

## Input Variables

| Variable | Required | Example |
|----------|----------|---------|
| `EVENT_NAME` | ✅ | Cherry Market Day, 樱花市集, Dragon Boat Festival |
| `SEASON` | ✅ | spring / summer / autumn / winter |
| `DATE` | ❌ | 5.10(Fri) - 5.19(Sun), 6月19日 |
| `LOCATION` | ❌ | Central Market Street, 中央广场 |
| `THEME_COLOR` | ❌ | Auto from season if omitted |
| `MASCOTS` | ❌ | Auto from season if omitted |
| `CITY_BACKDROP` | ❌ | Auto from season if omitted |
| `ICON_SET` | ❌ | Auto from season if omitted |
| `TAGLINE` | ❌ | Auto from season if omitted |
| `ASPECT_RATIO` | ❌ | 9:16 (default) or 16:9 |

## Season Palettes & Presets

### 🌸 Spring — Cherry Pink
- Color: `#FF6B9D` / `#FFB7D5`
- Sky: bright sunny blue
- Mascots: green tree mascot + pink bird/cherry mascot
- Backdrop: Japanese-style street with cherry blossom trees
- Icons: SHOP, PHOTO, LIVE, ENJOY
- Tagline: "Spring is here!"
- Decorations: cherry blossom petals, pink banners

### 🌊 Summer — Harbor Blue
- Color: `#4ECDC4` / `#45B7D1`
- Sky: bright blue with fluffy clouds
- Mascots: blue cloud mascot + orange dog mascot
- Backdrop: harbor terminal with ships, sunny waterfront
- Icons: HARBOR, NIGHT, LIVE, PHOTO
- Tagline: "Fun by the sea!"
- Decorations: nautical flags, harbor banners

### 🍂 Autumn — Leaf Green
- Color: `#6BCB77` / `#A8D8B9`
- Sky: warm golden afternoon light
- Mascots: green tree mascot (autumn leaves) + puppy with book
- Backdrop: city park with golden trees, reading nook
- Icons: BOOK, STORY, MUSIC, PICNIC
- Tagline: "Read & relax!"
- Decorations: falling leaves, warm string lights

### ❄️ Winter — Cocoa Red
- Color: `#C0392B` / `#E74C3C`
- Sky: overcast with snow
- Mascots: hot cocoa mug mascot + orange dog with scarf
- Backdrop: European-style winter market with snow
- Icons: GIFTS, SNOW, HOT, ENJOY
- Tagline: "Warm & cozy!"
- Decorations: snowflakes, warm lights, red ribbons

## Prompt Templates

### Portrait (9:16)

```
A vertical festival event poster in a cute needle-felt mascot style.

LAYOUT: Mobile phone poster format (9:16 ratio). Bright, cheerful atmosphere.

TOP SECTION:
- Header bar: "{HEADER_TEXT}" in white text on a thin dark semi-transparent banner
- Main title: "{EVENT_NAME}" in ultra-bold, chunky, rounded white bubble letters, filling the frame width, with small {SEASON_DECORATION} icons scattered on the letters
- A curved {THEME_COLOR} ribbon banner below the title with the tagline: "{TAGLINE}"

CENTER:
- A bright, sunny, photorealistic {CITY_BACKDROP} background with clear blue sky
- Two fluffy needle-felt 3D mascots standing in the foreground:
  - {MASCOT_1_DESCRIPTION}
  - {MASCOT_2_DESCRIPTION}
- The mascots are slightly oversized compared to the background, creating a charming scale contrast
- {THEME_COLOR} event banners and decorations visible in the background

BOTTOM SECTION:
- White rounded info card at the bottom with slight glass blur
- Calendar icon + "{DATE}" in bold text
- Location pin icon + "{LOCATION}" in regular text
- Row of 4-5 circular pastel icons representing: {ICON_SET}
- A {THEME_COLOR} rounded button: "{CTA_TEXT}"

STYLE:
- Needle-felt textile aesthetic, soft fuzzy textures
- Bean-shaped dot eyes on mascots, simple warm smiles, rosy cheeks
- {THEME_COLOR} as dominant seasonal accent color
- Bright, saturated, cheerful color palette
- Clean modern typography mixed with cute mascot characters
- Professional event poster layout, not childish
- High detail, 4K quality, sharp focus
```

### Landscape (16:9)

Same structure, replace first line with:
```
A landscape festival event poster in a cute needle-felt mascot style.

LAYOUT: Widescreen horizontal format (16:9 ratio). Bright, cheerful atmosphere.
```

And adjust: mascots centered horizontally, info block at bottom spanning full width, more background visible on sides.

### Mascot-Only (no text, for HTML overlay)

```
A photorealistic scene of two adorable oversized needle-felt 3D mascots on a bright sunny {CITY_BACKDROP}.

Mascot 1: {MASCOT_1_DESCRIPTION}
Mascot 2: {MASCOT_2_DESCRIPTION}

The mascots are slightly oversized compared to the surroundings, creating charming scale contrast. {THEME_COLOR} decorations and banners visible. Blue sky, bright daylight, cheerful atmosphere.

STYLE: Needle-felt textile aesthetic, soft fuzzy textures, bean-shaped dot eyes, simple warm smiles, rosy cheeks. High detail, 4K quality, sharp focus. No text, no typography, no words.
```

## Workflow

1. **Parse input** — Extract variables from user's request. Fill missing values from season preset. Do NOT over-ask.
2. **🔴 CHECKPOINT** — Present parsed variables to user as a table. Confirm before proceeding. If user says "直接生成", skip confirmation.
3. **Select template** — Portrait (9:16) by default, or landscape (16:9) if specified.
4. **Construct prompt** — Fill all placeholders. Add platform-specific suffixes if needed.
5. **🔴 CHECKPOINT** — Output the completed prompt. Ask user if they want to adjust variables or switch platform.

### Platform Suffixes (append if user specifies a platform)

| Platform | Suffix | Word Limit | Notes |
|----------|--------|------------|-------|
| Midjourney | `--ar 9:16 --style raw --v 7` | ~350 words max | Longer prompts work but diminishing returns after 60 tokens |
| DALL-E 3 | (none needed) | ~400 words max | Auto-expands; no negative prompt support |
| Stable Diffusion | Add negative prompt below | ~150 words + tags | Use tag-based style, not prose |
| Flux | (none needed) | ~300 words max | Handles natural language well |

**Negative prompt for SD/Flux (append separately):**
```
Negative: blurry, low quality, dark, distorted, ugly, deformed, text artifacts, watermark, logo, extra limbs, bad anatomy
```

**Output size reference:**

| Ratio | Standard | Hi-Res |
|-------|----------|--------|
| 9:16 portrait | 1024×1536 | 2160×3840 |
| 16:9 landscape | 1536×1024 | 3840×2160 |
| 1:1 square | 1024×1024 | 2048×2048 |

## Example

**Input:** "端午节海报，夏天，6月19日"

**Output prompt (9:16):**

```
A vertical festival event poster in a cute needle-felt mascot style.

LAYOUT: Mobile phone poster format (9:16 ratio). Bright, cheerful atmosphere.

TOP SECTION:
- Header bar: "🐉 DRAGON BOAT FESTIVAL 2026" in white text on a thin dark semi-transparent banner
- Main title: "DRAGON BOAT FESTIVAL" in ultra-bold, chunky, rounded white bubble letters, filling the frame width, with small dragon boat and zongzi icons scattered on the letters
- A curved green ribbon banner below the title with the tagline: "端午安康，粽情一夏！"

CENTER:
- A bright, sunny, photorealistic Chinese riverside park with willow trees, traditional stone bridge, and blue sky with fluffy white clouds
- Two fluffy needle-felt 3D mascots standing in the foreground:
  - A cone-shaped zongzi (rice dumpling) mascot wrapped in green bamboo leaves, round black bean eyes, tiny warm smile, rosy cheeks, red ribbon bow
  - A chubby baby dragon mascot in emerald green with golden belly, small wings, tiny horns, holding a miniature wooden paddle
- Green and gold banners and paper dragon boat decorations in the background

BOTTOM SECTION:
- White rounded info card at the bottom with slight glass blur
- Calendar icon + "6月19日 · 端午节" in bold text
- Location pin icon + "各地龙舟赛场" in regular text
- Row of 4 circular pastel icons: dragon boat racing, making zongzi, hanging mugwort, festival greeting
- A green rounded button: "了解更多 →"

STYLE:
- Needle-felt textile aesthetic, soft fuzzy textures
- Bean-shaped dot eyes on mascots, simple warm smiles, rosy cheeks
- Green and gold as dominant seasonal accent colors with red accents
- Bright, saturated, cheerful color palette
- Clean modern typography mixed with cute mascot characters
- Professional event poster layout, not childish
- High detail, 4K quality, sharp focus

--ar 9:16 --style raw --v 7
```

## Pitfalls

- CJK text in AI images is often garbled — for Chinese/Japanese/Korean text, prefer the mascot-only prompt and overlay text in HTML or design tool.
- Always include `needle-felt, fluffy, textile, tactile` — these are the key differentiators.
- Mascots must be slightly oversized in the foreground for the signature charm.
- Background must be REAL and BRIGHT — sunny blue sky, never dark or illustrated.
- White bold text must be explicitly described in the prompt.
- Prompt length matters: Midjourney handles ~350 words well; DALL-E 3 up to ~400; SD/Flux prefer <200 words with tags.
