# 📁 MANDATORY: AI Tool Task Local Storage Structure

## 🚨 CRITICAL: READ THIS FILE FIRST
**BEFORE starting ANY task, you MUST create a task-specific local storage file to track progress, capture insights, and store reusable information. This creates a knowledge base for future tasks and ensures continuity.**

---

## 🚨 MANDATORY: File Location Requirements

### **CRITICAL: ALL AI-Created Support Files MUST Be Created in This Repository**

**🚨 NEVER create support files in the Magento project root directory!**

**✅ ALWAYS create ALL support files in the magento-ai-agent-prompts repository root:**

| File Type | Examples | Location |
|-----------|----------|----------|
| **Local Storage Files** | `.local.md`, `.md` | magento-ai-agent-prompts repository root |
| **Testing Files** | `test_*.md`, `testing_*.md` | magento-ai-agent-prompts repository root |
| **Bash Scripts** | `*.sh`, `*.bash` | magento-ai-agent-prompts repository root |
| **Documentation** | `docs_*.md`, `notes_*.md` | magento-ai-agent-prompts repository root |
| **Configuration** | `config_*.md`, `setup_*.md` | magento-ai-agent-prompts repository root |
| **Debug Files** | `debug_*.md`, `logs_*.md` | magento-ai-agent-prompts repository root |

**❌ FORBIDDEN Locations:**
- Magento project root directory
- Magento app/ directory
- Magento var/ directory
- Any Magento project subdirectories

**✅ REQUIRED Location:**
- magento-ai-agent-prompts repository root directory ONLY

**Why This Matters:**
- Keeps Magento project clean and uncluttered
- Maintains separation between project code and AI support files
- Ensures support files are version controlled with the repository
- Prevents accidental commits of AI files to the Magento project
- **Git Integration**: All these file types are automatically ignored by `.gitignore` to prevent accidental commits

---

## 📋 Purpose
This file establishes the structure and format for AI tools to create task-specific local storage files (`.local.md`) that capture all relevant information, progress, and insights during task execution. This creates a valuable knowledge base for future tasks and ensures no important information is lost.

**Key Benefits:**
- **Knowledge Preservation**: Capture all insights and solutions for future reference
- **Progress Tracking**: Document task progress and decisions made
- **Reusable Information**: Store patterns, solutions, and configurations for future tasks
- **Continuity**: Ensure future AI sessions can understand previous work
- **Efficiency**: Avoid repeating research and problem-solving for similar tasks

---

## 📁 Task Local Storage File System

### **File Naming Convention**
```
{question}.{date-time}.local.md
```

**Naming Requirements (Following Contributing Guidelines):**
- **Use snake_case lowercase** for question names
- **Use descriptive but concise** names
- **Include date-time stamp** for uniqueness
- **Keep total filename length** reasonable

**Examples:**
- "fix_checkout_errors.2024-01-15-14-30.local.md"
- "create_custom_module.2024-01-15-09-15.local.md"
- "optimize_performance.2024-01-14-16-45.local.md"
- "debug_payment_issue.2024-01-14-11-20.local.md"

### **File Structure Template**
```markdown
# Task: {Question/Task Description}

> **File Type**: Task Local Storage File (`.local.md`)  
> **Task**: {Brief task description}  
> **Created**: {date-time}  
> **Status**: {In Progress/Completed/Failed/Paused}  
> **Project**: {project-name}  
> **AI Session**: {session identifier}  
> **Guidelines**: Following [`contributing_guidelines.md`](../contributing_guidelines.md)

---

## 🎯 Task Overview

### **Original Request**
{User's original request/question}

### **Clarified Requirements**
{Requirements after clarification process}

### **Scope Definition**
- **In Scope**: [List what's included]
- **Out of Scope**: [List what's excluded]
- **Success Criteria**: [How to measure completion]

---

## 🔍 Pre-Task Analysis

### **Existing Local Storage Files Scanned**
| File | Relevance | Key Information Found |
|------|-----------|----------------------|
| {filename} | {High/Medium/Low} | {Brief description of useful info} |

### **Environment Configuration**
{Load and display relevant environment info from {project}.local.md}

### **Previous Related Tasks**
{List any previous tasks that might be relevant}

---

## 📋 Task Execution Plan

### **Phase 1: [Phase Name]**
- [ ] **Objective**: [What we're trying to achieve]
- [ ] **Approach**: [How we'll do it]
- [ ] **Status**: [Not Started/In Progress/Completed/Failed]
- [ ] **Notes**: [Any important details]

### **Phase 2: [Phase Name]**
- [ ] **Objective**: [What we're trying to achieve]
- [ ] **Approach**: [How we'll do it]
- [ ] **Status**: [Not Started/In Progress/Completed/Failed]
- [ ] **Notes**: [Any important details]

---

## 🔧 Technical Implementation

### **Files Modified**
| File | Type | Purpose | Status |
|------|------|---------|--------|
| {filepath} | {New/Modified} | {What was done} | {Complete/Pending} |

### **Code Changes**
```php
// Example code changes
// File: app/code/Vendor/Module/etc/module.xml
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <module name="Vendor_Module" setup_version="1.0.0">
        <!-- Changes made -->
    </module>
