# mcp-openhexa
[![smithery badge](https://smithery.ai/badge/@mcrimi/mcp-openhexa)](https://smithery.ai/server/@mcrimi/mcp-openhexa)

A VERY rudimentary proof of concept of a local MCP server for OpenHEXA using Claude Desktop

# Setup guide

### Installing via Smithery

To install mcp-openhexa for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@mcrimi/mcp-openhexa):

```bash
npx -y @smithery/cli install @mcrimi/mcp-openhexa --client claude
```

### 1. Setup .venv and install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Configure Claude Desktop

1. Edit your Claude Desktop configuration file:
   - **macOS**: `/Users/{youruser}/Library/Application Support/Claude/claude_desktop_config.json`
   - **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

2. Add or merge the configuration from `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "openhexa": {
      "command": "{path}/mcp-openhexa/.venv/bin/python",
      "args": ["-m", "mcp_openhexa.server"],
      "cwd": "{path}/mcp-openhexa",
      "env": {
        "HEXA_TOKEN": "{YOUR TOKEN HERE}",
        "HEXA_SERVER_URL": "https://app.openhexa.org/"
      }
    }
  }
} 
```

3. Replace the placeholder values with URL and OpenHEXA token
4. Restart Claude Desktop
5. You should now see OpenHEXA as an integration tool:

  
![CleanShot 2025-07-04 at 10 24 17](https://github.com/user-attachments/assets/757ac51d-e8cd-49a1-93ed-7e9d84937dca)


### 3. Start Using with Claude

Once configured, you can ask Claude questions like:

- "Show me all workspaces in OpenHEXA"
- "List datasets in the 'public-health' workspace"
- "Search for pipelines containing 'analysis' in their name"
- "Get details about the 'covid-data' dataset"
- "Show recent runs for the 'data-processing' pipeline"
