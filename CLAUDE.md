# Lucent Landing — Development Guidelines

## Languages (REQUIRED)

The website is available in **Dutch** (default) and **English**.

Every future change to text, headings, buttons, or content on any of the following pages **MUST** be applied in both languages:

- `index.html`
- `privacy/index.html`
- `terms/index.html`

### How the i18n system works

Each page uses a `data-i18n` / `data-i18n-html` attribute system with a JavaScript `TRANSLATIONS` object at the bottom of the `<script>` block.

- **Text-only elements** use `data-i18n="key"` — the JS replaces `textContent`.
- **Elements with inner HTML** use `data-i18n-html="key"` — the JS replaces `innerHTML`.
- The `privacy/index.html` and `terms/index.html` pages store the full body HTML for each language in the `TRANSLATIONS.nl.content_body` and `TRANSLATIONS.en.content_body` keys.

### When editing text

1. Update the Dutch text in the HTML element itself (it is the fallback / default).
2. Update the corresponding English translation in `TRANSLATIONS.en` inside the `<script>` block of the same page.
3. If you add a new element, give it a `data-i18n="new_key"` attribute, add the Dutch value to `TRANSLATIONS.nl` and the English value to `TRANSLATIONS.en`.

**Never skip a translation. Both languages must always be in sync.**

### Language switcher

The 🇳🇱 / 🇬🇧 flag buttons are in every page's `<nav>`. Language preference is saved to `localStorage` under the key `lucent_lang` and is shared across all pages.
