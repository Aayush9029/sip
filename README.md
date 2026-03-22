<img src="assets/icon.png" width="128" alt="sip">

# sip

Summarize stdin using LLMs.

## Install

```bash
brew install aayush9029/tap/sip
```

Requires `OPENROUTER_API_KEY` ([get one](https://openrouter.ai/keys)) or run `sip --setup`.

## Usage

```bash
cat server.log | sip                    # summarize logs
nit elonmusk | sip                      # summarize nit output
cat main.py | sip -s code              # explain code
git log --oneline -50 | sip -l brief   # brief git summary
cat essay.md | sip -l detailed         # detailed summary
curl -s url | sip -s prose             # summarize web content
sip -m deepseek < data.json            # use a different model
sip --list-models                      # see available models
```

Piped output is clean text (no colors/formatting).

---

*More CLI tools: [`brew tap aayush9029/tap`](https://github.com/Aayush9029/homebrew-tap)*
