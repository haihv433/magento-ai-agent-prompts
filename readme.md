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

1. Clone or fetch the repository fresh from: https://github.com/haihv433/magento-ai-agent-prompts
2. Read all files in the /ai_instructions/ folder FIRST (MANDATORY)
3. Follow the instructions in /ai_instructions/ for all requirements

Please confirm you've read the repository and are ready to proceed.
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
1. Clone or fetch the repository fresh
2. Read the repository structure from readme.md
3. Read the systematic approach from [`/magento/`](./magento/) folder (for reference)
4. Find and read the relevant instruction file in [`/prompts/`](./prompts/) folder (for task execution)
5. Follow the step-by-step workflow
6. Apply the systematic approach for reference code checking
7. Provide a solution that maintains Magento compatibility

#### ⚠️ Important Notes for Users

- **Always start with the initial setup prompt** to ensure the AI tool understands the repository
- **Be specific about your task** so the AI can find the right instruction file
- **Wait for confirmation** that the AI has read the repository before proceeding
- **Reference the repository link** in your initial prompt

---

---

## 📂 Repository Structure

- **[`/ai_instructions/`](./ai_instructions/)** - **MANDATORY** AI tool instructions and response format requirements (MUST READ FIRST)
- **[`/magento/`](./magento/)** - **READ-ONLY** Core Magento development guidelines and systematic approaches (reference only)
- **[`/prompts/`](./prompts/)** - **TASK-SPECIFIC** instructions for common Magento development scenarios (executable tasks)
---

## 🧭 AI Tool Workflow

### When Given a Task:

1. **Read this readme.md completely** to understand the repository structure.

2. **Read ALL files in [`/ai_instructions/`](./ai_instructions/) folder FIRST** (MANDATORY):
   - [`mandatory_reading.md`](./ai_instructions/mandatory_reading.md) - Core AI tool requirements
   - [`response_format.md`](./ai_instructions/response_format.md) - Response labeling requirements

3. **Search the [`/prompts/`](./prompts/) folder** for relevant task instructions:
   - Look for files that match your task (e.g., "fix outdated code" → [`fix_outdated_module_code.md`](./prompts/fix_outdated_module_code.md))
   - If no exact match, find the closest related instruction file

4. **Read the selected prompt file** and follow its instructions carefully.

5. **Follow the mandatory reading requirements** specified in the prompt:
   - Most prompts require reading files in [`/magento/`](./magento/) folder (for reference)
   - Read any other files mentioned in the prompt

6. **Execute the task** following the systematic approach outlined in the instructions.

7. **Use proper labeling** in all responses as specified in the ai_instructions folder.

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
- **ALWAYS read ALL files in [`/ai_instructions/`](./ai_instructions/) folder FIRST** (MANDATORY)
- **ALWAYS read the relevant prompt file** from [`/prompts/`](./prompts/) folder (for task execution)
- **ALWAYS follow the mandatory reading requirements** (usually files in [`/magento/`](./magento/) folder for reference)
- **NEVER skip instructions** or assume you know the process
- **ALWAYS use the systematic approach** outlined in the magento folder (as reference)
- **ALWAYS use proper labeling** in all responses as specified in ai_instructions

### During Task Execution:
- **Follow the step-by-step workflows** provided in the prompt
- **Use the validation checklists** before proposing solutions
- **Reference the magento folder guidelines** for technical details
- **Apply the systematic approach** for all code changes

---

## ⚠️ Important

**Do not skip any instructions.**  
Always read and process all sections in the relevant files before performing or suggesting any code changes.

**Remember**: The [`/magento/`](./magento/) folder contains the **reference knowledge** (read-only), and [`/prompts/`](./prompts/) folder contains the **executable task instructions**. Both must be read and followed.

**🚨 MANDATORY: After reading this readme.md, you MUST read ALL files in the [`/ai_instructions/`](./ai_instructions/) folder FIRST, then read the files in the [`/magento/`](./magento/) folder for reference before proceeding with any task.**

---

## 🤝 Contributions

### For Human Contributors

**Please follow these conventions when contributing:**

#### 📁 Folder Structure
- **[`/ai_instructions/`](./ai_instructions/)** - **MANDATORY** AI tool instructions and response format requirements (MUST READ FIRST)
- **[`/magento/`](./magento/)** - **READ-ONLY** Core Magento development guidelines and systematic approaches (reference only)
- **[`/prompts/`](./prompts/)** - **TASK-SPECIFIC** instructions for common Magento development scenarios (executable tasks)

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
- **Distinguish between reference and executable content** - `/magento/` is read-only reference, `/prompts/` contains executable tasks

#### 🔄 Workflow for Adding New Prompts
1. **Identify the task category** (debugging, module development, API, etc.)
2. **Create a new `.md` file** in [`/prompts/`](./prompts/) using snake_case naming (executable tasks only)
3. **Reference existing content** in [`/magento/`](./magento/) folder rather than duplicating (read-only reference)
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