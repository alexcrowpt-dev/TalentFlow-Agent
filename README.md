# TalentFlow Agent

**Open-source AI-agent for automated job applications with a focus on quality over quantity.**

TalentFlow Agent is designed to revolutionize the job application process by moving beyond mass-mailing spam. It uses advanced AI (LLMs, RAG systems) to intelligently match candidates to vacancies, personalize applications, and ensure transparency, significantly increasing the quality and success rate of job-seeking efforts.

## 🚀 Vision & Business Model

The project follows a hybrid model:
- **Open-source Core:** A self-hosted, community-supported core for maximum transparency and flexibility.
- **Commercial Cloud SaaS:** A hosted solution with advanced features, analytics, and integrations.
- **Enterprise Self-Hosted:** Custom solutions for large companies requiring on-premise deployment and compliance.

| Model | Target Audience | Pricing | Key Features |
| :--- | :--- | :--- | :--- |
| **Free (Open-Source)** | Job seekers, Developers | Free | Self-hosted, community support, core matching logic. |
| **Starter (SaaS)** | Job seekers | $19/mo | Cloud access, 100 applications/month, basic analytics. |
| **Pro (SaaS)** | Power users, Recruiters | $49/mo | 500 applications/month, advanced analytics, integrations. |
| **Enterprise** | Large Companies | Custom | Unlimited usage, on-premise, SLA, dedicated support. |

## 🛠️ Tech Stack

The architecture is built for scalability, performance, and AI-first development.

| Component | Technology | Details |
| :--- | :--- | :--- |
| **Backend** | Python 3.11+, FastAPI, SQLAlchemy, PostgreSQL, Redis | High-performance API and core business logic. |
| **AI/ML** | OpenAI GPT-4o, Anthropic Claude, Ollama (fallback), LangChain, RAG-systems | Multi-LLM strategy for best performance and cost. |
| **Automation** | Flowise AI, n8n | No-code/low-code agent building and workflow automation. |
| **Frontend** | Next.js 14, TypeScript, Tailwind CSS, shadcn/ui | Modern, fast, and responsive user interface. |
| **DevOps** | Docker Compose, Kubernetes, GitHub Actions | Containerization and CI/CD for reliable deployment. |

## 🎯 Immediate Goals (Pre-MVP Stage)

The current focus is on rapid development to achieve the following milestones:

1.  **Week 1-2:** Core vacancy parser + basic AI matching.
2.  **Week 3-4:** MCP server + Docker deployment.
3.  **Week 5:** Landing page + first 100 GitHub stars.
4.  **Week 6:** Product Hunt launch + first paying customers.

## 🤝 Contributing

We welcome contributions! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines on how to submit issues, features, and pull requests.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
