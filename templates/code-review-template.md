# 💻 Code Review Workflow Template

**Template Purpose**: Systematic code repository analysis for security, performance, and maintainability  
**Complexity Level**: Moderate to Complex  
**Estimated Time**: 15-45 minutes depending on repository size

---

## 📋 Pre-Execution Checklist

- [ ] Repository path identified: `{PROJECT_PATH}`
- [ ] Review focus areas defined: `{DOMAIN_FOCUS}` (Security/Performance/General)
- [ ] Required tools accessible: `directory_tree`, `git_status`, `grep_ast`, `code-reasoning`, `web_search`
- [ ] Knowledge graph available for findings storage
- [ ] Clear understanding of repository technology stack

---

## 🚀 Workflow Execution Steps

### Step 1: Repository Context Analysis

**Purpose**: Understand project structure and current state

```bash
# Get comprehensive directory structure
directory_tree(path=\"{PROJECT_PATH}\", depth=3)

# Check current git status for context
git_status(repo_path=\"{PROJECT_PATH}\")

# Review recent commits for development activity
git_log(repo_path=\"{PROJECT_PATH}\", max_count=10)
```

**Expected Outputs**:
- Clear understanding of project organization
- Awareness of current development state
- Context about recent changes and activity

**Decision Point**: Is this a standard project structure? Any immediate red flags visible?

### Step 2: Structural Code Analysis

**Purpose**: Identify architectural patterns and potential issues

```bash
# Analyze main code patterns and architecture
grep_ast(pattern=\"class|function|interface|const.*=.*=>\", path=\"{PROJECT_PATH}\")

# Security-focused pattern search
grep(pattern=\"localStorage|sessionStorage|innerHTML|eval|dangerouslySetInnerHTML|document.write\", path=\"{PROJECT_PATH}\")

# Performance pattern analysis  
grep(pattern=\"useEffect\\\\(\\\\)|useState\\\\(\\\\)|for.*in.*|while.*|\\.forEach|\\.map|\\.filter\", path=\"{PROJECT_PATH}\")

# Code quality indicators
grep(pattern=\"TODO|FIXME|HACK|BUG|XXX|console\\.log|alert\\\\(\", path=\"{PROJECT_PATH}\")
```

**Expected Outputs**:
- Architectural pattern identification
- Security vulnerability candidates
- Performance bottleneck indicators  
- Code quality and maintenance indicators

**Decision Point**: What are the primary concerns based on patterns found?

### Step 3: Reasoning-Based Assessment

**Purpose**: Systematic analysis of findings and priority assessment

```bash
code-reasoning(
  thought=\"I need to analyze the code review findings systematically. From the directory structure, I can see [DESCRIBE STRUCTURE]. The grep patterns revealed [DESCRIBE KEY FINDINGS]. Let me prioritize these findings: 1) Security issues - [LIST], 2) Performance concerns - [LIST], 3) Maintainability issues - [LIST]. I should focus on [HIGHEST PRIORITY AREA] first.\",
  thought_number=1,
  total_thoughts=4,
  next_thought_needed=true
)
```

**Continue reasoning process**:
```bash
# Thought 2: Deep dive into priority issues
code-reasoning(
  thought=\"Focusing on [PRIORITY AREA], I found [SPECIFIC ISSUES]. These are concerning because [REASONING]. The potential impact is [ASSESS IMPACT]. I should research current best practices for [SPECIFIC TECHNOLOGY/PATTERN].\",
  thought_number=2,
  total_thoughts=4,
  next_thought_needed=true
)

# Thought 3: Solution approach analysis
code-reasoning(
  thought=\"For the identified issues, potential solutions include [LIST SOLUTIONS]. I need to validate these against current industry best practices and consider implementation complexity.\",
  thought_number=3,
  total_thoughts=4,
  next_thought_needed=true
)

# Thought 4: Recommendations synthesis  
code-reasoning(
  thought=\"Based on my analysis, I recommend: 1) Immediate fixes for [HIGH PRIORITY], 2) Short-term improvements for [MEDIUM PRIORITY], 3) Long-term architectural considerations for [LOW PRIORITY]. Let me research current best practices to validate these recommendations.\",
  thought_number=4,
  total_thoughts=4,
  next_thought_needed=false
)
```

**Expected Outputs**:
- Prioritized list of issues and concerns
- Understanding of root causes and implications
- Initial solution approaches identified

### Step 4: Best Practices Research

**Purpose**: Validate findings against current industry standards

```bash
# Research current best practices for identified technology
web_search(\"{TECHNOLOGY_STACK} best practices 2025 {DOMAIN_FOCUS}\")

# Security-specific research if relevant
web_search(\"{TECHNOLOGY_STACK} security vulnerabilities 2025 OWASP\")

# Performance optimization research if relevant  
web_search(\"{TECHNOLOGY_STACK} performance optimization 2025\")

# Code quality and maintainability standards
web_search(\"{TECHNOLOGY_STACK} code review checklist enterprise standards\")
```

