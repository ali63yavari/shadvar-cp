# Shadvar Aspire Agent (Go)

> [!TIP]
> A lightweight, container-native orchestration agent for .NET Aspire — enabling remote, polyglot service orchestration via Docker and Kubernetes. Runs as a standalone container, interprets Aspire app models, and executes services across environments. Designed for performance, extensibility, and production-aligned developer workflows.

> [!NOTE]
> “Shadvar” (شَدوَر) is a name derived from ancient Persian roots, possibly drawing from terms like xšaθra (meaning dominion or order in Avestan) and var (meaning holder or bearer). It symbolically refers to “the bearer of order” or “keeper of harmony”—which perfectly aligns with the role of an orchestrator in software systems.

**Shadvar** is an open-source orchestration bridge for [.NET Aspire](https://github.com/dotnet/aspire), built in Go for maximum portability and runtime efficiency. It enables you to run, manage, and observe services defined in Aspire app models on any container runtime — locally or remotely.

✅ Supports Docker  
🔜 Kubernetes-native (via CRD or controller)  
🔜 Secrets management  
🔜 Remote developer orchestration

---

## 🚀 Getting Started

### Prerequisites
- Go 1.21+
- Docker (installed and running)

### Clone and Run
```bash
git clone https://github.com/yourusername/aspire-agent-go.git
cd aspire-agent-go
go run ./cmd/agent
```

The agent starts an HTTP server on `:8080` and listens for orchestration commands.

### Example: Run a Service
Send a POST request with your Aspire `appModel.json` to run a service:
```bash
curl -X POST http://localhost:8080/run \
     -H "Content-Type: application/json" \
     -d @path/to/appModel.json
```

---

## 📁 Project Structure
```
aspire-agent/
├── cmd/agent/           # Main entrypoint
│   └── main.go
├── internal/
│   ├── api/             # HTTP API handlers
│   ├── orchestrator/    # Core orchestration logic
│   ├── appmodel/        # Aspire app model parsing
│   └── runtime/         # Environment utilities
├── pkg/
│   └── dockerclient/    # Docker API wrapper
├── Dockerfile           # To build the agent container
├── go.mod / go.sum      # Go dependencies
└── README.md
```

---

## 📦 Features (Planned)
- [x] Run services using Docker
- [ ] Pull and inject Aspire app model
- [ ] Log streaming support
- [ ] Secrets integration (Vault, AWS, etc.)
- [ ] Kubernetes support via CRDs and controllers
- [ ] Remote orchestration over HTTP/gRPC

---

## 🤝 Contributing
We welcome contributions! Open issues, submit pull requests, or suggest ideas.

### Dev Tips
- Use [Docker SDK for Go](https://pkg.go.dev/github.com/docker/docker/client)
- Keep containers lightweight (`scratch` or `distroless` base images)
- Follow idiomatic Go practices (`go fmt`, `golangci-lint`, etc.)

---

## 📄 License
MIT — use, modify, and share freely.

---

## 👨‍💻 Maintainer
Built by [YourName](https://github.com/yourusername) — focused on developer-friendly orchestration for Aspire and beyond.

---

## 💬 Feedback
Open an [issue](https://github.com/yourusername/aspire-agent-go/issues) or start a discussion. We'd love to hear your ideas!
