# Manhattan Project  
*A PixelMyNixel Open‑Source Template – v0.1.0*

> **Tagline:** *Clone → configure → ship.*  An AI‑accelerated full‑stack starter that sets sane defaults for multiple frameworks (Flask, FastAPI, Django, CLI), with support for documentation, CI, security, and an adhoc workflow for ticket‑scoped scripts.

---
## 🔗 Quick Links
| Resource | Description |
|----------|-------------|
| **🗂 Directory Structure** | [`docs/DIRECTORY_STRUCTURE.md`](docs/DIRECTORY_STRUCTURE.md) |
| **🤝 Contributing** | [`CONTRIBUTING.md`](CONTRIBUTING.md) |
| **🎫 Issue Templates** | `.github/ISSUE_TEMPLATE/` |
| **📜 Changelog** | [`CHANGELOG.md`](CHANGELOG.md) |
| **🌐 Org Home** | <https://github.com/pixelmynixel> – other projects & roadmap |
| **Landing Site** (WIP) | <https://pixelmynixel.com> |

---
## 💡 Why Manhattan Project?
PixelMyNixel builds nostalgic media tools (e.g. **ShelfSnap** – physical‑media collector app). We needed a **repeatable, AI‑friendly scaffold**.  Now you can:

* Clone / use template in seconds with your preferred framework.
* Let Cursor, Copilot, or ChatGPT refactor with consistent style.
* Choose a framework "flavor" (Flask, FastAPI, Django, CLI) while keeping the same project structure.
* Ship back‑end + optional mobile front‑end with the same CI.

---
## 📂 Project Layout (after `init_project.py`)
```
manhattan-project/
├─ src/                  # Main application code (framework-specific)
├─ adhoc/                # Ticket-scoped scratch scripts (CI‑ignored)
│   └─ archived/         # Frozen scripts for reference
├─ scripts/              # Core CLI helpers (init_project.py, seed_db.py)
├─ templates/            # Project flavor templates (flask, fastapi, etc.)
├─ tests/                # Test suites mirroring src/
├─ config/               # .env.example, YAML configs, docker-compose.yml
├─ assets/               # Static assets (optional)
├─ docs/                 # Documentation (markdown files, API docs, etc.)
├─ .github/
│   └─ workflows/ci.yml  # Ruff, MyPy, pytest, Expo build
├─ tickets/              # Project tickets with MP-XXX prefix
├─ requirements.txt      # Locked back‑end deps
├─ VERSION               # Semantic version file
└─ CHANGELOG.md
```

> **Note:** The `templates/flavors/` directory contains framework-specific templates. You can safely remove this directory if your project uses only one framework.

---
## 🏁 Getting Started
### 1. Use as template (GitHub UI)
1. **Use this template ▸ Create a new repository** under your account or org.
2. Clone locally **or** open in Cursor Codespace.
3. Follow *Project Bootstrap* below.

### 2. Project Bootstrap (local)
```bash
# clone
git clone https://github.com/<you>/my-new-app.git && cd my-new-app

# Python env
python -m venv venv && source venv/bin/activate    # Windows: venv\Scripts\activate
pip install -r requirements.txt

# Initialise with your preferred framework flavor
python scripts/init_project.py \
       --name   "My New App" \
       --author "<Your Name>" \
       --ticket MP-001 \
       --flavor flask     # Options: flask, fastapi, django, cli

pytest -q        # ✓ all green
```
*(Cursor users: open the folder; it auto‑detects the `venv` and test runner.)*

---
## 🏗️ Framework Flavors

Manhattan Project supports multiple frameworks through "flavors":

| Flavor | Best For | Command to Run |
|--------|----------|----------------|
| **flask** | Web apps, APIs | `python src/app.py` |
| **fastapi** | Modern APIs, Microservices | `uvicorn src.main:app --reload` |
| **django** | Complex web apps | `python src/manage.py runserver` |
| **cli** | Command-line tools | `python src/main.py` |

Each flavor maintains the same core project structure while adapting the `src/` directory for framework-specific conventions.

---
## 📄 Boilerplate Files

Manhattan Project includes several boilerplate/template files that help maintain consistency:

| File | Purpose |
|------|---------|
| **README.md** | Main project documentation (this file) |
| **CONTRIBUTING.md** | Contributing guidelines |
| **CHANGELOG.md** | Version history and changes |
| **docs/DIRECTORY_STRUCTURE.md** | Project structure guide |
| **tickets/TEMPLATE.md** | Template for new ticket files |
| **VERSION** | Current semantic version |

During `init_project.py`, these boilerplate files are customized for your specific project. You can safely customize them further to match your project's needs.

---
## 🔧 Prerequisites
| Tool | Minimum | Notes |
|------|---------|-------|
| **Python** | 3.9 | Back‑end & CLI scripts |
| **Node/npm** *(optional)* | 20 LTS | For React/Expo mobile front‑end |
| **Git** | 2.30 | |
| **Docker** *(optional)* | latest | Dev/prod parity via `docker-compose.yml` |

---
## 🔢 Versioning Policy (SemVer)
| Segment | Meaning |
|---------|---------|
| **MAJOR** x.0.0 | Breaking API changes |
| **MINOR** 0.x.0 | Backward‑compatible features |
| **PATCH** 0.0.x | Bug fixes |

Update **VERSION**, badge in README, and **CHANGELOG.md**. Tag release:
```bash
git tag -a vX.Y.Z -m "vX.Y.Z" && git push origin vX.Y.Z
```

---
## 🧪 Testing & CI
* **Pytest** for back‑end.
* **Ruff + Black** for lint/format.
* **MyPy** for type safety.
* **GitHub Actions** CI runs on push & PR; status checks required before merge.

---
## 🎫 Issue / Ticket Conventions
* Ticket ID format: `MP-123` (Manhattan Project) or project‑specific key (`SS-456`).
* PR titles: `feat: MP-123 short description` (Conventional Commits).
* Cursor‑generated adhoc scripts: `adhoc/MP-123_description.py`.

---
## 🔒 Security
* No secrets in VCS – use `.env` + GitHub Secrets.
* SQLAlchemy parameterised queries by default.
* Dependabot alerts enabled.

For vulnerabilities, see [`SECURITY.md`](SECURITY.md).

---
## 📜 License
MIT © PixelMyNixel 2025.  See [`LICENSE`](LICENSE).

*Happy coding & may your pixels be ever nixel‑perfect!*
