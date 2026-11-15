# Personal site

A static site: plain HTML, CSS and JavaScript. No build step, no dependencies.
Open `index.html` in a browser to preview it, or drop the whole folder on any static host
(GitHub Pages, Netlify, Cloudflare Pages…).

Everything you'll want to edit lives in **`content/`**. Anything marked `[placeholder]` is dummy text.

## Where to edit what

| I want to…                                   | Edit                         |
| -------------------------------------------- | ---------------------------- |
| Change name, email, links, intro, CV        | `content/site.js`            |
| Add / edit an article                        | `content/writing.js`         |
| Add / edit a project (and its case study)    | `content/projects.js`        |
| Add / edit a book and my thought on it       | `content/books.js`           |
| Add / edit a swim, pool time or finswim meet | `content/swim.js`            |
| Add / edit my mathematics study log          | `content/mathematics.js`     |

Each file starts with a comment explaining every field. To add something, copy an existing block and change it.
To remove something, delete its block. Empty fields hide themselves.

### Articles (`content/writing.js`)
Write the body in Markdown inside the backticks. The first article is a live demo of everything supported
(headings, quotes, lists, code, images with captions, dividers) — delete it when you're done.
Set `featured: true` to show an article on the homepage, `draft: true` to hide it.

### Projects (`content/projects.js`)
Pick a `layout` per project: `"simulation"` (live pheromone-field visual + interactive demo block),
`"terminal"` (terminal-window treatment) or `"standard"` (cover image + spec sheet).
The case study is a list of `sections` — text, figure, video, gallery, steps, demo, terminal, specs — in any order.
A `steps` item's `src` can be an image or a video (`.mp4`); add `poster` to show a still before it plays.
Git links go in `links: [{ label: "Source", url: "https://github.com/…" }]`.

### Books (`content/books.js`)
Title, author, cover image path and your `thought` (revealed on hover / tap). No cover? A typographic one is drawn.

### Swimming (`content/swim.js`)
The page is built from one object. `headline` is the big number at the top; `numbers` is the training strip;
`openWater` becomes a distance ladder (longest first, bar length follows `km`, colour follows `water`);
`pool` is the benchmark table; `fin` lists finswimming meets and their `events`.
`orgs` maps short codes (SFI, MSAAA…) to full names — hover an abbreviation to see it. Empty fields hide themselves.

### Mathematics (`content/mathematics.js`)
A single long-form study log in Markdown, rendered with the Writing page's reader.
`intro` becomes the standfirst under the title. `##` sections appear in the contents sidebar;
`###` marks groups, programmes and papers; `####` marks books, courses and resources.
Bold labels, lists and paragraphs work as they do in `writing.js`.

## Images and video
Put files in `assets/img/…` (and `assets/video/…`) and reference them by path, e.g. `"assets/img/projects/swarm.png"`.
Missing images show a labelled placeholder instead of breaking the layout.
Suggested folders already exist: `assets/img/writing`, `assets/img/projects`, `assets/img/books`.

## Design notes
- Fonts: Instrument Serif (display), Newsreader (reading), IBM Plex Mono (metadata), loaded from Google Fonts.
- Colours are CSS variables at the top of `assets/css/base.css` (one palette per page).
- Each page has its own stylesheet (`home.css`, `writing.css`, `projects.css`, `reading.css`, `swimming.css`, `mathematics.css`) and script.
- Article and project URLs are `writing.html#slug` and `projects.html#slug`.
- Respects `prefers-reduced-motion`; all interactions work with keyboard.
