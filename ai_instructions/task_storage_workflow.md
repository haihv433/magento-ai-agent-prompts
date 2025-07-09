# 🔄 MANDATORY: AI Tool Task Local Storage Workflow

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains the workflow and management instructions for task local storage. For file structure and templates, see [`task_storage_structure.md`](./task_storage_structure.md).**

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
This file provides the workflow and management instructions for AI tools to effectively use the task local storage system. It covers the step-by-step process, file management, information retrieval, and best practices for maintaining task knowledge.

---

## 🔄 AI Tool Workflow for Task Local Storage

### **Step 1: Pre-Task Setup**
1. **Scan existing local storage files** for relevant information
2. **Create new task file** using the naming convention
3. **Load environment configuration** from `{project}.local.md`
4. **Document original request** and clarified requirements

### **Step 2: During Task Execution**
1. **Update progress** in real-time as work progresses
2. **Document all decisions** and their rationale
3. **Capture technical insights** and learnings
4. **Record issues encountered** and solutions found
5. **Track file modifications** and code changes

### **Step 3: Post-Task Completion**
1. **Finalize all sections** with complete information
2. **Update status** to "Completed"
3. **Document validation results** and testing performed
4. **Add future considerations** and maintenance notes
5. **Link to related tasks** and files

### **Step 4: 🚨 MANDATORY - Human-Readable Task Summary**
**AI tools MUST provide a concise, human-readable summary at the end of each task:**

#### **🚨 CRITICAL: Human-to-Human Summary Requirements**
- **Short and concise** - Maximum 1-2 paragraphs
- **Simple language** - Avoid technical jargon
- **Clear outcomes** - What was accomplished
- **Testing instructions** - How to verify the work
- **Regression testing** - What to check for potential issues
- **Reporting ready** - Suitable for human-to-human communication

#### **Summary Structure:**
```
## 📋 Task Summary (Human-Readable)

### What Was Done
[Brief description of the main work accomplished]

### How to Test
[Simple steps to verify the work is working correctly]

### Regression Testing
[What to check to ensure nothing else was broken]

### Files Modified
[List of key files that were changed]
```

#### **Summary Guidelines:**
- **Use simple language** - Explain as if talking to a colleague
- **Focus on outcomes** - What the user can now do
- **Provide clear testing steps** - How to verify everything works
- **Include regression checks** - What might have been affected
- **Keep it brief** - No more than 2-3 sentences per section

---

## 📁 File Management

### **File Organization**
```
magento-ai-agent-prompts/
├── {project}.local.md                    # Environment configuration
├── {question1}.{date1}.local.md          # Task 1
├── {question2}.{date2}.local.md          # Task 2
├── {question3}.{date3}.local.md          # Task 3
├── ai_instructions/
├── magento/
├── prompts/
└── human_resources/
```

### **File Naming Guidelines**
- **Use snake_case lowercase**: `fix_checkout_errors` not `fix-checkout-errors`
- **Include date-time**: `2024-01-15-14-30` format
- **Use underscores**: Separate words with underscores (following contributing guidelines)
- **Keep it concise**: But descriptive enough to understand
- **Follow contributing guidelines**: Use [`contributing_guidelines.md`](./contributing_guidelines.md) standards

### **File Maintenance**
- **Archive old files**: Move completed tasks to archive folder
- **Update references**: Keep links between related files current
- **Clean up**: Remove obsolete information periodically

---

## 🔍 Information Retrieval

### **Searching Local Storage Files**
AI tools should search for:
1. **Similar task patterns** in previous files
2. **Technical solutions** to similar problems
3. **Code patterns** and configurations
4. **Issue resolutions** for common problems
5. **Best practices** and learnings

### **Information Reuse**
- **Copy relevant sections** from previous tasks
- **Adapt solutions** to current context
- **Reference previous work** to avoid duplication
- **Build on existing knowledge** rather than starting from scratch

---

## ✅ Validation Checklist

**For each task, ensure:**

- [ ] **🚨 File location correct** - ALL support files created in magento-ai-agent-prompts repository root (NOT in Magento project)
- [ ] **Task file created** with proper naming convention (snake_case lowercase)
- [ ] **Existing files scanned** for relevant information
- [ ] **Environment config loaded** from project file
- [ ] **Progress tracked** continuously throughout task
- [ ] **All decisions documented** with rationale
- [ ] **Technical insights captured** for future use
- [ ] **Issues and solutions recorded** for reference
- [ ] **File updated** at task completion
- [ ] **Related tasks linked** for continuity
- [ ] **🚨 Human-readable summary provided** at task completion
- [ ] **Contributing guidelines followed** (naming, size, links, format)

