# 💻 Code Review Workflow Example

**Scenario**: AI asked to review a React web application repository for security, performance, and maintainability issues.

**Request**: *"Can you review this React codebase and identify any security vulnerabilities, performance issues, or maintainability concerns?"*

---

## 🎯 Workflow Application

### Phase 1: Repository Overview (Required)

**Tools Used**: `directory_tree`, `git_status`, `git_log`

```bash
# Get repository structure
directory_tree(path="/project/react-app", depth=3)

# Check current git status  
git_status(repo_path="/project/react-app")

# Review recent commits for context
git_log(repo_path="/project/react-app", max_count=10)
```

**Expected Output Analysis**:
- Directory structure reveals React app with standard organization
- Git status shows current branch and any uncommitted changes
- Recent commits provide context about development activity

**Decision Point**: Repository is active React project with standard structure → Proceed to structural analysis

### Phase 2: Structural Code Analysis

**Tools Used**: `grep_ast`, `grep`

```bash
# Analyze main architectural patterns
grep_ast(pattern="class|function|interface|const.*=.*=>", path="/project/react-app")

# Look for security-related patterns
grep(pattern="localStorage|sessionStorage|innerHTML|eval|dangerouslySetInnerHTML", path="/project/react-app")

# Check for performance anti-patterns
grep(pattern="useEffect\\(\\)|useState\\(\\)|console\\.log", path="/project/react-app")

# Find TODO/FIXME items
grep(pattern="TODO|FIXME|HACK|BUG", path="/project/react-app")
```

**Expected Output Analysis**:
- AST analysis reveals component architecture and patterns
- Security patterns identify potential vulnerabilities
- Performance patterns show state management usage
- TODO items highlight known issues

### Phase 3: Reasoning-Based Assessment

**Tools Used**: `code-reasoning`

```bash
code-reasoning(
  thought="Analyze the React codebase structure. I found components using localStorage, multiple useEffect hooks, and some dangerouslySetInnerHTML usage. Let me systematically evaluate: 1) Security risks from localStorage and innerHTML usage, 2) Performance implications of useEffect patterns, 3) Maintainability concerns from component organization",
  thought_number=1, 
  total_thoughts=4, 
  next_thought_needed=true
)
```

**Continue reasoning iterations**:
- **Thought 2**: Analyze specific security vulnerabilities found
- **Thought 3**: Evaluate performance optimization opportunities  
- **Thought 4**: Assess maintainability and code organization issues

### Phase 4: Current Best Practices Research

**Tools Used**: `web_search`, `web_fetch`

```bash
# Research current React security best practices
web_search("React security best practices 2025 XSS prevention localStorage")

# Get performance optimization guidelines
web_search("React performance optimization hooks useEffect 2025")

# Check for latest security vulnerabilities
web_search("React security vulnerabilities 2025 dangerouslySetInnerHTML")
```

**Follow up with detailed content**:
```bash
# Fetch detailed security guide
web_fetch("https://reactjs.org/docs/security.html")

# Get performance best practices
web_fetch("https://react.dev/learn/render-and-commit")
```

### Phase 5: Quality Validation & Documentation

**Synthesis Process**:
1. **Security Assessment**: Cross-reference found patterns with current security guidelines
2. **Performance Evaluation**: Compare usage patterns with React best practices
3. **Maintainability Review**: Evaluate code organization against industry standards

---

## 📋 Example Findings & Recommendations

### 🚨 Security Issues Found

1. **XSS Vulnerability** (High Priority)
   ```javascript
   // Found in UserProfile.jsx
   <div dangerouslySetInnerHTML={{__html: userInput}} />
   ```
   **Recommendation**: Use DOMPurify for sanitization or remove dangerous HTML injection

2. **Sensitive Data in localStorage** (Medium Priority)
   ```javascript
   // Found in auth.js
   localStorage.setItem('authToken', response.token)
   ```
   **Recommendation**: Use httpOnly cookies or sessionStorage with encryption

### ⚡ Performance Issues Found

1. **Unnecessary Re-renders** (Medium Priority)
   ```javascript
   // Found in Dashboard.jsx - useEffect without dependencies
   useEffect(() => {
     fetchData()
   }) // Missing dependency array
   ```
   **Recommendation**: Add proper dependency arrays and consider useMemo/useCallback

2. **Large Bundle Size** (Low Priority)
   - All components imported in main bundle
   **Recommendation**: Implement code splitting with React.lazy()

### 🔧 Maintainability Concerns

1. **Inconsistent Component Structure** (Medium Priority)
   - Mix of class and functional components
   **Recommendation**: Standardize on functional components with hooks

2. **Missing TypeScript** (Low Priority)
   - JavaScript used throughout, potential runtime errors
   **Recommendation**: Gradual migration to TypeScript for better type safety

---

## ✅ Quality Validation Checklist

### Security Validation
- [x] Cross-referenced with OWASP React security guidelines
- [x] Verified against latest React security advisories
- [x] Checked for authentication/authorization patterns

### Performance Validation  
- [x] Compared with React DevTools profiling best practices
- [x] Verified against Core Web Vitals recommendations
- [x] Checked bundle analysis recommendations

### Maintainability Validation
- [x] Evaluated against React community standards
- [x] Checked folder structure best practices
- [x] Assessed testing coverage patterns

---

## 🔄 Follow-up Actions

### Immediate (High Priority)
1. Fix XSS vulnerability in UserProfile component
2. Secure localStorage usage in authentication

### Short-term (Medium Priority)  
1. Add dependency arrays to useEffect hooks
2. Standardize component architecture
3. Implement code splitting for performance

### Long-term (Low Priority)
1. Migrate to TypeScript gradually
2. Implement comprehensive testing strategy
3. Set up automated security scanning

---

## 📊 Tool Effectiveness Analysis

### What Worked Well
- **`grep_ast`**: Excellent for finding architectural patterns
- **`code-reasoning`**: Great for connecting findings and prioritizing issues
- **`web_search`**: Crucial for validating against current best practices

### What Could Be Improved
- **More specific pattern matching**: Could have used more targeted regex patterns
- **Automated testing**: Could have suggested running existing tests
- **Performance profiling**: Could have recommended using browser dev tools

### Lessons Learned
- Start broad with directory structure, then narrow to specific patterns
- Always validate findings against current best practices via web search
- Use reasoning tools to prioritize and connect findings systematically

---

**💡 Key Success Factor**: The combination of structural analysis + reasoning + current research provided comprehensive coverage that no single tool could achieve alone.