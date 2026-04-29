# Skills

[![Agent Skills Compatible](https://img.shields.io/badge/Agent%20Skills-Compatible-purple.svg)](https://agentskills.io/home)
![MIT License](https://img.shields.io/badge/license-MIT-lightgrey.svg)

A collection of agent skills for Claude Code, Codex, Gemini, Cursor, and more.

## Available Skills

### [git-codebase-preflight](https://github.com/n0an/git-codebase-preflight-skill)

Audits a repository through git history before reading source files.

- Analyzes commit frequency, active contributors, and project timeline
- Identifies hot files and recently changed areas
- Detects large files, binary assets, and repo structure
- Provides a prioritized list of files to inspect first
- Works on any Git repository without reading source code

### [swift-format-style](https://github.com/n0an/Swift-FormatStyle-Agent-Skill)

Reviews and writes modern Swift FormatStyle code with `.formatted()` APIs.

- Covers Date, Number, Measurement, and custom FormatStyle types
- Generates correct `.formatted()` calls with proper modifiers
- Reviews existing FormatStyle code for best practices
- Replaces legacy DateFormatter/NumberFormatter patterns
- Supports iOS 15+ / macOS 12+ APIs

### [app-intents](https://github.com/n0an/App-Intents-Agent-Skill)

Reviews and writes Swift App Intents code for Siri, Shortcuts, Spotlight, widgets, Control Center, and Apple Intelligence.

- Covers `AppIntent`, `AppEntity`, `IndexedEntity`, `TransientAppEntity`, `FileEntity`, and all query types (`EntityQuery`, `EntityStringQuery`, `EnumerableEntityQuery`, `EntityPropertyQuery`, `IntentValueQuery`)
- Handles the full snippet-intent lifecycle: `ShowsSnippetView`, `ShowsSnippetIntent`, `SnippetIntent`, `Button(intent:)`, multi-step interactive confirmation
- Apple Intelligence integration via `@AppIntent(schema:)`, `@AppEntity(schema:)`, `@AppEnum(schema:)` across `.photos.*`, `.journal.*`, `.mail.*`, `.browser.*`, `.visualIntelligence.*`
- Widget and Control Center wiring: `WidgetConfigurationIntent`, `ControlConfigurationIntent`, App Group shared storage, `WidgetCenter.reloadAllTimelines()`
- Catches ~35 common mistakes LLMs make, from `@Model` as `AppEntity` to missing `@Property`, stale shortcut parameters, and mutation inside `SnippetIntent.perform()`
- Supports iOS 16+ / macOS 13+ with iOS 19+ additions (`supportedModes`, `continueInForeground`, `requestChoice`, snippet `reload()`)

### [ffmpeg](https://github.com/n0an/ffmpeg-skill)

Categorized FFmpeg recipes for video automation pipelines, adapted from the Rendi FFmpeg cheatsheet.

- Format conversion, resize with aspect-ratio padding, frame-accurate trimming
- Audio processing: replace, extract, mix, crossfade, normalize, downsample for speech-to-text (16 kHz mono)
- Advanced editing: playback speed without pitch shift, jump cuts, social-media cropping, drawtext, subtitle burn-in, watermarking, vstack, intro/main/outro assembly
- Asset generation: image-to-video, slideshows with `xfade`, Ken Burns `zoompan`, looping GIFs, scene-change thumbnails, tiled storyboards
- Encoding tuning: CRF/preset guidance for libx264, libx265 with `hvc1` for Apple AirDrop, libvpx-vp9 for the web, `+faststart`, hardware acceleration (`*_nvenc`, `*_qsv`, VAAPI)
- Bakes in common FFmpeg footguns: `-c copy` rules, input vs output seeking, `setpts=PTS-STARTPTS` after `trim`, `setsar=1:1` after pad, `-pix_fmt yuv420p` for QuickTime

## Installation

### Any Agent (via [skills.sh](https://skills.sh))

```bash
npx skills add n0an/skills
```

To install a single skill:

```bash
npx skills add n0an/skills --skill git-codebase-preflight
npx skills add n0an/skills --skill swift-format-style
npx skills add n0an/skills --skill app-intents
npx skills add n0an/skills --skill ffmpeg
```

### Claude Code

```bash
/plugin marketplace add n0an/skills
```

## Author

Anton Novoselov, https://github.com/n0an

## License

The project is available under the MIT license. See the [LICENSE](./LICENSE) file for more info.