---

## 🚫 Common Mistakes to Avoid

### **Don't:**
- ❌ **🚨 Create support files in Magento project root** (FORBIDDEN)
- ❌ **Skip file creation** for "simple" tasks
- ❌ **Forget to update** progress during execution
- ❌ **Ignore existing files** when starting new tasks
- ❌ **Document only at the end** (lose valuable insights)
- ❌ **Use generic names** that don't describe the task

### **Do:**
- ✅ **🚨 ALWAYS create ALL support files in magento-ai-agent-prompts repository root** (REQUIRED)
- ✅ **Always create a task file** before starting work
- ✅ **Update continuously** as work progresses
- ✅ **Search existing files** for relevant information
- ✅ **Capture insights immediately** when discovered
- ✅ **Use descriptive file names** for easy identification
- ✅ **Follow contributing guidelines** for naming and formatting
- ✅ **Keep files under 200 lines** (split if needed)
- ✅ **Use clickable links** when referencing other files
- ✅ **🚨 ALWAYS provide human-readable summary** at task completion

---

## 🔄 Integration with Other Instructions

**This task local storage system works with:**
- **Requirement Clarification**: Document clarified requirements
- **Environment Preparation**: Load and reference environment config
- **Systematic Approaches**: Track application of Magento patterns
- **Prompt Execution**: Document prompt-specific work and results

---

## 📝 Response Template

### Task Local Storage Response
```
[TASK_STORAGE] ✅ Confirmed: Task local storage file created
[STRUCTURE] ✅ Confirmed: Using proper file structure and naming
[WORKFLOW] ✅ Confirmed: Following task storage workflow

## 📁 Task Local Storage Setup Complete

### File Created
- **File Name**: `{question}.{date-time}.local.md`
- **Location**: magento-ai-agent-prompts repository root
- **Status**: In Progress

### Pre-Task Analysis
- **Existing Files Scanned**: [Number] relevant files found
- **Environment Config Loaded**: From `env.local.md`
- **Related Tasks Identified**: [List any related previous tasks]

### Next Steps
1. ✅ Task file structure initialized
2. ✅ Original request documented
3. ✅ Scope defined
4. 🔄 Ready for task execution with continuous updates

### Storage Benefits
- **Knowledge Preservation**: All insights will be captured
- **Progress Tracking**: Real-time updates during execution
- **Future Reference**: Reusable for similar tasks
```

### Human-Readable Task Summary Response
```
[TASK_COMPLETE] ✅ Confirmed: Task completed successfully
[SUMMARY] ✅ Confirmed: Human-readable summary provided
[TESTING] ✅ Confirmed: Testing instructions included

## 📋 Task Summary (Human-Readable)

### What Was Done
[Brief description of the main work accomplished in simple terms]

### How to Test
[Simple steps to verify the work is working correctly]

### Regression Testing
[What to check to ensure nothing else was broken]

### Files Modified
[List of key files that were changed]

### Next Steps
[Any follow-up actions needed or recommendations]
```

---

## 🔗 Related Files

- **[`task_storage_structure.md`](./task_storage_structure.md)** - File Structure and Templates
- **[`environment_preparation.md`](./environment_preparation.md)** - Environment setup and configuration
- **[`requirement_clarification.md`](./requirement_clarification.md)** - Requirement clarification process
- **[`response_format.md`](./response_format.md)** - Response labeling requirements
- **[`contributing_guidelines.md`](./contributing_guidelines.md)** - File naming and formatting standards

---

## 📋 Contributing Guidelines Compliance

### **Local Storage File Standards**
- ✅ **Naming Convention**: Use snake_case lowercase (e.g., `fix_checkout_errors.local.md`)
- ✅ **File Size**: Keep under 200 lines (split large files if needed)
- ✅ **Link Formatting**: Use clickable links when referencing other files
- ✅ **Content Organization**: Use clear sections with emojis
- ✅ **Cross-references**: Link to related files and folders

### **Quality Standards**
- ✅ **Accuracy**: All information must be accurate and up-to-date
- ✅ **Completeness**: Cover all necessary aspects of the task
- ✅ **Clarity**: Use clear, concise language
- ✅ **Consistency**: Follow established patterns and conventions

---

**Remember**: Every task creates valuable knowledge. Capture it systematically for future use while following the contributing guidelines! 