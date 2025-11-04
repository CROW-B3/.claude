# Claude Code AI Development Infrastructure

> **Intelligent development assistance powered by auto-activating skills and specialized expert agents**

[![AI-Powered](https://img.shields.io/badge/AI-Claude%20Code-blue.svg)]()
[![Skills](https://img.shields.io/badge/Skills-5%20Auto--Activating-green.svg)]()
[![Agents](https://img.shields.io/badge/Agents-6%20Specialized-orange.svg)]()

## Overview

This directory contains a comprehensive AI development infrastructure for the AWS Data Lake platform. It provides context-aware assistance across Python, Go, Next.js, and AWS technologies through an intelligent system of auto-activating skills and specialized expert agents.

## 🎯 Quick Start

The system works automatically! Just start coding:

1. **Edit any file** in the project
2. **Skills auto-activate** based on file type and content
3. **Get expert help** by accepting suggestions or invoking agents
4. **Develop faster** with intelligent, context-aware assistance

## 📁 Directory Structure

```
.claude/
├── skills/                    # 5 Auto-activating skills
│   ├── python-data-engineering/
│   ├── go-microservices/
│   ├── nextjs-development/
│   ├── data-lake-management/
│   ├── aws-infrastructure/
│   └── skill-rules.json       # Activation triggers
├── agents/                    # 6 Specialized expert agents
│   ├── python-data-engineer.md
│   ├── go-backend-architect.md
│   ├── aws-infrastructure-architect.md
│   ├── data-lake-architect.md
│   ├── devops-sre-agent.md
│   └── fullstack-architect.md
├── hooks/                     # Auto-activation system
│   ├── user-prompt-submit.sh
│   └── activation-logic/
├── docs/                      # Additional documentation
├── ARCHITECTURE.md            # System architecture
├── GETTING_STARTED.md         # Onboarding guide
├── SUMMARY.md                 # Infrastructure stats
└── README.md                  # This file
```

## 🤖 Auto-Activating Skills (5)

Skills automatically suggest themselves based on what you're working on:

### 1. Python Data Engineering
**Activates when:** Working with `.py` files, PySpark, Pandas, Airflow
**Helps with:**
- PySpark optimization and performance tuning
- ETL pipeline design and best practices
- Pandas data manipulation
- Airflow DAG development

**Triggers:** `*.py`, `pyspark`, `pandas`, `airflow`, `etl`, `dataframe`

### 2. Go Microservices
**Activates when:** Working with `.go` files, gRPC, microservices
**Helps with:**
- Clean architecture patterns
- Goroutine and concurrency best practices
- gRPC service design
- Error handling and middleware

**Triggers:** `*.go`, `grpc`, `microservice`, `goroutine`, `gin`, `echo`

### 3. Next.js Development
**Activates when:** Working in `app/` directory with `.tsx` files
**Helps with:**
- Next.js 14+ App Router patterns
- Server Components vs Client Components
- Data fetching strategies
- UI component design with shadcn/ui

**Triggers:** `app/*.tsx`, `next.js`, `server component`, `app router`

### 4. Data Lake Management
**Activates when:** Working with S3, Glue, Athena, data lake concepts
**Helps with:**
- Medallion architecture (Bronze/Silver/Gold)
- Data partitioning strategies
- Query optimization
- Schema evolution

**Triggers:** `s3`, `glue`, `athena`, `data lake`, `medallion`, `parquet`

### 5. AWS Infrastructure
**Activates when:** Working with `.tf` files, Terraform, AWS services
**Helps with:**
- Infrastructure as Code best practices
- Security and IAM configurations
- Cost optimization
- Multi-environment setups

**Triggers:** `*.tf`, `terraform`, `cloudformation`, `cdk`, `aws`

## 👨‍💻 Specialized Agents (6)

For complex tasks, invoke expert agents:

### 1. Python Data Engineer
**For:** Pipeline optimization, ETL design, performance issues
**Expertise:** PySpark, data processing, distributed computing

### 2. Go Backend Architect
**For:** Microservice design, system architecture, performance
**Expertise:** Go patterns, concurrency, API design

### 3. AWS Infrastructure Architect
**For:** Cloud infrastructure, IaC, security, scalability
**Expertise:** Terraform, AWS services, architecture patterns

### 4. Data Lake Architect
**For:** Data lake design, query optimization, data modeling
**Expertise:** Medallion architecture, big data patterns

### 5. DevOps SRE Agent
**For:** Kubernetes, CI/CD, monitoring, deployment
**Expertise:** K8s, observability, automation

### 6. Fullstack Architect
**For:** End-to-end features, API integration, system design
**Expertise:** Full stack development, integration patterns

## ⚙️ How It Works

### Auto-Activation System

The system uses hooks and skill rules to automatically detect context:

1. **File Detection:** Monitors file paths and extensions
2. **Content Analysis:** Scans for technology keywords
3. **Skill Matching:** Compares against `skill-rules.json`
4. **Smart Suggestions:** Offers relevant skills automatically

### Skill Rules Configuration

Skills are defined in `skills/skill-rules.json`:

```json
{
  "python-data-engineering": {
    "filePatterns": ["*.py", "**/airflow/**", "**/spark/**"],
    "keywords": ["pyspark", "pandas", "airflow", "etl"],
    "priority": 10
  }
}
```

### Customization

To adjust triggers:
1. Edit `skills/skill-rules.json`
2. Add your project-specific patterns
3. Adjust priority values (higher = more likely to activate)

## 📊 System Stats

- **Total Skills:** 5 auto-activating
- **Total Agents:** 6 specialized experts
- **Documentation:** 4,500+ lines
- **Languages Supported:** Python, Go, TypeScript
- **Frameworks:** 8+ (PySpark, Airflow, Gin, Next.js, Terraform, K8s, etc.)
- **AWS Services:** 15+ integrated

## 🚀 Usage Examples

### Example 1: Working with PySpark

```python
# You edit: services/python/etl/process_events.py
from pyspark.sql import SparkSession

df = spark.read.parquet("s3://bucket/data/")
```

**Claude suggests:**
> "I notice you're working with PySpark. The `python-data-engineering` skill can help with optimization patterns, performance tuning, and ETL best practices. Would you like me to activate it?"

### Example 2: Building Go Service

```go
// You edit: services/go/api/handlers.go
func HandleRequest(ctx context.Context) error {
    // implementation
}
```

**Claude suggests:**
> "I see you're working with Go. The `go-microservices` skill provides clean architecture patterns, concurrency best practices, and error handling guidance. Activate it?"

### Example 3: Complex Task with Agent

```
You: "This Spark job processes 100GB and takes 2 hours. How can I optimize it?"

Claude: [Automatically invokes python-data-engineer agent]
"I'll analyze your Spark job for optimization opportunities..."
```

## 🎓 Documentation

| Document | Purpose |
|----------|---------|
| [GETTING_STARTED.md](GETTING_STARTED.md) | Complete onboarding guide |
| [ARCHITECTURE.md](ARCHITECTURE.md) | System architecture deep-dive |
| [SUMMARY.md](SUMMARY.md) | Infrastructure summary & stats |
| [skills/](skills/) | Individual skill documentation |
| [agents/](agents/) | Agent definitions and use cases |

## 🔧 Configuration Files

### Essential Files
- `skills/skill-rules.json` - Skill activation triggers
- `hooks/user-prompt-submit.sh` - Auto-activation hook
- `settings.local.json` - User preferences

### Modifying Skills

To add new triggers to a skill:

1. Edit `skills/skill-rules.json`
2. Add patterns under the skill name
3. Test by editing matching files

Example:
```json
{
  "python-data-engineering": {
    "filePatterns": ["*.py", "**/custom-path/**"],
    "keywords": ["pyspark", "custom-keyword"],
    "priority": 10
  }
}
```

## 🛠️ Troubleshooting

### Skills Not Activating?

1. Check `skills/skill-rules.json` for correct patterns
2. Verify hooks are enabled in Claude Code settings
3. Look for file pattern matches in your current file

### Agent Not Available?

1. Check the agent file exists in `agents/` directory
2. Verify the agent is properly documented
3. Try explicitly requesting the agent by name

## 📈 Benefits

- ✅ **Faster Development:** Context-aware suggestions reduce research time
- ✅ **Best Practices:** Skills embed production-proven patterns
- ✅ **Multi-Technology:** Seamless support across Python, Go, TypeScript
- ✅ **Auto-Discovery:** No need to remember commands or docs
- ✅ **Expert Help:** Specialized agents for complex problems
- ✅ **Customizable:** Adjust triggers to match your workflow

## 🎯 Next Steps

1. **Read** [GETTING_STARTED.md](GETTING_STARTED.md) for detailed onboarding
2. **Explore** individual skill documentation in `skills/`
3. **Try** editing files and watch skills activate
4. **Invoke** an agent for a complex task
5. **Customize** `skill-rules.json` for your needs

## 🤝 Contributing

To add new skills or agents:

1. Follow the structure in existing skills/agents
2. Update `skill-rules.json` with activation triggers
3. Document the skill/agent thoroughly
4. Test with relevant file types

## 📞 Support

- **Repository:** [github.com/CROW-B3/.claude](https://github.com/CROW-B3/.claude)
- **Issues:** [GitHub Issues](https://github.com/CROW-B3/.claude/issues)
- **Main Project:** Located in parent directory `../`

## 📄 License

MIT License - Part of the AWS Data Lake Platform project

---

**Status:** Active Development
**Last Updated:** 2025-11-04
**Version:** 1.0.0

🚀 **Your AI development assistant is ready! Start coding and watch the magic happen.**
