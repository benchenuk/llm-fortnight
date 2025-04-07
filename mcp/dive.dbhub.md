# Dive AI Agent + DBHub

Setting the following environment as an example to explore MCP servers:

`Dive -> DBHub -> PostgreSQL`


## Dive AI Agent 
[Dive](https://github.com/OpenAgentPlatform/Dive) is an open-source MCP Host Desktop Application that seamlessly integrates with any LLMs supporting function calling capabilities. 

Once set up properly, it is possible to interact with the underlying database with natural language. 
![images/dive.ai.mcp.png](../images/dive.ai.mcp.png)

```json
{
  "mcpServers": {
    "echo": {
      "enabled": false,
      "command": "node",
      "args": [
        "/Users/benchen/.dive/scripts/echo.js"
      ],
      "disabled": true
    },
    "postgresql_dbhub_sse": {
      "enabled": true,
      "transport": "sse",
      "url": "http://localhost:8080/sse"
    }
  }
}
```

## DBHub 
[DBHub](https://github.com/bytebase/dbhub/) is a universal database gateway implementing the Model Context Protocol (MCP) server interface. This gateway allows MCP-compatible clients to connect to and explore different databases.

### Installation 
```
docker run --rm --init \
   --name dbhub \
   --publish 8080:8080 \
   bytebase/dbhub \
   --transport sse \
   --port 8080 \
   --dsn "postgres://sandbox:sandbox@host.docker.internal:5432/sandbox?sslmode=disable"
```

This will kick off DBHub connecting to a local postgreSQL database. 
The SSE URL will be hosted at [http://localhost:8080/sse](http://localhost:8080/sse).

![images/dbhub.startup.png](../images/dbhub.startup.png)


## PostgreSQL

### Installation
```
brew install postgresql@17
```
### Minimal Setup 
- create new user
- create new database (e.g.`sandbox`)
- create new schema/namespace (e.g. `rag`)
- grant permission to schema
- create new table (e.g. `tasks`)
- populate data for tests


**Useful commands**
```
brew services stop postgresql
brew services start postgresql
```

**Useful files**
```
/opt/homebrew/var/postgresql@17/pg_hba.conf #host all all 0.0.0.0 32 trust
/opt/homebrew/var/postgresql@17/postgresql.conf #listen_addresses = '*'
/opt/homebrew/var/log/postgresql@17.log
```

## MCP Inspector
The [MCP inspector](https://github.com/modelcontextprotocol/inspector?tab=readme-ov-file) is a developer tool for testing and debugging MCP servers. 

Simply run the command:
```
npx @modelcontextprotocol/inspector node build/index.js
```
Use the SSE URL to the target MCP server. E.g. `http://localhost:8080/sse`.

