# ¿Dónde está mi maleta?

A single-scene Spanish 2010 adventure for approximately novice-high to intermediate-low learners. Fictional Hotel Brisa, Mexico. Designed for 5–10 minutes of exploratory reading, typed replies, hints, and reflection; actual timing depends on the learner. Prepared for a Weber State University classroom; this is not an official university product.

## Published course version

Play: https://gemaster99.github.io/course-modules/span2010/games/

The Spanish 2010 course page includes a Games card. Source files are in `GEMaster99/course-modules`, folder `span2010/games`. To update the existing course deployment, replace only the game files in that folder; leave the course root and module pages in place.

## Play locally

Unzip the package and open `index.html` in a modern browser. Keep all five game files together: index.html, style.css, dialogue.js, matcher.js, app.js. No install, build, API key, student account, or server is required. If clipboard access is unavailable for a local file, the ending includes a text download.

You play Alex Rivera. Inspect your reservation and passport, talk to Lucía, check your belongings, explain the taxi journey, describe the suitcase, request help, collect the bag, request the key, and write a short reflection. All essential scene actions are keyboard-accessible buttons; inventory offers the documents again. Enter sends; Shift+Enter inserts a new line.

## Publish using GitHub Pages

1. Create a public repository on your GitHub account (public repositories support GitHub Pages on GitHub Free).
2. Unzip this package. Upload its **contents**, including `index.html`, to the repository root, then commit. Uploading the ZIP alone will not create a playable site. Avoid replacing unrelated files in an existing repository.
3. Open repository **Settings → Pages**. Under Build and deployment, set **Source: Deploy from a branch**, then select **main** and **/(root)**, and save.
4. Wait for the Pages deployment to complete. Open the URL displayed in Pages settings; it normally has the form `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.
5. Test that link in a private browser window, then share it with students. Students need no GitHub account.

There are no AI calls, metered services, external fonts, tracking scripts, or third-party assets. GitHub's normal hosting terms and limits apply. Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Edit for your class

Open `dialogue.js` with a plain-text/code editor. Each step contains:

- `question` and `reply`: short NPC lines. A reply often introduces the next question; keep both consistent when editing.
- `answers`: complete acceptable phrasings. Add variants students actually use. Keep the first two entries as good selectable models.
- `repairs`: pairs of [comprehensible student phrase, supportive Spanish model]. These progress the story. This includes some Spanglish; code-switching is not inherently rejected.
- `distractors`: pairs of [authored playful choice, kind joke + useful model + repeated question]. These keep the learner on the same step.
- `vocab` and `starter`: the first two hint levels. The third reveals selectable models mixed with authored distractors.

Keep the step IDs/order unless you also change `app.js`, which links them to exploration and inventory events. The hotel illustration is inline SVG in `index.html`; colors and responsive layout are in `style.css`. Document text and reflection behavior are in `app.js`.

### Matching and feedback limitations

This is authored dialogue, not general Spanish understanding. The matcher ignores case, accents, common punctuation, and repeated spaces. Missing accents are accepted without diagnosis. Otherwise it uses whole-phrase banks. It permits one insertion, deletion, or substitution in a single word of at least five letters; it does not drop words or ignore negation. It deliberately does not fuzzy-match short verb/pronoun differences such as dejo/dejé or lo/la. Add pedagogically acceptable variants explicitly to `answers` or `repairs`.

Unknown replies are **not labeled incorrect**. They get clarification and progressively stronger hints. A learner can complete the scene with the authored choices. A comprehensible present-tense location statement can progress and receives a preterite model. Current requests remain in the present. Examples practice `se lo doy`, `llámelo`, and `me la da`. No grades, correctness percentage, or inferred proficiency score are produced.

The reflection is accepted after a minimum of 20 characters, with a model for self-review; the program does not judge its grammar, truth, or number of sentences. Review copied transcripts in your normal teaching workflow if desired. The app does not submit them.

## Privacy and saved progress

Answers stay in browser memory unless the learner opts into “Guardar progreso en este navegador.” That option stores the entire conversation and game state in that browser's local storage. Turning it off removes the saved game. Restart resets the conversation and saved progress (and starts a fresh save if the option remains on). Do not enter actual passport or other personal information. Everything in the scene is fictional. Hosting providers may receive ordinary web access requests, but the game code sends no student responses. No analytics or remote requests are included.

## Verification

94 automated assertions passed against the answer matcher and game flow using a small simulated DOM: all answer banks and repair/distractor entries, conservative typo boundaries, negation, unknown-answer/hint fallback, exploration and pickup gates, complete successful journey, transcript content, optional local save, and restart. Syntax was checked with Node.js. The published game was also played to completion in a browser, including hints, distractors, repairs, transcript copying, saved-progress reload, and restart. Desktop and 390px mobile layouts were inspected. See `VERIFICATION.md` for details.
