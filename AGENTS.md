# Gemini CLI Agent Instructions

## Project Overview
Gemini CLI is an open-source AI agent providing terminal access to Gemini models. It features a monorepo structure with npm workspaces, built with Node.js (>=20), TypeScript, and React (via Ink for CLI UI).

Key packages:
- `packages/cli`: Terminal UI and command processing
- `packages/core`: Backend logic, API orchestration, tool execution
- `packages/sdk`: Programmatic SDK
- `packages/a2a-server`: Agent-to-Agent server
- `packages/devtools`: Developer tools
- `packages/test-utils`: Testing utilities
- `packages/vscode-ide-companion`: VS Code integration

## Development Setup
- Node.js ~20.19.0 (development), >=20 (production)
- Install: `npm install`
- Build: `npm run build` (packages) or `npm run build:all` (includes sandbox/VS Code)
- Start dev: `npm run start`
- Debug: `npm run debug`
- Test: `npm run test` (unit), `npm run test:e2e` (integration)

## Architecture Decisions
- Monorepo with npm workspaces for package management
- Event-driven scheduler for tool execution
- MCP (Model Context Protocol) for extensibility
- Sandboxing support (Docker/Podman/macOS Seatbelt) for security
- OpenTelemetry tracing for debugging

## Coding Conventions
- Strict TypeScript: `strict: true`, no implicit any, strict null checks
- ESLint: No `require()`, throw Error objects only, no typeof for property checks
- ES modules only (`"type": "module"`)
- React with Ink for CLI rendering
- Vitest for testing
- Prettier for formatting

## Potential Pitfalls
- Node version mismatch: Use ~20.19.0 for dev to avoid upstream issues
- Sandboxing: Set `GEMINI_SANDBOX=true` in ~/.env for security; requires Docker/Podman
- Monorepo: Changes in core may affect multiple packages; run `npm run build` after core changes
- API keys: Required for Gemini access; configure via CLI or env vars
- Tracing: Enabled automatically; use Genkit UI (`npm run telemetry -- --target=genkit`) for debugging

## Key Files and Directories
- `packages/cli/src/index.ts`: Main CLI entry point
- `packages/core/`: Shared backend logic
- `scripts/build.js`: Build orchestration
- `docs/local-development.md`: Detailed dev setup and tracing
- `CONTRIBUTING.md`: Contribution guidelines and PR process
- `evals/`: Evaluation tests for agent behavior
- `integration-tests/`: End-to-end tests

## Links
- [Full documentation](https://geminicli.com/docs/)
- [Local development guide](docs/local-development.md)
- [Contributing guide](CONTRIBUTING.md)
- [Architecture overview](GEMINI.md)</content>
<parameter name="filePath">c:\Users\Home\Documents\GitHub\gemini-cli\AGENTS.md