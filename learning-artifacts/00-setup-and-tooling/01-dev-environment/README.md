# Dev Environment exercises

Lesson: `phases/00-setup-and-tooling/01-dev-environment/docs/en.md`.

## Use the course environment

A dedicated `.venv` has been created in the repository root with Python 3.12.14.
PyTorch, NumPy, Matplotlib, and Jupyter are installed in it.

At the start of a new terminal session, run:

```bash
cd "$HOME/Desktop/ivan/learning/ai-engineering-from-scratch"
source .venv/bin/activate
```

`source` selects this environment for your current shell. It does not reinstall anything.
Check which Python you are using with:

```bash
which python
```

The path should end in `ai-engineering-from-scratch/.venv/bin/python`.

## Run hello world in all four languages

Run all commands below from the repository root, with the course environment active.

Python:

```bash
python learning-artifacts/00-setup-and-tooling/01-dev-environment/hello.py
```

TypeScript:

```bash
node learning-artifacts/00-setup-and-tooling/01-dev-environment/hello.ts
```

Your installed Node.js 26 can run this TypeScript file directly by removing its type annotation.
This execution does not perform TypeScript type checking.

Rust, first compile and then run:

```bash
mkdir -p target/dev-environment
rustc --edition=2021 learning-artifacts/00-setup-and-tooling/01-dev-environment/hello.rs -o target/dev-environment/hello-rust
./target/dev-environment/hello-rust
```

Julia:

```bash
julia learning-artifacts/00-setup-and-tooling/01-dev-environment/hello.jl
```

Each program prints:

```text
Hello, world!
```

## Check PyTorch and the course setup

```bash
python -c 'import torch; print("PyTorch:", torch.__version__); print("MPS available:", torch.backends.mps.is_available())'
python3 phases/00-setup-and-tooling/01-dev-environment/code/verify.py --route beginner --show-later
```

Verified on 2026-09-29:

- All four hello-world programs printed the expected line and exited successfully.
- PyTorch 2.14.0 loaded from this repository's `.venv`.
- A tensor calculation on Apple MPS returned `14.0` for the dot product of `[1, 2, 3]` with itself.
- All 11 environment checks passed: 2 required checks and 9 optional checks.

Try changing the greeting in each source file and running it again. Compile Rust again after editing its source.
