---
name: readme
description: Analyze codebase and generate or update README.md with project information. Use when creating a new README or updating an existing one to reflect current project state.
disable-model-invocation: true
allowed-tools: Bash, Read, Glob
---

## What I do

1. **Analyze project structure**: Examine directory layout, source files, and configuration
2. **Detect project type**: Identify language/framework from package.json, Cargo.toml, go.mod, requirements.txt, etc.
3. **Extract metadata**: Get project name, description, scripts, dependencies from config files
4. **Check existing README**: Review current README.md content if it exists
5. **Detect codebase changes**: Analyze recent git changes to understand what's new or modified
6. **Generate README**: Create comprehensive README with appropriate sections
7. **Update existing README**: Edit current README.md to reflect codebase changes
8. **Show preview**: Display generated content for confirmation before writing

## How to use

Invoke me directly with `/readme`:
- `/readme` - generate a new README for the project
- `/readme update` - update existing README based on recent changes
- `/readme minimal` - create a bare-bones README
- `/readme detailed` - include all possible sections

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
