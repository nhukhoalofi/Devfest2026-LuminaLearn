# HACKATHON ROADMAP & COMMIT PLAN

**Basis:** [Project Brief](../PROJECT_BRIEF.md). **Planning assumption:** 10 working hours **after the official coding start**; change this to the organizer's actual schedule. These are *relative work windows*, **not historical timestamps**.

## Execution timeline

| Window | Phase / feature | Delivery & gate | PIC | Planned time | Current state |
|---|---|---|---|---:|---|
| Preparation | **P0 — Brief / provenance** | Scope, origin of inherited code, organizer eligibility question | TV1 | 0.5 h | Brief written; organizer confirmation **pending** |
| H0–H1 | **P1 — Create UI** | Simple topic form, 3-step editor with stable width and honest statuses | TV3 | 1.0 h | Planned |
| H1–H2.5 | **P2 — Agent / storyboard** | New-topic Gemini request → validated typed scene plan, no fabricated data | TV1 | 1.5 h | Planned |
| H2.5–H3.5 | **P3 — Verify / teacher review** | Math & physics tests, editable script, explicit approval gate | TV1 + TV2 | 1.0 h | Planned |
| H3.5–H5.5 | **P4 — Physics video** | Remotion optics visuals, ray geometry and MP4 contact sheet | TV2 | 2.0 h | Planned |
| H5.5–H6.5 | **P5 — Voice + captions** | DUTAI TTS `baotrang`, real WAV proof, spoken timeline, signed external consent | TV3 | 1.0 h | Planned |
| H6.5–H7.5 | **P6 — Album** | Curated successful outputs or validated YouTube embeds, playback | TV3 | 1.0 h | Planned |
| H7.5–H10 | **P7 — Integrate, QA, demo** | E2E smoke, tests, scientific review, fallback, README, demo evidence | All | 2.5 h | Planned |

*P1–P7 sum to 10h. P0 is preparatory; the competition timeline and rules may differ.*

## Incremental, evidence-based commits

Make one commit **after** its diff has been tested; multiple commits within a milestone are fine. Never recreate fake historical timings.

| Order | Suggested commit | Representative paths | Verification before push |
|---|---|---|---|
| Already imported | `init dự án` | Existing Phase 1–5 repository tree | Disclose source-tree identity in brief |
| P0 | `docs(brief): define hackathon MVP, demo scope and provenance` | `PROJECT_BRIEF.md` | Brief matches existing code and plan |
| P0 | `docs(roadmap): map milestones to brief and release gates` | `docs/HACKATHON_ROADMAP.md` | Time budget and gates agree |
| P0 | `docs(timeline): add issue-ready progress tracker` | `docs/PROJECT_TIMELINE.csv` | Every task linked to a P0/P1 brief scope |
| P0 | `ci: add hackathon typecheck and unit-test workflow` | `.github/workflows/hackathon-ci.yml` | Run CI; distinguish successful/pending/failed |
| P1 | `feat(web): make create-video steps consistent and responsive` | `apps/web/src/app/`, `components/` | Check steps 1/2/3 desktop+mobile |
| P2 | `feat(agent): produce typed lesson storyboard from new topics` | `packages/agent/`, `scene-schema/` | New-topic tests and malformed JSON rejection |
| P3 | `feat(review): gate render on verified content and teacher approval` | `packages/validator/`, web API | Invalid claim cannot render |
| P4 | `feat(physics): render reusable rainbow ray optics scenes` | `packages/animation/`, `apps/worker/` | Geometry tests + true MP4/contact sheet |
| P5 | `feat(tts): integrate DUTAI Bảo Trang and timed captions` | `packages/hybrid-renderer/`, web UI | Audible voice check, consent, quota error test |
| P6 | `feat(album): save and play curated video references` | `apps/web/src/app/api/`, UI | No mock video; sanitized embed URLs |
| P7 | `test(e2e): verify topic-to-mp4 workflow and demo fallback` | `apps/web/e2e/`, docs | CI and manual demo evidence |
| P7 | `docs(release): record DevFest setup, attribution and limitations` | `README.md`, `docs/` | Works from documented environment |

## Exit gates

- **H2:** A teacher can enter a fresh topic and obtain a structured storyboard. If live Gemini is unavailable, explain the limitation rather than calling a fixture "AI generation".
- **H4:** Invalid math/physics claims fail closed; edited content cannot bypass teacher signoff.
- **H6:** One physics video renders with verified optics and inspectable frames, without silently substituting fake results.
- **H8:** If licensed/authorized TTS is available, real narration plays with subtitles; otherwise report a clearly labeled video-only fallback. Album opens a real playable source.
- **H10:** Demonstrable end-to-end flow, QA evidence, release notes and explicit pre-existing-work declaration.

## Workflow

1. Open an issue for a scoped, testable task; link its brief requirement.
2. Work in short feature branches (`feat/create-flow`, `feat/physics-optics`, etc.), preserve the functional baseline.
3. Commit small changes with the actual time and original author; include tests or evidence.
4. Open a PR with screenshots, test output and required scientific/teacher review. Merge only when checked.
5. Update `docs/PROJECT_TIMELINE.csv` with real status. A commit message or checklist is **not** evidence the feature works.

## Fallbacks and exclusions

- No Gemini quota → use a labeled fixture for walkthrough, and state that live AI was not tested.
- No DUTAI credentials/API → do not fabricate narration; show the documented silent-video limitation.
- Render environment failure → play a **clearly attributed existing** demo video; do not claim freshly generated.
- YouTube copyright or embed restriction → use only authorized videos or licensed local MP4 assets.
- Cloud Run persistence and workload quotas need separate validation. Cloud deployment remains P2 unless time permits.

## Provenance and licensing

The pre-existing target tree matches `LuminaLearn` source Phase 1–5 exactly (see brief). Importing additional historical V3 files into this repository must be declared as reused development, not presented as hackathon-time implementation. The internal planning note about a 30% threshold requires authoritative organizer confirmation. Keep upstream URLs, license obligations, and audio/visual asset rights in review records.
