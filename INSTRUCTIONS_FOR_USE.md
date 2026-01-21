# Instructions for using the system prompt

## Claude Code

To preserve Claude Code's built-in capabilities while adopting the anti-engagement system prompt, use the following invocation when starting a session:

```bash
claude --append-system-prompt-file SYSTEM_PROMPT.md
```

## Codex & Gemini CLI

There does not appear to be a way to append the system prompt when involking `codex` or `gemini` from the command line.
