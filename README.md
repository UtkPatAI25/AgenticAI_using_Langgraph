# AgenticAI using LangGraph

A demonstration of building a conversational AI agent with LangGraph, equipped with tool-usage capabilities (Google Serper search and Pushover notifications), workflow evaluation, and a Gradio-powered user interface.

## Features

![image](https://github.com/user-attachments/assets/7c298b0e-2118-49bc-9560-eaa68fa6e6f6)


- **Agentic workflow**: Multi-step reasoning with success criteria and feedback loop.
- **Tool Integration**:
  - *Google Serper API*: For web search queries.
  - *Pushover API*: For sending push notifications.
- **Evaluator Node**: Uses a language model to judge task completion and provide feedback.
- **Memory and State Management**: Tracks conversation, feedback, and task state.
- **Gradio UI**: Interactive chat interface for conversational workflows.

![image](https://github.com/user-attachments/assets/1eac0169-71cf-4d25-a3de-250910fce07c)


## File Structure

- `Agentic_Langgraph.ipynb`: Main notebook containing code for agent, tools, workflow, and UI.
- `requirements.txt`: Python dependencies.

## Quickstart

### 1. Clone the Repository

```bash
git clone https://github.com/UtkPatAI25/AgenticAI_using_Langgraph.git
cd AgenticAI_using_Langgraph
```

### 2. Set Up Environment

- Install dependencies:

  ```bash
  pip install -r requirements.txt
  ```

- Create a `.env` file in the repo root with your API keys:
  ```
  OPENAI_API_KEY=your_openai_key
  SERPER_API_KEY=your_serper_key
  PUSHOVER_TOKEN=your_pushover_token
  PUSHOVER_USER=your_pushover_user_key
  ```

### 3. Run the Notebook

Open and run `Agentic_Langgraph.ipynb` in Jupyter or VSCode.

### 4. Launch the Gradio App

At the end of the notebook, a Gradio chat interface will start in your browser:
- Ask questions, define success criteria, and see the agent reason and use tools.

## Example Usage

- **User:** What is the GDP of USA?
- **Success Criteria:** The answer must include the latest GDP figure for the USA.
- The agent will:
  1. Search the web using Serper API.
  2. Present an answer.
  3. If you wish, can send notifications with Pushover.

## Requirements

See `requirements.txt` for all dependencies. Key libraries:
- `langgraph`, `langchain-core`, `langchain-openai`
- `gradio`
- `python-dotenv`
- `requests`
- `pydantic`

## How It Works

1. **Agent Node**: LLM-based assistant, can use tools.
2. **Tool Node**: Calls APIs for web search and notifications.
3. **Evaluator Node**: LLM checks if success criteria are met, provides feedback.
4. **Router Nodes**: Control the workflow based on agent/evaluator decisions.
5. **UI**: Gradio interface for user interaction; supports conversation history and flow visualization.

## Customization

- Add more tools by extending the `tools` list in the notebook.
- Change LLMs or models by modifying the `ChatOpenAI` instantiation.
- Update UI/criteria as needed for your use case.

## License

See [LICENSE](LICENSE) for details.

---

**Inspired by LangGraph's agentic workflow capabilities.**
