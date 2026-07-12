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

Node.js and npm are required to install and run Tailwind CSS.

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

Install the dependencies declared in `package.json`:

```bash
npm install
```

This installs Tailwind CSS and its command-line interface locally for the project.

Do not install Tailwind CSS globally.

## Check the contribution guide

Before making your first commit, read the contribution guide:

[CONTRIBUTING.md](../CONTRIBUTING.md)

## Run the development environment

From the `hugo/` directory, start the Tailwind CSS watcher:

```bash
npm run dev
```

Keep it running while editing the styles.

In another terminal, from the same directory, start the Hugo development server:

```bash
hugo server
```

The local website will be available at:

```text
http://localhost:1313
```

## Production build

From the `hugo/` directory, generate the minified Tailwind stylesheet:

```bash
npm run build
```

Then generate the website:

```bash
hugo
```

The generated website will be written to `hugo/public/`.

## Troubleshooting

If a required tool is missing or a command fails, ask a more experienced team member before spending time troubleshooting. There is little value in repeating issues that have already been solved by the team.
