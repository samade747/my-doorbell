# secrets-demo — Loop Engineering Project 10 (The Secrets Drill)

The drill is about **where a secret lives**, not what it unlocks (a dummy value is fine).

- `check_token.py` looks for `MY_API_TOKEN` in a root `.env` file first, then in the process
  environment.
- `.env` is gitignored (see repo-root `.gitignore`), so it **never reaches a fresh cloud clone**.

## Run 1 — secret in `.env` (fails in the cloud)

Locally you have `.env` with `MY_API_TOKEN=dummy-abc123`. You push. `.env` does not travel.
The routine clones the repo, runs `python secrets-demo/check_token.py`, finds nothing → **FAIL**.

## Run 2 — secret in the routine's Variables panel (works)

Add `MY_API_TOKEN=dummy-abc123` in the routine's **Environment → Variables**. The cloud session
now has it in `os.environ`. Same script → **OK**.

## Lesson

Gitignored files are invisible to the cloud runner. Secrets belong in the environment/variables
configuration, which is injected into the session at runtime and never committed.
