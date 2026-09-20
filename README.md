# SHA0926 — Family in the Qur'an and Sunnah Perspective — Course Slides

A single self-contained static site. Visitors see a module-code gate first;
entering the correct code (`SHA0926`) reveals all 15 weeks of slides, each in
its own royal-styled accordion card.

## Files

```
index.html       — the whole site (gate + all 15 weeks of slides
                   + the 15 revision question papers)
marking/weekNN.html — the 15 marking schemes (week01.html … week15.html).
                   Loaded on demand, ONLY when the week's marking scheme is
                   switched on (see below). They are NOT inside index.html.
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


## Revision question papers and marking schemes (show / hide)

Under the slides of every week there are now two extra cards:

1. **ރިވިޝަން ސުވާލު — ހަފްތާ N ގެ ސުވާލު ޕޭޕަރު** (question paper)
2. **މާކިން ސްކީމް — ހަފްތާ N ގެ މާކިން ކްރައިޓީރިއާ** (marking scheme)

Just like `LAST_VISIBLE_WEEK`, two variables at the bottom of `index.html`
control which weeks show them:

```js
var QUESTIONS_VISIBLE = 5;   // question papers
var MARKING_VISIBLE   = 0;   // marking schemes (hidden by default)
```

Allowed values (same for both):

| Value     | Result                                          |
|-----------|-------------------------------------------------|
| `0`       | hidden for every week                           |
| `5`       | shown for weeks 1 to 5                          |
| `[2, 4]`  | shown only for weeks 2 and 4                    |
| `'ALL'`   | shown for all 15 weeks                          |

A week that is hidden by `LAST_VISIBLE_WEEK` hides its papers and marking
scheme as well.

### Upload

Copy `index.html` (replace the old one) and the whole `marking/` folder into
the repository root, next to the existing `fonts/` folder. Commit.

### Keeping the marking scheme really private

Because the site is a soft gate, the files in `marking/` are still public in
the repository even while `MARKING_VISIBLE = 0`. The scheme is not inside
`index.html`, so students will not see it in the page or the page source, but
anyone who guesses the file address can open it. If the scheme must stay
confidential until release, **upload the `marking/` folder only at the moment
you want to release it** (and then set `MARKING_VISIBLE`).
