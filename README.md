# 9708 Economics — Knowledge Self-Check

A single-file, offline-capable study site for Cambridge International AS & A Level Economics (9708).
Everything (questions, styles, logic) lives in `index.html`; there is no build step and no server.

## What the site does

- **MCQ practice** — 30-question sets, per-chapter filters, keyboard answering (A–D, Enter).
- **Flashcards** — spaced-repetition boxes, only-due mode.
- **Short answers** — typed responses with a self-check against model points.
- **Progress** — attempts, accuracy, mastery per syllabus chapter.
- **Question bank** — import questions from JSON, PDF or pasted text; edit, delete, re-file chapters; export the whole bank as JSON.
- **Accounts** — optional Supabase sign-in for cross-device progress; guests can practise without saving.

## Deploying on GitHub Pages

1. Create a public repository, e.g. `economics-9708`.
2. Upload `index.html` (and this README) to the repository root, on the `main` branch.
3. Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`, Save.
4. The site appears at `https://<your-user>.github.io/economics-9708/` within a minute or two.

Updating the site: replace `index.html` with the new version and commit; Pages rebuilds automatically.

## Admin rights on this public copy

This copy is deliberately read-only. The passphrase gate is removed and any locally forged admin flag is
ignored, so a visitor cannot unlock editing even by reading the source or editing localStorage.

Editing is reserved for the owner and happens one of two ways:

1. **Owner account through Supabase** — create a project, run `supabase-schema.sql`, sign up once (the first
   account is made admin by the schema), then sign in here. Only that account passes the database's
   row-level security, so it is the only account that can write.
2. **A private local build** — keep a separate copy with admin mode enabled offline; edit the bank there and
   ship the updated `index.html` to this repository.

Do not upload the private admin build to this repository: it contains the passphrase.

## Updating the question bank

- Click the account button, enter the admin passphrase to unlock admin mode **on that device only**.
- Question bank → Import → choose JSON files → *Replace bank* (fresh start) or *Append* (merge).
- Export JSON gives you a backup of everything currently loaded.

The bank is stored in the browser's localStorage, so each device has its own copy. Importing does not
publish anything; nothing you import is uploaded anywhere.

## Notes

- No past-paper content is included in this repository. Question sets you add locally stay local.
- The admin passphrase is inside `index.html`. It only unlocks local editing; if you connect Supabase,
  real permissions are enforced by the database (row-level security), not by the passphrase.
- Optional backend: run `supabase-schema.sql` in a Supabase project and paste the project URL plus the
  anon key in the app's backend dialog.
- Typefaces load from a CDN; if that host is unreachable the page falls back to system serif/sans stacks.

