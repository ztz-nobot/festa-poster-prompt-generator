# 🎪 Festa Poster Prompt Generator

> 基于 CITY FESTA STUDIO 设计系统的毛毡风格节日海报提示词生成器
> 
> 输入变量 → 输出可直接用于 Midjourney / DALL-E / Stable Diffusion 的提示词
> 
> Darwin 评估：**90.3 / 100 · S 级（卓越）**

---

## 效果展示

<img src="https://raw.githubusercontent.com/ztz-nobot/festa-poster-prompt-generator/main/preview.png" width="300" alt="poster preview">

*端午节海报*

---

## 快速安装

### 方式一：一行命令

```bash
mkdir -p ~/.hermes/skills/creative/zdesign && \
curl -o ~/.hermes/skills/creative/zdesign/SKILL.md \
  https://raw.githubusercontent.com/ztz-nobot/festa-poster-prompt-generator/main/SKILL.md
```

### 方式二：手动安装

1. 下载 `SKILL.md` 文件
2. 放到 `~/.hermes/skills/creative/zdesign/` 目录下
3. 重启 Hermes Agent

安装后直接对 Hermes 说：
> "帮我设计一个海报提示词：樱花市集，春天，4月10日"

Hermes 会自动加载 zdesign skill 并生成提示词。

---

## 设计公式：五步法（FIVE MOVES, ONE FEELING）

| # | 设计要素 | 英文 | 提示词关键词 |
|---|---------|------|-------------|
| 01 | 毛毡手作角色 | Needle-felt 3D mascots | `needle-felt, fluffy, textile, tactile, bean eyes, rosy cheeks` |
| 02 | 大圆体白标题 | Chunky white display type | `ultra-bold chunky rounded white bubble letters, filling frame` |
| 03 | 蓝天实景街景 | Real bright-sky backdrop | `bright sunny photorealistic [city/harbor/park], blue sky` |
| 04 | 一季一主色 | One seasonal accent color | 见下方「四季预设」 |
| 05 | 信息块+图标行 | Info block + icon row | `white rounded info card, date+location, circular icon row` |

**核心方法论：** 可爱，是这套的方法论（Cute is the method）

---

## 输入变量

| 变量 | 必填 | 示例 |
|------|------|------|
| `EVENT_NAME` | ✅ | 樱花市集、Dragon Boat Festival、Harbor Light Fest |
| `SEASON` | ✅ | spring / summer / autumn / winter |
| `DATE` | ❌ | 5.10(Fri) - 5.19(Sun)、6月19日 |
| `LOCATION` | ❌ | 中央广场、Central Market Street |
| `THEME_COLOR` | ❌ | 不填则自动匹配 |
| `MASCOTS` | ❌ | 不填则自动匹配 |
| `CITY_BACKDROP` | ❌ | 不填则自动匹配 |
| `ICON_SET` | ❌ | 不填则自动匹配 |
| `TAGLINE` | ❌ | 不填则自动匹配 |
| `ASPECT_RATIO` | ❌ | 9:16（默认竖版）或 16:9 |

不需要填满所有变量，最少只需要 **活动名 + 季节 + 日期** 三个。

---

## 四季预设

| 季节 | 主色 | 吉祥物 | 场景 | 标语 |
|------|------|--------|------|------|
| 🌸 春 | 樱粉 `#FF6B9D` | 绿树 + 粉鸟 | 樱花街道 | "Spring is here!" |
| 🌊 夏 | 港蓝 `#4ECDC4` | 蓝云 + 橙狗 | 海港码头 | "Fun by the sea!" |
| 🍂 秋 | 叶绿 `#6BCB77` | 树 + 小狗 | 城市公园 | "Read & relax!" |
| ❄️ 冬 | 可可红 `#C0392B` | 热可可杯 + 橙狗 | 雪街市集 | "Warm & cozy!" |

---

## 支持平台

