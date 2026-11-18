# Zydel Kenzoi — Christening Invitation

A single-page, static invitation that displays the invitation card artwork full width. All the details — 19 December, 8:00 AM, Saint Agustine Parish Church, reception at Leal's Residence — are on the card itself.

```
index.html                     the page
style.css                      colours and layout
404.html                       sends /index.html/Name links back to the invitation
assets/christening-card.webp   the invitation artwork (also the social preview image)
```

No build step, no dependencies beyond the Google Fonts link.

## Adding a name

**Type it.** Open the page with no name in the link and a **Guest name** box appears above the card. Type the guest's name — it shows as *Rodel Lobendino / You are invited* and the address bar updates to `index.html#Rodel%20Lobendino`. Copy that link and send it; anyone opening it sees the same greeting without the input box.

**Or put it in the link yourself:**

```
.../index.html#Rodel%20Lobendino        works locally and on GitHub Pages
.../index.html?name=Rodel%20Lobendino   same thing
.../index.html/Rodel%20Lobendino        GitHub Pages only (handled by 404.html)
```

`%20` is the encoded space, so a link can contain a space. A name in the link hides the input box, so guests only see the greeting. Without a name the page shows the box and looks otherwise exactly as before.

The `index.html/Name` form cannot work when you open the file directly from disk (`file:///...`), because the browser treats the name as a file path that does not exist. Use the `#` form for local testing.

## Editing

- **Artwork:** replace `assets/christening-card.webp` with a file of the same name. If your new image has different dimensions, update the `width` and `height` attributes on the `<img>` in `index.html`.
- **Signature line:** "With love, the Leal family" is the only text on the page — edit it in the `<footer>` of `index.html`.
- **Colours:** CSS variables at the top of `style.css` (`--blue-ink`, `--blue`, `--cream`, `--brown`, `--gold`).

## Deploy on GitHub Pages

1. Create a new repository on GitHub, e.g. `christening`.
2. Upload `index.html`, `style.css`, `404.html`, `README.md` and the `assets` folder (or from a terminal: `git init`, `git add .`, `git commit -m "invitation"`, then `git push`).
3. In the repo go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`, then **Save**.
5. Wait about a minute. The invitation is live at:

   `https://<your-username>.github.io/christening/`
