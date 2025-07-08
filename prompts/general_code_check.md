# 🔍 AI Agent Instruction: General Code Check

## 🚨 CRITICAL: READ ALL MAGENTO FOLDER INSTRUCTIONS FIRST
**BEFORE performing any code checking task, you MUST read and understand ALL instructions in the [`/magento/`](../magento/) folder.**

### Required Reading Order:
1. **[`design_patterns.md`](../magento/design_patterns.md)** - Complete systematic approach for Magento development
2. **[`terminology.md`](../magento/terminology.md)** - Magento-specific terms and concepts
3. **Any other files in [`/magento/`](../magento/) folder** - Additional Magento-specific guidelines

---

## 📋 Task Overview
Perform comprehensive code checking and analysis of Magento applications to identify issues, verify code quality, and ensure proper functionality. This includes syntax checking, error detection, compatibility verification, and performance analysis.

---

## 🎯 Common Code Check Scenarios

### Syntax and Error Checking
- **PHP syntax errors** - Check for syntax issues in PHP files
- **XML validation** - Verify XML file structure and syntax
- **JavaScript errors** - Check for JS syntax and runtime errors
- **CSS/Less validation** - Verify stylesheet syntax and structure
- **Template errors** - Check PHTML template syntax and logic

### Code Quality Analysis
- **Coding standards** - Verify PSR and Magento coding standards
- **Code complexity** - Check for overly complex methods and classes
- **Code duplication** - Identify duplicate code patterns
- **Documentation** - Verify code documentation and comments
- **Naming conventions** - Check class, method, and variable naming

### Compatibility and Integration
- **Magento version compatibility** - Check for version-specific issues
- **PHP version compatibility** - Verify PHP version requirements
- **Module compatibility** - Check for module conflicts and dependencies
- **API compatibility** - Verify API endpoint functionality
- **Database compatibility** - Check database schema and queries

### Performance Analysis
- **Database queries** - Analyze query performance and optimization
- **Memory usage** - Check for memory leaks and excessive usage
- **Cache efficiency** - Verify caching implementation and usage
- **Frontend performance** - Check JavaScript and CSS optimization
- **Backend performance** - Analyze PHP execution time and bottlenecks

---

## 🔍 Systematic Code Check Process

### Step 1: Environment Preparation
1. **Verify environment readiness** using environment preparation instructions
2. **Ensure clean state** - Clear cache and generated code if needed
3. **Check tool availability** - Verify required tools are available
4. **Set up logging** - Enable appropriate logging for analysis

### Step 2: Initial Code Scan
1. **File structure analysis**:
   ```bash
   # Check for empty or corrupted files
   find app -name "*.php" -size 0
   find app -name "*.xml" -size 0
   
   # Check for syntax errors in PHP files
   find app -name "*.php" -exec php -l {} \;
   
   # Check for XML syntax errors
   find app -name "*.xml" -exec xmllint --noout {} \;
   ```

2. **Basic error detection**:
   ```bash
   # Check error logs
   tail -100 var/log/system.log
   tail -100 var/log/debug.log
   tail -100 var/log/exception.log
   ```

### Step 3: Magento-Specific Checks
1. **Module validation**:
   ```bash
   # Check module registration
   php bin/magento module:status
   
   # Check for module conflicts
   php bin/magento setup:di:compile
   ```

2. **Configuration validation**:
   ```bash
   # Check configuration syntax
   php bin/magento config:show
   
   # Validate database configuration
   php bin/magento setup:db:status
   ```

3. **Cache and generated code**:
   ```bash
   # Check cache status
   php bin/magento cache:status
   
   # Verify generated code
   ls -la generated/code/
   ```

### Step 4: Advanced Analysis
1. **Code quality tools** (if available):
   ```bash
   # PHP CodeSniffer (if installed)
   vendor/bin/phpcs app/code/
   
   # PHP Mess Detector (if installed)
   vendor/bin/phpmd app/code/ text cleancode,codesize,controversial,design,naming,unusedcode
   ```

2. **Performance analysis**:
   ```bash
   # Check memory usage
   php -r "echo memory_get_peak_usage(true) / 1024 / 1024 . ' MB';"
   
   # Check execution time
   time php bin/magento cache:clean
   ```

