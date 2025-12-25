# Repository Guidelines

## Project Structure & Module Organization
- `src/`: core C++ library, Python bindings, and examples (`src/examples/`).
- `test/`: test suites and fixtures; Python tests live under `test/src/pythontests`, and C++ tests are grouped under `test/src/unittests` and related folders.
- `doc/`: documentation sources and contributor references in `doc/sphinxdoc/`.
- `packaging/`, `debian/`, `utils/`, `.github/`, `travis/`: build, CI, and packaging helpers.
- Build outputs appear in `build/` after running waf (not checked in).

## Build, Test, and Development Commands
- `python3 waf configure --build-static --with-python --with-examples --with-cpptests`: configure a full local build (adjust flags as needed).
- `python3 waf`: compile everything configured.
- `python3 waf install`: install library, bindings, and extractors to your system.
- `python3 waf run_tests`: run C++ base unit tests.
- `python3 waf run_python_tests`: run Python algorithm tests (requires Python bindings and extra test data).
- `python3 waf doc`: build Sphinx docs into `doc/sphinxdoc/_build/html/`.
- `python3 waf --help`: list all configuration flags.

## Coding Style & Naming Conventions
- Spaces only; no tabs. Indent with 2 spaces in C++ and 4 spaces in Python.
- Braces stay on the same line (except function definitions may vary); `else` starts on a new line.
- Commas are followed by a space; keep operator spacing readable.
- Prefer `const` references for read-only parameters; use `bool` for booleans and `Real` for real numbers.
- Names are not abbreviated; sizes end with `Size`. Classes use `CamelCase`; parameters use `camelCase` with a lowercase first letter. Identifiers are case-sensitive.

## Testing Guidelines
- Follow the existing layout and naming in `test/src/` (for example, `test_*.py` and `*_test.py` in `test/src/pythontests`).
- Some Python tests require extra assets and models; use the `essentia-audio` and `essentia-models` repos as described in `doc/sphinxdoc/installing.rst`.

## Commit & Pull Request Guidelines
- Commits should be one semantic change with clear, descriptive subjects (imperative mood is common; scoped prefixes like `cibuildwheel:` appear in history).
- Contributions must comply with the Developer's Certificate of Origin; for changes over 20 lines, provide the signed CLA scan per `doc/sphinxdoc/contribute.rst`.
- PRs should include a short description, motivation, and relevant test evidence; link related issues when applicable.
