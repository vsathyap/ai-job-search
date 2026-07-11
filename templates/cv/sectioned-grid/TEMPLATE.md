# Template: sectioned-grid

- **Type:** CV
- **Engine:** xelatex
- **Page limit:** 2 pages
- **Fonts:** Lato (bundled in `fonts/lato/` - Regular/Bold/Italic/Bold-Italic; a Black weight is also bundled for the name). Same family as the stock `cover.cls` cover letter, for visual consistency between the two documents.
- **Class/packages:** standard `article` class with `fontspec`, `xcolor`, `hyperref`, `enumitem` - no custom `.cls` file

## Compile command

    cd cv && xelatex -interaction=nonstopmode main_<company>.tex

(Copy `fonts/lato/` into the same output directory as the compiled `.tex`, or adjust the `Path` option in the `\setmainfont`/`\newfontfamily` calls to point at `../templates/cv/sectioned-grid/fonts/lato/`.)

## Style rules

- Recreates the candidate's original Word-designed CV: large blue name + bold title, thin blue rule under the header, bold gray profile statement, then sections laid out as **black bold-caps label (left, ~16% width) + wide content column (right, ~80% width)**.
- Dated sections (Education, Professional Experience) use `\cvdate{date}{title}{institution}{location}{description}`, which adds a second inner column for the date (~22% of the content column width) before the entry text. Institution/role title is bold; institution name and location are italic, with location right-aligned via `\hfill`.
- Undated sections (Publications & Patents, Skills, Software Skills, Languages, References) use `\cvblock{content}` directly in the content column - no date column.
- Section order used in the drafted example: Education, Professional Experience, Publications & Patents, Technical & Professional Skills, Software Skills, Languages, References. Follow this order unless the target role calls for reordering (e.g. moving Education after Experience for non-academic roles per the standard tailoring guidance in `05-cv-templates.md`).
- No icons are used anywhere (matches the original's plain-text contact line) - do not add FontAwesome or similar icon packages to the header.
- Colors: name in `cvblue` (RGB 58,110,165); section labels and body text in black/`cvgray` - do not recolor section labels blue, the original design keeps them black.

## Known pitfalls

- **Never write `\item [text]` with the bracket immediately after `\item`.** LaTeX parses a `[` immediately following `\item` as the optional custom-label argument, not as body text - this silently drops most of the item's visible text and can push the label into an overfull hbox that renders off the left edge of the page. Always write `\item{}[text]` (the empty group defeats the optional-argument check) when the item's real content happens to start with a literal `[`, or better, just don't wrap item text in literal brackets at all when filling in the template - the `[PLACEHOLDER]` bracket convention is only for the skeleton, not for final drafted content.
- The label column text (`EDUCATION`, `PROFESSIONAL EXPERIENCE`, etc.) will visibly wrap to 2-3 lines for longer labels since the column is narrow (~16% of the text width) - this is expected and matches the original design; don't try to force it onto one line by widening the column, since that steals space from the content column.
- Nested minipages require `[t]` (top) alignment on every `\begin{minipage}` - if a new minipage is added without `[t]`, it will vertically center instead of top-align and misalign against its sibling column.
