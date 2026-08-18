# configs/ — per-class config packages (model 1)

Each `<id>.config.json` here is a class's config package. A student launches
`https://trostparadox.github.io/quizprep/?cfg=<id>` and the app fetches `configs/<id>.config.json`.

**A package is `{ cfg, … }`** where `cfg` carries the display name, course/section, release schedule,
`anonymize` flag, and (optionally) the instructor's RSA **public** key. It also carries the class's
banks, one of:
- `banks: { "<chapter>": <bank>, … }` — one textbook (merges over the stock app), or
- `manifest: [ { id, title, textbook, chapter }, … ] + banks: { "<unit-id>": <bank>, … }` — a
  **multi-textbook** course (chapters from more than one book, rendered as one flat ordered list).

**Built by the Instructor Console** (Config tab → "Export config + bank (Model 1)"). The maintainer
drops the exported file here and pushes; instructors never touch GitHub.

**IP:** packages contain only the (publishable, original) banks + the public key — **never course
source text**, never a private key. Public repo = world-readable; keep it that way.