### Step 5: Frontend Analysis
1. **Static files check**:
   ```bash
   # Check static file deployment
   php bin/magento setup:static-content:deploy -f
   
   # Verify static file permissions
   ls -la pub/static/
   ```

2. **JavaScript and CSS validation**:
   ```bash
   # Check for JS errors (if grunt available)
   grunt jshint
   
   # Check for CSS issues (if grunt available)
   grunt csslint
   ```

---

## ✅ Validation Checklist

### Before Starting Code Check
- [ ] **Environment prepared** - Clean development environment
- [ ] **Tools available** - Required checking tools are installed
- [ ] **Logging enabled** - Appropriate logging is configured
- [ ] **Scope defined** - Clear understanding of what to check
- [ ] **Backup created** - Important files backed up if needed

### During Code Check
- [ ] **Syntax errors identified** - All syntax issues found and logged
- [ ] **Configuration validated** - Magento configuration is correct
- [ ] **Module conflicts detected** - Any module issues identified
- [ ] **Performance issues found** - Performance bottlenecks identified
- [ ] **Security issues checked** - Security vulnerabilities assessed

### After Code Check
- [ ] **Issues documented** - All found issues are clearly documented
- [ ] **Priority assigned** - Issues prioritized by severity
- [ ] **Solutions proposed** - Fixes suggested for identified issues
- [ ] **Testing recommended** - Appropriate testing strategies suggested
- [ ] **Follow-up planned** - Next steps for issue resolution

---

## 🚫 Common Mistakes to Avoid

### Technical Mistakes
- **Skipping environment preparation** - Always prepare environment first
- **Ignoring error logs** - Always check logs for detailed error information
- **Rushing through checks** - Take time to perform thorough analysis
- **Not documenting findings** - Always document what was found
- **Ignoring performance implications** - Consider performance impact of issues

### Process Mistakes
- **Not backing up before changes** - Always backup important files
- **Skipping validation steps** - Always validate findings
- **Not considering user impact** - Consider how issues affect users
- **Ignoring compatibility** - Check for version compatibility issues
- **Not communicating findings** - Clearly communicate results to user

---

## 📝 Response Template

### Code Check Analysis Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ✅ Confirmed: I will follow the code checking workflow

## 🔍 Code Check Analysis Complete

### Environment Status
- **Environment Prepared**: ✅ Ready for code checking
- **Tools Available**: [List available tools]
- **Logging Enabled**: ✅ Appropriate logging configured

### Check Results Summary
- **Files Checked**: [Number] files analyzed
- **Issues Found**: [Number] issues identified
- **Critical Issues**: [Number] critical issues
- **Warnings**: [Number] warnings
- **Recommendations**: [Number] recommendations

### Issues Found
[List of issues with severity levels]

### Recommendations
[List of specific recommendations for fixes]

### Next Steps
[Clear next steps for issue resolution]
```

### Issue Detail Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ✅ Confirmed: I will follow the code checking workflow

## 🐛 Issue Analysis

### Issue Details
- **Type**: [Syntax/Configuration/Performance/Security]
- **Severity**: [Critical/High/Medium/Low]
- **Location**: [File path and line number]
- **Description**: [Detailed description of the issue]

### Root Cause
[Explanation of why the issue occurs]

### Impact Assessment
- **User Impact**: [How this affects users]
- **Performance Impact**: [Performance implications]
- **Security Impact**: [Security implications if any]

### Proposed Solution
[Step-by-step solution approach]

### Testing Strategy
[How to test the fix]

### Risk Assessment
[Potential risks and mitigation strategies]
```

---

## 🔗 Related Resources

- **[`design_patterns.md`](../magento/design_patterns.md)** - Systematic development approach
- **[`terminology.md`](../magento/terminology.md)** - Magento terms and concepts
- **[`fix_magento_bugs.md`](./fix_magento_bugs.md)** - Bug fixing workflow
- **[`environment_preparation.md`](../ai_instructions/environment_preparation.md)** - Environment preparation
- **Magento Developer Documentation** - Official debugging guides
- **PHP CodeSniffer Documentation** - Coding standards checking
- **PHP Mess Detector Documentation** - Code quality analysis 