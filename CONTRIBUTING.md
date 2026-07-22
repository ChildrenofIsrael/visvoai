# Contributing to visvoai

Welcome — and thank you. This guide is written for beginners and for anyone who brings care, intuition, and wisdom to their work. Contribute at your own pace; small, clear steps are better than fast, confused ones.

Spirit & intention
- Work with calm curiosity. If something is unclear, pause, ask, and document what you learned.
- Treat contributions as learning opportunities: every doc fix, test, or small improvement moves the project (and you) forward.

Quick setup (fork → clone → upstream)
1. Fork the repository on GitHub.
2. Clone your fork:
   - SSH:
     git clone git@github.com:<your-github-username>/visvoai.git
   - HTTPS:
     git clone https://github.com/<your-github-username>/visvoai.git
3. Enter the repo and add upstream:
   cd visvoai
   git remote add upstream https://github.com/ChildrenofIsrael/visvoai.git
4. Sync and create a branch:
   git fetch upstream
   # find upstream default branch with: git remote show upstream
   git checkout -b feat/setup-dev upstream/main

Python dev environment (simple)
1. Create and activate a venv:
   python -m venv .venv
   source .venv/bin/activate   # Windows: .venv\Scripts\activate
2. Upgrade packaging tools:
   pip install -U pip build setuptools wheel
3. Install packages in editable mode:
   pip install -e packages/visvoai-core
   pip install -e "packages/visvoai-ai[openai]"  # optional extras
   pip install -e packages/visvoai-cli

Notes:
- The repo uses PEP 420 namespace packages (visvoai.*). Do not add a top-level __init__.py in the namespace root.
- Install only the provider extras you need.

Run linters & tests
1. (Optional) Install pre-commit and run:
   pip install pre-commit
   pre-commit install
   pre-commit run --all-files
2. Run package tests:
   pytest -q packages/visvoai-core
   pytest -q packages/visvoai-ai
   pytest -q packages/visvoai-cli

If tests fail: copy the failing pytest output into the PR or an Issue — that makes it much easier to diagnose and help.

Beginner-friendly first contributions
- Fix a typo or clarify a README snippet.
- Improve a docstring or add an example to a README.
- Fix a small failing test you encounter while setting up.
- Add a brief note to this file if something in these steps was unclear.

Branch & commit guidance
- Branch name: feat/<short-desc> or fix/<short-desc>
  Example: feat/setup-dev or fix/readme-typo
- Commit message style:
  type(scope): short summary
  body (optional, wrap at ~72 chars)

Example:
```bash
git checkout -b fix/readme-typo
git add README.md
git commit -m "docs(readme): fix typo in setup steps"
git push -u origin fix/readme-typo
```

Pull request checklist
- Target the upstream default branch (main).
- Include a short description of what you changed and why.
- Run tests locally and mention results.
- If behavior changed, add or update tests; if not, explain.

If you want help
- I can commit this file and open a PR to the repo for you.
- Or I can walk you through the git commands step-by-step while you run them locally.
- If something breaks, paste the exact output and Ill help debug.

Thank you for contributing thoughtfully — every small step counts.
