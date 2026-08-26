TITAN GATE

Default-deny permission control, credential isolation, execution, and audit logging for autonomous agents.

Titan Gate places a control boundary between an AI agent and the tools it wants to use. Every call is checked against that agent's YAML permission manifest before execution. Allowed calls are recorded before they run and finalized with their result or error afterward.

Inventor and IP owner: Julius Cameron Hill
Organization: Titan Universal AI LLC
Status: Working Python prototype

What it does

Registers agents with explicit tool permissions.

Denies undeclared tools and scopes by default.

Suspends, resumes, or permanently revokes an agent.

Executes approved shell, browser, HTTP API, file, and email operations.

Encrypts stored credentials and injects them only during approved calls.

Records agent changes, credential events, tool intent, results, and failures.

Replays earlier calls or returns a dry-run preview.

Exposes a JWT-protected REST API, statistics endpoint, and WebSocket endpoint.

Stores state locally in SQLite using WAL mode.

Execution path

Agent request
    -> JWT authentication
    -> Agent status check
    -> Manifest permission check
    -> Credential injection when requested
    -> Tool execution
    -> Result and audit record

Implemented tools

Tool

Implemented scopes

shell

r
