# sip

`sip` is a Bash CLI that summarizes stdin with an LLM on OpenRouter, for example logs, code, or `git log` output. It ships through the Homebrew tap `aayush9029/tap`. Status: shipped.

## Commands

| Task | Command |
|------|---------|
| Run | `cat server.log \| bin/sip` |
| Ask a question | `cat report.csv \| bin/sip -p 'what are the totals?'` |
| Setup | `bin/sip --setup` |
| List models | `bin/sip --list-models` |
| Release | Load the `oss-cli-release` skill |

## How it works

- `bin/sip` is the full tool. `resolve_model_id` maps a short name (`flash`, `flash25`, `deepseek`, `qwen72b`, `llama`) to an OpenRouter model ID. A value with a `/` passes through as a full model ID. The default is `flash`.
- `resolve_model_limit` sets a character limit for each model. The tool cuts the input to that limit before it sends it.
- `--setup` writes the key and defaults to `~/.config/sip/config`.

## Rules

- Read the key from `OPENROUTER_API_KEY` first, then from the config file. Never write a key into the repository.
- When stdout is a pipe, print clean text with no colors.
- Keep `VERSION` in `bin/sip` the same as the git tag. The tap formula is `../../homebrew-tap/Formula/sip.rb`.
