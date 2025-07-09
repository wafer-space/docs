# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Sphinx-based documentation project for wafer.space end user documentation. The documentation uses:
- **Sphinx** as the documentation generator
- **Furo** theme for styling
- **MyST Parser** for Markdown support
- **Cogapp** for code generation

## Common Commands

### Build Documentation
```bash
# Build HTML documentation
make html

# Clean build directory and rebuild
make clean html

# Build other formats
make latexpdf  # PDF via LaTeX
make epub      # EPUB format
```

### Development Server
```bash
# Live reload server for development
make livehtml
# OR
sphinx-autobuild -b html . _build
```

### Install Dependencies
```bash
# Setup virtual environment and install dependencies
make setup

# Or just install dependencies in current environment
make install

# Clean virtual environment
make clean-venv
```

## Architecture Notes

### Documentation Structure
- Main entry point: `index.md` - Contains the master table of contents
- Configuration: `conf.py` - Sphinx configuration with project metadata and extension settings
- Build output: `_build/` directory (gitignored)
- Templates: `_templates/base.html` for custom HTML modifications

### Key Configuration Details
- Uses MyST parser with colon_fence extension enabled for enhanced Markdown features
- Git-based versioning automatically extracted from tags
- Source files use `.rst` suffix by default but `.md` files are supported via MyST
- Theme: Furo (modern, responsive documentation theme)

### Adding New Pages
1. Create new `.md` files in the root directory
2. Add the filename (without extension) to the toctree in `index.md`
3. The documentation will automatically include the new page in the build

### Important Build Behavior
- The build process uses `git describe --tags --always` to determine version numbers
- All Markdown files support MyST syntax including directives and roles
- The project name "wafer.space End User Documentation" is used throughout the build

## Git Workflow

### Branch Management
- When making changes, start a new git branch and then make sure to commit to the git repository frequently as you work
- Once the work has been completed ask the user if you should merge the created branch into the main branch
- Don't delete the branches after merging
- When merging the branches to main, make sure to not fast forward

## Automated Testing

### Link Checking
- All pull requests automatically trigger link checking via GitHub Actions
- The workflow waits for ReadTheDocs preview deployment, then uses muffet to validate all links
- Both internal navigation and external references are tested
- PR comments show results and detailed reports are available as workflow artifacts
- Broken links will fail the PR status checks and prevent merging