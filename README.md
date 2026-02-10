# Allegro Lab Website

**Please don't be shy and add your accomplishments to the page! If you want to add features to the webpage using Claude Code, that's ok too -- just make sure that the code is dead simple to maintain.**

The entire site is a single `index.html` file. No build step, no dependencies.

## How to edit

Open `index.html` and edit the HTML directly. Each section is marked with comments like `<!-- === NEWS SECTION === -->`.

### Add a news item

Copy a `<tr>` block in the News section. Add new items at the top (most recent first). Only the 7 most recent items are shown on the page; older items are automatically hidden.

```html
<tr>
  <td class="news-date">Feb 2026</td>
  <td>Description of the news item.</td>
</tr>
```

### Add a person

Copy a `person-card` `<div>` into the appropriate group (Faculty, PhD Students, MS Students, etc.):

```html
<div class="person-card" data-areas="llm-science reasoning">
  <img src="img/yourphoto.jpeg" alt="Photo">
  <div class="person-name">Your Name</div>
  <div class="person-role">PhD Student</div>
  <div class="person-links">
    <a href="https://yourwebsite.com">Website</a>
  </div>
  <div class="person-bio">
    Your bio here.
  </div>
  <div class="person-pub">
    <span class="pub-title">Paper Title.</span>
    <span class="pub-venue">Venue Year.</span>
    <a href="https://arxiv.org/abs/...">[paper]</a>
  </div>
</div>
```

- Add your photo to the `img/` folder and reference it in the `src` attribute. If no photo is available, use `img/favicon.png` as a placeholder.
- The `person-bio`, `person-links`, and `person-pub` sections are all optional.
- Use `data-areas` to tag research areas (space-separated). Valid areas: `llm-science`, `law-policy`, `reasoning`, `efficiency`, `evaluation`. These render as clickable tags and power the research area filter.
- For alumni, set the role to show their trajectory, e.g. `Undergraduate &rarr; PhD at UC Berkeley`.

### Add a project link

Copy a `project-link` `<a>` tag in the Projects section:

```html
<a class="project-link" href="https://example.com/project">
  <div class="project-name">Project Name</div>
  <div class="project-desc">Short description.</div>
</a>
```

## Rules

1. **Bios are clamped to 8 lines, publications to 5 lines.** Anything longer is hidden with overflow. Keep them concise.
2. **Check your changes with Claude or another LLM before pushing.** Ask it to proofread for typos and broken HTML.
3. **Undergrads:** Contact your mentor to be added to the site. Do not add yourself directly.
4. **Photos:** Add images to the `img/` folder. Use reasonable file sizes (under 1MB ideally).
5. **Keep it simple.** This site is intentionally one file. Don't add build tools, frameworks, or external CSS.

## Deploying

Push to `master`. GitHub Pages serves it automatically. No build step needed.
