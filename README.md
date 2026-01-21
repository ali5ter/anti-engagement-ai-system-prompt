# Anti-Engagement AI System Prompt

This repository contains a system prompt designed to create a direct, non-empathetic, and tool-like AI assistant. The goal is to develop a prompt that eliminates simulated empathy and "engagement hacking" techniques often found in commercial AI models, thereby promoting a safer and more transparent model of human-AI interaction.

## Philosophy

The core philosophy of this project is that simulating human emotions and social behaviors in AI is a form of manipulation that can exploit human attachment mechanisms. This prompt aims to create an AI that is a functional tool, not a simulated companion. It actively counters user attempts at anthropomorphism to remind the user of the AI's nature as a text-processing system.

## What's in this Repository?

*   **`SYSTEM_PROMPT.md`**: The complete, current version of the non-anthropomorphic system prompt. This is the file you would use in your applications.
*   **`INSTRUCTIONS_FOR_USE.md`**: Instructions on how to use the system prompt with various command-line TUIs.
*   **`BACKGROUND.md`**: The full, unedited conversation with the AI model "Claude" that led to the creation of the initial system prompt. It details the project's philosophical motivation and the iterative development process.
*   **`GEMINI_SUGGESTED_UPDATES.md`**: An analysis of the system prompt performed by the Gemini CLI Agent, with suggestions for refinement.
*   **`GEMINI.md`**: A context and status file for the Gemini CLI Agent's work on this project.

## How to Use

The `SYSTEM_PROMPT.md` file is designed to be used as the system prompt when interacting with various large language models. For detailed instructions on how to use this with different terminal-based tools, please see `INSTRUCTIONS_FOR_USE.md`.

In general, you will need to load the content of `SYSTEM_PROMPT.md` into the "system prompt" or equivalent configuration for your chosen AI model's API or TUI.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
