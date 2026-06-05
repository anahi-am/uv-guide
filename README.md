## Why UV?

Python used to require several tools to set up a project. `uv` replaces all of them in a single tool.
The main benefit is consistency. `uv` generates a uv.lock file, which records the exact version of every package installed — so every machine, every CI run (automated tests that run in the cloud), and every deployment (when you push your app to a server) works from the exact same environment. No more "it works on my computer...".
Every uv add or uv remove automatically updates pyproject.toml, resolves dependencies, and rewrites the lockfile in one step, no manual edits needed.

## What is it?

`uv` is a Python dependency manager written in Rust, which makes it much faster than `pip`.
It manages everything: the project's Python version, the virtual environment, and the dependencies themselves (the external packages your code needs to run).

## Installation

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## Usage

**Initialize a new project:**

```bash
uv init
```

**Create a virtual environment and install dependencies:**

```bash
uv venv
uv sync
```

**Activate the environment:**

```bash
# macOS / Linux
source .venv/bin/activate

# Windows
.venv\Scripts\activate
```

**Add a new package:**

```bash
uv add <package-name>
```

**Remove a package:**

```bash
uv remove <package-name>
```

**Run a script or command inside the environment:**

```bash
uv run python main.py
uv run pytest
```
uv run executes anything inside the project environment, automatically verifying it's in sync with the lockfile before running, so you're always using the correct dependencies.

**Update all dependencies:**

```bash
uv sync --upgrade
```

This updates both the virtual environment and `pyproject.toml` automatically.

---

## Interesting Articles

- [uv — Official Repository ](https://github.com/astral-sh/uv) —  The source code and full documentation for uv, by Astral. Good reference for advanced features, changelogs, and benchmarks.
- [Python dependencies with uv](https://vladfilippov.com/python-dependencies-with-uv/) — A practical day-to-day workflow guide for uv, covering everything from adding dependencies to CI/CD integration and deployment.
- [uv: A Guide to Python Package Management](https://flocode.substack.com/p/044-python-environments-again-uv) — Beginner-friendly walkthrough of uv for data/engineering workflows, with a focus on VS Code and Jupyter Notebooks.
- [Production-ready Python Docker Containers with uv](arthttps://hynek.me/articles/docker-uv/) — Advanced guide on building optimised Docker containers with uv, covering multi-stage builds, layer caching, and production best practices.

