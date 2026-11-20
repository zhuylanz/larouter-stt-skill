<div align="center">
  <img src="assets/lapage-logo.svg" alt="LaPage" width="112" />
  <h1>LaRouter Speech-to-Text Skill</h1>
  <p>OpenAI-compatible speech-to-text and subtitles through LaRouter.</p>
</div>

<p align="center">
  <a href="https://github.com/zhuylanz/larouter-stt-skill">GitHub Repository</a>
  ·
  <a href="https://lapage.vn">LaPage Digital</a>
</p>

Use this skill to give Codex, Claude Code and other AI agents speech-to-text transcripts and subtitles through
LaRouter's OpenAI-compatible API.

## Install

Give your agent this repository link and ask it to add the skill:

```text
https://github.com/zhuylanz/larouter-stt-skill
```

For a local checkout (recommended, so updates are a `git pull`):

```sh
git clone https://github.com/zhuylanz/larouter-stt-skill
```

The skill instructions are in [SKILL.md](SKILL.md).

## Updates

The skill checks this repository for a newer `VERSION` each time it is used.
When there is one, the agent pulls the new instructions (or downloads them if
the skill is not a git checkout) and follows them. If GitHub is unreachable it
continues with the installed version.

Maintainers: on every change to the instructions, bump `VERSION` and
`metadata.version` in `SKILL.md` together, or installed agents will not update.

## What It Supports

- Speech-to-text through `/v1/audio/transcriptions` with the `larouter-stt`
  model ($0.006 per minute of audio).
- Transcripts as JSON or plain text, timed segments (`verbose_json`), and
  subtitles as SRT or VTT.
- Vietnamese, English and about 90 other languages, detected automatically.
- Common audio and video formats.

## Endpoint

```text
https://i-larouter.lapage.vn/v1
```

## Authentication

Set your LaRouter API key in the environment:

```sh
export LAROUTER_API_KEY='your-key'
```

The skill never prints or stores credentials. If the variable is unset, it can
use the `experimental_bearer_token` from `~/.codex/config.toml` for the
request only.

## About LaPage Digital

LaPage Digital builds practical digital systems for growing businesses,
including websites, content platforms, automation, and AI-enabled operations.
This skill packages a predictable LaRouter workflow for those environments.

## License

This repository contains LaPage Digital workflow guidance for LaRouter audio
operations. Contact LaPage Digital before redistributing or adapting it for
another organization.
