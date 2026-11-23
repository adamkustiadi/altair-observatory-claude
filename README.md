# Altair Observatory

A calm, responsive portal to AI learning resources, videos, and articles, by **AI Creator Labs**.
Built as a single static file, with English as the default language and an EN | ID toggle.

## Pages

| Page | Name | What it holds |
|------|------|---------------|
| Home | Altair Observatory | Intro, search across all content, quick topic chips |
| Resources | Altair Archive | 20 AI skills in 6 categories, "What is a skill?", changelog, install guide |
| Knowledges | Altair Telescope | 6 learning videos, played inside the portal, with search and sorting |
| Articles | Altair Journal | 12 articles grouped by tag (4 main tags, 14 small tags) |

## Features

- Responsive layout (desktop, tablet, phone) with no horizontal scroll
- EN | ID language toggle, remembered in the browser
- Dark, Light, and System themes, remembered in the browser
- Collapsible left sidebar (icon mode) on Resources, Knowledges, and Articles
- Search on Home across skills, videos, and articles
- Video player panel opens inside the portal (YouTube embed)
- Shareable links, for example `#/resources/skill-builder`, `#/knowledges/podcast-6`, `#/articles/what-is-a-skill`

## Project structure

```
.
├── index.html   # the whole site: HTML, CSS, JavaScript, and content
└── README.md
```

No build step and no dependencies. Fonts come from Google Fonts and videos from YouTube, so an internet connection is needed for those.

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
- **Videos:** `DATA.videos` (slug, YouTube id, episode, topic, duration, views, date, title). Optional `img` sets a local thumbnail, such as `images/podcast-6.jpg`.
- **Articles:** `DATA.articles` (slug, tag, small tags, date, reading time, English and Indonesian title, excerpt, and body). Optional `video`, `skills`, and `cta` link related content.

Indonesian text for interface labels is in the `ID` dictionary. Each `data-i` key in the HTML must be unique.

## Checklist before publishing

- [ ] Open the live Vercel URL on a real phone and a desktop
- [ ] Confirm YouTube thumbnails and video playback work
- [ ] Confirm Google Fonts load
- [ ] Check all links in EN and ID
- [ ] Confirm the sample quote attribution and the WhatsApp number in the footer with AI Creator Labs
- [ ] Re-read the articles against the source videos

## Notes

- No third-party logos or brand assets are used. The visual identity is original.
- Articles do not promise income or results.
- Class links point to the AI Creator Labs website and Instagram.

## Credits

Content and brand: AI Creator Labs. Portal design and build: Adam, with Claude.
