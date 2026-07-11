# Development Setup

This project uses Hugo to generate the website and Tailwind CSS for styling.

## Requirements

Install the following tools before working on the project:

* Git
* Hugo (Extended edition)
* Node.js (LTS)
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

Node.js is required to install and run Tailwind CSS.

Verify whether Node.js and npm are already installed:

```bash
node --version
npm --version
```

Use a current **LTS release** of Node.js.

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

Install the current Node.js LTS release using your distribution's package manager or another suitable installation method.

## Install project dependencies

Tailwind CSS is installed locally as a project dependency.

From the repository root, run:

```bash
npm install
```

This installs the dependencies declared in `package.json`.

Do not install Tailwind CSS globally.

## Configure the repository

Follow the contribution guide before making your first commit:

[CONTRIBUTING.md](../CONTRIBUTING.md)

## Run the development environment

From the repository root, start the Tailwind development process:

```bash
npm run dev
```

In another terminal, start the Hugo development server:

```bash
hugo server
```

The local website will be available at:

```text
http://localhost:1313
```

## Production build

Generate the Tailwind CSS production output:

```bash
npm run build
```

Then build the Hugo website:

```bash
hugo
```

The generated website will be written to the `public/` directory.

## Troubleshooting

If a required tool is missing or a command fails, ask a more experienced team member before spending time troubleshooting. There is little value in repeating issues that have already been solved by the team.
