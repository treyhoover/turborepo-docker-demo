Simply open as a vscode devcontainer, or run it manually with the following:

```
docker compose -f .devcontainer/docker-compose.yml up -d
docker compose -f .devcontainer/docker-compose.yml exec app pnpm exec pnpm exec turbo dev
```