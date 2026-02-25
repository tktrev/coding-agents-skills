---
name: readme-generator
description: Analyze codebase and generate or update README.md with project information
license: MIT
compatibility: opencode
metadata:
  audience: developers
  workflow: documentation
---

## What I do

1. **Analyze project structure**: Examine directory layout, source files, and configuration
2. **Detect project type**: Identify language/framework from package.json, Cargo.toml, go.mod, requirements.txt, etc.
3. **Extract metadata**: Get project name, description, scripts, dependencies from config files
4. **Check existing README**: Review current README.md content if it exists
5. **Generate README**: Create comprehensive README with appropriate sections
6. **Show preview**: Display generated content for confirmation before writing

## When to use me

Use this when you want to:
- Create a new README.md for a fresh project
- Update an existing README to reflect current codebase state
- Add missing sections like installation, usage, or API docs
- Generate documentation based on project structure

## How to use

1. Load this skill: `skill({ name: "readme-generator" })`
2. I'll analyze your project structure and config files
3. I'll show you what I found and what sections I'll include
4. You'll confirm or specify what to include
5. I'll generate the README and show a preview
6. You can edit before I write it to README.md

## Project Analysis Steps

### 1. Detect Project Type

Check for:
- `package.json` - Node.js/npm project
- `Cargo.toml` - Rust project
- `go.mod` - Go project
- `requirements.txt` / `pyproject.toml` - Python project
- `pom.xml` / `build.gradle` - Java project
- `*.csproj` - C#/.NET project
- `Gemfile` - Ruby project

### 2. Extract Project Info

From config files:
- **Name**: project name
- **Description**: from config or prompt user
- **Version**: current version
- **Scripts**: build, test, start commands
- **Dependencies**: key dependencies
- **License**: from LICENSE file or config

### 3. Analyze Structure

- List root directory contents
- Identify src/, lib/, app/, tests/ directories
- Check for docs/, examples/, scripts/ folders
- Look for main entry points

### 4. Generate README Sections

Based on project type, include:
- **Title & Badges**: name, version, license, CI status
- **Description**: what the project does
- **Features**: key capabilities
- **Prerequisites**: required tools/versions
- **Installation**: how to install
- **Usage**: basic usage examples
- **API**: for libraries, document public interfaces
- **Configuration**: config options if applicable
- **Development**: how to contribute/run dev mode
- **Testing**: how to run tests
- **License**: license info
- **Directory Structure**: overview of code organization

## Output Format

Generated README follows common conventions:
- Markdown format
- Badge placeholders for CI/CD
- Code blocks for examples
- Tables for options/CLI flags
- Link references for dependencies

## Options

- **Update only**: Tell me "update" to only modify existing README sections
- **Minimal**: Tell me "minimal" to create a bare-bones README
- **Detailed**: Tell me "detailed" to include all possible sections
- **Custom sections**: Specify which sections to include

## Example

User: "Generate README for this project"
Skill finds: Node.js project with package.json, tests/, README exists
Action: Analyze existing README, update with current package.json info, add missing sections
