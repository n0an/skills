<h1 align="center">Agent Skills by Anton Novoselov</h1>

<p align="center">
    <a href="https://agentskills.io/home">
        <img src="https://img.shields.io/badge/Agent%20Skills-Compatible-purple.svg" alt="Agent Skills Compatible" />
    </a>
    <img src="https://img.shields.io/badge/license-MIT-lightgrey.svg" alt="MIT License" />
</p>

A curated collection of agent skills for Claude Code, Codex, Gemini, Cursor, and more.


## Available Skills

| Skill | Description |
|-------|-------------|
| [git-codebase-preflight](https://github.com/n0an/git-codebase-preflight-skill) | Audits a repository through git history before reading source files |
| [swift-format-style](https://github.com/n0an/Swift-FormatStyle-Agent-Skill) | Reviews and writes modern Swift FormatStyle code with `.formatted()` APIs |


## Installing

### Claude Code

```bash
# Register the marketplace
/plugin marketplace add n0an/skills

# Install a specific skill
/plugin install git-codebase-preflight@n0an/skills
/plugin install swift-format-style@n0an/skills
```

Or install individual skills directly:

```bash
/plugin install n0an/git-codebase-preflight-skill
/plugin install n0an/Swift-FormatStyle-Agent-Skill
```

### Gemini

```bash
gemini extensions install https://github.com/n0an/git-codebase-preflight-skill.git --consent
gemini extensions install https://github.com/n0an/Swift-FormatStyle-Agent-Skill.git --consent
```

### npx (Claude Code, Codex, Gemini, Cursor)

```bash
npx skills add https://github.com/n0an/git-codebase-preflight-skill --skill git-codebase-preflight
npx skills add https://github.com/n0an/Swift-FormatStyle-Agent-Skill --skill swift-format-style
```


## License

All skills are available under the [MIT License](https://opensource.org/licenses/MIT).
