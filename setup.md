---
title: Setup
---

## Installing uv

The first requirement for this workshop is uv which is an extremely fast Python package and project manager tool. It is a direct replacement for tools like pip, pip-tools, pipx, poetry, pdm, and more. Installation instructions are given in the [uv documentation](https://docs.astral.sh/uv/getting-started/installation/) but the main macOS, Linux, and Windows installation commands are presented below.

Install uv on macOS and Linux with:

```bash
$ curl -LsSf https://astral.sh/uv/install.sh | sh
```

Install uv on Windows with:

```bash
$ powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

You may need to restart your terminal to ensure that uv was installed. Check the installation by displaying the version number using the `--version` option as shown below. If the command displays the uv version number then the installation was successful.

```bash
$ uv --version
```

```output
uv 0.8.4 (e176e1714 2025-07-30)
```

## Installing Ruff

Another requirement for this workshop is the [Ruff](https://docs.astral.sh/ruff/) tool for code linting and formatting. There are many ways to install Ruff depending on how you plan to use the tool. Ruff can be executed directly with the following uv command

```bash
$ uvx ruff check
```

Or use uv to install Ruff as a command line tool with

```bash
$ uv tool install ruff
```

Editors such as Sublime Text, Zed, Neovim, Visual Studio Code, and others support Ruff through extensions or plugins.
