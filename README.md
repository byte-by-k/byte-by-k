# Hi, I'm Kamlesh 👋

Engineering leader, architect, and builder — 20+ years designing distributed systems, shipping full-stack products, leading global teams, and occasionally open-sourcing the tools I wish had existed sooner.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-kamleshcy-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/kamleshcy)
[![Email](https://img.shields.io/badge/Email-kamleshcy%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:kamleshcy@gmail.com)

---

## Tech Stack

**Languages & Frameworks**

![Java](https://img.shields.io/badge/Java-17+-orange?style=flat&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?style=flat&logo=springboot)
![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![React](https://img.shields.io/badge/React-JS-61DAFB?style=flat&logo=react&logoColor=black)
![Vert.x](https://img.shields.io/badge/Vert.x-Framework-purple?style=flat)

**Infrastructure & Cloud**

![AWS](https://img.shields.io/badge/AWS-Cloud-FF9900?style=flat&logo=amazonaws)
![Kubernetes](https://img.shields.io/badge/Kubernetes-Container%20Orchestration-326CE5?style=flat&logo=kubernetes)
![Docker](https://img.shields.io/badge/Docker-Containers-2496ED?style=flat&logo=docker)
![Azure DevOps](https://img.shields.io/badge/Azure%20DevOps-CI%2FCD-0078D7?style=flat&logo=azuredevops)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-Streaming-231F20?style=flat&logo=apachekafka)

**Data & Caching**

![Hazelcast](https://img.shields.io/badge/Hazelcast-Distributed%20Cache-FF6600?style=flat)
![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?style=flat&logo=redis)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-SQL-336791?style=flat&logo=postgresql)

---

## Open Source — The Lazarus Ecosystem

**What happens to your data when all retries are exhausted?**
Spring Retry drops the payload. Lazarus persists it, reprocesses it, and makes it queryable by AI agents.

```java
@Lazarus(
    retryOn      = { TransientDataException.class, TimeoutException.class },
    backoff      = @LazarusBackoff(initialDelay = 500, multiplier = 2, maxDelay = 8000),
    retryLimit   = 3,
    reprocessVia = ReprocessingStrategy.KAFKA,
    topic        = "lazarus.reprocess.orders"
)
public void processOrder(@LazarusPayload OrderRequest order) {
    // Just write the happy path — Lazarus handles the rest
}
```

| Repo | What it does |
|---|---|
| [**lazarus-lib**](https://github.com/byte-by-k/lazarus-lib) | Spring Boot AOP library — `@Lazarus` annotation, exponential backoff, payload persistence |
| [**lazarus-mcp**](https://github.com/byte-by-k/lazarus-mcp) | MCP Server — exposes the Lazarus DB as AI-queryable tools (`list_events`, `retry_batch`, …) |
| [**mcp-agent-java**](https://github.com/byte-by-k/mcp-agent-java) | Java AI agent (Spring AI / LangChain4j) that talks to lazarus-mcp |
| [**mcp-agent-python**](https://github.com/byte-by-k/mcp-agent-python) | Python AI agent (Anthropic SDK / LangChain) that talks to lazarus-mcp |

---

*Building things that don't fall apart quietly.*
