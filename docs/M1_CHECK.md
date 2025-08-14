# M1 - Reset baseline checklist

What we expect:
- Server runs locally (dev_start_all or equivalent).
- WORKSPACES_ROOT is set to the external rdev-test/workspaces.
- Git operations (editor Git UI) run from the server repo root.
- .env remains local and is ignored.

How to test:
1. Start servers: pwsh -ExecutionPolicy Bypass -File .\tools\dev_start_all.ps1
2. Confirm health endpoints /db/health and /health
3. Check 
ode -e "console.log(require('./api/lib/fsSafe').WORKSPACES_ROOT)"
4. Create a workspace via editor and confirm files appear in the WORKSPACES_ROOT.
