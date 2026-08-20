# Crit_Colour Studio

Colour Studio is a SwiftUI app for iPhone and iPad that trains designers to
notice how context changes colour. Its interaction architecture applies Don
Norman's human-centred principles: visible signifiers, natural mapping,
feedforward before action, reversible attempts and diagnostic feedback.

The project connects academic colour theory with direct observation, physical
experimentation and responsible interface design. Learners move from everyday
colour experience through perceptual illusions and scientific foundations into
an open design sandbox.

**Current release:** Version 1.0.0 (Build 1) · August 2026  
**Designed and built by:** Kamalanarayanan  
**Product:** A CRIT Studio product

## Run the app

1. Open `ColourStudio.xcodeproj` in Xcode 26 or later.
2. Choose the `ColourStudio` scheme and an iPhone or iPad.
3. Press Run.

The deployment target is **iOS 17.0**. Choose Product → Test to run the twelve
included colour-science, architecture, persistence and media-export checks.

## What is built

- **Perceptual opening:** the first launch demonstrates simultaneous contrast
  before revealing that both grey swatches are identical. Returning launches
  use a short wordmark transition, with a static Reduce Motion alternative.
- **Cut-paper identity:** neutral paper grain, cut edges, tape, registration
  marks and tactile depth distinguish the app without tinting experiment areas.
- **Today:** one clear next milestone; field tasks appear only after the Reality
  phase makes their conceptual model available.
- **Four-phase Glitch journey:** Everyday Experience → Analog and Digital
  Glitches → Reality → Sandbox, with visible prerequisite explanations.
- **Everyday meaning:** emotion and cultural context appear before numbers or
  formal colour models.
- **Fixed sticky-note glitch:** the same standard yellow sample crosses yellow
  and navy grounds so identity stays visible instead of being held in memory.
- **Hands-on studio:** afterimage, one-colour/two-contexts,
  two-colours/one-appearance and vanishing-edge experiments.
- **Prediction before explanation:** learners commit before seeing a score or
  principle; the grounds then slide away while the identical samples remain.
- **Personal observation:** learners record “I saw it,” “Not yet,” or
  “Something else” so the model never overrules their actual experience.
- **Paper-box interaction:** 42 fixed swatches grouped as Deep, Mid, Pale and
  Neutral, with tap, drag/drop, long-press names and accessibility labels.
- **Real design briefs:** rescue a poster, fix a call-to-action and separate
  chart data, measured using real WCAG contrast ratios.
- **Natural-mapping colour solid:** rotation controls hue, radial movement
  controls chroma and vertical lift controls lightness. A dashed path and text
  describe the target direction before the learner moves.
- **Persistent reference tray:** up to five pinned swatches remain available
  across screens, with visible removal controls and accessible names.
- **Forcing functions:** AAA export remains visibly locked below 7:1 with a
  luminance diagnosis; white/black tint controls remain locked until the
  requested primary-ink balance is built.
- **Errorless diagnostics:** exercise results preserve the canvas and draw a
  lightness/chroma/hue delta vector instead of issuing a wrong-answer banner.
- **Camera Colour Hunt:** three scavenger briefs, steadiness and clipping
  feedback, white-balance locking and CIEDE2000 paper matching.
- **Computational constancy trace:** the guided camera glitch records the
  automatic white-balance guess, a locked first light and the same surface in a
  second light. True Tone and auto white balance are correctly distinguished.
- **Studio Critic:** on supported iOS 26 devices, Apple Intelligence gives a
  short on-device critique structured as What works / What your eye may miss /
  Try next, grounded in the deterministic engine result.
- **Notebook portfolio:** saved experiments support private reflections and a
  locally rendered, shareable image card with the model-estimate caveat.
- **Display check:** a short, skippable setup and neutral-ramp check before the
  first colour-sensitive exercise.
- **First-use wayfinding:** a one-time scroll cue on Today, visible horizontal
  scroll affordances, and a replayable animated paper-placement guide.
- **Inclusive paper placement:** drag/drop has a highlighted destination, while
  tap-ground-then-tap-paper remains a fully equivalent keyboard and assistive
  technology path.
- **Test feedback:** a dedicated Feedback tab captures contextual categories,
  clarity/ease/learning ratings and comments. Notes remain local until the
  tester deliberately shares them through the system share sheet.
- **Inclusive paths:** colour-vision simulations are described as simulations,
  and the afterimage lesson includes safety, skip and alternative responses.
