# Getting Started with Your AI-Powered Development Environment

## What You've Got

You now have a **production-ready, enterprise-grade AI development infrastructure** for your multi-technology AWS Data Lake platform. This system will supercharge your development with intelligent, context-aware assistance.

## 🎯 Core Components

### 1. Auto-Activating Skills (5)

Your skills automatically suggest themselves based on what you're working on:

| Skill | Triggers When | Helps With |
|-------|--------------|------------|
| **python-data-engineering** | Editing `.py` files, working with Airflow/Spark | PySpark optimization, ETL patterns, Airflow DAGs |
| **go-microservices** | Editing `.go` files, working with gRPC | Clean architecture, performance, concurrency |
| **nextjs-development** | Editing `.tsx` files in `app/` | Server Components, App Router, performance |
| **data-lake-management** | Working with S3/Glue/Athena | Medallion architecture, partitioning, governance |
| **aws-infrastructure** | Editing `.tf` files, Terraform work | IaC best practices, security, cost optimization |

### 2. Specialized Agents (6)

Call these experts for complex tasks:

| Agent | Expertise | Use For |
|-------|-----------|---------|
| **python-data-engineer** | PySpark, Airflow, Glue | "Optimize this Spark job", "Design ETL pipeline" |
| **go-backend-architect** | Go, gRPC, microservices | "Build auth service", "Review architecture" |
| **aws-infrastructure-architect** | Terraform, AWS, IaC | "Design VPC", "Set up EKS cluster" |
| **data-lake-architect** | Medallion, partitioning, catalog | "Design data lake", "Optimize queries" |
| **devops-sre-agent** | Kubernetes, CI/CD, monitoring | "Set up observability", "Configure autoscaling" |
| **fullstack-architect** | Next.js, React, APIs | "Build dashboard", "Integrate with backend" |

### 3. Hook System

The magic that makes everything work:
- **skill-activation-prompt**: Suggests skills based on your prompts
- **post-tool-use-tracker**: Tracks file changes for context
- **Other hooks**: Additional automation (copied from showcase)

## 🚀 How to Use

### Automatic Skill Activation

Just start working! The system detects what you're doing:

**Example 1: Working on PySpark**
```python
# You create: data-engineering/etl/user_events.py
from pyspark.sql import SparkSession

# Claude Code automatically suggests:
"I notice you're working with PySpark. The python-data-engineering
skill can help with:
- Job optimization patterns
- Performance tuning
- Best practices for ETL

Would you like me to use this skill?"
```

**Example 2: Building Infrastructure**
```hcl
# You create: infrastructure/terraform/vpc.tf
resource "aws_vpc" "main" {
  cidr_block = "10.0.0.0/16"
}

# Claude Code automatically suggests:
"I see you're working on AWS infrastructure with Terraform.
The aws-infrastructure skill provides:
- VPC design best practices
- Security configurations
- Cost optimization tips

Shall I activate it?"
```

### Invoking Specialized Agents

For complex, multi-step tasks, ask for a specialized agent:

**Example: Optimize Data Pipeline**
```
You: "I have a Spark job processing 100GB daily that takes 2 hours.
Can you optimize it?"

Claude: I'll use the python-data-engineer agent to analyze and
optimize your Spark job.

[Agent performs deep analysis, provides optimizations]
```

**Example: Design Infrastructure**
```
You: "Design a production-ready EKS cluster for our data lake platform"

Claude: I'll use the aws-infrastructure-architect agent to design
a secure, scalable EKS setup.

[Agent provides complete Terraform configuration]
```

## 📚 Skill Details

### Python Data Engineering
**Location**: `.claude/skills/python-data-engineering/`

**Covers**:
- PySpark job structure and optimization
- Airflow DAG patterns
- AWS Glue integration
- Data quality validation
- FastAPI data services
- Streaming with Kafka/Kinesis
- Performance tuning

**Resource Files**:
- `resources/pyspark-patterns.md`: Join strategies, window functions, optimization

### Go Microservices
**Location**: `.claude/skills/go-microservices/`

**Covers**:
- Clean architecture patterns
- gRPC service design
- Concurrency patterns (goroutines, channels)
- Database integration (GORM)
- Middleware and authentication
- Testing strategies
- Observability

