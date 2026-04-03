<p align="center">
  <img src="assets/icon.png" width="128" alt="sip">
  <h1 align="center">sip</h1>
  <p align="center">Summarize stdin using LLMs</p>
</p>

<p align="center">
  <a href="https://github.com/Aayush9029/sip/releases/latest"><img src="https://img.shields.io/github/v/release/Aayush9029/sip" alt="Release"></a>
  <a href="https://github.com/Aayush9029/sip/blob/main/LICENSE"><img src="https://img.shields.io/github/license/Aayush9029/sip" alt="License"></a>
</p>

<p align="center">
  <img src="assets/demo.gif" alt="sip demo">
</p>

## Install

```bash
brew install aayush9029/tap/sip
```

Or tap first:

```bash
brew tap aayush9029/tap
brew install sip
```

Requires `OPENROUTER_API_KEY` ([get one](https://openrouter.ai/keys)) or run `sip --setup`.

## Usage

```bash
cat server.log | sip                                # summarize logs
nit elonmusk | sip                                  # summarize nit output
cat main.py | sip -s code                           # explain code
git log --oneline -50 | sip -l brief                # brief git summary
cat report.csv | sip -p 'what are the totals?'      # ask a question
sip -m deepseek < data.json                         # use a different model
sip --list-models                                   # see available models
```

## Options

| Flag | Description |
|------|-------------|
| `-p, --prompt <text>` | Ask a specific question about the input |
| `-l, --level <level>` | `brief` \| `normal` \| `detailed` (default: `normal`) |
| `-s, --style <style>` | `auto` \| `logs` \| `code` (default: `auto`) |
| `-m, --model <name>` | Model shorthand or OpenRouter model ID (default: `flash`) |
| `--list-models` | List supported models |
| `--setup` | Configure API key and defaults |

Piped output is clean text (no colors/formatting).

## License

MIT
