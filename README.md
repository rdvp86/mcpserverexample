# MCP Server Deep Dive Deployment

A Model Context Protocol (MCP) server example demonstrating how to package and deploy an MCP server installable directly from GitHub using `uvx`.

## Tools

- **add** – Adds two integers and returns the result.

## Installation

### Prerequisites

- [uv](https://docs.astral.sh/uv/getting-started/installation/) installed on your machine.
- Claude Desktop installed.

### Add to Claude Desktop

Open your `claude_desktop_config.json` file:

- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`
- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`

Add the following entry inside the `mcpServers` object:

```json
"mcpserverexample": {
  "command": "uvx",
  "args": [
    "--from",
    "git+https://github.com/rdvp86/mcpserverexample.git",
    "mcp-server"
  ]
}
```

### Full config example

```json
{
  "mcpServers": {
    "mcpserverexample": {
      "command": "uvx",
      "args": [
        "--from",
        "git+https://github.com/rdvp86/mcpserverexample.git",
        "mcp-server"
      ]
    }
  }
}
```

Restart Claude Desktop after saving the file. The server will be fetched and installed automatically from GitHub on first run.

## Development

Clone the repo and install dependencies with `uv`:

```bash
git clone https://github.com/rdvp86/mcpserverexample.git
cd mcpserverexample
uv sync
```

Run the server locally:

```bash
uv run mcp-server
```
