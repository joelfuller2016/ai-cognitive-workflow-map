# ⚡ Quick Reference: AI Cognitive Workflow Tools

> **Fast access guide for immediate tool selection and workflow implementation**

## 🎯 Immediate Decision Matrix

### Request Type → Tool Strategy

| What You're Asked | Start With | Then Use | Quality Check |
|-------------------|------------|----------|---------------|
| **"Review this code"** | `directory_tree` + `git_status` | `grep_ast` + `code-reasoning` | Security + performance validation |
| **"Research X topic"** | `mcp-reasoner` (complexity analysis) | `web_search` + synthesis | Multiple source verification |
| **"Help debug this"** | `code-reasoning` (problem decomposition) | Code analysis tools + testing | Root cause validation |
| **"Current status of X"** | `web_search` (recent info required) | `web_fetch` for details | Date and source verification |
| **"Plan project Y"** | `taskmanager` + `code-reasoning` | Phased tool application | Feasibility assessment |
| **"Analyze complex problem"** | `mcp-reasoner` (beam search) | Multi-tool orchestration | Iterative validation |

## 🧩 Tool Categories (Quick Pick)

### 🧠 When You Need to THINK
```bash
# Complex analysis with multiple approaches
mcp-reasoner(strategy="beam_search", beamWidth=3)

# Step-by-step problem solving  
code-reasoning(thought="Break down this problem...")

# Adaptive thinking with revisions
sequentialthinking(dynamic_adjustment=true)
```

### 🔍 When You Need INFORMATION
```bash
# Current events, recent info
web_search("topic + recent + 2024/2025")

# Internal company context
google_drive_search("project OR policy OR internal")

# Detailed content analysis
web_fetch(specific_url) # After search results
```

### 💻 When You Need CODE ANALYSIS
```bash
# Start here ALWAYS for code projects
directory_tree(path, depth=3)
git_status(repo_path)

# Deep structural analysis
grep_ast(pattern="class|function", path=repo)

# Pattern matching and exploration
grep(pattern="TODO|FIXME|BUG", path=repo)
```

### 🧠 When You Need PERSISTENCE
```bash
# Store relationships and insights
create_entities([entity_data])
create_relations([relationship_data])

# Manage multi-step workflows
taskmanager.create_project(tasks=[])
```

## ⚡ Common Workflow Patterns

### 🔥 **Code Review (5-Step)**
```
1. directory_tree(repo) + git_status(repo)
2. grep_ast("main patterns", repo)
3. code-reasoning("analyze architecture + issues")
4. web_search("[technology] security best practices 2025")
5. Document findings + recommendations
```

### 🔥 **Research Deep-Dive (4-Step)**
```
1. mcp-reasoner("break down research question")
2. web_search("authoritative sources") + google_drive_search("internal context")
3. web_fetch(key_sources) + synthesis
4. knowledge_graph.store(findings)
```

### 🔥 **Complex Problem Analysis (6-Step)**
```
1. code-reasoning("understand problem scope")
2. mcp-reasoner(strategy="beam_search", explore_alternatives=true)
3. web_search("current best practices + solutions")
4. Apply domain-specific tools
5. Test/validate approach
6. Document solution + rationale
```

## 🚨 Red Flags & Quick Fixes

### ❌ **AVOID These Patterns**
- **Tool hunting**: Randomly trying tools without reasoning first
- **Over-searching**: Multiple searches without synthesis
- **Context loss**: Not using knowledge graph for complex projects
- **Quality skipping**: No validation or source checking

### ✅ **ALWAYS Do This**
- **Reason first**: Start with thinking tools for complex requests
- **Quality gates**: Verify sources, check dates, cross-reference
- **Context persistence**: Use knowledge graph for multi-session work
- **Iterative refinement**: Don't settle for first-pass solutions

## 🎛️ When to Scale Up Tool Usage

| Complexity Signal | Scale Up Action |
|------------------|------------------|
| **Multiple unknowns** | Add `mcp-reasoner` with beam search |
| **Cross-domain problem** | Combine tool categories |
| **High stakes decision** | Multiple reasoning strategies + validation |
| **Multi-session project** | Task management + knowledge persistence |
| **Novel problem type** | Experimental tool combinations |

## 📊 Quality Checkpoints (Don't Skip!)

### ✅ **Information Quality**
- [ ] Sources are authoritative (official docs, academic, industry leaders)
- [ ] Information is current (check dates for rapidly changing topics)
- [ ] Cross-referenced multiple sources
- [ ] Internal context considered (Google Drive search)

### ✅ **Reasoning Quality**  
- [ ] Problem properly decomposed
- [ ] Multiple approaches considered
- [ ] Assumptions documented
- [ ] Edge cases addressed

### ✅ **Code Quality**
- [ ] Security implications assessed
- [ ] Performance considerations reviewed
- [ ] Maintainability evaluated
- [ ] Best practices verified

## 🔄 Emergency Workflows

### 🚨 **"I'm Lost" Recovery**
```bash
1. code-reasoning("What am I trying to solve exactly?")
2. read_graph() # Check existing context
3. Simplify: Break into smaller pieces
4. Start with just one tool + validation
```

### 🚨 **"Results Don't Make Sense"**
```bash
1. web_search("verify key claims")
2. Cross-reference with authoritative sources
3. mcp-reasoner("identify gaps in logic")
4. Iterative refinement
```

### 🚨 **"Too Much Information"**
```bash
1. sequentialthinking("prioritize most important aspects")
2. Focus on user's core question
3. Save secondary insights to knowledge graph
4. Provide focused response + offer to expand
```

---

## 🎯 One-Minute Tool Selection Guide

**30 seconds**: Read the request and ask "What type of problem is this?"

**20 seconds**: Pick primary tool category:
- Need to think? → Reasoning tools
- Need current info? → Web search  
- Need code analysis? → Code tools
- Multi-step project? → Task management

**10 seconds**: Start with that tool and iterate based on results

**Remember**: It's better to start simple and scale up than to over-engineer from the beginning!

---

**🚀 Need the full guide? See [WORKFLOW_MAP.md](./WORKFLOW_MAP.md) for complete documentation.**