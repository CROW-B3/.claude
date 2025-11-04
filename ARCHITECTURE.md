# Multi-Technology Data Lake Platform - Architecture

## Overview

This is a cutting-edge, enterprise-grade data lake platform leveraging AWS infrastructure with a multi-technology stack designed for scalability, performance, and modern development practices.

## Technology Stack

### Infrastructure & Cloud
- **AWS Services**: S3, Glue, Athena, EMR, Lambda, ECS/EKS, RDS, DynamoDB, CloudWatch
- **Infrastructure as Code**: Terraform, AWS CDK
- **Container Orchestration**: Kubernetes (EKS), Docker
- **CI/CD**: GitHub Actions, AWS CodePipeline

### Backend Services
- **Python**: FastAPI, Flask, Pandas, PySpark, Apache Airflow
- **Go**: Gin, Echo, high-performance microservices
- **Node.js**: Express, NestJS (for specific services)

### Frontend
- **Next.js 14+**: App Router, Server Components, Server Actions
- **React 18+**: TypeScript, TanStack Query, Zustand
- **UI Library**: shadcn/ui, Tailwind CSS
- **Visualization**: D3.js, Recharts, Apache ECharts

### Data Engineering
- **Data Lake**: AWS S3 with structured zones (raw/bronze, processed/silver, curated/gold)
- **Data Catalog**: AWS Glue Data Catalog
- **ETL/ELT**: AWS Glue, Apache Spark, DBT, Pandas
- **Streaming**: Apache Kafka, AWS Kinesis
- **Orchestration**: Apache Airflow, AWS Step Functions
- **Query Engine**: AWS Athena, Presto, Trino

### Databases
- **OLTP**: PostgreSQL (RDS), DynamoDB
- **OLAP**: Redshift, ClickHouse
- **Cache**: Redis, ElastiCache
- **Time Series**: TimescaleDB, InfluxDB

### Observability
- **Monitoring**: CloudWatch, Prometheus, Grafana
- **Logging**: CloudWatch Logs, ELK Stack
- **Tracing**: AWS X-Ray, OpenTelemetry, Jaeger
- **Error Tracking**: Sentry

## Architecture Principles

### 1. Multi-Agent Intelligence System
- **Specialized Agents**: Each technology stack has dedicated AI agents
- **Context-Aware**: Agents understand project structure and activate automatically
- **Skill-Based**: Modular skills following 500-line rule with progressive disclosure
- **Auto-Activation**: Hook-based system for intelligent skill suggestions

### 2. Microservices Architecture
- **Service Decomposition**: Domain-driven design
- **API Gateway**: Centralized routing and authentication
- **Service Mesh**: Istio for advanced traffic management
- **Event-Driven**: Kafka/Kinesis for inter-service communication

### 3. Data Lake Zones (Medallion Architecture)
```
Raw Zone (Bronze)     → Landing zone for raw data
Processed Zone (Silver) → Cleaned, validated, enriched data
Curated Zone (Gold)   → Business-ready, aggregated data
```

### 4. Security & Compliance
- **IAM**: Fine-grained access control
- **Encryption**: At-rest (KMS) and in-transit (TLS)
- **Secrets Management**: AWS Secrets Manager, Vault
- **Audit**: CloudTrail, audit logging
- **Compliance**: GDPR, HIPAA-ready configurations

## Project Structure

```
/
├── infrastructure/           # IaC (Terraform, CDK)
│   ├── terraform/
│   ├── cdk/
│   └── kubernetes/
├── services/
│   ├── python/              # Python microservices
│   │   ├── data-ingestion/
│   │   ├── etl-pipeline/
│   │   └── ml-service/
│   ├── go/                  # Go microservices
│   │   ├── api-gateway/
│   │   ├── auth-service/
│   │   └── stream-processor/
│   └── nodejs/              # Node.js services
│       └── notification-service/
├── frontend/                # Next.js application
│   ├── app/
│   ├── components/
│   └── lib/
├── data-engineering/
│   ├── airflow/            # DAGs and workflows
│   ├── glue/               # Glue jobs
│   ├── spark/              # Spark applications
│   └── dbt/                # DBT transformations
├── shared/
│   ├── schemas/            # Shared data schemas
│   ├── proto/              # gRPC definitions
│   └── utils/
└── .claude/                # AI Infrastructure
    ├── skills/
    ├── agents/
    ├── hooks/
    └── commands/
```

## Agent System Architecture

### Specialized Agents
1. **Python Data Engineer Agent**: PySpark, Pandas, Airflow, Glue
2. **Go Backend Agent**: Microservices, gRPC, high-performance APIs
3. **Next.js Frontend Agent**: App Router, Server Components, RSC
4. **AWS Infrastructure Agent**: Terraform, CDK, AWS services
5. **Data Lake Architect Agent**: Data modeling, ETL design, optimization
6. **DevOps/SRE Agent**: Kubernetes, CI/CD, monitoring
7. **Security & Compliance Agent**: IAM, encryption, audit
8. **Performance Optimization Agent**: Query optimization, caching, scaling

