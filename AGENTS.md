# AGENTS.md - Agent Guidelines for CFPs Repository

## Overview

This repository contains conference talk proposals (CFPs) - both accepted and rejected submissions to various conferences. The content consists of markdown files documenting talk abstracts, speaker bios, and talk metadata.

## Repository Structure

```
cfps/
├── README.md                    # Main index of all proposals
├── accepted/                    # Accepted CFPs (markdown files)
│   ├── 2026-national-coding-day-...
│   ├── 2026-fossasia-summit-...
│   └── ...
├── pending/                     # Directory for pending submissions
└── .gitignore                   # Git ignore rules
```

## Workflow Guidelines

### Adding New Proposals

1. Place new proposals in `pending/` directory until accepted
2. When accepted, move to `accepted/` directory
3. Follow naming convention: `{year}-{conference-short-name}-{talk-title-slug}.md`
4. Update README.md index when status changes

### Proposal File Format

Each proposal should be a markdown file with frontmatter containing:

```yaml
---
title: "Talk Title"
conference: "Conference Name"
year: 2026
status: accepted | rejected | pending
duration: 30min | 45min | 60min
tags: []
---
```

### Content Guidelines

- Use clear, concise language
- Include speaker bio at the end of each proposal
- Add relevant tags for categorization
- Include target audience level (beginner/intermediate/advanced)
- Add links to related talks or resources when applicable

## Markdown Style

- Use ATX-style headers (`#`, `##`, `###`)
- Use bullet points for lists (not numbered unless sequence matters)
- Keep lines under 120 characters for readability
- Use code blocks with language identifiers for code examples
- Include blank lines between block elements

### Code Block Guidelines

```python
def example_function():
    """Example function demonstrating code block style."""
    return "Hello, World!"
```

### Link Formatting

- Use descriptive link text: `[Apache Airflow](https://airflow.apache.org)`
- Place links at bottom of file in "References" section for long proposals

## Writing Conventions

### Talk Titles

- Capitalize first letter of each word (title case)
- Keep under 100 characters
- Avoid jargon unless audience is technical

### Descriptions

- Start with problem/motivation
- Explain what attendees will learn
- Include practical takeaways
- Target 150-300 words for abstract

### Speaker Bio

- 2-3 sentences maximum
- Include relevant credentials and experience
- Add links to professional profiles (GitHub, Twitter, LinkedIn)

## Git Conventions

### Commit Messages

Use conventional format:

- `feat: add new proposal for Conference Name`
- `move: relocate proposal from pending to accepted`
- `docs: update README index`

### Branch Naming

- `main` - production content
- `feat/{conference}-{year}` - new proposal draft

## Error Handling

- Verify proposal follows required format before commit
- Check all external links are valid
- Ensure frontmatter is valid YAML
- Validate markdown renders correctly

### Common Issues and Solutions

1. **Invalid YAML syntax in frontmatter**
   - Check for missing colons, quotes, or proper indentation
   - Use spaces (not tabs) for indentation
   - Ensure status values are lowercase

2. **Broken links**
   - Verify URLs are HTTPS when possible
   - Test links in a browser before committing

3. **Missing or incorrect frontmatter**
   - Required fields: title, conference, year, status, duration, tags
   - All fields must be present even if empty (use `[]` for empty tags)

## Manual Validation Checklist

Before each commit, verify:

- [ ] Frontmatter has all required fields (title, conference, year, status, duration, tags)
- [ ] Status values are lowercase: `accepted`, `rejected`, or `pending`
- [ ] Year is a valid 4-digit number
- [ ] Duration is one of: `30min`, `45min`, `60min`
- [ ] All external URLs are accessible (no 404s)
- [ ] Markdown renders without errors
- [ ] No broken internal links to other proposal files
- [ ] File follows naming convention: `{year}-{conference}-{slug}.md`

## Useful Commands

There are no build commands for this documentation-only repository:

```bash
# Preview markdown (macOS)
open README.md

# Validate YAML frontmatter (requires Python)
python -c "import yaml; yaml.safe_load(open('proposal.md').read())"
```

## Tips for Agents

- Always check existing accepted proposals for style reference
- Maintain consistent formatting across all proposals
- Keep proposal content factual and verifiable
- Include relevant context for conference organizers
- Respect speaker privacy and professional information
- When in doubt about formatting, match the style of existing accepted proposals