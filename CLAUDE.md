# Job Application Assistant for Vasudha Sathyapriyan

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Vasudha Sathyapriyan, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Vasudha Sathyapriyan
- **Location:** Copenhagen, Denmark (open to relocation: Denmark, India, Belgium, Netherlands, Finland, Sweden; prefers hybrid or partly-hybrid/onsite roles over fully remote)
- **Languages:** English, Tamil, Kannada, Hindi (native/bilingual); no Danish proficiency
- **Status:** Employed full-time as DSP Engineer at Demant A/S (Oticon); PhD thesis in final review, defense expected October 2026
- **LinkedIn headline:** "DSP Engineer at Oticon | PhD Fellow at Aalborg University"

### Education
- **PhD in Electrical and Electronics Engineering (Industrial)** (2021-Present) - Aalborg University (enrolled, Marie Skłodowska-Curie Fellowship), based full-time at Demant A/S (Oticon), Smørum, Denmark
  - Thesis: "Speech enhancement in hearing aid applications using remote microphones" (final review, defense expected October 2026)
  - Topics: adaptive beamforming, multi-microphone noise reduction, DNN-based mask estimation, wireless acoustic sensor networks. Visiting stints at Aalborg University campus and Imperial College London.
- **MSc in Electrical and Electronics Engineering (Cum Laude)** (2018-2020) - Delft University of Technology, Delft, Netherlands
  - Thesis: "Noise reduction in hearing aids with binaural cue (ILD/ITD) preservation"
- **B.E. in Electrical and Electronics Engineering** (2013-2017) - SSN College of Engineering, Chennai, India

### Professional Experience
- **DSP Engineer** (September 2024 - Present) - **Demant A/S (Oticon)** (Smørum, Denmark)
  - Develop and optimize DSP algorithms for hearing instruments across the full product lifecycle
  - Research and implement adaptive beamforming and multi-microphone noise reduction; train/evaluate DNNs for mask estimation (PyTorch)
  - Verify algorithm performance through acoustic measurements, real-time testing, and clinical data analysis with audiologists
- **Graduate Research Intern** (July 2019 - November 2019) - **Bosch Security and Safety Systems** (Eindhoven, Netherlands)
  - Improved beamforming algorithms for microphone arrays in conference room systems
- **Software Engineer** (June 2017 - May 2018) - **Visteon Corporation** (Chennai, India)
  - Developed embedded software for automotive instrument clusters using Agile methodology

### Technical Skills
- **Primary:** Statistical signal processing, adaptive beamforming, multi-microphone noise reduction, speech enhancement, detection/estimation theory, constrained optimization (Lagrangian methods)
- **Secondary:** Deep learning for audio (PyTorch, DNN mask estimation), embedded software (C++)
- **Domain:** Hearing aid / assistive hearing technology, audio and speech signal processing, spatial audio
- **Software:** Python, MATLAB, PyTorch, C++, Git, Linux, Agile

### Certifications
None on file.

### Publications
- V. Sathyapriyan et al. (2025). "Head-Steered Channel Selection for Hearing Aid Applications Using Remote Microphones." IEEE Access.
- V. Sathyapriyan et al. (2025). "Binary Estimator Selection Methods for Hearing Aids With a Remote Microphone." IEEE Access.
- V. Sathyapriyan et al. (2024). "Speech Enhancement in Hearing Aids Using Target Speech Presence Estimation Based on a Delayed Remote Microphone Signal." IEEE ICASSP.
- V. Sathyapriyan et al. (2023). "Speech Enhancement using Binary Estimator Selection Applied to Hearing Aids with a Remote Microphone." IEEE ICFSP.
- V. Sathyapriyan et al. (2022). "A Linear MMSE Filter Using Delayed Remote Microphone Signals for Speech Enhancement in Hearing Aid Applications." IEEE IWAENC.
- V. Sathyapriyan, M. Çaliş, R. C. Hendriks (2021). "Binaural beam-forming with dominant spatial cue preservation for hearing aids." EUSIPCO.

Plus 2 patents (see `01-candidate-profile.md` for full details).

### Awards
None on file.

### Behavioral Profile
Not yet assessed - see `.claude/skills/job-application-assistant/02-behavioral-profile.md` (left blank; populate manually or via a future `/setup --section behavioral` run).

### What Excites You
- Taking algorithms from research/derivation to deployed, real-time products
- Framing messy real-world problems as estimation, detection, or constrained-optimization tasks and solving them rigorously

### Target Sectors
- Hearing aid / audio technology: Demant/Oticon, GN/Jabra, Sonova/Phonak, WSAudiology, Qualcomm (Speech & Audio Research), Goodix
- Broader audio/speech ML and signal processing: TrackMan (sensor/radar modelling), and adjacent sensor-fusion or acoustic ML roles

### Deal-breakers
- Fully remote-only roles (prefers hybrid or partly-hybrid/onsite)
- Roles requiring fluent Danish
- Relocation outside the approved list: Denmark, India, Belgium, Netherlands, Finland, Sweden

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