- **Dual-track completion:** physical work can be self-confirmed without a
  photo, or locally attached as evidence to unlock a high-resolution 16:9
  certificate and an actual five-second 1080 × 1920 H.264 Story reel.

## Camera and AI boundaries

The camera observes rendered RGB after illumination, optics, sensor response,
white balance and image processing. It does **not** measure a material's
spectral absorption and is not a spectrometer. That limitation is taught
inside the camera lesson.

True Tone changes the display white point and cannot be controlled by a
third-party app. Auto white balance changes the camera rendering and can be
locked through AVFoundation on supported hardware. The guided digital glitch
teaches this boundary rather than claiming to disable all computational
photography.

The Studio Critic uses Apple's on-device Foundation Models framework when the
device, OS and Apple Intelligence settings support it. It explains measured
facts supplied by the app; it does not calculate scores or replace them. The
rest of the app works when the model is unavailable.

## Privacy

There are no third-party packages, accounts, API keys or network calls. Camera
frames are sampled live and not stored. Notebook entries and test feedback stay
in local app storage. Portfolio cards and feedback summaries only leave through
the system share sheet when the learner explicitly chooses.

Evidence photos are downsampled and stored in the app's private Application
Support directory. The test build does not upload them or perform instructor
review. Reward artwork uses the configurable placeholder identity **Colour
Studio Learning Lab**; approved university assets and a credential-verification
service must be supplied before making an institutional claim.

## Project map

```
Engine/
  ColorScience.swift   sRGB↔CIELAB, CIEDE2000, WCAG contrast, CVD simulation
  Palette.swift        fixed 42-swatch paper box
  Scoring.swift        deterministic exercise grading
  Curriculum.swift     original teaching content
  HumanCenteredLearning.swift  phase, evidence and five-anchor state stores
UI/
  LaunchAnimationView.swift    first-use illusion and returning wordmark
  HomeView.swift               Today and display setup
  RootView.swift               Today, Studio, Notebook and Feedback navigation
  PaperPalette.swift           grouped tap and drag/drop palette
  StudioFeedbackView.swift     ratings, comments and explicit feedback export
  StudioNotebookView.swift     reflection, portfolio and image export
  AIStudioCriticView.swift     capability-gated on-device critique
  StudioVisuals.swift          tactile paper system and neutral canvas
  NormanComponents.swift       anchor tray, delta vector, CIELAB solid, lockout
Levels/
  LearningJourneyView.swift    four phases, sticky-note glitch and interlocks
  RewardStudioView.swift       certificate and five-second Story video export
  OneBecomesTwoView.swift      core predict/build/commit/prove loop
  TwoBecomeOneView.swift       advanced context challenge
  AfterimageView.swift         timed perceptual experiment
  VanishingBoundaryView.swift  perception plus accessibility
  DesignBriefView.swift        poster, button and chart briefs
  CameraLabView.swift          live camera matching and white balance
  ReadingView.swift            visual prediction/reveal concepts
```

## Verification and known limitation

The app builds for iPhone and iPad simulators. All twelve automated tests pass.
CIEDE2000 uses a published Sharma, Wu & Dalal reference pair; WCAG values,
palette uniqueness/gamut, exact swatch matching, scoring identity, notebook
serialization, feedback serialization, journey prerequisites, five-item anchor
limits and the five-second vertical video export are checked.

The simultaneous-contrast induction gains remain a **model estimate**, not a
measurement of the learner or a human-validated appearance model. The UI says
so. Before making learning-outcome claims, fit and test the model with real
observers. Display conditions and cameras also vary by device. See
`PRODUCT_REVIEW.md` for the post-redesign critique and recommended research.

## Support

For app support, bug reports, accessibility issues, general feedback or feature
requests, contact:

**Email:** [kamalgeek92@gmail.com](mailto:kamalgeek92@gmail.com)

When requesting support, include the app version, device model, iOS version and
a short description of what happened. Do not include private evidence photos or
other sensitive information.

This repository must be public for its URL to be used as the App Store Support
URL. The repository page should remain available so existing users can reach
the support information above.

## Attribution

Exercises are adapted from Josef Albers, *Interaction of Color* (Yale
University Press, 1963). No text or plate from the book is reproduced; all
teaching copy is original. This project is not affiliated with Yale.

© 2026 Kamalanarayanan. All rights reserved.
