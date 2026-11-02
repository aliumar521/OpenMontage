# Fork notes (aliumar521/OpenMontage)

Fork of [calesthio/OpenMontage](https://github.com/calesthio/OpenMontage) (AGPLv3), registered in Skunkworks as `openmontage`.

## Remotes
- `origin` = aliumar521/OpenMontage. `upstream` = calesthio/OpenMontage (push disabled).
- Update: `git fetch upstream && git merge upstream/main`, then push to `origin`.
- Keep fork changes in **new files only** (this file, `.claude/commands/to-postiz.md`) so merges stay clean.

## Running
- Runs locally with Claude Code. It isn't hosted (Skunkworks decision 2026-11-02).
- Python venv: `.venv` (Python 3.11). Remotion: `remotion-composer/` (`npm install` done). FFmpeg: `C:/ffmpeg/bin`.
- Keys go in `.env` (gitignored, copied from `.env.example`). The zero-key path uses Piper TTS, free stock and Remotion.
- Outputs go in `projects/<project-id>/` (gitignored).

## Handing a render to Postiz
Follow Skunkworks `docs/standards/hosting.md`, "Content pipeline": upload over HTTPS, then make a **draft** post. Never schedule directly.
Use `/to-postiz <path-to-mp4> [caption]`. It needs `POSTIZ_API_URL=https://postiz.flyk.pro/api` and `POSTIZ_API_KEY` in the shell environment.
