# PROJECT BRIEF — DevFest 2026 | LuminaLearn

> **Status:** Hackathon planning brief, drafted 14/11/2026. This is a proposal, **not** a claim of eligibility, competition dates, or finished functionality.

## 1. Problem and audience

Vietnamese teachers and STEM creators spend substantial time turning difficult concepts into short, understandable videos. General video generators can create attractive imagery but do not inherently prove that scientific claims, diagrams or numbers are correct.

**Primary user:** a teacher/creator preparing a 9:16 Vietnamese explainer.  
**Value proposition:** **One topic → verified, editable educational storyboard → narrated motion-graphics MP4.**

## 2. Demo scenario and deliverable

**Main demo:** “Vì sao sau cơn mưa có cầu vồng?” (Physics / optics), targeting **45–60 seconds**, vertical **9:16**. Explain white sunlight, initial dispersion on refraction, internal reflection, exit refraction and the observer's viewing geometry. Avoid depicting internal reflection as necessarily total internal reflection. Demonstrate the optical paths with coherent geometry.

**Fallback demo:** a supported Mathematics topic, using pre-existing math pipeline where possible.

**User journey**
1. Enter a new learning topic and choose subject/duration.
2. Generate a lesson plan, script and storyboard using Gemini (or a clearly marked offline/demo path).
3. Validate supported scientific claims; inspect and edit the narration/storyboard; require appropriate human approval.
4. Render motion graphics with Remotion; synthesize Vietnamese audio with DUTAI TTS (`zerotts`, voice `baotrang`) **only with explicit API authorization and available access**; align subtitles and scenes.
5. Preview/download the MP4. Optionally curate a finished video in **Album** via a reviewed YouTube embed link or permitted local artifact.

## 3. MVP boundaries

| Priority | Included | Acceptance evidence |
|---|---|---|
| **P0** | Input topic → structured storyboard → validated render | A new, non-hardcoded input generates a demonstrable storyboard and playable MP4 |
| **P0** | Verified math/physics claims and safe failure | Incorrect/unsupported facts are flagged; no mock result presented as production proof |
| **P0** | Teacher review before export | Edited lesson/narration requires correct re-review or reapproval where required |
| **P0** | Clear create-video flow | Input, review and export work without layout jumping between steps |
| **P1** | DUTAI Vietnamese narration + timed subtitles | Audible WAV→MP4 voiceover; verify audio stream, duration and transcript |
| **P1** | Simple video Album | Real completed videos or manually curated permitted YouTube embeds; no fake downloads |
| **P1** | Release QA/demo | Build/tests, extracted render frames, documented limitations and a rehearsable demo |
| **P2** | Cloud Run deployment | Deploy only after persistent storage, secrets and resource limits are addressed |

**Out of scope for hackathon:** LMS, student accounts/grades, PDF RAG, uncontrolled autonomous multi-agent expansion, automatic YouTube uploads, a second video-render engine, and large-scale music generation.

## 4. Technical approach

Use the existing **pnpm monorepo**: Next.js Web, Gemini/agent orchestration, Zod scene contracts, scientific validator/SymPy where appropriate, Remotion/FFmpeg video rendering. Prefer adding thin adapters and reusable physics components to rewriting the system.

**Key gates:** validated facts; explicit third-party API consent; teacher approval; real MP4 + actual audible audio checks; frame QA at optical intersections; no secrets or unlicensed audio in Git.

## 5. Provenance — critical hackathon disclosure

The target repo `nhukhoalofi/Devfest2026-LuminaLearn` **already contained prior work at the start of this brief**:

- Target baseline commit: `b5cacb79c437eb985e9246cb87cea78337292e52` (14/11/2026).
- Its Git tree `f3d4d1849e868d2dd309b12c987381863d44d56d` matches the tree of source repo `nhukhoalofi/LuminaLearn` commit `8bac503f5eb5ff4f401300a8dd9e5919f071bf93` (07/11/2026, math pipeline Phase 1–5).
- The source repo also has a newer feature branch; **that work is not implicitly new work just because it is copied into the hackathon repo**.
- Before claiming compliance, submit a genuine pre-existing-work declaration to the organizer. Earlier internal planning documents mention a possible **30% pre-event-work threshold**; its official applicability and interpretation have **not** been independently verified here.

Do **not** rewrite history, backdate commits, fabricate interim progress, claim old code as newly written, or auto-import the latest V3 branch merely to generate many commits.

## 6. Team, scope change, and success test

Three-person suggested work split (assign real names later):
- **TV1 / Product & AI:** brief, lesson planning, review and demo narrative.
- **TV2 / Motion & Science:** physics templates, formula/geometry validation, frame QA.
- **TV3 / Web & Integration:** UI, TTS, video jobs, Album and CI/deployment.

This brief reflects the **current physics + two-feature UI demo direction**. The 04/11/2026 planning documents originally emphasized a 30–45-second Math/Simpson example. Preserve those plans as historical input; the change of demo topic is explicit here.

**Demo is accepted only if:** (a) a topic not solely hardcoded produces an approved storyboard, (b) a real playable MP4 is generated, (c) facts/optical geometry are checked, (d) audible narration is demonstrated if TTS access exists, and (e) successful work and unfinished limitations are disclosed honestly.

## 7. References

- Original work: https://github.com/nhukhoalofi/LuminaLearn
- Hackathon repo: https://github.com/nhukhoalofi/Devfest2026-LuminaLearn
- Existing plans in `docs/LuminaLearn_KeHoach_DuAn_ChiTiet_DevFest2026.docx` and `docs/LuminaLearn_KeHoach_TrienKhai_ChiTiet_Theo_Phase_V2.docx`.
- Timeline and proposed commits: `docs/HACKATHON_ROADMAP.md`.
