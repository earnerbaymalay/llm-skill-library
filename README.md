# LLM Skill Library

Unified repository for exporting and managing skills across multiple LLM platforms:
- **Claude AI** (claude.ai)
- **Claude Code** (web, desktop, CLI)
- **Google LLM IDE** (antigravity)

## Directory Structure

```
├── claude-ai/              # Skills exported from claude.ai
├── claude-code/            # Skills from Claude Code projects
├── google-llm-ide/         # Skills from Google's LLM IDE
└── README.md
```

## Export Instructions

### From Claude.ai

1. Go to [claude.ai/settings](https://claude.ai/settings)
2. Navigate to **Skills** or **Custom Skills**
3. For each skill:
   - Click **Export** or **Download**
   - Save the `.md` or JSON file
   - Place in `claude-ai/` directory

**Alternative**: If no direct export available, manually copy skill text into `claude-ai/<skill-name>.md`

### From Claude Code

1. **Project skills** (`.claude/skills/`):
   ```bash
   cp -r <project>/.claude/skills/* claude-code/
   ```

2. **Global settings** (`settings.json`):
   ```bash
   cp ~/.claude/settings.json claude-code/settings-global.json
   ```

3. **Keybindings**:
   ```bash
   cp ~/.claude/keybindings.json claude-code/keybindings.json
   ```

### From Google LLM IDE (antigravity)

1. Open Google LLM IDE workspace
2. For each skill/prompt:
   - **Export**: Use IDE's export feature (usually ⬇️ or File → Export)
   - Save to `google-llm-ide/` directory
3. **Configuration**:
   - Export any workspace config (YAML/JSON)
   - Save as `google-llm-ide/config.yaml`

**Note**: If IDE doesn't have direct export, copy skill source text to `.md` files.

## Usage

Once exported, organize by naming convention:

```
claude-ai/
├── skill-name-1.md
├── skill-name-2.json
└── metadata.json

claude-code/
├── skill-name.md
├── settings-global.json
└── keybindings.json

google-llm-ide/
├── skill-name-1.md
├── skill-name-2.yaml
└── config.yaml
```

## Contributing

- Add skills to appropriate source directory
- Use consistent naming: `kebab-case-skill-name.{md,json,yaml}`
- Include a brief description in a `metadata.json` per source (optional)
- Commit and push to main branch

## Metadata Template (Optional)

For each directory, optionally add `metadata.json`:

```json
{
  "source": "claude-ai|claude-code|google-llm-ide",
  "exported_at": "2026-11-20",
  "count": 5,
  "skills": [
    {
      "name": "skill-name",
      "type": "prompt|custom|workflow",
      "description": "Brief description"
    }
  ]
}
```
