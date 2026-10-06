# Logic Correctness Protocol

Use for any problem with real logic: algorithms, validation, scoring, scheduling, calculators, ranking, parsing, rule engines. If the problem is mostly forms or presentation, skip to a light version (validate inputs, test the few calculations).

Time cap: about 10–15 minutes for the engine and tests. This pays back many times over in debugging.

## 1. Separate logic from UI

- Put core logic in a pure module (no DOM, no framework state). Example shape: `engine(input, state) -> result`.
- Return **error codes and data**, not display strings. The UI translates codes into Bangla/English. This keeps validation errors bilingual.
- Never mutate the original input. Keep the originally loaded data separate from working state so Reset can restore it exactly.

## 2. Tests first from the statement

Add a test runner early (for Vite: `npm i -D vitest`, then `npm test`).

Test tiers:

1. **Sample checks** from the statement, verbatim. Load fixtures from the byte-identical files in `docs/problem/samples/` (or the single copy the app uses) instead of retyping data, and take expected values from `docs/problem/SAMPLE_CHECKS.md`.
2. **Edge cases:** empty, single item, maximum size, nothing reachable/valid, everything excluded.
3. **Invalid input:** each validation rule has at least one failing fixture. Check the code returned, and that **all** errors are collected, not only the first.
4. **Determinism/ties:** equal-score cases, ordering rules, repeated runs give identical output.
5. **Boundary limits:** at the limit and just beyond.
6. **Generated unseen case:** one dataset you build yourself with different ranges/IDs than the sample.

Hard-coded sample answers are never acceptable. If a branch mentions a sample ID or value, it is a bug.

## 3. Differential test against a brute-force oracle

When a clever algorithm decides the answer, also write a tiny brute-force version (enumerate all candidates) and compare on many small random inputs. This catches tie-break and exclusion bugs that sample checks miss. Keep inputs tiny so it runs in milliseconds.

## 4. Common pitfalls

- **String ordering:** compare IDs with code-unit comparison (`a < b`), not locale-aware comparison, unless the statement says otherwise. Remember `"C10" < "C2"` as strings.
- **Numeric vs string:** do not sort numeric-looking strings numerically unless asked.
- **Tie rules:** apply them in the exact order stated. A standard shortest/optimal algorithm often does **not** satisfy a "smallest sequence" tie-break by itself; handle it explicitly (for example compute distances first, then build the answer by choosing the smallest valid next step).
- **Floating point:** prefer integers; round only at display time.
- **Undirected data:** treat `(A,B)` and `(B,A)` as the same when duplicates are forbidden.
- **Whitespace/case:** do not trim or lowercase identifiers unless the statement says so.
- **Object/Map order:** never depend on insertion order for results that must be deterministic.
- **Excluded items:** excluded things must be excluded everywhere (as start, destination, and intermediate steps), not just in one place.

## 5. Validation rules

- Validate the whole input and report **every** problem with a stable code and the offending ID/path.
- Reject all-or-nothing: if the file is invalid, keep the previously loaded valid data and show the errors.
- Check cross-references (IDs that must exist, categories that must match), uniqueness, type, range, and count limits.
- Show errors in the active language.

## 6. UI contract

- Recompute immediately after every state change; never require re-import.
- The result panel shows what the statement says to show (for example sequence, destination, total) and the exact status strings.
- Animations must be short, non-blocking, and respect `prefers-reduced-motion`. Computation happens first; animation is decoration.

## 7. Done when

All tiers pass, the adversarial fixtures behave, and the UI shows engine output without recomputing anything itself.
