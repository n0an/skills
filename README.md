# Skills

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

## Installation

### Any Agent (via [skills.sh](https://skills.sh))

```bash
npx skills add n0an/skills
```

To install a single skill:

```bash
npx skills add n0an/skills --skill git-codebase-preflight
npx skills add n0an/skills --skill swift-format-style
```

### Claude Code

```bash
/plugin marketplace add n0an/skills
```

## Author

Anton Novoselov, https://github.com/n0an

## License

The project is available under the MIT license. See the [LICENSE](./LICENSE) file for more info.
