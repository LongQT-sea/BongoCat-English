# Contributing Guide

Thank you very much for your interest and contributions to BongoCat! Before submitting your contribution, please take some time to read the following guidelines to ensure your contribution can proceed smoothly.

## Transparent Development

All work is done publicly on GitHub. Pull Requests from both core team members and external contributors go through the same review process.

## Submitting Issues

We use [Github Issues](https://github.com/LongQT-sea/BongoCat-English/issues) for bug reports and new feature suggestions. Before submitting an issue, please make sure you have searched for similar problems, as they may have already been answered or are being fixed. For bug reports, please include complete steps that can be used to reproduce the problem. For new feature suggestions, please specify the changes you want and the expected behavior.

## Submitting Pull Requests

### Collaboration Process

- Claim an issue: Create an issue on Github and claim it (or directly claim an existing issue), informing everyone that you are fixing it to avoid duplicate work.
- Project development: After completing the preparation work, proceed with bug fixes or feature development.
- Submit PR.

### Prerequisites

- [Rust](https://v2.tauri.app/start/prerequisites/): Please install the rust environment according to the official website steps.
- [Node.js](https://nodejs.org/en/): Used to run the project.
- [Pnpm](https://pnpm.io/): This project uses Pnpm for package management.

### Install Dependencies

```shell
pnpm install
```

### Start Application

```shell
pnpm tauri dev
```

### Build Application

> If you need to debug after packaging, please add `--debug` after the following command

```shell
pnpm tauri build
```

## Commit Guidelines

Commit messages should follow the [conventional-changelog standard](https://www.conventionalcommits.org/en/v1.0.0/).

### Commit Types

Here is a list of commit types:

- feat: New features or functionality
- fix: Bug fixes
- docs: Documentation updates
- style: Code style updates
- refactor: Code refactoring, without introducing new features and bug fixes
- perf: Performance optimization
- chore: Other commits

We look forward to your participation, let's make BongoCat better together!