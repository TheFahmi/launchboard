# Flowtask MCP for OpenCode

Add to your `~/.config/opencode/oh-my-opencode.json` or `opencode.json`:

```json
{
  "mcp": {
    "flowtask": {
      "command": "bun",
      "args": ["run", "/path/to/flowtask/src/mcp/server.ts"],
      "env": {
        "FLOWTASK_API_URL": "http://localhost:3030"
      }
    }
  }
}
```

## Available Tools

| Tool | Description |
|------|-------------|
| flowtask_list_tasks | List/filter tasks by workspace, column, priority |
| flowtask_create_task | Create new task with title, priority, labels |
| flowtask_update_task | Update task fields (title, description, progress, column) |
| flowtask_move_task | Move task between columns (drag-and-drop equivalent) |
| flowtask_add_comment | Add comment to a task |
| flowtask_get_stats | Get workspace statistics and velocity |
| flowtask_list_workspaces | List all workspaces |
| flowtask_get_rules | Get AI project rules for a workspace |

## Tool Details

### flowtask_list_tasks

Filter tasks across the board.

- `workspace` (optional) — workspace name or ID
- `column` (optional) — backlog, planned, ready, in-progress, testing, done
- `priority` (optional) — 1 (critical), 2 (high), 3 (medium), 4 (low)
- `search` (optional) — search query for task title

### flowtask_create_task

Create a new task.

- `title` (required) — task title
- `workspace` (optional) — defaults to first workspace
- `priority` (optional) — defaults to 3 (medium)
- `labels` (optional) — array of label names (e.g., ["feat", "bug"])
- `description` (optional) — task description
- `assignee` (optional) — assignee name
- `column` (optional) — defaults to backlog

### flowtask_update_task

Update any task field.

- `taskId` (required) — shortId (e.g., feat-a1b2) or UUID
- `title`, `description`, `priority`, `progress` (0-100), `column`, `assignee`, `aiAssisted`

### flowtask_move_task

Move a task between columns (equivalent to drag-and-drop).

- `taskId` (required) — shortId or UUID
- `column` (required) — target column

### flowtask_add_comment

Add a comment to a task.

- `taskId` (required) — shortId or UUID
- `comment` (required) — comment text
- `author` (optional) — defaults to "AI Agent"

### flowtask_get_stats

Get workspace statistics.

- `workspace` (optional) — defaults to first workspace

### flowtask_list_workspaces

List all workspaces with task counts. No arguments.

### flowtask_get_rules

Get active AI project rules for a workspace.

- `workspace` (optional) — defaults to first workspace
