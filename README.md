# Skills

[![Agent Skills Compatible](https://img.shields.io/badge/Agent%20Skills-Compatible-purple.svg)](https://agentskills.io/home)
![MIT License](https://img.shields.io/badge/license-MIT-lightgrey.svg)

A collection of agent skills for Claude Code, Codex, Gemini, Cursor, and more.

## Available Skills

### iOS

#### [app-intents](https://github.com/n0an/App-Intents-Agent-Skill)

Reviews and writes Swift App Intents code for Siri, Shortcuts, Spotlight, widgets, Control Center, and Apple Intelligence.

- Covers `AppIntent`, `AppEntity`, `IndexedEntity`, `TransientAppEntity`, `FileEntity`, and all query types (`EntityQuery`, `EntityStringQuery`, `EnumerableEntityQuery`, `EntityPropertyQuery`, `IntentValueQuery`)
- Handles the full snippet-intent lifecycle: `ShowsSnippetView`, `ShowsSnippetIntent`, `SnippetIntent`, `Button(intent:)`, multi-step interactive confirmation
- Apple Intelligence integration via `@AppIntent(schema:)`, `@AppEntity(schema:)`, `@AppEnum(schema:)` across `.photos.*`, `.journal.*`, `.mail.*`, `.browser.*`, `.visualIntelligence.*`
- Widget and Control Center wiring: `WidgetConfigurationIntent`, `ControlConfigurationIntent`, App Group shared storage, `WidgetCenter.reloadAllTimelines()`
- Catches ~35 common mistakes LLMs make, from `@Model` as `AppEntity` to missing `@Property`, stale shortcut parameters, and mutation inside `SnippetIntent.perform()`
- Supports iOS 16+ / macOS 13+ with iOS 19+ additions (`supportedModes`, `continueInForeground`, `requestChoice`, snippet `reload()`)

#### [swift-format-style](https://github.com/n0an/Swift-FormatStyle-Agent-Skill)

Reviews and writes modern Swift FormatStyle code with `.formatted()` APIs.

- Covers Date, Number, Measurement, and custom FormatStyle types
- Generates correct `.formatted()` calls with proper modifiers
- Reviews existing FormatStyle code for best practices
- Replaces legacy DateFormatter/NumberFormatter patterns
- Supports iOS 15+ / macOS 12+ APIs

#### [background-execution](https://github.com/n0an/Background-Execution-Agent-Skill)

Reviews and writes Swift background-execution code that runs while the app is backgrounded or suspended.

- Covers `BGTaskScheduler`: `BGAppRefreshTask`, `BGProcessingTask`, and `BGContinuedProcessingTask` (iOS 26), with registration timing, `Info.plist` identifiers, expiration, and `setTaskCompleted`
- `beginBackgroundTask` / `endBackgroundTask` assertions and `ProcessInfo.performExpiringActivity` for finishing in-flight work
- Background `URLSession` downloads and uploads, including the full `handleEventsForBackgroundURLSession` relaunch flow
- Silent and VoIP push, the `UIBackgroundModes` matrix, background audio, and the SwiftUI `.backgroundTask` modifier
- macOS schedulers (`NSBackgroundActivityScheduler`, `beginActivity`) and the system constraints that decide whether background work runs at all

#### [widgets](https://github.com/n0an/Widgets-Agent-Skill)

Reviews and writes SwiftUI WidgetKit code across every widget surface.

- Covers all widget kinds: Home Screen, Lock Screen / accessory, and watch widgets, plus Controls (Control Center, Lock Screen, Action button), Live Activities, and the Dynamic Island
- Timeline model: `TimelineProvider` / `AppIntentTimelineProvider`, reload policies and the daily reload budget, `WidgetCenter` reloads, and push-updated widgets (`WidgetPushHandler`)
- Renders correctly in every appearance: `widgetRenderingMode`, `widgetAccentable()`, `widgetAccentedRenderingMode`, and the luminance-to-alpha trick for the tinted/accented Home & Lock Screen
- Interactivity and Controls: `Button(intent:)` / `Toggle(intent:)`, `ControlWidgetToggle` (`SetValueIntent`) vs `ControlWidgetButton`, the app-process boundary, and the App Group store
- Live Activities: `ActivityAttributes` / `ContentState`, `ActivityConfiguration`, `DynamicIsland`, push (token / channel / push-to-start), and `supplementalActivityFamilies` for Apple Watch and CarPlay
- Spans WWDC 2020-2026 with the SiriKit `.intentdefinition` to App Intents and ClockKit to WidgetKit migration map, ~40 anti-patterns, and a worked end-to-end example; supports iOS 14+ / iPadOS / macOS / watchOS / visionOS

#### [observability](https://github.com/n0an/Observability-Agent-Skill)

Reviews and writes Swift observability code - logging, metrics, diagnostics, and production telemetry on Apple platforms.

- Covers unified logging (`Logger`, levels and persistence rules, privacy redaction), Console.app and the `log` CLI with scripted simulator/device capture workflows, and `OSLogStore` support-log export
- Signpost instrumentation (`OSSignposter`, Instruments, `xctrace`, `mxSignpost` field histograms) plus activity tracing and correlation IDs
- MetricKit end to end: `MXMetricManager` payloads and diagnostics through the iOS 27 Swift-native `MetricManager`, launch histograms, hang and exit-reason tracking
- Crash, hang, and OOM observability: watchdog codes, jetsam's missing crash reports, the hang tooling matrix, and symbolication (dSYM/UUID contract, `atos`, MetricKit call stacks)
- Request-level network telemetry (`URLSessionTaskMetrics`, error taxonomy, non-fatal report design) and production pipelines (App Store Connect Power and Performance API, OpenTelemetry)
- Third-party SDK integration rules (one crash handler, dSYM upload, breadcrumb bridging) and ~33 anti-pattern catches; supports iOS 14+ / macOS

### Other

#### [git-codebase-preflight](https://github.com/n0an/git-codebase-preflight-skill)

Audits a repository through git history before reading source files.

- Analyzes commit frequency, active contributors, and project timeline
- Identifies hot files and recently changed areas
- Detects large files, binary assets, and repo structure
- Provides a prioritized list of files to inspect first
- Works on any Git repository without reading source code

#### [ffmpeg](https://github.com/n0an/ffmpeg-skill)

Categorized FFmpeg recipes for video automation pipelines, adapted from the Rendi FFmpeg cheatsheet.

- Format conversion, resize with aspect-ratio padding, frame-accurate trimming
- Audio processing: replace, extract, mix, crossfade, normalize, downsample for speech-to-text (16 kHz mono)
- Advanced editing: playback speed without pitch shift, jump cuts, social-media cropping, drawtext, subtitle burn-in, watermarking, vstack, intro/main/outro assembly
- Asset generation: image-to-video, slideshows with `xfade`, Ken Burns `zoompan`, looping GIFs, scene-change thumbnails, tiled storyboards
- Encoding tuning: CRF/preset guidance for libx264, libx265 with `hvc1` for Apple AirDrop, libvpx-vp9 for the web, `+faststart`, hardware acceleration (`*_nvenc`, `*_qsv`, VAAPI)
- Bakes in common FFmpeg footguns: `-c copy` rules, input vs output seeking, `setpts=PTS-STARTPTS` after `trim`, `setsar=1:1` after pad, `-pix_fmt yuv420p` for QuickTime

#### [rich-html](https://github.com/n0an/rich-html-skill)

Renders content as a polished, self-contained HTML deck or document instead of plain Markdown.

- Produces two single-file output profiles: a fullscreen **Deck** (keyboard / click / swipe navigation, progress bar, counter) and a long-scrolling **Document** (sections, tables, legends, inline diagrams)
- Mermaid diagrams (flowcharts, sequence, dependency graphs) themed to match the page, with the slide-visibility render gotcha already solved
- Expressive layout out of the box: cards, big-stat numbers, callout notes, pills, flow steps, and tables
- Download buttons that link the best experiment, result JSON, or full log straight from the page
- A cohesive GitHub-dark design system; ideal for recaps of long runs, showcases, pitches, architecture write-ups, reports, and specs

#### [simplified-technical-language](https://github.com/n0an/simplified-technical-language)

Writes, rewrites, and reviews technical text with the [ASD-STE100 Simplified Technical English](https://www.asd-ste100.org/about_STE.html) rules - the controlled language standard born in aviation maintenance.

- Three modes: write new procedures/descriptions, rewrite existing text into STE, or review text and report rule violations
- Enforces the core limits: 20-word procedural / 25-word descriptive sentences, 6-sentence paragraphs, one instruction per sentence, 3-noun clusters
- Controls vocabulary: one word one meaning, part-of-speech control, a substitutions table for the frequent offenders ("prior to commencing" becomes "before you start")
- Grammar discipline: approved verb forms only, no -ing verb forms, no "shall/should/may", mandatory active voice and imperatives in procedures
- Structures safety text: WARNING vs CAUTION vs NOTE, command-first warnings, conditions before commands
- Ends every rewrite with a rule-by-rule compliance checklist instead of trusting text that merely looks compliant

## Installation

### Any Agent (via [skills.sh](https://skills.sh))

```bash
npx skills add n0an/skills
```

To install a single skill:

```bash
npx skills add n0an/skills --skill app-intents
npx skills add n0an/skills --skill swift-format-style
npx skills add n0an/skills --skill background-execution
npx skills add n0an/skills --skill widgets
npx skills add n0an/skills --skill observability
npx skills add n0an/skills --skill git-codebase-preflight
npx skills add n0an/skills --skill ffmpeg
npx skills add n0an/skills --skill rich-html
npx skills add n0an/skills --skill simplified-technical-language
```

### Claude Code

```bash
/plugin marketplace add n0an/skills
```

## Author

Anton Novoselov, https://github.com/n0an

## License

The project is available under the MIT license. See the [LICENSE](./LICENSE) file for more info.
