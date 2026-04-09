When running commands with the `run_command` tool, follow these steps:
1. Always use a working directory (`Cwd`) within the workspace: `/home/huyph/Projects/php/v82/workflows`
2. Execute the command using `docker compose` with direct paths to the Laradock directory:
   `docker compose -f ../laradock/docker-compose.yml --project-directory ../laradock exec -u laradock -T workspace bash -c "cd workflows && <your_command>"`

**Important Notes:**
- All commands MUST run inside the `workspace` container.
- If you need to run a command in a specific subdirectory of `workflows`, ensure you `cd` to it inside the container: `cd workflows/subdir && <command>`.
- Use the `-T` flag with `docker compose exec` to avoid TTY issues in non-interactive environments.
