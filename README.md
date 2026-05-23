# 👋 Hi, I'm Kamlesh

> **Building resilient, intelligent systems — one annotation at a time.**

I'm a backend engineer passionate about **distributed systems**, **fault-tolerant architectures**, and **AI-powered developer tooling**. I work primarily in **Java** and **Python**, with a focus on making complex failure scenarios first-class citizens in application design.

---

## 🚀 What I'm Building

### 🩹 [lazarus-lib](https://github.com/byte-by-k/lazarus-lib)
> *Spring-native annotation library for intelligent exception healing and async reprocessing*

Going beyond `@Retryable` — `@Lazarus` captures failed method payloads, persists them, and routes them for reprocessing via **Kafka**, **AWS Lambda**, or a **REST endpoint** of your choice. Never silently drop a failure again.

```java
@Lazarus(
  retryOn = {TransientException.class, TimeoutException.class},
  backoff = @LazarusBackoff(delay = 1000, multiplier = 2),
  reprocessVia = ReprocessingStrategy.KAFKA
)
public void processOrder(@LazarusPayload OrderRequest order) {
    // Your business logic
}
```

---

### 🤖 [mcp-agent-java](https://github.com/byte-by-k/mcp-agent-java)
> *AI Agent backed by an MCP (Model Context Protocol) server — Java edition*

An AI agent built with **Spring AI** or **LangChain4j** that dynamically discovers and calls tools exposed by an MCP server. Demonstrates the full agent loop: tool discovery → reasoning → invocation → synthesis.

---

### 🐍 [mcp-agent-python](https://github.com/byte-by-k/mcp-agent-python)
> *AI Agent backed by an MCP server — Python edition*

The same agent pattern implemented in Python using **FastMCP** + **Anthropic SDK** (or LangChain). Lightweight, async-first, and easy to extend with new MCP tool servers.

---

### 🔍 [lazarus-mcp](https://github.com/byte-by-k/lazarus-mcp)
> *MCP Server that exposes the Lazarus database as AI-queryable tools*

An MCP server that lets AI agents (and humans via Claude) query, inspect, retry, and analyze failed payloads stored by `lazarus-lib`. Bridge between your healing infrastructure and intelligent agents.

---

## 🛠️ Tech Stack

| Domain | Technologies |
|---|---|
| **Languages** | Java 17+, Python 3.11+ |
| **Frameworks** | Spring Boot, Spring AI, LangChain4j, FastAPI, FastMCP |
| **Messaging** | Apache Kafka, AWS Lambda, REST/Webhooks |
| **AI / Agents** | Anthropic Claude, MCP (Model Context Protocol), LangChain |
| **Data** | PostgreSQL, JPA/Hibernate, Flyway |
| **Build** | Maven, Gradle, pip, Poetry |

---

## 🧠 Ideas & Philosophy

- **Failures are data** — every exception carries context worth preserving and learning from.
- **Annotations > boilerplate** — developer experience is a feature.
- **Agents should be tool-aware** — MCP makes AI agents practical, not just powerful.
- **Cross-language patterns matter** — the same architectural ideas should work in Java and Python.

---

## 📫 Reach me

- 📧 kamleshcy@gmail.com
- 💼 [LinkedIn](https://linkedin.com/in/kamleshcy)
- 🐙 [GitHub](https://github.com/byte-by-k)

---

*"The best retry strategy is the one that remembers why it failed."*