### Skills (Auto-Activating)
1. **python-data-engineering**: PySpark, Pandas, Glue, Airflow patterns
2. **go-microservices**: Go best practices, gRPC, performance
3. **nextjs-development**: App Router, Server Components, RSC patterns
4. **aws-infrastructure**: IaC, AWS services, best practices
5. **data-lake-management**: Medallion architecture, ETL patterns
6. **kubernetes-deployment**: K8s manifests, Helm, operators
7. **api-design**: RESTful, GraphQL, gRPC design patterns
8. **data-modeling**: Schema design, normalization, partitioning

## Development Workflow

### 1. Skill Auto-Activation
- Hook system detects file type and context
- Automatically suggests relevant skills
- Progressive disclosure loads detailed resources as needed

### 2. Agent-Assisted Development
- Specialized agents for complex tasks
- Architecture reviews
- Code refactoring
- Performance optimization

### 3. Automated Quality Checks
- Pre-commit hooks for linting, formatting
- Type checking (mypy, TypeScript strict mode)
- Unit/integration tests
- Infrastructure validation (terraform validate, cfn-lint)

### 4. CI/CD Pipeline
```
Code Push → Lint/Test → Build → Security Scan → Deploy Staging → E2E Tests → Deploy Prod
```

## Key Features

### Intelligent Development Environment
- Context-aware skill activation
- Multi-language support (Python, Go, TypeScript)
- Infrastructure-as-code assistance
- Data engineering pattern recognition

### Production-Ready Patterns
- Error handling and resilience
- Observability built-in
- Security best practices
- Scalability from day one

### Data Lake Excellence
- Automated data quality checks
- Schema evolution management
- Partition optimization
- Cost optimization strategies

## Getting Started

1. **Set up Claude Code Infrastructure**
   ```bash
   # Skills and agents are auto-configured
   # Hook system activates based on file context
   ```

2. **Initialize Project Components**
   ```bash
   # Infrastructure
   cd infrastructure/terraform && terraform init

   # Python services
   cd services/python && poetry install

   # Go services
   cd services/go && go mod download

   # Frontend
   cd frontend && npm install
   ```

3. **Deploy Data Lake**
   ```bash
   cd infrastructure/terraform/data-lake
   terraform apply
   ```

## Skill Activation Triggers

### Python Development
- Keywords: python, pandas, pyspark, airflow, glue, etl
- Files: `**/*.py`, `**/Dockerfile.python`
- Content: `import pandas`, `from pyspark`, `from airflow`

### Go Development
- Keywords: golang, microservice, grpc, gin, echo
- Files: `**/*.go`, `**/go.mod`
- Content: `package main`, `func main()`

### Next.js Development
- Keywords: nextjs, react, server component, app router
- Files: `app/**/*.tsx`, `components/**/*.tsx`
- Content: `'use client'`, `'use server'`, `export default async`

### AWS Infrastructure
- Keywords: terraform, cdk, cloudformation, aws, infrastructure
- Files: `**/*.tf`, `**/*.yaml` (CloudFormation), `**/cdk/**`
- Content: `resource "aws_`, `AWS::`, `new cdk.`

### Data Engineering
- Keywords: data lake, etl, pipeline, airflow, spark, glue
- Files: `airflow/dags/**/*.py`, `glue/**/*.py`, `spark/**/*.scala`
- Content: `DAG(`, `GlueContext`, `SparkSession`

## Performance Targets

- **API Response Time**: p95 < 200ms
- **ETL Processing**: Scalable to TB/day
- **Frontend TTI**: < 2s
- **Query Performance**: Athena queries optimized with partitioning
- **Availability**: 99.9% uptime SLA

## Security Measures

- **Zero Trust Architecture**: Assume breach, verify everything
- **Least Privilege**: Minimal IAM permissions
- **Data Encryption**: AES-256 at rest, TLS 1.3 in transit
- **Secrets Rotation**: Automated rotation for all credentials
- **Vulnerability Scanning**: Container and dependency scanning
- **Audit Logging**: Comprehensive CloudTrail logging

## Next Steps

1. Review skill definitions in `.claude/skills/`
2. Understand agent capabilities in `.claude/agents/`
3. Configure hook system for auto-activation
4. Start with infrastructure deployment
5. Build services iteratively with AI assistance

---

**Built with**: Claude Code Infrastructure Showcase patterns + Production best practices
**Status**: Production-Ready Architecture
**Last Updated**: 2025-11-04
