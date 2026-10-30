---
name: resume-tailoring
description: Tailor a LaTeX resume to a job listing for ATS keyword matching, one fresh copy per listing. Use when the user pastes a job listing to tailor their resume to, or asks to tailor, target, or keyword-match a resume.
---

Each listing gets its own **copy** of the base resume, tuned so ATS keyword matching hits while every claim stays **backed**: true on the resume already, or confirmed by the user in this conversation. The base page is full, so edits are minor and keyword-level: rewording, not new content.

## Steps

Work one listing at a time; the user reviews each copy before sending the next.

1. **Locate the base.** Find the base `.tex` resume (usually `resume.tex` on the Desktop) and confirm it with the user once per session. The base changes only to absorb new backed facts (step 7).
2. **Read the listing.** Pull the basic and preferred qualifications, the responsibilities' exact phrasing, named tools and services, and the years-of-experience bar. Done when you can name the 8-12 strings an ATS would score.
3. **Copy.** `cp -n <base> <First>_<Last>_<Job_Title>.tex` beside the base, with the listing's title in underscored words (`Will_Katabian_Software_Development_Engineer_Robotics.tex`).
4. **Edit.** Apply the rules under _Keyword edits_ and _Experience bar_. Done when every listing string that the resume can back appears in the copy, and every edit is backed.
5. **Compile and inspect.** See _Compile_. Done when the PDF is one page and no Skills row or bullet ends in a stray word on its own line. Fix overflow with the moves under _Fitting the page_, then recompile.
6. **Report.** A table of edits: location, change, listing keyword hit. Then what you left out on purpose, then questions whose "yes" would unlock real keywords (tools the listing names that the resume omits, duties the user may have done but never wrote down). For a stretch role, say so plainly.
7. **Backport.** When the user confirms a new fact, add it to the current copy, then offer it for the base and every earlier copy it strengthens. Edit, compile, and inspect one file per command so the user can approve or stop each one.

## Keyword edits

- **Mirror the listing's exact string.** ATS matching is mostly literal: "SQL and NoSQL" in the listing becomes "SQL (Postgres), NoSQL (Redis)"; "cloud-native" stays hyphenated.
- **Reword existing evidence** toward the listing: a bullet's opening verb and adjectives ("Architected a secure, distributed system on AWS"), the Skills rows, and the order of items within a row (lead with what the listing names).
- **Abbreviations:** use the listing's form. When the listing uses neither, spell the term out once in a bullet and abbreviate it in Skills.
- **Leave the listing's unbacked core out** (its frameworks, languages, or domains the user has not touched) and name those omissions in the report, since claiming them fails the first technical screen.

## Experience bar

When the listing asks for more years than the user has, show **years-only dates** everywhere (`2025 – Present`, `2021 – 2025`). Dates stay present and accurate; background checks verify them. Write no year count anywhere on the page. Count every real role, founder work and overlapping ones included, and let scope words (owned, shipped solo, end to end) carry seniority. Early-career listings keep full month dates.

## Fitting the page

In order of preference:

1. Drop a Skills item the listing never mentions.
2. Drop a Skills item already named verbatim in a bullet; the ATS still finds it there.
3. Shorten a Skills label (`Cloud and infra` to `Cloud`).
4. Drop the addition least relevant to this listing.

## Compile

`tectonic -X compile <file>.tex` writes the PDF beside the source with no build clutter. Install it with `brew install tectonic` if missing, after asking. Inspect line breaks without rendering images:

```sh
python3 -c "import fitz,sys; d=fitz.open(sys.argv[1]); print('pages', d.page_count); print(d[0].get_text())" <file>.pdf
```

Tectonic runs XeTeX while Overleaf runs pdfLaTeX. If the PDF loses bold or the font changes, the template's font package is pdfLaTeX-only: wrap it in `\ifPDFTeX ... \else` with `fontspec` loading its OpenType twin (Charter's is XCharter). When refactoring a RenderCV template, keep its entry environments, the `calc` package, and their odd lengths (`0 cm + 0.00001 cm`) verbatim; the right-hand date column depends on them.

Write shell commands plainly, one file per command, with file names spelled out; the user reads each before approving it.
