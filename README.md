# 🧠 MCP Server: Local AI Tooling with Python

This project sets up a lightweight Model Context Protocol (MCP) server using Python, enabling AI assistants like Claude to interact with local data files such as CSV and ParquetBy integrating with Claude for Desktop, you can perform tasks like summarizing datasets or retrieving specific information through natural language queries

## 🚀 Features

**Local MCP Server (`mix_server`)**: Facilitates communication between Claude and your local tool.
**CSV and Parquet Readers**: Tools to load and process tabular data formats commonly used in data analysi.
**Modular Structure**: Clean codebase designed for easy expansion with additional tool.
**Seamless Claude Integration**: Connects directly with Claude for Desktop, allowing natural language interactions with your dat.

## 🛠️ Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/yourusername/mcp-server.git
   cd mcp-server
   ``


   ```

2. **Set Up a Virtual Environment**:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ``


   ```

3. **Install Dependencies**:

   ```bash
   pip install mcp[cli] pandas pyarrow
   ``

   ```

## 📁 Project Structue

````bash
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
      "command": "/absolute/path/to/venv/bin/python",
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
