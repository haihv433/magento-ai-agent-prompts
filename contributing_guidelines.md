# 🤝 Contributing to Magento AI Agent Prompts

## 📋 Purpose
This file provides comprehensive guidelines for contributing to the Magento AI Agent Prompts repository. Follow these conventions to ensure consistency and maintainability.

---

## 📁 Folder Structure

### Repository Organization
- **[`/ai_instructions/`](./ai_instructions/)** - **MANDATORY** AI tool instructions and response format requirements (MUST READ FIRST)
- **[`/magento/`](./magento/)** - **READ-ONLY** Core Magento development guidelines and systematic approaches (reference only)
- **[`/prompts/`](./prompts/)** - **TASK-SPECIFIC** instructions for common Magento development scenarios (executable tasks)
- **[`/human_resources/`](./human_resources/)** - **REFERENCE** Human-readable resources like screenshots and visual instructions

### Content Types
- **AI Instructions** (`/ai_instructions/`) - Mandatory reading for AI tools
- **Magento Guidelines** (`/magento/`) - Reference knowledge (read-only)
- **Task Prompts** (`/prompts/`) - Executable task instructions
- **Human Resources** (`/human_resources/`) - User-facing documentation

---

## 📝 File Naming Convention

### Naming Rules
- **Use snake_case lowercase** for all file names
- **Be descriptive** but concise
- **Use hyphens** to separate words
- **Include file type** in name when appropriate

### Examples
✅ **Good Names:**
- `design_patterns.md`
- `fix_outdated_module_code.md`
- `debug_magento_issues.md`
- `environment_preparation.md`
- `task_storage_structure.md`

❌ **Avoid:**
- `DesignPatterns.md`
- `fix-outdated-code.md`
- `debugMagentoIssues.md`
- `environment_prep.md` (too abbreviated)

---

## 📏 File Size Requirements

### Size Limits
- **MANDATORY: All files must be under 200 lines** (approximately 6,000-8,000 characters)
- **Purpose**: Ensure AI tools can read files smoothly without crashing
- **If content exceeds 200 lines**: Split into multiple files with clear naming

### Splitting Examples
- `environment_preparation.md` → `env_setup.md` + `env_validation.md`
- `task_local_storage.md` → `task_storage.md` + `task_workflow.md`
- `design_patterns.md` → `patterns_overview.md` + `patterns_implementation.md`
- `requirement_clarification.md` → `requirement_clarification_process.md` + `requirement_clarification_workflow.md`
- `terminology.md` → `terminology_core.md` + `terminology_advanced.md`

### Splitting Guidelines
1. **Logical separation** - Split by topic or workflow
2. **Clear naming** - Use descriptive names for split files
3. **Cross-references** - Link between related files
4. **Maintain context** - Each file should be self-contained

---

## 🔗 Link Formatting Convention

### Link Rules
- **ALWAYS use clickable links** when referencing files or folders within the repository
- **Use relative paths** for internal references
- **Include display text** that describes the target

### Link Formats
```markdown
# Same directory
[`filename.md`](./filename.md)

# Parent directory
[`filename.md`](../filename.md)

# Subdirectory
[`filename.md`](./subdirectory/filename.md)

# Folders
[`/magento/`](./magento/)
[`/prompts/`](./prompts/)
```

### Examples
✅ **Good Links:**
- `[`/magento/`](./magento/)` for folders
- `[`design_patterns.md`](./magento/design_patterns.md)` for files
- `[`fix_outdated_module_code.md`](../prompts/fix_outdated_module_code.md)` for files in subdirectories

❌ **Avoid:**
- `design_patterns.md` (not clickable)
- `./magento/design_patterns.md` (no display text)
- `[design patterns](./magento/design_patterns.md)` (no backticks)

---

## 📋 Content Guidelines

### General Principles
- **Keep instructions concise** - Reference existing content instead of duplicating
- **Use clear section headers** with emojis for easy navigation
- **Include mandatory reading requirements** when applicable
- **Provide step-by-step workflows** for complex tasks
- **Add validation checklists** before proposing solutions
- **ALWAYS use clickable links** when referencing other files or folders
- **Distinguish between reference and executable content**

### Content Types

#### AI Instructions (`/ai_instructions/`)
- **Purpose**: Mandatory reading for AI tools
- **Content**: Workflows, processes, requirements
- **Style**: Instructional, systematic, comprehensive
- **Required**: Response templates, validation checklists

#### Magento Guidelines (`/magento/`)
- **Purpose**: Reference knowledge (read-only)
- **Content**: Patterns, terminology, best practices
- **Style**: Reference, educational, comprehensive
- **Required**: Cross-references, examples

#### Task Prompts (`/prompts/`)
- **Purpose**: Executable task instructions
- **Content**: Step-by-step workflows, specific tasks
- **Style**: Actionable, specific, task-oriented
- **Required**: Validation checklists, error handling

---

## 🔄 Workflow for Adding New Content

