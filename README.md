# mcp-openhexa
A VERY rudimentary proof of concept of a local MCP server for OpenHEXA using Claude Desktop

# Setup guide

### 1. Install Dependencies

```bash
# Option 1: Using pip
pip install -r requirements.txt

# Option 2: Install in development mode
pip install -e .
```

### 2. Configure Claude Desktop

1. Edit your Claude Desktop configuration file:
   - **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
   - **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

2. Add or merge the configuration from `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "openhexa": {
      "command": "python",
      "args": ["-m", "mcp_openhexa.server"],
      "env": {
        "HEXA_TOKEN": "your_openhexa_token_here",
        "HEXA_SERVER_URL": "https://your-openhexa-instance.com"
      }
    }
  }
}
```

3. Replace the placeholder values with your actual OpenHEXA credentials
4. Restart Claude Desktop
5. You should now see:

   
![CleanShot 2025-07-04 at 10 24 17](https://github.com/user-attachments/assets/757ac51d-e8cd-49a1-93ed-7e9d84937dca)


### 5. Start Using with Claude

Once configured, you can ask Claude questions like:

- "Show me all workspaces in OpenHEXA"
- "List datasets in the 'public-health' workspace"
- "Search for pipelines containing 'analysis' in their name"
- "Get details about the 'covid-data' dataset"
- "Show recent runs for the 'data-processing' pipeline"
