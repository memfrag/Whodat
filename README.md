# Whodat

Tag a meeting transcript with who said what — down to the individual sentence — then export it
as a self-contained HTML page or tagged markdown.

**→ [memfrag.github.io/Whodat](https://memfrag.github.io/Whodat/)**

Everything runs in the browser. No server, no upload, no build step: the whole app is one
`index.html`.

## What it does

You start with two things: a list of attendees and a plain text transcript. Whodat splits the
transcript into paragraphs and sentences, and then you attribute them.

- **Sentence-level tagging.** Click a sentence, shift-click for a range, ⌘-click to add or drop
  one, or grab a whole paragraph with `A`. Press `1`–`9` to attribute the selection.
- **Untagged text stays dimmed** and snaps to full contrast once attributed, so the remaining
  work is always visible at a glance. `Tab` jumps to the next unattributed sentence.
- **Fix the text while you tag.** Edit any sentence in place, split one at the cursor, join
  several into one, break a paragraph in two, or delete text outright. Everything is undoable
  with `⌘Z`.
- **Smart-ish parsing.** Speaker prefixes are matched against the attendee list and pre-assigned,
  leading timestamps are pulled into the margin, and WebVTT/SRT scaffolding is stripped. The
  sentence splitter knows about `Dr.`, `e.g.`, initials and decimals.
- **Already-tagged files come back tagged.** A line starting with `Martin:`, `**Martin:**`,
  `**Martin**:`, `*Martin:*` or `**Martin (00:04:12):**` arrives pre-attributed — and stays fully
  editable, so you can re-tag, edit or delete any of it. Because that is the exact shape of
  Whodat's own markdown export, **an exported `.md` imports straight back**: title, date,
  attendees, timestamps and every attribution survive the trip, and re-exporting produces a
  byte-identical file.
- **Nothing is lost.** Work is autosaved to the browser, and `Save .json` produces a project file
  you can reopen later or move to another machine.

## Exports

| Export | What you get |
| --- | --- |
| `.html` | A standalone page — speaker filter chips, live search, print styles, light/dark. One file, no external requests. |
| `.md` | `**Speaker (timestamp):** text` blocks, one per contiguous run of speech. |
| `.json` | The editable project, to reopen in Whodat. |

## Keyboard

| | |
| --- | --- |
| `1`–`9` / `0` | Attribute to speaker / clear attribution |
| `A` | Select the whole paragraph |
| `E` | Edit the selected sentence (`⌘↩` save, `esc` cancel) |
| `J` / `S` | Join selected sentences / break the paragraph here |
| `⌫` | Delete the selection |
| `Tab` | Next unattributed sentence |
| `↑` `↓` | Move the selection (`⇧` to extend) |
| `⌘Z` / `⇧⌘Z` | Undo / redo |
| `⌘S` | Save the project file |
| `?` | Shortcut list |

## Running it locally

Open `index.html` in a browser. That's the whole story — clone the repo, double-click the file,
or serve the folder with anything you like.

`sample-transcript.txt` is a short fake meeting for trying it out, and `sample-transcript.md`
is the same idea already tagged with `**Name:**` prefixes.

## License

MIT — see [LICENSE](LICENSE).