</config>
```

### **Database Changes**
- **Tables Created**: [List any new tables]
- **Tables Modified**: [List any modified tables]
- **Data Migrations**: [Any data changes required]

### **Configuration Changes**
- **System Configuration**: [Any admin configuration changes]
- **Cache Management**: [Cache clearing/flushing required]
- **Index Management**: [Index rebuilding required]

---

## 🐛 Issues Encountered

### **Issue 1: [Issue Description]**
- **Date**: [When encountered]
- **Severity**: [Critical/High/Medium/Low]
- **Status**: [Open/Resolved/Workaround]
- **Description**: [Detailed description]
- **Solution**: [How it was resolved]
- **Prevention**: [How to prevent in future]

### **Issue 2: [Issue Description]**
- **Date**: [When encountered]
- **Severity**: [Critical/High/Medium/Low]
- **Status**: [Open/Resolved/Workaround]
- **Description**: [Detailed description]
- **Solution**: [How it was resolved]
- **Prevention**: [How to prevent in future]

---

## 💡 Insights & Learnings

### **Technical Insights**
- **Pattern Discovered**: [Any useful patterns or approaches]
- **Best Practice Applied**: [Best practices used]
- **Performance Considerations**: [Performance implications]
- **Security Considerations**: [Security aspects]

### **Magento-Specific Learnings**
- **Magento Version Compatibility**: [Version-specific considerations]
- **Module Interactions**: [How modules interact]
- **Extension Points**: [Customization points used]
- **API Usage**: [APIs utilized]

### **Reusable Solutions**
- **Code Patterns**: [Reusable code patterns]
- **Configuration Patterns**: [Reusable configurations]
- **Debugging Techniques**: [Useful debugging approaches]
- **Testing Strategies**: [Testing approaches used]

---

## 📊 Progress Tracking

### **Timeline**
| Date/Time | Phase | Status | Notes |
|-----------|-------|--------|-------|
| {timestamp} | {phase} | {status} | {notes} |

### **Milestones**
- [ ] **Milestone 1**: [Description] - {Date}
- [ ] **Milestone 2**: [Description] - {Date}
- [ ] **Milestone 3**: [Description] - {Date}

### **Time Tracking**
- **Total Time Spent**: [Hours/minutes]
- **Time per Phase**: [Breakdown by phase]
- **Bottlenecks**: [What took the most time]

---

## ✅ Validation & Testing

### **Testing Performed**
| Test Type | Status | Results | Notes |
|-----------|--------|---------|-------|
| {Unit/Integration/Functional} | {Pass/Fail} | {Results} | {Notes} |

### **Validation Checklist**
- [ ] **Functionality**: [Does it work as expected?]
- [ ] **Performance**: [Performance impact acceptable?]
- [ ] **Security**: [Security considerations addressed?]
- [ ] **Compatibility**: [Compatible with existing code?]
- [ ] **Documentation**: [Code documented properly?]

---

## 🔄 Future Considerations

### **Maintenance Requirements**
- **Regular Tasks**: [Any ongoing maintenance needed]
- **Monitoring**: [What to monitor]
- **Updates**: [Update considerations]

### **Potential Improvements**
- **Enhancements**: [Future improvements possible]
- **Optimizations**: [Performance optimizations]
- **Extensions**: [How to extend functionality]

### **Related Tasks**
- **Dependencies**: [Tasks that depend on this]
- **Prerequisites**: [Tasks needed before this]
- **Follow-up**: [Tasks that should follow this]

---

## 📋 Contributing Guidelines Compliance

### **File Standards**
- ✅ **Naming Convention**: Using snake_case lowercase
- ✅ **File Size**: Under 200 lines (split if needed)
- ✅ **Link Formatting**: Using clickable links for references
- ✅ **Content Organization**: Clear sections with emojis
- ✅ **Cross-references**: Linking to related files

### **Quality Standards**
- ✅ **Accuracy**: All information is accurate and up-to-date
- ✅ **Completeness**: Covering all necessary aspects
- ✅ **Clarity**: Using clear, concise language
- ✅ **Consistency**: Following established patterns

---

## 📝 Notes & Observations

### **General Notes**
{Any additional observations or notes}

### **User Feedback**
{Any feedback received from the user}

### **Lessons Learned**
{What was learned from this task}

---

## 📋 Human-Readable Task Summary

### **What Was Done**
{Brief description of the main work accomplished in simple terms}

### **How to Test**
{Simple steps to verify the work is working correctly}

### **Regression Testing**
{What to check to ensure nothing else was broken}

### **Files Modified**
{List of key files that were changed}

### **Next Steps**
{Any follow-up actions needed or recommendations}

---

## 🔗 Related Files

### **Local Storage Files**
- **Environment**: `{project}.local.md`
- **Related Tasks**: [List related task files]

### **Project Files**
- **Modified**: [List project files modified]
- **Created**: [List new files created]
- **Referenced**: [List files referenced]

---

> **Note**: This task local storage file contains all information related to this specific task.  
> It should be updated continuously as the task progresses and can be referenced for future similar tasks.

---

## 🔗 Related Files

- **[`task_storage_workflow.md`](./task_storage_workflow.md)** - AI Tool Workflow for Task Local Storage
- **[`environment_preparation.md`](./environment_preparation.md)** - Environment setup and configuration
- **[`requirement_clarification.md`](./requirement_clarification.md)** - Requirement clarification process 