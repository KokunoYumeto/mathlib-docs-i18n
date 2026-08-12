# mathlib documentation internationalization sidecar

This independent sidecar is for AI-produced translations of mathlib docstrings,
module documentation, tutorials, and theorem explanations. Formal Lean source,
identifiers, declarations, and proofs remain in the exact upstream repositories.

It is not an official leanprover-community or mathlib project. The upstream
authors and maintainers have not requested, reviewed, approved, or endorsed its
translations.

## Identity model

- Declaration documentation is keyed by the fully qualified Lean declaration
  name from one exact mathlib commit, for example `Mathlib.Algebra...foo`.
- Module prose without a declaration is keyed by exact module path plus a
  content-addressed anchor.
- Every record also binds the source file, source-content SHA-256, upstream
  commit, locale, translation hash, terminology decisions, and status.
- A translation record has `formal_code_changed: false` by construction.
- Renames and moved declarations create explicit supersession records; they do
  not silently reuse an identifier.

Exact upstream pointers are in [`upstream/`](upstream/). The initial translation
registry is empty.

Every published output must say:

> Independently maintained, AI-produced translation. No endorsement by mathlib,
> Lean, leanprover-community, or upstream authors is claimed or implied.