### Adding New Prompts
1. **Identify the task category** (debugging, module development, API, etc.)
2. **Create a new `.md` file** in [`/prompts/`](./prompts/) using snake_case naming
3. **Reference existing content** in [`/magento/`](./magento/) folder rather than duplicating
4. **Follow the established format** with clear sections and workflows
5. **Update the README** if adding new task categories

### Adding New AI Instructions
1. **Identify the instruction type** (workflow, process, requirement)
2. **Create a new `.md` file** in [`/ai_instructions/`](./ai_instructions/) using snake_case naming
3. **Follow the established format** with clear sections
4. **Update the README** to include the new file in mandatory reading

### Adding New Magento Guidelines
1. **Identify the topic** (patterns, terminology, structure)
2. **Create a new `.md` file** in [`/magento/`](./magento/) using snake_case naming
3. **Reference existing content** instead of duplicating
4. **Update the README** to include the new file in reference reading

---

## 📚 Example Prompt Structure

### Standard Prompt Template
```markdown
# AI Agent Instruction: [Task Name]

## 🚨 CRITICAL: READ ALL MAGENTO FOLDER INSTRUCTIONS FIRST
**BEFORE performing any task, you MUST read and understand ALL instructions in the [`/magento/`](../magento/) folder.**

### Required Reading Order:
1. **[`patterns_overview.md`](../magento/patterns_overview.md)** - Core approach and scenarios
2. **[`patterns_implementation.md`](../magento/patterns_implementation.md)** - Implementation workflows and tools
3. **Any other files in [`/magento/`](../magento/) folder** - Additional Magento-specific guidelines

## 📋 Task Overview
[Brief description of what this prompt covers]

## 🎯 Common Scenarios
- [Scenario 1 description]
- [Scenario 2 description]
- [Scenario 3 description]

## 🔍 Analysis Process
[Step-by-step process for analyzing the task]

## 🛠️ Implementation Workflows
[Specific workflows for different scenarios]

## ✅ Validation Checklist
- [ ] [Validation item 1]
- [ ] [Validation item 2]
- [ ] [Validation item 3]

## 🚫 Common Mistakes to Avoid
- [Mistake 1 and how to avoid it]
- [Mistake 2 and how to avoid it]
- [Mistake 3 and how to avoid it]

## 🔗 Related Files
- **[`related_file1.md`](./related_file1.md)** - [Description]
- **[`related_file2.md`](./related_file2.md)** - [Description]
```

---

## 🎯 Quality Standards

### Content Quality
- **Accuracy**: All information must be accurate and up-to-date
- **Completeness**: Cover all necessary aspects of the topic
- **Clarity**: Use clear, concise language
- **Consistency**: Follow established patterns and conventions

### Technical Quality
- **Code examples**: Include relevant code examples when appropriate
- **Error handling**: Address common errors and edge cases
- **Performance**: Consider performance implications
- **Security**: Address security considerations

### Documentation Quality
- **Structure**: Use consistent structure and formatting
- **Navigation**: Include clear navigation with emojis
- **Cross-references**: Link to related content
- **Examples**: Provide practical examples

---

## 🚫 Common Mistakes to Avoid

### Content Mistakes
- ❌ **Duplicating content** instead of referencing existing files
- ❌ **Creating files over 200 lines** without splitting
- ❌ **Using inconsistent naming conventions**
- ❌ **Missing cross-references** between related files
- ❌ **Incomplete validation checklists**

### Technical Mistakes
- ❌ **Modifying core Magento files** in examples
- ❌ **Ignoring error handling** in workflows
- ❌ **Missing performance considerations**
- ❌ **Incomplete security reviews**

### Documentation Mistakes
- ❌ **Not using clickable links** for internal references
- ❌ **Inconsistent formatting** across files
- ❌ **Missing mandatory reading requirements**
- ❌ **Unclear section headers**

---

## 🔄 Contribution Process

### Before Contributing
1. **Read existing content** to understand the structure
2. **Check file sizes** to ensure they're under 200 lines
3. **Review naming conventions** for consistency
4. **Understand the folder structure** and content types

### During Contribution
1. **Follow established patterns** and conventions
2. **Use proper link formatting** for all internal references
3. **Include validation checklists** for actionable content
4. **Test your content** for clarity and completeness

### After Contributing
1. **Update the README** if adding new files
2. **Check all links** to ensure they work correctly
3. **Verify file sizes** are under 200 lines
4. **Review for consistency** with existing content

---

## 📞 Getting Help

### Questions and Feedback
- **Open an issue** for questions or suggestions
- **Use discussions** for general feedback
- **Check existing issues** before creating new ones
- **Provide context** when asking questions

### Review Process
- **All contributions** will be reviewed for quality and consistency
- **Feedback will be provided** for improvements
- **Collaboration is encouraged** for complex changes

---

**Thank you for contributing to the Magento AI Agent Prompts repository!**

**Remember**: Every contribution helps improve the experience for AI tools and developers working with Magento. 