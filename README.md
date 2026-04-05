# OpenLLM Skill Packs

Pre-built skill packs for OpenLLM agents. Each pack is a collection of markdown skills for a specific domain.

## Install

Using the skill manager (inside OpenLLM):
```
/skill install https://github.com/RachEma-ux/openllm-skills providers
/skill install https://github.com/RachEma-ux/openllm-skills chat
/skill install https://github.com/RachEma-ux/openllm-skills all
```

Or manually:
```bash
git clone https://github.com/RachEma-ux/openllm-skills.git /tmp/skills
cp /tmp/skills/packs/providers/*.md ~/.claude/commands/
```

## Packs

| Pack | Skills | Purpose |
|------|--------|---------|
| **providers** | review-provider, test-connection, sync-keys | LLM provider management |
| **chat** | debug-stream, token-audit | Chat streaming & tokens |
| **agents** | review-pipeline | Agent orchestration |
| **documents** | chunk-preview, embedding-inspect | RAG pipeline |
| **automation** | workflow-lint, trigger-test | Workflow & triggers |
| **governance** | policy-check, secret-rotate | Security & policies |
| **database** | schema-review, migration-check | PostgreSQL & Drizzle |
| **frontend** | component-review, route-audit | React UI |
| **general** | review-security, full-review | Cross-cutting reviews |

## Profiles

Switch between skill sets:
```
/skill profile providers    → only provider skills active
/skill profile frontend     → only frontend skills active  
/skill profile all          → everything active
```

## Create Your Own

Drop a `.md` file in any pack directory:

```markdown
---
name: my-skill
description: What it does
context: fork
allowedTools:
  - Read
  - Grep
  - Bash
---

Your prompt instructions here.
Use $ARGUMENTS for user input.
```