**Follow-up detailed research**:
```bash
# Fetch comprehensive guides for critical areas
web_fetch(\"[URL_OF_AUTHORITATIVE_GUIDE]\")
```

**Expected Outputs**:
- Current industry best practices validation
- Security advisory information
- Performance optimization techniques
- Code quality standards and checklists

### Step 5: Quality Validation & Documentation

**Purpose**: Validate findings and create comprehensive recommendations

#### Security Validation Checklist
- [ ] Cross-referenced with OWASP guidelines
- [ ] Verified against technology-specific security advisories  
- [ ] Checked for authentication/authorization patterns
- [ ] Validated input sanitization and output encoding
- [ ] Reviewed dependency security status

#### Performance Validation Checklist
- [ ] Compared with Web Vitals standards (if web application)
- [ ] Evaluated against technology performance best practices
- [ ] Assessed database query efficiency (if applicable)
- [ ] Reviewed caching and optimization strategies
- [ ] Analyzed bundle size and loading patterns (if applicable)

#### Maintainability Validation Checklist
- [ ] Evaluated code organization and structure
- [ ] Assessed documentation quality and coverage
- [ ] Reviewed testing strategy and coverage
- [ ] Checked coding standards consistency
- [ ] Analyzed technical debt indicators

---

## 📊 Expected Output Template

### 🚨 **Critical Issues** (Fix Immediately)
1. **[Issue Category]**: [Specific Issue Description]
   - **Location**: [File/Line References]
   - **Risk Level**: High/Medium/Low
   - **Impact**: [Describe Impact]
   - **Recommendation**: [Specific Action]
   - **Resources**: [Links to Best Practices]

### ⚡ **Performance Opportunities** (Address Soon)
1. **[Performance Area]**: [Specific Optimization]
   - **Current Impact**: [Measurable Impact]
   - **Optimization Approach**: [Recommended Solution]
   - **Expected Benefit**: [Quantified Improvement]
   - **Implementation Effort**: [Time/Complexity Estimate]

### 🔧 **Maintainability Improvements** (Long-term)
1. **[Code Quality Area]**: [Improvement Description]
   - **Current State**: [Assessment]
   - **Target State**: [Desired Outcome]
   - **Implementation Plan**: [Phased Approach]
   - **Success Metrics**: [Measurable Outcomes]

### ✅ **Positive Findings**
- [List things done well]
- [Highlight good practices observed]
- [Note architectural strengths]

---

## 🎯 Customization Guidelines

### For Different Technology Stacks

**React/Frontend Applications**:
- Focus on XSS prevention, bundle optimization, accessibility
- Add patterns: `className|style=|onClick|onChange`
- Research React security best practices specifically

**Node.js/Backend Applications**:
- Focus on input validation, SQL injection, authentication
- Add patterns: `req\\.|res\\.|express|router|middleware`
- Research Node.js security vulnerabilities specifically

**Python Applications**:
- Focus on injection attacks, dependency security, data handling
- Add patterns: `import|def |class |if __name__|eval|exec`
- Research Python security best practices specifically

**Mobile Applications**:
- Focus on data storage, network security, platform-specific issues
- Add patterns specific to iOS/Android development
- Research mobile security guidelines (OWASP Mobile)

### For Different Review Focus Areas

**Security-Focused Review**:
- Increase security pattern searches
- Add authentication/authorization analysis
- Include dependency vulnerability checking
- Research OWASP guidelines extensively

**Performance-Focused Review**:
- Add performance profiling tool suggestions
- Include database query analysis
- Focus on algorithmic complexity patterns
- Research performance monitoring best practices

**Architecture Review**:
- Focus on design patterns and structure
- Analyze module dependencies and coupling
- Evaluate scalability and maintainability
- Research architectural best practices

---

## 🔄 Error Handling & Iteration

### Common Issues & Solutions

**Issue**: Too many results from pattern matching
- **Solution**: Use more specific patterns or focus on high-priority areas first

**Issue**: Repository too large for comprehensive analysis
- **Solution**: Focus on critical directories first, use sampling approach

**Issue**: Technology stack not familiar
- **Solution**: Increase research time, focus on universal principles

**Issue**: Conflicting best practice recommendations
- **Solution**: Prioritize official documentation and recent sources

### Iteration Strategies

**Quick Pass** (15 minutes):
- Focus on security patterns only
- Use basic grep instead of grep_ast
- Limit reasoning to 2 thoughts
- Quick web search validation

**Comprehensive Pass** (45+ minutes):
- Full structural analysis with grep_ast
- Extended reasoning with multiple pathways
- Detailed research with web_fetch
- Complete validation checklists

---

## 📈 Success Metrics

### Immediate Metrics
- Number of critical issues identified
- Security vulnerabilities discovered
- Performance bottlenecks found
- Code quality improvements suggested

### Long-term Metrics  
- Reduction in production bugs (post-implementation)
- Improved security scan results
- Performance metrics improvement
- Developer productivity increase

---

**💡 Template Usage Tip**: Customize the grep patterns based on your specific technology stack and focus areas. Start with broader patterns and narrow down based on initial findings.