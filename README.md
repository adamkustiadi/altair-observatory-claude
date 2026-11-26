# Altair Observatory

A calm, responsive portal to AI learning resources, videos, and articles, by **AI Creator Labs**.
Built as a single static file, with English as the default language and an EN | ID toggle.

## Pages

| Page | Name | What it holds |
|------|------|---------------|
| Home | Altair Observatory | Intro, search across all content, quick topic chips |
| Resources | Altair Archive | 20 AI skills in 6 categories, "What is a skill?", changelog, install guide |
| Knowledges | Altair Telescope | 6 learning videos in 4 topics (Start Here, Understand AI, Risks & Reality, Careers) with search and sorting, each with its own detail page |
| Articles | Altair Journal | 12 articles grouped by tag (4 main tags, 14 small tags) |

## Features

- Responsive layout (desktop, tablet, phone) with no horizontal scroll
- EN | ID language toggle, remembered in the browser
- Dark, Light, and System themes, remembered in the browser
- Collapsible left sidebar (icon mode) on Resources, Knowledges, and Articles
- Search on Home across skills, videos, and articles
- Clear main navigation: RESOURCES, KNOWLEDGES, and ARTICLES in bold small capitals, brighter text, gold on hover and for the active tab (thin underline), on Home and on every inner page, on desktop and phone
- Consistent page layout on Resources, Knowledges, and Articles: a compact layered header panel, then a sticky search bar outside the panel with a transparent, frosted-glass look
- Short video titles on cards (maximum two lines); the video page keeps the full original title in an "Original title" line
- Typography: Manrope for card and list titles, a serif only for the logo and large hero headlines
- Animated star logo (inline SVG, with a soft glow and a gentle sparkle that respects reduced-motion settings) beside the site name in the navigation bar, matching the favicon
- Each video has its own page with the player, About, What You'll Learn, Key Takeaways, Common Questions, and Related Knowledge, including class cards (YouTube embed)
- Shareable links, for example `#/resources/skill-builder`, `#/knowledges/podcast-6`, `#/articles/what-is-a-skill`

## Project structure

```
.
├── index.html   # the whole site: HTML, CSS, JavaScript, and content
└── README.md
```

No build step and no dependencies. Fonts (Inter, Manrope, and the serif) come from Google Fonts and videos from YouTube, so an internet connection is needed for those.

## Run locally

Open `index.html` in a browser. For a closer match to production, serve it over HTTP:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

1. Create a GitHub repository and upload `index.html` and `README.md` to the root.
2. In Vercel, choose **Add New → Project** and import the repository.
3. Leave the framework preset as **Other**, with no build command and no output directory.
4. Deploy. Vercel serves `index.html` automatically over HTTPS, which the video embeds need.

## Editing content

All content lives in the `DATA` object inside `index.html`.

- **Skills:** `DATA.resources` (id, category, level, English and Indonesian title and description)
- **Videos:** `DATA.videos` (slug, YouTube id, episode, topic, duration, views, date, title). The short card titles are in `VSH` (English and Indonesian). Optional `img` sets a local thumbnail, such as `images/podcast-6.jpg`.
- **Video detail pages:** `VD` (keyed by video slug: about, learn, takeaways, FAQ, related videos, articles, skills, and the class cards). `cls` is one class key or a list of keys; the classes themselves (general, income workshop, agent builder, creator incubator) are defined in `CLS`. Everything is in English and Indonesian.
- **Articles:** `DATA.articles` (slug, tag, small tags, date, reading time, English and Indonesian title, excerpt, and body). Optional `video`, `skills`, and `cta` link related content.

Indonesian text for interface labels is in the `ID` dictionary. Each `data-i` key in the HTML must be unique.

## Notes

- No third-party logos or brand assets are used. The visual identity is original.
- Articles do not promise income or results.
- Class cards (including AI Creator Incubator on video #1) are written from the class descriptions and should be reviewed with AI Creator Labs.
- Class links point to the AI Creator Labs website and Instagram.

## Submission notes

- Live site: https://altair-observatory-claude.vercel.app/
- Attach `index.html` (and `README.md`) as the file; include the GitHub link in the notes.
- Fonts (Cormorant Garamond, Inter, Manrope) are open-licensed (OFL). Video thumbnails come from AI Creator Labs' own YouTube channel.

## Brand document

`Altair Observatory Brand Design.pdf` explains the name, tagline, brand personality, colors, typography, logo, and creator's note (in Indonesian).

## Credits

Content and brand: AI Creator Labs. Portal design and build: Adam, with Claude.
