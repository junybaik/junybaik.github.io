# Pay Me Right — website

The public website for Pay Me Right, an offline paycheck estimator for hourly
workers.

## Pages

| URL | File | Purpose |
| --- | --- | --- |
| `/` | `index.html` | What the app is, plus links to support and privacy |
| `/support/` | `support/index.html` | How to get help by email |
| `/privacy/` | `privacy/index.html` | The app's privacy policy |

`404.html` handles any other address.

## Rules this site follows

- **No frameworks, build step, or dependencies.** The files in this repository
  are what is served.
- **No JavaScript.**
- **No analytics, cookies, tracking pixels, or third-party requests.** Every
  byte is served from this repository, so the site's own behaviour matches the
  promise the privacy policy makes about the app.
- **No forms.** The support page hands out a `mailto:` address rather than
  posting anything anywhere.
- **No app source code or internal documents.** This site carries only the pages
  above.

Links between pages are relative, so the site works both when served by GitHub
Pages and when opened from a local file server.

## Editing

`styles.css` is the only stylesheet. It defines each colour once as a custom
property and overrides them under `prefers-color-scheme: dark`, so a colour is
never repeated by hand. Type sizes use `clamp()` and layout uses flexible rows,
so pages reflow from narrow phones up to desktop without a media query.

Accessibility rules to preserve when editing:

- One `<h1>` per page, and heading levels that never skip a level.
- The `Skip to content` link is the first focusable element on every page.
- Body and secondary text meet at least a 4.5:1 contrast ratio; link text meets
  3:1 as a large or bold element, and clears 4.5:1 in practice.
- Interactive rows stay at or above 44×44px.
- State is never carried by colour alone.

## Privacy policy

The text on `privacy/index.html` is the app's approved policy, copied without
altering any of its claims. **Do not edit that text here.** If the policy
changes in the app repository, copy the new approved version across so both
match, and update its "Last updated" date.

The one addition on the page is a contact sentence pointing at the support email
and the support page. It adds a way to reach us and makes no claim about data.

## Publishing

Push to `main`. GitHub Pages publishes it at
<https://junybaik.github.io/>; the live build takes a minute or two after a
push.