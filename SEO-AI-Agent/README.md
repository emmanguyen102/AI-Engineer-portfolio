# SEO-AI-Agent

**SEO-AI-Agent** is an AI-powered agent that analyzes web pages for SEO (Search Engine Optimization) using an LLM (Large Language Model) and external APIs. It is designed to answer SEO-related questions about any web page by generating a detailed SEO report and reasoning based on ReAct prompting structure.

## Features

- **Automated SEO Analysis:** Uses an LLM (e.g., OpenAI GPT-4) to interpret user questions and decide when to fetch SEO reports.
- **Action Loop:** Follows a Thought → Action → PAUSE → Action_Response → Answer cycle for robust reasoning.
- **Extensible Actions:** Currently supports fetching a full SEO report for any web page via RapidAPI.
- **Prompt Engineering:** Uses a custom system prompt to guide the LLM’s reasoning and action selection.

## How It Works

1. **User asks a question** about a web page (e.g., “How many images are there on https://example.com?”).
2. The agent reasons about the question and, if needed, triggers an action (e.g., fetches an SEO report).
3. The action is executed using an external API (RapidAPI SEO Analyzer).
4. The result is fed back into the agent, which then produces a final answer.

## Code Structure

- `main.py`: Entry point. Runs the agent loop, manages LLM interaction, and handles action execution.
- `actions.py`: Defines available actions. Currently includes `get_seo_page_report(url: str)` which calls the RapidAPI SEO Analyzer.
- `prompts.py`: Contains the system prompt and example sessions for the agent’s reasoning loop.

## Dependencies

- **SimplerLLM**: For LLM abstraction and utility functions.
- **RapidAPIClient**: For making API calls to external SEO services.
- **OpenAI GPT-4** (or compatible LLM): For language understanding and reasoning.

> **Note:** The `SimplerLLM` and `RapidAPIClient` modules must be available in your Python environment. These may be custom or third-party packages not included in this repo.

## Setup

1. **Clone the repository:**
   ```bash
   git clone <repo-url>
   cd SEO-AI-Agent
   ```

2. **Install dependencies:**
   - Ensure you have Python 3.8+.
   - Install required packages (you may need to manually install `SimplerLLM` and any other dependencies).

   ```bash
   pip install openai
   # Install SimplerLLM and RapidAPIClient as needed
   ```

3. **Configure API Keys:**
   - Set up your OpenAI API key for LLM access.
   - Set up your RapidAPI key for the SEO Analyzer.

4. **Run the agent:**
   ```bash
   python main.py
   ```

## Example Usage

The agent will prompt for a question and then loop through reasoning and action steps, outputting the final answer based on the SEO report.

## Extending

- Add new actions in `actions.py` and update `available_actions` in `main.py`.
- Modify the system prompt in `prompts.py` to change the agent’s reasoning style.

## License

MIT (or specify your license here)
