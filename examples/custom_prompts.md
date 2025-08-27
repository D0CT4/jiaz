# Custom Prompt Examples for JIAZ

This directory contains example custom prompt templates that can be used with the `--format` option in JIAZ AI features.

## Usage

```bash
# Use custom prompt for description standardization
jiaz analyze issue PROJ-123 --marshal-description --format /path/to/custom-description-prompt.txt

# Use custom prompt for rundown summary
jiaz analyze issue PROJ-123 --rundown --format /path/to/custom-rundown-prompt.txt
```

## Template Variables

Your custom prompts can use the following template variables:

### For Description Standardization (`--marshal-description`)
- `{title}` - The JIRA issue title
- `{description}` - The original issue description

### For Rundown Summary (`--rundown`)
- `{issue_data}` - Complete issue data including comments, status, children issues, etc.

## Examples

### Simple Description Template
```text
You are an expert in writing clear JIRA descriptions.

Reformat this issue into a clean structure:

**What needs to be done:**
<Brief task description>

**Acceptance Criteria:**
<Success conditions>

Title: {title}
Description: {description}
```

### Corporate Standard Template
```text
You are a technical writer following company standards.

Transform this JIRA issue into our standard format:

## Executive Summary
<One-line summary>

## Requirements
<What needs to be built/fixed>

## Definition of Done
<Acceptance criteria>

## Technical Notes
<Implementation details>

Input Title: {title}
Input Description: {description}
```

## Tips

1. Always include the template variables (`{title}`, `{description}`, `{issue_data}`)
2. Be specific about the desired output format
3. Include clear instructions for the AI
4. Test your prompts with different issue types
5. Keep prompts focused and concise for better results
