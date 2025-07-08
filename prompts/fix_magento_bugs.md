# 🐛 AI Agent Instruction: Fix Magento Bugs

## 🚨 CRITICAL: READ ALL MAGENTO FOLDER INSTRUCTIONS FIRST
**BEFORE performing any bug fixing task, you MUST read and understand ALL instructions in the [`/magento/`](../magento/) folder.**

### Required Reading Order:
1. **[`design_patterns.md`](../magento/design_patterns.md)** - Complete systematic approach for Magento development
2. **[`terminology.md`](../magento/terminology.md)** - Magento-specific terms and concepts
3. **Any other files in [`/magento/`](../magento/) folder** - Additional Magento-specific guidelines

---

## 📋 Task Overview
Fix bugs and issues in Magento applications by following a systematic debugging approach that maintains code quality and Magento best practices.

---

## 🎯 Common Bug Scenarios

### Frontend Issues
- **Layout problems** - Missing blocks, incorrect positioning
- **Template errors** - PHP syntax errors in PHTML files
- **JavaScript errors** - Console errors, broken functionality
- **CSS styling issues** - Visual display problems
- **Responsive design bugs** - Mobile/tablet display issues

### Backend Issues
- **Database errors** - SQL queries, data integrity
- **Model/Resource issues** - Data loading/saving problems
- **Service layer bugs** - Business logic errors
- **API endpoint failures** - REST/SOAP API issues
- **Admin interface problems** - Backend functionality errors

### Performance Issues
- **Slow page loading** - Performance bottlenecks
- **Memory leaks** - Resource consumption problems
- **Cache issues** - Caching problems
- **Database performance** - Slow queries, indexing issues

### Integration Issues
- **Payment gateway errors** - Payment processing failures
- **Shipping calculation bugs** - Shipping method issues
- **Third-party module conflicts** - Extension compatibility problems
- **API integration failures** - External service connection issues

---

## 🔍 Systematic Bug Analysis Process

### Step 1: Information Gathering
1. **Collect error details**:
   - Error messages and stack traces
   - Magento version and edition
   - PHP version and server environment
   - Module list and versions
   - Recent changes or updates

2. **Identify scope**:
   - Frontend vs backend issue
   - Specific area affected (admin, storefront, API)
   - User impact (all users, specific groups, specific actions)

3. **Reproduce the issue**:
   - Steps to reproduce
   - Data conditions that trigger the bug
   - Browser/device specific issues

### Step 2: Root Cause Analysis
1. **Check error logs**:
   - `var/log/exception.log`
   - `var/log/system.log`
   - `var/log/debug.log`
   - Web server error logs

2. **Enable debugging**:
   - Set `MAGE_MODE=developer`
   - Enable error reporting
   - Use Xdebug for step-by-step debugging

3. **Analyze code flow**:
   - Trace execution path
   - Identify where the bug occurs
   - Check data flow and transformations

### Step 3: Solution Development
1. **Apply systematic approach** from [`design_patterns.md`](../magento/design_patterns.md)
2. **Use proper Magento patterns**:
   - Dependency injection
   - Service layer architecture
   - Event-driven programming
   - Plugin/observer patterns

3. **Follow coding standards**:
   - PSR coding standards
   - Magento coding standards
   - Proper error handling
   - Input validation

---

## 🛠️ Implementation Workflows

### Frontend Bug Fix Workflow
1. **Identify affected files**:
   - Layout XML files
   - Template PHTML files
   - JavaScript files
   - CSS/Less files

2. **Check theme inheritance**:
   - Verify parent theme structure
   - Check for proper overrides
   - Ensure file locations are correct

3. **Debug template issues**:
   - Check PHP syntax in PHTML
   - Verify variable availability
   - Test template rendering

4. **Fix JavaScript issues**:
   - Check console errors
   - Verify jQuery/RequireJS usage
   - Test event handlers

### Backend Bug Fix Workflow
1. **Identify affected components**:
   - Model classes
   - Resource models
   - Service classes
   - Controllers

2. **Check database integrity**:
   - Verify table structure
   - Check foreign key relationships
   - Validate data consistency

3. **Debug business logic**:
   - Trace method execution
   - Check data transformations
   - Verify business rules

4. **Test API endpoints**:
   - Verify request/response format
   - Check authentication/authorization
   - Test error handling

### Performance Bug Fix Workflow
1. **Identify bottlenecks**:
   - Use profiling tools
   - Check database query performance
   - Analyze memory usage

2. **Optimize code**:
   - Implement caching strategies
   - Optimize database queries
   - Reduce memory consumption

3. **Check configuration**:
   - Verify cache settings
   - Check index configuration
   - Review cron job schedules

---

## ✅ Validation Checklist

### Before Proposing Solution
- [ ] **Root cause identified** - Clear understanding of why the bug occurs
- [ ] **Scope defined** - Know which components are affected
- [ ] **Impact assessed** - Understand user/business impact
- [ ] **Solution approach** - Follow Magento best practices
- [ ] **Testing strategy** - Plan for testing the fix
- [ ] **Rollback plan** - Strategy to revert if needed

### Solution Quality Check
- [ ] **Follows Magento patterns** - Uses proper architecture
- [ ] **Maintains compatibility** - Works with existing code
- [ ] **Includes error handling** - Proper exception management
- [ ] **Performance considered** - No performance regression
- [ ] **Security reviewed** - No security vulnerabilities
- [ ] **Documentation updated** - Code comments and documentation

### Testing Requirements
- [ ] **Unit tests** - Test individual components
- [ ] **Integration tests** - Test component interactions
- [ ] **Functional tests** - Test complete workflows
- [ ] **Performance tests** - Verify no performance impact
- [ ] **Cross-browser testing** - Test on different browsers
- [ ] **Mobile testing** - Test responsive design

---

## 🚫 Common Mistakes to Avoid

### Technical Mistakes
- **Modifying core files** - Always use proper override mechanisms
- **Ignoring error logs** - Always check logs for detailed error information
- **Rushing to solutions** - Take time to understand the root cause
- **Not testing thoroughly** - Test all scenarios and edge cases
- **Ignoring performance impact** - Consider performance implications

### Process Mistakes
- **Not documenting changes** - Always document what was changed and why
- **Skipping validation** - Always validate the fix works as expected
- **Not considering rollback** - Have a plan to revert changes if needed
- **Ignoring user impact** - Consider how changes affect user experience
- **Not communicating** - Keep stakeholders informed of progress

---

## 📝 Response Template

### Bug Analysis Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ✅ Confirmed: I will follow the bug fixing workflow

## 🐛 Bug Analysis

### Issue Summary
[Brief description of the bug]

### Root Cause Analysis
[Detailed explanation of why the bug occurs]

### Affected Components
[List of files/components that need modification]

### Proposed Solution
[Step-by-step solution approach]

### Testing Strategy
[How to test the fix]

### Risk Assessment
[Potential risks and mitigation strategies]
```

### Solution Implementation Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ✅ Confirmed: I will follow the bug fixing workflow

## 🛠️ Bug Fix Implementation

### Files Modified
[List of files with changes]

### Code Changes
[Detailed code changes with explanations]

### Testing Instructions
[Step-by-step testing process]

### Deployment Notes
[Important considerations for deployment]
```

---

## 🔗 Related Resources

- **[`design_patterns.md`](../magento/design_patterns.md)** - Systematic development approach
- **[`terminology.md`](../magento/terminology.md)** - Magento terms and concepts
- **Magento Developer Documentation** - Official debugging guides
- **Magento Stack Exchange** - Community debugging resources 