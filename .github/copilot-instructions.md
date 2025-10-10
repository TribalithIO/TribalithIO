# TribalithIO AI Coding Agent Instructions

## Project Overview

TribalithIO is a browser-based real-time strategy game focused on territorial control, alliances, and resource management. The codebase is a fork/rewrite of OpenFront.io, with custom enhancements and modular architecture.

## Architecture & Major Components

- **src/client/**: Frontend game client (UI, game logic, networking)
- **src/server/**: Node.js backend server (game state, multiplayer, security)
- **map-generator/**: Go-based tool for generating playable map files
- **resources/**: Static assets (images, flags, sounds, cosmetics, maps)
- **tests/**: Jest-based unit and integration tests for core logic

## Developer Workflows

- **Install dependencies**: `npm i`
- **Run development mode (client & server)**: `npm run dev`
- **Run client only**: `npm run client`
- **Run server only**: `npm run server`
- **Build for production**: `npm run build`
- **Run tests**: `npm test`
- **Map generation**: In `map-generator/`, use `go run .` after preparing assets/maps and info.json

## Key Conventions & Patterns

- **Alliance, territory, and resource logic**: Centralized in `src/core/` and `src/server/`
- **Security (rate limiting, fingerprinting, bot detection)**: See `src/server/Gatekeeper` and related modules
- **Map assets**: Each map requires an `image.png` and `info.json` in `assets/maps/<map_name>/` (see `map-generator/README.md`)
- **Testing**: All new logic should have corresponding Jest tests in `tests/` (see file naming conventions)
- **TypeScript**: Used throughout client/server; type definitions in `src/global.d.ts`
- **Environment variables**: Example config in `example.env`

## Integration Points

- **Client-server communication**: WebSocket and REST APIs (see `src/client/networking` and `src/server/routes`)
- **External dependencies**: npm (Node.js), Go (map-generator), Docker (optional, see `Dockerfile`)
- **Assets licensing**: AGPL v3 for code, CC BY-SA 4.0 for assets

## Examples

- To add a new map: follow steps in `map-generator/README.md` and update `main.go`
- To extend alliance logic: modify relevant classes in `src/core/Alliance*` and add tests in `tests/Alliance*.test.ts`
- To debug server: use `npm run server` and inspect logs/output

## References

- Main documentation: `README.md`, `map-generator/README.md`, `src/server/README.md`
- For security, see `src/server/Gatekeeper`
- For assets, see `resources/` and `map-generator/assets/`

---

**If any section is unclear or missing, please provide feedback so this guide can be improved for future AI agents.**
