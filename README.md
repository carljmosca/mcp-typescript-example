
# TypeScript MCP Example Server

This project demonstrates a minimal [Model Context Protocol (MCP)](https://modelcontextprotocol.org/) server implementation in TypeScript, using the official [TypeScript SDK](https://github.com/modelcontextprotocol/typescript-sdk). It provides a simple API for tool invocation and resource access, and is compatible with the MCP Inspector for testing and exploration.

---

## Features

- **Addition Tool**: Add two numbers via the MCP protocol.
- **Greeting Resource**: Generate a dynamic greeting for any name.
- **Streamable HTTP Transport**: Uses the recommended HTTP transport for MCP.
- **Express.js Integration**: Easily extensible and familiar web server setup.

npm install @modelcontextprotocol/sdk express zod@3
npx -y tsx server.ts
npx @modelcontextprotocol/inspector

## Getting Started

### 1. Install dependencies

```sh
npm install @modelcontextprotocol/sdk express zod@3
```

### 2. Run the server

```sh
npx -y tsx server.ts
```

The server will start on [http://localhost:3000/mcp](http://localhost:3000/mcp).

### 3. Test with MCP Inspector

You can use the official MCP Inspector to interact with this server:

```sh
npx @modelcontextprotocol/inspector
```

**Inspector Settings:**

- **Transport Type:** Streamable HTTP
- **URL:** http://localhost:3000/mcp
- **Connection Type:** Via Proxy

---

## API Overview

### Tools

- **add**: Adds two numbers.
	- **Input:** `{ "a": number, "b": number }`
	- **Output:** `{ "result": number }`

### Resources

- **greeting://{name}**: Returns a greeting for the given name.
	- **Example:** `greeting://Alice` → `Hello, Alice!`

---

## Project Structure

- `server.ts` — Main server implementation
- `package.json` — Project dependencies
- `README.md` — This documentation

---

## Troubleshooting

- Ensure Node.js 18+ is installed.
- If you see port conflicts, change the port in `server.ts` or set the `PORT` environment variable.
- For MCP Inspector issues, see [MCP Inspector documentation](https://github.com/modelcontextprotocol/inspector).

---

## License

MIT (see [LICENSE](LICENSE) if present)