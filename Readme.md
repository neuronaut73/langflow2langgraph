# LangFlow to LangGraph Converter 🧠➡️🧱

Convert LangFlow JSON exports into fully structured, production-ready LangGraph Python code.

---

## 🚀 Features
- Parses LangFlow `.json` files
- Reconstructs node functions, edge connections, and flow logic
- Extracts custom Python code blocks
- Sets LangGraph entry and finish points
- Supports conditional routing and loop constructs
- Generates proper state management code
- Validates and fixes generated code
- Supports a wide range of node types
- Easy to run in a virtual environment or via CLI

See [UPDATES.md](UPDATES.md) for recent improvements and changes.

---

## 🧪 Quickstart (Local Usage)

```bash
# 1. Clone or download this repo
git clone https://github.com/neuronaut73/langflow2langgraph.git
cd langflow2langgraph

# 2. Create a virtual environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# 3. Install dependencies
pip install -e .

# 4. Run conversion (example)
python run_converter.py  # Or use CLI below
```

---

## 💻 CLI Usage (Optional)

After installation, you can run:

```bash
lf2lg path/to/langflow.json --output my_graph.py
```

To enable this, add to `setup.py` or `pyproject.toml`:

```python
entry_points={
    'console_scripts': [
        'lf2lg=langflow2langgraph.cli:main'
    ]
}
```

---

## 📦 Installation from GitHub

```bash
pip install git+https://github.com/neuronaut73/langflow2langgraph.git
```

---

## 📂 Project Organization

This project supports two ways to organize your Langflow exports and LangGraph outputs:

### Flat Structure

The flat structure is simple and straightforward. All Langflow JSON exports go into the `input_flows` directory, and all generated LangGraph Python files go into the `output_graphs` directory.

```
input_flows/
└── simple_chat.json

output_graphs/
└── simple_chat.py
```

### Project-Based Structure

The project-based structure organizes files by project or use case. Each project has its own directory with `input_flows` and `output_graphs` subdirectories.

```
projects/
└── simple_chat/
    ├── input_flows/
    │   └── simple_chat.json
    ├── output_graphs/
    │   └── simple_chat.py
    └── README.md
```

This structure is more scalable and makes it easier to manage multiple projects. Each project can have its own documentation, tests, and version history.

---

## 🛠 Project Structure

```
langflow2langgraph/
├── langflow2langgraph/
│   ├── __init__.py
│   ├── converter.py       # Main converter logic
│   ├── mapping.py         # Mappings between Langflow and LangGraph
│   ├── node_categories.py  # Node category definitions
│   ├── state_fields.py    # State field definitions
│   ├── code_generators.py # Code generators for different node types
│   ├── validator.py      # Code validation and fixing
│   ├── code_generator.py  # LangGraph code generation
│   └── cli.py             # Command-line interface
├── input_flows/          # Langflow JSON exports (flat structure)
│   ├── simple_chat.json   # Simple chat example
│   ├── retrieval_qa.json  # Retrieval QA example
│   ├── agent_example.json # Agent example
│   ├── loop_flow.json     # Loop example
│   └── conditional_flow.json # Conditional routing example
├── output_graphs/        # Generated LangGraph Python files (flat structure)
│   ├── simple_chat.py     # Simple chat example
│   ├── retrieval_qa.py    # Retrieval QA example
│   ├── agent_graph.py     # Agent example
│   ├── loop_graph.py      # Loop example
│   └── conditional_graph.py # Conditional routing example
├── projects/             # Project-based structure
│   ├── simple_chat/      # Simple chat project
│   │   ├── input_flows/  # Langflow JSON exports
│   │   ├── output_graphs/ # Generated LangGraph Python files
│   │   └── README.md     # Project documentation
│   ├── retrieval_qa/     # Retrieval QA project
│   ├── agent/            # Agent project
│   ├── conditional/      # Conditional routing project
│   ├── loop/             # Loop project
│   └── README.md         # Projects documentation
├── tests/
│   └── test_converter.py
├── batch_convert.py      # Batch conversion script (flat structure)
├── batch_convert_projects.py # Batch conversion script (project-based structure)
├── test_all_graphs.py    # Test all converted graphs (flat structure)
├── test_all_projects.py  # Test all project graphs (project-based structure)
├── fix_indentation.py    # Fix indentation issues in generated code
├── setup.py
├── README.md
├── UPDATES.md           # Recent updates and changes
└── requirements.txt
```

---

## ✅ Requirements

- Python 3.8+
- langchain
- Any other dependencies listed in `requirements.txt`

---

## 🔐 Optional: Build a Standalone Binary (no Python needed)

Use PyInstaller to build a single executable:

```bash
pip install pyinstaller
pyinstaller --onefile langflow2langgraph/cli.py
```

Result: `dist/lf2lg.exe` or `dist/lf2lg` — ready-to-run binary.

---

## 🌐 Maintained by PatRec UG

This project is developed and maintained by **[PatRec UG](https://patrec.eu)** — a company offering AI automation using agent-driven architectures.

### 🧠 Our Services Include:
- **PREDICTOR.AI**: Demand forecasting, pricing, and replenishment
- **DETECTOR.AI**: Detect fraud, defects, failures, and anomalies
- **Company GPTs & Agents**: Automate decisions and documents with local vector storage
- **RISK.AI**: Manage market, credit, and operational risk with AI-enhanced tools

> "We got an ROI of x10 from the Demand.AI Forecasting Model PatRec developed."
> — SCM Lead, Henkel AG

- 🌍 Website: [patrec.eu](https://patrec.eu)
- 📬 Newsletter: [Subscribe](https://scmsync.com)
- ⏰ Book a Call: [Schedule](https://patrec.eu)

---

## 📄 License

MIT License. Use freely, modify gladly, and share the love. ❤️

---

## 💬 Questions or Ideas?

Create an issue or pull request — or reach out on GitHub!
