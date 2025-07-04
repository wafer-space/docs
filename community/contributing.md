# Contributing to Community Documentation

Thank you for your interest in contributing to the wafer.space community documentation! This guide will help you add your knowledge and experiences to our growing resource collection.

## Before You Begin

### What Makes Good Community Content?

The best community contributions are:

- **Practical** - Based on real experience with wafer.space or GF180MCU PDK
- **Detailed** - Include specific steps, code examples, or screenshots
- **Original** - Your own work or properly attributed content
- **Helpful** - Solve real problems or share valuable insights
- **Clear** - Well-organized and easy to understand

### Content Guidelines

✅ **DO contribute:**
- Project postmortems and lessons learned
- Workflow improvements and automation scripts
- Debugging experiences and solutions
- Design techniques and optimizations
- Tool integration guides
- Performance benchmarks and comparisons

❌ **DON'T contribute:**
- Copyrighted material without permission
- Promotional content or advertisements
- Unverified claims or speculation
- Off-topic content unrelated to IC design
- Personal attacks or inappropriate content

## How to Contribute

### Method 1: GitHub Pull Request (Recommended)

1. **Fork the repository**
   ```bash
   # Fork the documentation repository on GitHub
   # Clone your fork locally
   git clone https://github.com/YOUR-USERNAME/wafer-space.readthedocs.org.git
   cd wafer-space.readthedocs.org
   ```

2. **Create a new branch**
   ```bash
   git checkout -b community/your-contribution-name
   ```

3. **Add your content**
   - Place your markdown files in the appropriate subdirectory under `community/`
   - Follow the naming convention: `your-topic-name.md`
   - Include any images in a subfolder with the same name

4. **Test your changes**
   ```bash
   # Build the documentation locally
   make html
   # View at _build/html/index.html
   ```

5. **Submit a pull request**
   - Push your branch to your fork
   - Create a pull request with a clear description
   - Wait for review and address any feedback

### Method 2: GitHub Issue

If you're not comfortable with Git:

1. Open a new issue in the repository
2. Use the "Community Contribution" template
3. Paste your content in markdown format
4. A maintainer will help integrate your contribution

## Content Structure

### File Organization

```
community/
├── index.md                    # Main community page (don't edit)
├── contributing.md             # This file (don't edit)
├── case-studies/
│   ├── index.md               # Case studies index
│   └── your-project-name.md   # Your case study
├── tips-and-tricks/
│   ├── index.md               # Tips index
│   └── your-tip-topic.md      # Your tips
├── workflows/
│   ├── index.md               # Workflows index
│   └── your-workflow.md       # Your workflow guide
├── troubleshooting/
│   ├── index.md               # Troubleshooting index
│   └── solving-x-problem.md   # Your solution
└── success-stories/
    ├── index.md               # Success stories index
    └── your-success-story.md  # Your story
```

### Markdown Template

Use this template as a starting point for your contribution:

```markdown
# Your Title Here

*Author: Your Name (optional: your GitHub username)*  
*Date: YYYY-MM-DD*  
*Category: [Case Study|Tips|Workflow|Troubleshooting|Success Story]*

## Overview

Brief introduction to what this document covers and why it's useful.

## Background/Context

Any necessary background information or prerequisites.

## Main Content

Your detailed content here. Use clear sections and subsections.

### Code Examples

```language
# Include code examples with syntax highlighting
your code here
```

### Images

When including images, organize them in a folder with the same name as your document:

```
community/
├── your-contribution/
│   ├── your-contribution.md
│   └── images/
│       ├── diagram1.png
│       └── screenshot.png
```

Then reference them in your markdown:

```markdown
![Descriptive alt text](images/diagram1.png)
```

## Results/Outcomes

What were the results? What did you learn?

## Resources and References

- List any helpful links
- Credit sources and collaborators
- Link to your project repository if applicable

## Questions or Feedback?

*Feel free to reach out to me at [your contact method] or open an issue on the documentation repository.*
```

## Writing Style Guide

### General Guidelines

1. **Use clear headings** - Help readers navigate your content
2. **Include examples** - Show, don't just tell
3. **Define acronyms** - Not everyone knows every term
4. **Use lists** - Break down complex information
5. **Add visuals** - Diagrams and screenshots help understanding

### Technical Writing Tips

- Start with the problem you're solving
- Provide step-by-step instructions
- Include command-line examples in code blocks
- Mention version numbers for tools
- State assumptions explicitly
- Include troubleshooting sections

### Code Formatting

Always use fenced code blocks with language specification:

````markdown
```python
def example_function():
    return "Use syntax highlighting!"
```

```bash
# Shell commands should be clearly marked
cd /path/to/project
make clean
```

```verilog
// Verilog code with proper highlighting
module example(
    input clk,
    output reg led
);
```
````

## Review Process

After you submit your contribution:

1. **Initial Review** - Maintainers check for guidelines compliance
2. **Technical Review** - Community members may provide feedback
3. **Revisions** - You may be asked to clarify or expand sections
4. **Approval** - Once approved, your content is merged
5. **Publication** - Your contribution goes live!

## Recognition

Contributors are recognized in several ways:

- Author attribution on your contributed pages
- Mention in the repository's CONTRIBUTORS file
- Community contributor badge (coming soon)

## Need Help?

If you need assistance with your contribution:

- Open a "Help Wanted" issue in the repository
- Ask in the wafer.space Discord #documentation channel
- Review existing contributions for examples

## License

By contributing to this documentation, you agree that your contributions will be licensed under the same license as the main project (typically Creative Commons or similar).

---

*Thank you for helping build a valuable resource for the open source silicon community! Your contributions make a difference.*