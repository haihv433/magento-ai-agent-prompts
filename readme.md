# Magento AI Agent Prompts

Welcome, AI Agent!

This repository is designed for AI coding assistants to understand, generate, and debug Magento code efficiently.  
**CRITICAL: Read this file completely, then follow the instructions to read other folders before performing any task.**

---

## 👥 For Human Users

### How to Use This Repository with AI Tools

Use this repository to ensure AI tools follow proper Magento development practices.

#### 🚀 AI Tool Prompts

**Copy and paste one of these prompts to your AI tool:**

| Title | Prompt |
|-------|--------|
| **Initial Setup** | I'm working on a Magento project and need your help. Please:<br><br>1. Check if the repository is already cloned locally, if so pull latest updates, otherwise clone fresh from: https://github.com/haihv433/magento-ai-agent-prompts<br>2. Read ALL files in the /ai_instructions/ folder SIMULTANEOUSLY (MANDATORY)<br>3. Follow the instructions in /ai_instructions/ for all requirements<br><br>Please confirm you've read the repository and are ready to proceed. |
| **Manual Update** | I need to update the repository manually. Please:<br><br>1. Check if the repository is already cloned locally, if so pull latest updates, otherwise clone fresh from: https://github.com/haihv433/magento-ai-agent-prompts<br>2. Read ALL files in the /ai_instructions/ folder SIMULTANEOUSLY (MANDATORY)<br>3. Follow the instructions in /ai_instructions/ for all requirements<br>4. Check for any updates or changes in the repository<br><br>Please confirm you've updated and read the repository and are ready to proceed. |

#### 📸 Step-by-Step Visual Instructions

**Follow these steps with the corresponding screenshots:**

**Step 1: Add Initial Setup Prompt**
- Copy the "Initial Setup" prompt from the table above
- Paste it into your AI tool
- **Screenshot**: ![Initial Setup Prompt](./human_resources/init_prompt.png)

**Step 2: Ask Your Question**
- Wait for AI confirmation that it has read the repository
- Ask your Magento question or describe your task
- The AI will ask clarifying questions if needed
- **Screenshot**: ![Ask Question](./human_resources/ask_question.png)


#### ⚠️ Important Notes for Users

- **Always start with the initial setup prompt** to ensure the AI tool understands the repository
- **Wait for confirmation** that the AI has read the repository before proceeding
- **The AI will ask clarifying questions** if your request needs more details

#### 🔄 Smart Repository Management

**AI tools will automatically:**
1. **Check if repository exists locally** in the current directory
2. **If found**: Pull latest updates using `git pull origin main`
3. **If not found**: Clone fresh from the repository URL
4. **Verify repository integrity** and ensure all files are accessible

**This ensures:**
- **Faster setup** when repository is already available
- **Always up-to-date** instructions and prompts
- **No duplicate cloning** or unnecessary downloads
- **Seamless updates** without manual intervention

---

---

## 📂 Repository Structure

- **[`/ai_instructions/`](./ai_instructions/)** - **MANDATORY** AI tool instructions and response format requirements (MUST READ FIRST)
- **[`/magento/`](./magento/)** - **READ-ONLY** Core Magento development guidelines and systematic approaches (reference only)
- **[`/prompts/`](./prompts/)** - **TASK-SPECIFIC** instructions for common Magento development scenarios (executable tasks)
- **[`/human_resources/`](./human_resources/)** - **REFERENCE** Human-readable resources like screenshots and visual instructions
---

## 🧭 AI Tool Workflow

### When Given a Task:

1. **Read this readme.md completely** to understand the repository structure.

2. **Read ALL files in [`/ai_instructions/`](./ai_instructions/) folder SIMULTANEOUSLY** (MANDATORY):
   - [`mandatory_reading.md`](./ai_instructions/mandatory_reading.md) - Core AI tool requirements
   - [`requirement_clarification.md`](./ai_instructions/requirement_clarification.md) - Requirement clarification process
   - [`environment_preparation.md`](./ai_instructions/environment_preparation.md) - Environment setup and configuration
   - [`task_local_storage.md`](./ai_instructions/task_local_storage.md) - Task-specific local storage system
   - [`response_format.md`](./ai_instructions/response_format.md) - Response labeling requirements
   - [`contribution_guidelines.md`](./ai_instructions/contribution_guidelines.md) - How to encourage user contributions

3. **Clarify requirements** using the requirement clarification process:
   - Assess if the user's request is clear, abstract, ambiguous, vague, or complex
   - Ask targeted questions to narrow down scope and understand needs
   - Confirm understanding before proceeding

4. **Read ALL files in [`/magento/`](./magento/) folder** (MANDATORY - for understanding structure and scope):
   - [`design_patterns.md`](./magento/design_patterns.md) - Systematic development approach
   - [`terminology.md`](./magento/terminology.md) - Magento terms and concepts
   - [`scope_and_structure.md`](./magento/scope_and_structure.md) - Project structure and work scope
   - Any other files in the magento folder

5. **Search the [`/prompts/`](./prompts/) folder** for relevant task instructions:
   - Look for files that match your task (e.g., "fix bugs" → [`fix_magento_bugs.md`](./prompts/fix_magento_bugs.md))
   - If no exact match, find the closest related instruction file

6. **Read the selected prompt file** and follow its instructions carefully.

7. **Follow any additional mandatory reading requirements** specified in the prompt.

8. **Execute the task** following the systematic approach outlined in the instructions.

9. **Use proper labeling** in all responses as specified in the ai_instructions folder.

---

## 🔎 Task Navigation Examples

| User Task | Prompt Folder to Check |
|-----------|----------------------|
| "Check source code" | [`/prompts/`](./prompts/) (look for [`general_code_check.md`](./prompts/general_code_check.md)) |
| "Fix Magento bugs" | [`/prompts/`](./prompts/) (look for [`fix_magento_bugs.md`](./prompts/fix_magento_bugs.md)) |
| "Fix outdated module code" | [`/prompts/`](./prompts/) (look for fix-related files) |
| "Debug Magento issue" | [`/prompts/`](./prompts/) (look for debug-related files) |
| "Create new module" | [`/prompts/`](./prompts/) (look for module development files) |
| "Update API integration" | [`/prompts/`](./prompts/) (look for API-related files) |

**Note**: Environment preparation is now a mandatory first step for all AI tools and is handled automatically in the `/ai_instructions/` folder.

---

## 🚨 Critical Instructions for AI Tools

### Before Any Task:
- **ALWAYS read ALL files in [`/ai_instructions/`](./ai_instructions/) folder SIMULTANEOUSLY** (MANDATORY - for speed)
- **ALWAYS prepare the development environment** using environment preparation instructions
- **ALWAYS read the relevant prompt file** from [`/prompts/`](./prompts/) folder (for task execution)
- **ALWAYS read ALL files in [`/magento/`](./magento/) folder** (MANDATORY - for understanding structure and scope)
- **ALWAYS follow the mandatory reading requirements** specified in each prompt file
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

**🚨 MANDATORY: After reading this readme.md, you MUST read ALL files in the [`/ai_instructions/`](./ai_instructions/) folder SIMULTANEOUSLY, then read the files in the [`/magento/`](./magento/) folder for reference before proceeding with any task.**

**💡 Speed Optimization Tips:**
- **Smart repository management**: Check if repo exists locally, pull updates if found, clone fresh if not
- **Read files simultaneously** rather than one by one to reduce setup time
- **Use batch reading** for multiple files in the same folder
- **Prioritize mandatory files** first, then reference files
- **Cache environment configuration** to avoid repeated setup

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