| 平台 | 提示词格式 | 字数限制 | 附加参数 |
|------|-----------|---------|---------|
| **Midjourney** | 自然语言描述 | ≤350 词 | `--ar 9:16 --style raw --v 7` |
| **DALL-E 3** | 自然语言描述 | ≤400 词 | 无需附加 |
| **Stable Diffusion** | tag 格式 | ≤150 tags | 需添加 Negative prompt |
| **Flux** | 自然语言描述 | ≤300 词 | 无需附加 |

---

## 使用示例

### 输入

> 帮我设计一个海报提示词：端午节，夏天，日期6月19日

### 输出（Midjourney 版本）

```
A vertical festival event poster in a cute needle-felt mascot style.

LAYOUT: Mobile phone poster format (9:16 ratio). Bright, cheerful atmosphere.

TOP SECTION:
- Header bar: "🐉 DRAGON BOAT FESTIVAL 2026" in white text on a thin dark semi-transparent banner
- Main title: "DRAGON BOAT FESTIVAL" in ultra-bold, chunky, rounded white bubble letters, filling the frame width, with small zongzi and dragon boat icons scattered on the letters
- A curved green ribbon banner below the title with the tagline: "端午安康，粽情一夏！"

CENTER:
- A bright, sunny, photorealistic Chinese riverside park with willow trees, traditional stone bridge, and blue sky with fluffy white clouds
- Two fluffy needle-felt 3D mascots standing in the foreground:
  - A cone-shaped zongzi rice dumpling mascot wrapped in green bamboo leaves, round black bean eyes, tiny warm smile, rosy cheeks, wearing a red ribbon bow
  - A chubby baby dragon mascot in emerald green with golden belly, small wings, tiny horns, holding a miniature wooden paddle
- Green and gold traditional banners and paper dragon boat decorations in the background

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
- Bright, saturated, cheerful color palette, warm 6500K daylight
- Clean modern typography mixed with cute mascot characters
- Professional event poster layout, not childish
- High detail, 4K quality, sharp focus

--ar 9:16 --style raw --v 7
```

---

## 中文文字处理

⚠️ AI 图像生成器对中文文字的渲染**经常乱码**，推荐方案：

1. 用 **Mascot-Only 模式** 生成纯背景图（无文字）
2. 用 **Photoshop / Figma / Canva** 叠加中文文字
3. 或用 Hermes 生成 **HTML 海报**，文字完美渲染

---

## 参数速查

| 参数 | 值 | 说明 |
|------|------|------|
| 吉祥物高度 | 画面高度的 40-60% | 前景，略大于背景 |
| 标题字号 | 画面宽度的 15-20% | 需填满水平空间 |
| 信息卡片圆角 | 16-20px | 内边距 16-24px |
| 图标行 | 4-5 个图标 | 直径 36-44px，间距 12-16px |
| 吉祥物眼睛 | 8-12px | 圆豆形状，黑色 |
| 腮红 | 10-14px，40% 透明度粉色 | 眼睛下方两侧 |
| 色温 | 暖色 6000-7000K | 明亮日光感 |

---

## Darwin 评估报告

| 维度 | 得分 | 权重 |
|------|------|------|
| Frontmatter Quality | 10/10 | 7 |
| Workflow Clarity | 8.3/10 | 12 |
| Failure Mode Encoding | 10/10 | 12 |
| Checkpoint Design | 10/10 | 6 |
| Actionable Specificity | 8.8/10 | 17 |
| Resource Integration | 10/10 | 4 |
| Overall Architecture | 10/10 | 12 |
| Test Performance | 8/10 | 23 |
| Anti-pattern Blacklist | 10/10 | 6 |
| **总分** | **90.3/100** | **S 级** |

---

## 许可证

MIT License

基于 [CITY FESTA STUDIO](https://x.com/VigoCreativeAI) 教程系列设计系统。

---

Made with 🎨 by [Hermes Agent](https://hermes-agent.nousresearch.com)
