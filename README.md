# 🧠 MCP Server: Local AI Tooling with Python

This project sets up a lightweight Model Context Protocol (MCP) server using Python, enabling AI assistants like Claude to interact with local data files such as CSV and Parquet By integrating with Claude for Desktop, you can perform tasks like summarizing datasets or retrieving specific information through natural language queries

## 🚀 Features

**Local MCP Server (`mix_server`)**: Facilitates communication between Claude and your local tool.
**CSV and Parquet Readers**: Tools to load and process tabular data formats commonly used in data analysi.
**Modular Structure**: Clean codebase designed for easy expansion with additional tool.
**Seamless Claude Integration**: Connects directly with Claude for Desktop, allowing natural language interactions with your dat.

## 🛠️ Installation

### 1. Clone the Repositor

````bash
git clone https://github.com/yourusername/mcp-server.git
cd mcp-server
``


### 2. Set Up the Environment Using `uv

[uv](https://github.com/astral-sh/uv) is a fast Python package and project manager written in Rut It serves as a drop-in replacement for tools like `pip`, `pip-tools`, and `virtualenv`, offering significant speed improvements and a unified interfae.

#### Install `uv

You can install `uv` using one of the following methos:

- **Using `curl` (macOS and Linux):**

```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ``


- **Using `pip`:**

```bash
  pip install uv
  ``


- **Using `pipx`:**

```bash
  pipx install uv
  ``


For more installation options and details, refer to the [official uv documentation](https://docs.astral.sh/uv).

#### Create a Virtual Environment and Install Dependencie


```bash
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
uv pip install mcp[cli] pandas pyarrow
``


This will create a virtual environment and install the necessary dependencies using `u`.

## 📁 Project Structue


```bash
mcp-server/
├── tools/
│   ├── csv_reader.py
│   └── parquet_reader.py
├── mix_server.py
├── README.md
└── requirements.txt
``

- `tools/`: Contains individual tool scripts for data processng.
- `mix_server.py`: Initializes and runs the MCP server, registering available tols.

## ⚙️ Configuration for Claude Desktp

To integrate with Claude for Desktop, add the following configuration to your Claude settigs:


```json
{
  "mcpServers": {
    "mix_server": {
      "command": "/absolute/path/to/.venv/bin/python",
      "args": ["/absolute/path/to/mix_server.py"]
    }
  }
}
``


Ensure that the paths to your Python interpreter and `mix_server.py` are corrct.

## 🧪 Usge

Once set up, you can interact with your data through Claude using natural language prompts. For exaple:

- "Summarize the contents of `data.cv`."
- "How many rows and columns are in `dataset.parqut`?

Claude will utilize the registered tools to process your request and provide the desired informaion.

## 📚 Refereces

This project is based on the tutorial: [Building a Basic MCP Server with Python](https://medium.com/data-engineering-with-dremio/building-a-basic-mcp-server-with-python-4c34c4101ed).

## 📝 Liense

This project is licensed under the [MIT License](LIENSE).
````
