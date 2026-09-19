# SHA0926 — Family in the Qur'an and Sunnah Perspective — Course Slides

A single self-contained static site. Visitors see a module-code gate first;
entering the correct code (`SHA0926`) reveals all 15 weeks of slides, each in
its own royal-styled accordion card.

## Files

```
index.html       — the whole site (gate + all 15 weeks of slides)
fonts/Faruma.ttf — the Dhivehi Faruma font, embedded via @font-face so it
                   renders correctly on every device, even ones without the
                   font installed
```

## Deploying to GitHub Pages

1. Create a new repository on GitHub (e.g. `sha0926-slides`).
2. Upload both `index.html` and the `fonts/` folder (with `Faruma.ttf` inside
   it) to the repository, keeping the same folder structure.
3. In the repository, go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**, pick the `main` branch
   and the `/ (root)` folder, then **Save**.
5. After a minute or two, GitHub will give you a live link, usually:
   `https://<your-username>.github.io/<repo-name>/`
6. Open that link — you should see the module-code gate. Enter `SHA0926` to
   see the slides.

## Changing the module code

Open `index.html`, search for:

```js
var CORRECT_CODE = 'SHA0926';
```

and change the text between quotes to whatever code you want.

## Important note on the gate

This is a **soft gate** only — convenient for keeping the slides tidy behind
a simple step, not real security. Since everything runs in the visitor's own
browser, anyone who views the page source can find the code, or could open
the browser console and reveal the hidden content directly. Do not rely on
this to protect sensitive information.

## Fixing a typo or updating a slide

Since everything lives in one `index.html` file, search for the exact
Dhivehi/Arabic text you want to change and edit it directly, then re-upload
the file to GitHub (or edit it directly in GitHub's web editor).
