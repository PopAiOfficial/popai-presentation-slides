# PopAI Presentation Skill

A Cursor skill for generating professional presentations (PPTX) via [PopAI](https://www.popai.pro) API.
PopAI has built-in research capabilities - it will automatically search, collect, and organize relevant content into a polished slide deck.

## Setup

1. Sign up / sign in at [https://www.popai.pro/popai-skill](https://www.popai.pro/popai-skill)
2. Copy your **Access Token** from the PopAI Skill page
3. Export the token in your shell:

```bash
export POPAI_ACCESS_TOKEN=<your_token>
```

## Usage

> **Important:** The `--query` must be a **meaningful presentation topic** (e.g. "2025 Global AI Industry Trends and Investment Outlook"). Vague or irrelevant queries such as `"test"`, `"hello"`, or `"asdf"` will cause the generation to fail. The API needs a real topic to research and build slides from.

```bash
# Generate from a specific topic
python3 skills/popai-powerpoint-pptx/generate_ppt.py --query "2025 Global AI Industry Trends and Investment Outlook"

# With reference files (max 5)
python3 skills/popai-powerpoint-pptx/generate_ppt.py --query "Tesla Q4 2024 Earnings Summary" --file earnings.pdf revenue_chart.png

# With a custom .pptx template (preserves layout & styles)
python3 skills/popai-powerpoint-pptx/generate_ppt.py --query "Annual Sustainability Report for Acme Corp" --tpl branded_template.pptx

# Multi-round modification on an existing deck
python3 skills/popai-powerpoint-pptx/generate_ppt.py --channel-id "CHANNEL_ID" --query "Add a competitive analysis slide and switch the color scheme to dark blue"
```

## Project Structure

```
skills/
  popai-powerpoint-pptx/
    SKILL.md          # Skill definition & agent workflow instructions
    generate_ppt.py   # CLI script for PPT generation
```

## Features

- **Topic-based generation** — provide a topic and get a complete deck with researched content
- **Reference files** — upload PDFs, images, or documents as source material (`--file`)
- **Template support** — supply your own `.pptx` template for 100% layout fidelity (`--tpl`)
- **Multi-round editing** — refine an existing deck by passing `--channel-id` with new instructions
- **URL references** — include URLs directly in the query for the API to fetch and process

## More Capabilities

For the full list of capabilities, agent workflow details, output event formats, and multi-round modification rules, see [`skills/popai-powerpoint-pptx/SKILL.md`](skills/popai-powerpoint-pptx/SKILL.md).

## Support

For issues or questions, contact **customerservice@popai.pro**
