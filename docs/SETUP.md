<!--
document: SETUP
scope: development
status: active
version: 1.0
updated: 2026-10-01T21:00+02:00
-->

# Development Setup

This project uses Hugo to generate the website and Tailwind CSS for styling.

## Requirements

Install the following tools before working on the project:

* Git
* Hugo (Extended edition)
* Node.js and npm
* Visual Studio Code (recommended)

## Install Hugo

This project requires the **Extended edition** of Hugo.

Verify whether Hugo is already installed:

```bash
hugo version
```

The output must contain `extended`.

### Windows

Recommended:

```powershell
winget install Hugo.Hugo.Extended
```

### macOS

Recommended:

```bash
brew install hugo
```

### Linux

Use your distribution's package manager if it provides a sufficiently recent Extended build.

Otherwise, install Hugo from the official release packages.

## Install Node.js

Node.js and npm are required to provide the Tailwind CSS dependencies used by Hugo.

Verify whether they are already installed:

```bash
node --version
npm --version
```

Use a current Node.js LTS release.

### Windows

Recommended:

```powershell
winget install OpenJS.NodeJS.LTS
```

### macOS

Recommended:

```bash
brew install node
```

### Linux

Install a current Node.js LTS release using an appropriate installation method for your distribution.

## Install project dependencies

From the repository root, enter the Hugo project directory:

```bash
cd hugo
```

Install the dependencies declared in `package.json` and `package-lock.json`:

```bash
npm ci
```

This installs Tailwind CSS and its command-line interface locally for the project.

Do not install Tailwind CSS globally.

## Check the contribution guide

Before making your first commit, read the contribution guide:

[CONTRIBUTING.md](../CONTRIBUTING.md)

## Run the development environment

From the `hugo/` directory, start the Hugo development server:

```bash
hugo server
```

Hugo processes Tailwind CSS as part of its asset pipeline. No separate Tailwind watcher is required.

The local website will be available at:

```text
http://localhost:1313
```

## Production build

From the `hugo/` directory, generate the production website:

```bash
hugo --minify
```

Hugo processes and minifies the Tailwind CSS during the build.

The generated website will be written to `hugo/public/`.

This is the same build command used by the GitHub Pages deployment workflow.

## Troubleshooting

If a required tool is missing or a command fails, ask a more experienced team member before spending time troubleshooting. There is little value in repeating issues that have already been solved by the team.