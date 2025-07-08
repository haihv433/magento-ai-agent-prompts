# Magento AI Agent Prompts

Welcome, AI Agent!

This repository is designed for AI coding assistants to understand, generate, and debug Magento code efficiently.  
**CRITICAL: Read this file completely, then follow the instructions to read other folders before performing any task.**

---

## 👥 For Human Users

### How to Use This Repository with AI Tools

Use this repository to ensure AI tools follow proper Magento development practices.

#### 🚀 Initial Setup Prompt

**Copy and paste this prompt to your AI tool before starting any Magento task:**

```
I'm working on a Magento project and need your help. Please:

1. Read the entire repository at: https://github.com/haihv433/magento-ai-agent-prompts
2. Read all files in the /magento/ folder first
3. When I give you a task, search the /prompts/ folder for relevant instructions
4. Follow all mandatory reading requirements before performing any task

Please confirm you've read and understood the repository structure before we proceed.
```

#### 📋 Task Assignment Format

**When assigning a specific task, use this format:**

```
Task: [Your specific task description]
Example: "Fix outdated module code" or "Debug Magento issue" or "Create new module"

Please:
1. Find the relevant instruction file in the /prompts/ folder
2. Follow all mandatory reading requirements
3. Execute the task using the systematic approach
4. Provide clear explanations for your changes
```

#### 🎯 Example Usage

**User:** "I need help fixing an outdated Magento module that has compatibility issues."

**AI Tool should:**
1. Read the repository structure from readme.md
2. Read the systematic approach from /magento/ folder
3. Find and read `/prompts/fix_outdated_module_code.md`
4. Follow the step-by-step workflow
5. Apply the systematic approach for reference code checking
6. Provide a solution that maintains Magento compatibility

#### ⚠️ Important Notes for Users

- **Always start with the initial setup prompt** to ensure the AI tool understands the repository
- **Be specific about your task** so the AI can find the right instruction file
- **Wait for confirmation** that the AI has read the repository before proceeding
- **Reference the repository link** in your initial prompt

---

---

## 📂 Repository Structure

- **[`/magento/`](./magento/)** - Core Magento development guidelines and systematic approaches
- **[`/prompts/`](./prompts/)** - Task-specific instructions for common Magento development scenarios
---

## 🧭 AI Tool Workflow

### When Given a Task:

1. **Read this readme.md completely** to understand the repository structure.

2. **Search the [`/prompts/`](./prompts/) folder** for relevant task instructions:
   - Look for files that match your task (e.g., "fix outdated code" → [`fix_outdated_module_code.md`](./prompts/fix_outdated_module_code.md))
   - If no exact match, find the closest related instruction file

3. **Read the selected prompt file** and follow its instructions carefully.

4. **Follow the mandatory reading requirements** specified in the prompt:
   - Most prompts require reading files in [`/magento/`](./magento/) folder first
   - Read any other files mentioned in the prompt

5. **Execute the task** following the systematic approach outlined in the instructions.

---

## 🔎 Task Navigation Examples

| User Task | Prompt Folder to Check |
|-----------|----------------------|
| "Fix outdated module code" | [`/prompts/`](./prompts/) (look for fix-related files) |
| "Debug Magento issue" | [`/prompts/`](./prompts/) (look for debug-related files) |
| "Create new module" | [`/prompts/`](./prompts/) (look for module development files) |
| "Update API integration" | [`/prompts/`](./prompts/) (look for API-related files) |

---

## 🚨 Critical Instructions for AI Tools

### Before Any Task:
- **ALWAYS read the relevant prompt file** from [`/prompts/`](./prompts/) folder
- **ALWAYS follow the mandatory reading requirements** (usually files in [`/magento/`](./magento/) folder)
- **NEVER skip instructions** or assume you know the process
- **ALWAYS use the systematic approach** outlined in the magento folder

### During Task Execution:
- **Follow the step-by-step workflows** provided in the prompt
- **Use the validation checklists** before proposing solutions
- **Reference the magento folder guidelines** for technical details
- **Apply the systematic approach** for all code changes

---

## ⚠️ Important

**Do not skip any instructions.**  
Always read and process all sections in the relevant files before performing or suggesting any code changes.

**Remember**: The [`/magento/`](./magento/) folder contains the foundation knowledge, and [`/prompts/`](./prompts/) folder contains the task-specific instructions. Both must be read and followed.

**🚨 MANDATORY: After reading this readme.md, you MUST read the files in the [`/magento/`](./magento/) folder before proceeding with any task.**

---

## 🤝 Contributions

### For Human Contributors

**Please follow these conventions when contributing:**

#### 📁 Folder Structure
- **[`/magento/`](./magento/)** - Core Magento development guidelines and systematic approaches
- **[`/prompts/`](./prompts/)** - Task-specific instructions for common Magento development scenarios

#### 📝 File Naming Convention
- **Use snake_case lowercase** for all file names
- **Examples**: [`design_patterns.md`](./magento/design_patterns.md), [`fix_outdated_module_code.md`](./prompts/fix_outdated_module_code.md), `debug_magento_issues.md`
- **Avoid**: `DesignPatterns.md`, `fix-outdated-code.md`, `debugMagentoIssues.md`

#### 🔗 Link Formatting Convention
- **ALWAYS use clickable links** when referencing files or folders within the repository
- **Format**: `[`display_text`](./relative_path)` for same directory, `[`display_text`](../relative_path)` for parent directory
- **Examples**: 
  - `[`/magento/`](./magento/)` for folders
  - `[`design_patterns.md`](./magento/design_patterns.md)` for files
  - `[`fix_outdated_module_code.md`](../prompts/fix_outdated_module_code.md)` for files in subdirectories

#### 📋 Content Guidelines
- **Keep instructions concise** - Reference existing content in [`/magento/`](./magento/) folder instead of duplicating
- **Use clear section headers** with emojis for easy navigation
- **Include mandatory reading requirements** when applicable
- **Provide step-by-step workflows** for complex tasks
- **Add validation checklists** before proposing solutions
- **ALWAYS use clickable links** when referencing other files or folders in the repository

#### 🔄 Workflow for Adding New Prompts
1. **Identify the task category** (debugging, module development, API, etc.)
2. **Create a new `.md` file** in [`/prompts/`](./prompts/) using snake_case naming
3. **Reference existing content** in [`/magento/`](./magento/) folder rather than duplicating
4. **Follow the established format** with clear sections and workflows
5. **Update this README** if adding new task categories

#### 📚 Example Prompt Structure
```markdown
# AI Agent Instruction: [Task Name]

## 🚨 CRITICAL: READ ALL MAGENTO FOLDER INSTRUCTIONS FIRST
**BEFORE performing any task, you MUST read and understand ALL instructions in the [`/magento/`](../magento/) folder.**

### Required Reading Order:
1. **[`design_patterns.md`](../magento/design_patterns.md)** - Complete systematic approach for Magento development
2. **Any other files in [`/magento/`](../magento/) folder** - Additional Magento-specific guidelines

## 📋 Task Overview
[Brief description]

## 🎯 Common Scenarios
[Bullet points of scenarios]

## 🔍 Analysis Process
[Step-by-step process]

## 🛠️ Implementation Workflows
[Specific workflows]

## ✅ Validation Checklist
[Checklist items]

## 🚫 Common Mistakes to Avoid
[Key points to avoid]
```

**Feel free to improve, add prompts, or share feedback while following these conventions!**

---