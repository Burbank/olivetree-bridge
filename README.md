# Olive Tree Bridge

**Bridge HTTPS links into the Olive Tree Bible Study app on Mac and iOS.**

Many chat interfaces (like Grok Bot, ChatGPT, and others) can open `https://` links but not custom URL schemes like `olivetree://`. This tiny static page acts as a bridge: you click an HTTPS link, and it redirects to open the verse in Olive Tree Bible Study.

🔗 **Live demo:** [Matthew 11:28](https://burbank.github.io/olivetree-bridge/?ref=40.11.28)

---

## How to Use

### In Chat (Markdown)

When chatting with AI assistants or sharing references, use this format:

```markdown
[Matthew 11:28](https://burbank.github.io/olivetree-bridge/?ref=40.11.28)
```

The link will redirect to `olivetree://bible/40.11.28` and open the verse in Olive Tree.

### URL Format

```
https://burbank.github.io/olivetree-bridge/?ref={book}.{chapter}.{verse}
```

- **`book`** — Protestant book number (1–66), see table below
- **`chapter`** — Chapter number
- **`verse`** — Verse number (optional; omit for whole chapter)

**Examples:**
- `?ref=43.3.16` → John 3:16
- `?ref=19.23` → Psalm 23 (whole chapter)
- `?ref=1.1.1` → Genesis 1:1

---

## Book Numbers

Olive Tree uses Protestant book numbering (1–66):

| Range | Testament | Books |
|-------|-----------|-------|
| 1–39  | Old Testament | Genesis (1) through Malachi (39) |
| 40–66 | New Testament | Matthew (40) through Revelation (66) |

### Common References

| Book | Number | Book | Number |
|------|--------|------|--------|
| Genesis | 1 | Matthew | 40 |
| Psalms | 19 | John | 43 |
| Proverbs | 20 | Romans | 45 |
| Isaiah | 23 | 1 Corinthians | 46 |
| Jeremiah | 24 | Ephesians | 49 |
| Daniel | 27 | Philippians | 50 |
| Malachi | 39 | Revelation | 66 |

**Full list:** See [Olive Tree's URL scheme documentation](https://github.com/OliveTreeBible/OliveTreeUrlExample) or count sequentially through a Protestant Bible's table of contents.

---

## Requirements

- **Mac:** Olive Tree Bible Study app installed ([download](https://www.olivetree.com/apps))
- **iOS:** Olive Tree Bible Study app from the [App Store](https://apps.apple.com/us/app/bible-app-read-study-daily/id332615624) (iPhone/iPad)

On first use, your operating system may ask permission to open Olive Tree. The bridge works identically on both Mac and iOS.

---

## Notes

### Obsidian Users

If you're using Obsidian, you can skip this bridge and link directly to `olivetree://bible/{ref}` since Obsidian supports custom URL schemes natively. This bridge is primarily for web-based chat UIs and other apps that only open HTTPS links.

### How It Works

This is a single static HTML page hosted on GitHub Pages. When you visit with a `?ref=` parameter, it:
1. Validates the reference format
2. Redirects to `olivetree://bible/{ref}`
3. Falls back to a manual link + App Store/download link if the app doesn't open automatically

Platform detection (iOS vs Mac) provides appropriate fallback messaging.

---

## Contributing

Improvements welcome! Open an issue or PR at [github.com/Burbank/olivetree-bridge](https://github.com/Burbank/olivetree-bridge).

## License

Public domain / [Unlicense](https://unlicense.org) — use freely.