### Next.js Development
**Location**: `.claude/skills/nextjs-development/`

**Covers**:
- App Router and Server Components
- Server Actions for mutations
- Client vs Server component patterns
- Data fetching strategies
- Authentication with NextAuth
- Performance optimization
- SEO and metadata

### Data Lake Management
**Location**: `.claude/skills/data-lake-management/`

**Covers**:
- Medallion architecture (Bronze/Silver/Gold)
- S3 bucket organization
- Partitioning strategies
- Schema evolution
- Data quality frameworks
- Cost optimization
- Query performance tuning

### AWS Infrastructure
**Location**: `.claude/skills/aws-infrastructure/`

**Covers**:
- Terraform module design
- VPC and networking
- EKS cluster setup
- RDS configuration
- S3 and data lake infrastructure
- Security best practices
- Cost optimization

## 🎓 Learning Path

### Week 1: Get Familiar
1. Read `.claude/ARCHITECTURE.md`
2. Browse through skill files
3. Try editing files and watch skills activate
4. Test one agent on a simple task

### Week 2: Deep Dive
1. Pick your primary language (Python/Go/TypeScript)
2. Read that skill's resource files thoroughly
3. Apply patterns in your code
4. Invoke agents for code reviews

### Week 3: Master the System
1. Customize skill-rules.json for your needs
2. Create new skills for your specific patterns
3. Use agents for complex architecture decisions
4. Share learnings with team

## 🛠️ Customization

### Adjust Skill Triggers

Edit `.claude/skills/skill-rules.json`:

```json
{
  "python-data-engineering": {
    "promptTriggers": {
      "keywords": [
        "python",
        "pyspark",
        // Add your team's terminology
        "data pipeline",
        "etl job"
      ]
    },
    "fileTriggers": {
      "pathPatterns": [
        "**/*.py",
        // Add your project structure
        "services/data-processing/**/*.py"
      ]
    }
  }
}
```

### Create New Skills

1. Create directory: `.claude/skills/your-skill-name/`
2. Add `SKILL.md` with frontmatter
3. Add to `skill-rules.json`
4. Test with hook commands

### Add New Agents

1. Create `.claude/agents/your-agent.md`
2. Define role, expertise, approach
3. Document deliverables
4. Start using immediately (no config needed!)

## 🔧 Troubleshooting

### Skills Not Activating?

1. Check hook is executable:
   ```bash
   chmod +x .claude/hooks/skill-activation-prompt.sh
   ```

2. Test hook manually:
   ```bash
   echo '{"prompt":"working with pyspark"}' | \
     npx tsx .claude/hooks/skill-activation-prompt.ts
   ```

3. Verify `skill-rules.json` syntax:
   ```bash
   cat .claude/skills/skill-rules.json | jq .
   ```

### Hooks Not Running?

Check `.claude/settings.json` (or `settings.local.json`) has:
```json
{
  "hooks": {
    "UserPromptSubmit": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "$CLAUDE_PROJECT_DIR/.claude/hooks/skill-activation-prompt.sh"
          }
        ]
      }
    ]
  }
}
```

## 🎯 Best Practices

1. **Let Skills Activate Naturally**: Don't force them, let the system suggest
2. **Use Agents for Complex Tasks**: Multi-step architecture, optimization, design
3. **Read Resource Files**: Deep patterns in skill resource files
4. **Iterate on Triggers**: Adjust keywords based on your vocabulary
5. **Share with Team**: Document team-specific patterns in skills

## 📈 Measuring Success

Track how the AI infrastructure helps:
- ✅ Faster onboarding (new devs productive faster)
- ✅ Fewer bugs (best practices enforced)
- ✅ Better code quality (consistent patterns)
- ✅ Faster development (less searching for examples)
- ✅ Better documentation (skills are living docs)

## 🎉 You're Ready!

Your AI development infrastructure is **production-ready** and waiting to help.

**Next Steps**:
1. Start coding in your primary language
2. Watch skills activate
3. Invoke an agent for a complex task
4. Customize triggers for your team

**Questions?**
- Read: `.claude/ARCHITECTURE.md`
- Browse: `.claude/skills/*/SKILL.md`
- Check: `.claude/agents/*.md`

---

**Happy Coding!** Your AI pair programmer is ready to work. 🚀
