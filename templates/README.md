# 📋 Workflow Templates

Ready-to-use templates for common AI cognitive workflow scenarios. Copy, customize, and apply these templates for consistent, high-quality results.

## 🎯 How to Use Templates

1. **Copy Template**: Use the appropriate template for your scenario
2. **Customize Parameters**: Adjust file paths, search terms, and reasoning prompts  
3. **Execute Sequentially**: Follow the step-by-step structure
4. **Validate Results**: Include quality checkpoints
5. **Document Insights**: Store findings in knowledge graph

---

## 📂 Available Templates

### 🔍 Analysis Templates
- **[request-analysis-template.md](./request-analysis-template.md)** - General request analysis and complexity assessment
- **[complex-problem-template.md](./complex-problem-template.md)** - Multi-step reasoning for complex problems

### 💻 Code Templates  
- **[code-review-template.md](./code-review-template.md)** - Comprehensive code repository analysis
- **[security-review-template.md](./security-review-template.md)** - Security-focused code assessment
- **[performance-review-template.md](./performance-review-template.md)** - Performance optimization analysis

### 📚 Research Templates
- **[technical-research-template.md](./technical-research-template.md)** - Deep technical topic investigation
- **[market-research-template.md](./market-research-template.md)** - Competitive and market analysis
- **[internal-research-template.md](./internal-research-template.md)** - Company-specific document research

### 🧠 Reasoning Templates
- **[multi-pathway-template.md](./multi-pathway-template.md)** - Beam search reasoning for alternatives
- **[sequential-reasoning-template.md](./sequential-reasoning-template.md)** - Step-by-step problem solving
- **[decision-framework-template.md](./decision-framework-template.md)** - Structured decision making

---

## 🔧 Template Variables

Most templates use these common variables - replace with your specific values:

| Variable | Description | Example |
|----------|-------------|---------|
| `{REQUEST_DESCRIPTION}` | The original user request | "Review this codebase for security issues" |
| `{PROJECT_PATH}` | Path to code repository | "/project/my-app" |
| `{SEARCH_TERMS}` | Web search keywords | "React security best practices 2025" |
| `{COMPLEXITY_LEVEL}` | Simple/Moderate/Complex | "Complex" |
| `{DOMAIN_FOCUS}` | Subject area focus | "Security", "Performance", "Architecture" |
| `{TIME_CONSTRAINT}` | Available time/effort | "Quick overview" vs "Comprehensive analysis" |

---

## ⚡ Quick Template Selection Guide

### Choose by Request Type

| Request Pattern | Recommended Template |
|----------------|----------------------|
| **"Review this code..."** | [code-review-template.md](./code-review-template.md) |
| **"Research X topic..."** | [technical-research-template.md](./technical-research-template.md) |
| **"Analyze this problem..."** | [complex-problem-template.md](./complex-problem-template.md) |
| **"What's the current state of..."** | [market-research-template.md](./market-research-template.md) |
| **"Find information about..."** | [internal-research-template.md](./internal-research-template.md) |
| **"Help me decide..."** | [decision-framework-template.md](./decision-framework-template.md) |

### Choose by Complexity Level

| Complexity | Template Approach |
|------------|------------------|
| **Simple** | [request-analysis-template.md](./request-analysis-template.md) |
| **Moderate** | Domain-specific template + validation |
| **Complex** | [multi-pathway-template.md](./multi-pathway-template.md) + domain template |

---

## 🔄 Template Customization Guidelines

### 🎛️ **Adjusting Tool Parameters**

```bash
# Reasoning Tools - Adjust based on complexity
mcp-reasoner(strategy="beam_search", beamWidth=3)  # Standard
mcp-reasoner(strategy="mcts", numSimulations=75)   # Deep analysis

# Search Tools - Adjust scope and specificity  
web_search("broad topic 2025")                     # Initial research
web_search("specific technical detail framework")   # Focused research

# Code Tools - Adjust depth and patterns
directory_tree(path, depth=2)                      # Quick overview
directory_tree(path, depth=4)                      # Comprehensive analysis
```

### 📊 **Quality Checkpoint Customization**

**Basic Quality Checks** (All Templates):
- Source verification and currency checking
- Cross-reference multiple sources  
- Document assumptions and limitations

**Domain-Specific Checks**:
- **Code Reviews**: Security, performance, maintainability
- **Research**: Authority, currency, comprehensiveness
- **Analysis**: Logic validity, alternative consideration

### 🔗 **Integration Point Customization**

**Knowledge Management Integration**:
```bash
# Store findings for future reference
create_entities([{
  "name": "Analysis Results", 
  "entityType": "Workflow Output",
  "observations": ["Key findings and insights"]
}])
```

**Task Management Integration**:
```bash
# For multi-step projects
taskmanager.create_project({
  "name": "Analysis Project",
  "tasks": ["Phase 1", "Phase 2", "Validation"]
})
```

---

## 📋 Template Validation Checklist

Before using any template, ensure:

### ✅ **Tool Availability**
- [ ] Required tools are accessible and functional
- [ ] Proper permissions for file access and web search
- [ ] Knowledge graph and task management systems ready

### ✅ **Context Preparation**  
- [ ] Clear understanding of the request scope
- [ ] Relevant file paths and project context identified
- [ ] Time and quality expectations established

### ✅ **Customization Readiness**
- [ ] Template variables identified and values prepared
- [ ] Domain-specific requirements understood
- [ ] Quality validation criteria defined

---

## 🚀 Advanced Template Usage

### 🔄 **Template Chaining**
Combine multiple templates for complex scenarios:

```
1. Start: request-analysis-template.md
2. Branch: domain-specific template (code/research/analysis)  
3. Enhance: multi-pathway-template.md for alternatives
4. Conclude: decision-framework-template.md for recommendations
```

### 🧠 **Custom Template Creation**
For frequently repeated scenarios:

1. **Identify Pattern**: Note recurring request types
2. **Extract Structure**: Document successful tool sequences
3. **Generalize Steps**: Create reusable variable structure
4. **Validate Template**: Test with multiple scenarios
5. **Document Usage**: Include examples and customization notes

### 📈 **Template Evolution**
Keep templates current and effective:

- **Regular Review**: Update tools and techniques quarterly
- **Success Tracking**: Monitor which templates work best
- **Community Input**: Incorporate feedback and improvements
- **Version Control**: Track template changes and improvements

---

**💡 Pro Tip**: Start with the simplest applicable template and scale up complexity only as needed. Better to get good results quickly than to over-engineer from the start!

---

**🔗 Next Steps**: Choose a template below that matches your current scenario and customize it for your specific needs.