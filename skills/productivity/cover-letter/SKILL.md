---
name: cover-letter
description: Write a one-page LaTeX cover letter for a job listing, paired with that listing's tailored resume. Use when the user asks for a cover letter, or to add one alongside a tailored resume.
---

Each listing gets its own **letter**, written beside that listing's tailored resume copy and matching its look. Where the resume is scanned for keywords, the letter is read by a person in under a minute: it argues **fit**, connecting two or three pieces of **evidence** to the listing's top needs. Every claim is **backed** in the sense the [`resume-tailoring`](../resume-tailoring/SKILL.md) skill defines: on the resume already, or confirmed by the user in this conversation.

## Steps

1. **Gather.** Read the listing and its tailored resume copy. If no copy exists yet, run `resume-tailoring` first. Done when you can name the listing's three top needs, one specific detail about the company that the listing states, and the resume evidence behind each need.
2. **Copy the shell.** Name the file `<First>_<Last>_<Job_Title>_Cover_Letter.tex` (the resume copy's name plus `_Cover_Letter`) and put it beside the resume copy. Build it from the resume copy's preamble and header (geometry, font block, contact line) so the two read as a set. Then add the date, the company name, and a salutation: the hiring manager's name if the listing gives one, otherwise `Dear <Company> Hiring Team,`.
3. **Draft.** Follow _Structure_ and _Voice_. Done when every paragraph maps to a listing need, every sentence of fact is backed, and the body is 250 to 350 words.
4. **Compile and inspect.** Use the _Compile_ section of `resume-tailoring`. Done when the PDF is one page with the signature on it.
5. **Report.** List each paragraph, the listing need it answers, and the resume line that backs it. Give the word count. Then ask the questions whose "yes" would let the letter use stronger evidence.

## Structure

Four paragraphs, then the sign-off:

1. **Hook.** Open on something specific to this company, taken from the listing (a product, a metric, its stated problem), and connect it to the user's own work in one or two sentences. In the same paragraph, name the role and what the user would own.
2. **Proof.** The strongest piece of evidence for the listing's top need. Name it, give its concrete detail (a number, a tool, the scope), and say what it shows about the role's actual work.
3. **Proof.** The second need, handled the same way. Add a third need here only if the word budget allows.
4. **Range and close.** One sentence on breadth or ownership that covers a remaining need. Then close forward: offer to discuss a specific first problem from the listing, and thank the reader.

When the user falls short of the experience bar, let scope and outcomes carry the case and keep year counts off the page, matching the resume's _Experience bar_ rule.

## Voice

- **First person, plain, concrete.** Each sentence carries a fact, a number, or a reason. A sentence that would fit any company's letter gets rewritten until it fits only this one.
- **Mirror the listing's phrases** a few times where they truly apply ("first try", "evals"). This shows the user read the listing, and the letter stays theirs.
- **Evidence over adjectives.** Instead of calling the user passionate or detail-oriented, show the work that proves it.
- **Open on the company's problem and the user's evidence**, rather than on the candidate's wish to apply.
- Use the user's own phrasing from the resume where it fits, so the letter and the resume sound like one author.
