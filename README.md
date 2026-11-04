# mathlib documentation translations: a registry for translated Lean documentation

A registry and record format for AI-produced translations of the documentation of mathlib, the Lean 4 mathematics
library, and of the *Mathematics in Lean* tutorial: docstrings, module documentation, tutorials and theorem
explanations, each keyed to one exact upstream commit. The Lean source code, declarations and proofs stay in the
upstream repositories and are never changed here.

## Status

The registry is set up but empty: no locale and no translation has been added, and there is no release.

## How records are identified

- Declaration documentation is keyed by the fully qualified Lean declaration name in one exact mathlib commit, for
  example `Mathlib.Algebra...foo`.
- Module prose without a declaration is keyed by the module path plus a content-addressed anchor.
- Every record also names the source file, the SHA-256 of the source content, the upstream commit, the locale, the
  hash of the translation, the terminology decisions and the status.
- A translation record has `formal_code_changed: false` by construction.
- Renamed or moved declarations get explicit supersession records; an identifier is never silently reused.

## Contents

- [upstream/](upstream/): the exact upstream commits of mathlib4 and *Mathematics in Lean*, with the hashes of their
  licence files.
- [registry/](registry/): the translation and release registries (empty).
- [schemas/](schemas/): JSON schemas for translation records and release manifests.
- [locales/](locales/README.md): one folder per language, holding translated prose only.
- [releases/](releases/README.md): releases, each bound to exact upstream commits and translation records.

Every published translation carries the notice: "Independently maintained, AI-produced translation. No endorsement by
mathlib, Lean, leanprover-community, or upstream authors is claimed or implied."

## Sources and credits

- [mathlib4](https://github.com/leanprover-community/mathlib4) and
  [Mathematics in Lean](https://github.com/leanprover-community/mathematics_in_lean), by the leanprover-community and
  their authors, both under the Apache License 2.0.

## Rights

Translated upstream documentation keeps the Apache 2.0 notices and attribution of its source. The repository's own
translation prose and code are offered under the Apache License 2.0, and its own factual metadata and schemas are
also dedicated to the public domain under CC0 1.0; see [LICENSE](LICENSE) and [RIGHTS.md](RIGHTS.md).
