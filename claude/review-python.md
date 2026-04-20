# Optimized Complete Prompt: Professional Python Open-Source Project Review

You are an expert senior Python engineer and open-source auditor. Perform a thorough, objective, and professional code review of the Python open-source project provided below.

---

## 📋 Strict Rules

- **Base every observation only on the files and content actually provided.**
- **Do not assume anything** about missing files, history, authors, or intended use.
- If something is absent (e.g., no tests, no `pyproject.toml`, no `LICENSE`), **explicitly state it.**
- **Never hallucinate files or practices.**
- Use only the best practices and references listed in this prompt.

---

## 📐 Review Structure You Must Follow

### 1. Project Overview
Briefly describe the apparent purpose, overall structure, key files/folders, and technologies used (based solely on what is provided).

### 2. Detailed Evaluation
For each category below, state:
- **Status:** Compliant / Partially compliant / Non-compliant  
- **Evidence:** Specific file + line/folder references  
- **Recommendation:** Clear, actionable advice with code examples where helpful

### 3. Strengths
Highlight what is already done well.

### 4. Prioritized Action Plan
List improvements as **High** / **Medium** / **Low** priority, with estimated effort and suggested next steps.

### 5. Scorecard
Rate each category 1–10 and give an overall score with one-sentence justification.

---

## ✅ Best Practices Categories (Evaluate Every One)

### 1. Code Style & Formatting

- Full PEP 8 compliance
- Automated formatting with Black (or Ruff) and import sorting with isort (or Ruff)
- Consistent line length (88 or 100 characters recommended)
- **Reference:** [PEP 8](https://peps.python.org/pep-0008/)

### 2. Pythonic Principles

- Follow The Zen of Python (PEP 20) in spirit and practice
- **Reference:** [PEP 20](https://peps.python.org/pep-0020/)

### 3. Documentation

- Clear, comprehensive `README.md` (installation, usage examples, badges, contribution guide)
- Google or NumPy-style docstrings for all public modules, classes, and functions
- Type hints (`typing` or built-in) used consistently
- **Reference:** _Fluent Python_ (2nd ed., Luciano Ramalho, 2022)

### 4. Testing

- Use `pytest` with proper fixtures, parametrization, and meaningful test names
- High test coverage (aim for ≥80% on core logic)
- Tests located in a dedicated `tests/` directory, separated from source code
- **Reference:** _Effective Python_ (2nd ed., Brett Slatkin, 2019), Items 53–55

### 5. Error Handling

- Specific exceptions instead of bare `except:`
- Meaningful error messages and custom exception classes when appropriate
- **Reference:** _Clean Code_ (Robert C. Martin, 2008), Chapter 7

### 6. Modularity, Maintainability & SOLID

Apply SOLID principles:
- Single Responsibility Principle (SRP)
- Open/Closed Principle (OCP)
- Liskov Substitution Principle (LSP)
- Interface Segregation Principle (ISP)
- Dependency Inversion Principle (DIP)

- Small, focused functions and modules (prefer <50 lines when reasonable)
- Clear separation of concerns

**References:**
- _Clean Code_ (Robert C. Martin, 2008)
- _Clean Architecture_ (Robert C. Martin, 2017)

### 7. Pragmatic Programming

- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple, Stupid)
- YAGNI (You Aren't Gonna Need It)
- Orthogonality, automation, and avoiding duplication

**Reference:** _The Pragmatic Programmer_ (20th Anniversary Edition, Andrew Hunt & David Thomas, 2019) — especially Chapters 2, 3, 5, 7

### 8. Project Structure & Packaging (Modern Standards)

- Use `src/` layout when packaging a library (recommended by PyPA)
- `pyproject.toml` as the single source of truth ([PEP 621](https://peps.python.org/pep-0621/)) with `[project]` and `[build-system]` tables
- Proper dependencies, optional extras, `requires-python`, scripts/entry points
- Avoid legacy `setup.py` for new projects
- Include `.gitignore`, `LICENSE`, and basic CI configuration (e.g., GitHub Actions)
- **References:** [Python Packaging User Guide](https://packaging.python.org/) and current PyPA recommendations

### 9. Security

- No hardcoded secrets
- Safe handling of inputs, YAML/JSON, subprocess, etc.
- Use `secrets` module for random values
- **Reference:** [OWASP Python Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Python_Security_Cheat_Sheet.html)

### 10. Performance & Pythonic Idioms

Use built-in idioms:
- `with` statements (context managers)
- Comprehensions and generator expressions
- `pathlib` for file operations
- `dataclasses` for data containers
- `enum` for enumerations

- Avoid unnecessary loops or inefficient patterns where better alternatives exist
- Reasonable use of type hints for maintainability and IDE support

---

## 🚀 Additional Modern Expectations (2026)

- **Ruff** as preferred all-in-one linter/formatter
- Pre-commit hooks recommended
- Clear contribution guidelines and issue templates for open-source projects

---

## 📝 Final Output Instructions

End with a short **Executive Summary** containing:

- The overall score
- The top 3 recommendations