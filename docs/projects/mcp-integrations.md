# MCP Server Integrations

**Model Context Protocol (MCP) tools for AI assistant integration**

**Status: Active**

> Tools for integrating AI assistants into development workflows using the Model Context Protocol.

---

## Projects

### MCP Server Tutorial

**[GitHub Repository](https://github.com/DazzleML/MCP-Server-Tutorial)**

Complete guide to building MCP servers for AI assistant integration.

**Topics Covered**:
- File system access for AI assistants
- Task management integration (Todoist)
- Database query interfaces
- Custom tool creation
- Security best practices

**Use Cases**:
- Build custom AI assistant tools
- Integrate AI into existing systems
- Create domain-specific AI capabilities
- Learn MCP architecture

**Example Projects**:
```python
# File system MCP server
from mcp import Server

server = Server("filesystem")

@server.tool()
def list_files(directory: str) -> list[str]:
    """List files in directory for AI assistant"""
    return os.listdir(directory)
```

---

### Integration with TodoAI

DazzleML tools integrate with the [TodoAI](https://github.com/Todo-AI) ecosystem:

**TodoAI-Todoist MCP Server**:
- Enhanced MCP server with AI capabilities
- Local caching for performance
- Natural language task creation
- Intelligent task prioritization
- AI-powered task completion suggestions

**Features**:
- Create tasks from natural language
- Query tasks with complex filters
- Update task priorities intelligently
- Schedule tasks based on context
- Analyze productivity patterns

---

## Model Context Protocol

MCP is a standard for integrating AI assistants with external tools and data sources.

**Benefits**:
- **Standardized interface** - Same API across tools
- **Security** - Controlled access to resources
- **Flexibility** - Easy to add new capabilities
- **Extensibility** - Build custom integrations

**Architecture**:
```
AI Assistant <-> MCP Client <-> MCP Server <-> Your Tools/Data
```

---

## Use Cases

### AI-Assisted Development
```python
# AI can now access your codebase
ai_query("Find all functions that handle user authentication")
# AI uses MCP to search files, returns relevant functions
```

### Task Management
```python
# Natural language task creation
ai_command("Add a task to review pull request #123 tomorrow")
# AI creates task with due date via TodoAI MCP server
```

### Database Queries
```python
# AI can query your database
ai_query("How many users signed up last week?")
# AI uses MCP to run SQL query, returns result
```

### Custom Workflows
```python
# Build domain-specific AI tools
@mcp_server.tool()
def analyze_training_run(run_id: str):
    """Analyze AI training run for issues"""
    # AI can now analyze training runs
```

---

## Getting Started

### 1. Install MCP Library

```bash
pip install model-context-protocol
```

### 2. Create MCP Server

```python
from mcp import Server

server = Server("my-tool")

@server.tool()
def my_function(param: str) -> str:
    """Function AI can call"""
    return f"Result: {param}"

server.run(port=3000)
```

### 3. Connect AI Assistant

Configure your AI assistant to use the MCP server:
```json
{
  "mcp_servers": [
    {
      "name": "my-tool",
      "url": "http://localhost:3000"
    }
  ]
}
```

### 4. Use in AI Conversations

```
User: "Use my-tool to process 'hello'"
AI: *calls my_function via MCP*
AI: "Result: hello"
```

---

## Security Best Practices

### Access Control
- Require authentication for MCP servers
- Use API keys or OAuth
- Limit AI access to specific tools

### Input Validation
- Validate all parameters
- Sanitize file paths
- Prevent SQL injection

### Rate Limiting
- Limit requests per minute
- Prevent abuse
- Protect backend services

### Audit Logging
- Log all MCP requests
- Track what AI accesses
- Monitor for suspicious activity

---

## Example: TodoAI Integration

```python
from todoai_todoist import TodoistMCPServer

# Initialize MCP server
server = TodoistMCPServer(api_key=TODOIST_API_KEY)

# AI can now:
# - Create tasks
# - Query tasks
# - Update priorities
# - Schedule deadlines
# - Analyze productivity

server.run(port=3001)
```

**AI Usage**:
```
User: "Add a task to review the proposal tomorrow"
AI: *creates task via MCP*
AI: "Created task 'Review proposal' due tomorrow"

User: "What are my high-priority tasks?"
AI: *queries tasks via MCP*
AI: "You have 3 high-priority tasks: ..."
```

---

## Resources

- **MCP Specification**: [modelcontextprotocol.io](https://modelcontextprotocol.io)
- **Example Servers**: See MCP-Server-Tutorial repository
- **TodoAI Integration**: [Todo-AI organization](https://github.com/Todo-AI)
- **Community**: [GitHub Discussions](https://github.com/DazzleML/discussions)

---

## License

GPL 3.0 - See repository for details

---

**Part of [DazzleML](https://github.com/DazzleML) - AI Development Tools**
