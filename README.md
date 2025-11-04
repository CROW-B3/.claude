# Claude Code AI Development Infrastructure

Intelligent development assistance powered by auto-activating skills and specialized expert agents for AWS Data Lake platform development.

## Overview

This directory contains an AI development infrastructure that provides context-aware assistance across Python, Go, Next.js, and AWS technologies through an intelligent system of auto-activating skills and specialized expert agents.

## Quick Start

The system operates automatically:

1. Edit any file in the project
2. Skills auto-activate based on file type and content
3. Get expert help by accepting suggestions or invoking agents
4. Develop with intelligent, context-aware assistance

## Directory Structure

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
│   ├── skill-activation-prompt.sh
│   ├── skill-activation-prompt.ts
│   └── post-tool-use-tracker.sh
├── commands/                  # Custom slash commands
├── ARCHITECTURE.md            # System architecture
└── README.md                  # This file
```

## Auto-Activating Skills

Skills automatically activate based on file context and content:

### Python Data Engineering
- **Activates:** `.py` files, PySpark, Pandas, Airflow
- **Focus:** PySpark optimization, ETL pipeline design, data manipulation, Airflow DAGs
- **Triggers:** `*.py`, `pyspark`, `pandas`, `airflow`, `etl`, `dataframe`

### Go Microservices
- **Activates:** `.go` files, gRPC, microservices
- **Focus:** Clean architecture, concurrency patterns, gRPC service design, error handling
- **Triggers:** `*.go`, `grpc`, `microservice`, `goroutine`, `gin`, `echo`

### Next.js Development
- **Activates:** `app/` directory with `.tsx` files
- **Focus:** App Router patterns, Server/Client Components, data fetching, UI design
- **Triggers:** `app/*.tsx`, `next.js`, `server component`, `app router`

### Data Lake Management
- **Activates:** S3, Glue, Athena operations
- **Focus:** Medallion architecture, partitioning strategies, query optimization, schema evolution
- **Triggers:** `s3`, `glue`, `athena`, `data lake`, `medallion`, `parquet`

### AWS Infrastructure
- **Activates:** `.tf` files, Terraform, AWS services
- **Focus:** Infrastructure as Code, security configurations, cost optimization, multi-environment setups
- **Triggers:** `*.tf`, `terraform`, `cloudformation`, `cdk`, `aws`

## Specialized Agents

Expert agents for complex tasks:

### Python Data Engineer
- **Purpose:** Pipeline optimization, ETL design, performance issues
- **Expertise:** PySpark, data processing, distributed computing

### Go Backend Architect
- **Purpose:** Microservice design, system architecture, performance
- **Expertise:** Go patterns, concurrency, API design

### AWS Infrastructure Architect
- **Purpose:** Cloud infrastructure, IaC, security, scalability
- **Expertise:** Terraform, AWS services, architecture patterns

### Data Lake Architect
- **Purpose:** Data lake design, query optimization, data modeling
- **Expertise:** Medallion architecture, big data patterns

### DevOps SRE Agent
- **Purpose:** Kubernetes, CI/CD, monitoring, deployment
- **Expertise:** K8s, observability, automation

### Fullstack Architect
- **Purpose:** End-to-end features, API integration, system design
- **Expertise:** Full stack development, integration patterns

## System Architecture

### Auto-Activation System

The system uses hooks and skill rules for automatic context detection:

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

To adjust activation triggers:
1. Edit `skills/skill-rules.json`
2. Add project-specific patterns
3. Adjust priority values (higher = more likely to activate)

## Usage Examples

### Working with PySpark

```python
# File: services/python/etl/process_events.py
from pyspark.sql import SparkSession

df = spark.read.parquet("s3://bucket/data/")
```

Claude automatically suggests the `python-data-engineering` skill for optimization patterns and ETL best practices.

### Building Go Services

```go
// File: services/go/api/handlers.go
func HandleRequest(ctx context.Context) error {
    // implementation
}
```

Claude automatically suggests the `go-microservices` skill for clean architecture patterns and concurrency guidance.

## Configuration Files

### Essential Files
- `skills/skill-rules.json` - Skill activation triggers
- `hooks/skill-activation-prompt.sh` - Auto-activation hook
- `hooks/post-tool-use-tracker.sh` - File tracking hook
- `settings.local.json` - User preferences

### Modifying Skills

To add new triggers:

```json
{
  "python-data-engineering": {
    "filePatterns": ["*.py", "**/custom-path/**"],
    "keywords": ["pyspark", "custom-keyword"],
    "priority": 10
  }
}
```

## Troubleshooting

### Skills Not Activating

1. Verify `skills/skill-rules.json` contains correct patterns
2. Ensure hooks are enabled in Claude Code settings
3. Check file patterns match current working files

### Agent Not Available

1. Verify agent file exists in `agents/` directory
2. Check agent documentation is complete
3. Request agent explicitly by name

## System Statistics

- **Skills:** 5 auto-activating
- **Agents:** 6 specialized experts
- **Documentation:** 4,500+ lines
- **Languages:** Python, Go, TypeScript
- **Frameworks:** PySpark, Airflow, Gin, Next.js, Terraform, Kubernetes
- **AWS Services:** 15+ integrated

## Contributing

To add new skills or agents:

1. Follow the structure in existing skills/agents
2. Update `skill-rules.json` with activation triggers
3. Document thoroughly
4. Test with relevant file types

## Repository Information

- **Repository:** [github.com/CROW-B3/.claude](https://github.com/CROW-B3/.claude)
- **Issues:** [GitHub Issues](https://github.com/CROW-B3/.claude/issues)
- **License:** MIT License
- **Status:** Active Development
- **Last Updated:** 2025-11-04
- **Version:** 1.0.0
