# 🔧 MANDATORY: AI Tool Environment Preparation

## 🚨 CRITICAL: READ THIS FILE FIRST
**BEFORE performing ANY task, you MUST prepare and verify the Magento development environment. This ensures proper PHP version compatibility, tool availability, and clean development state.**

## 🔧 How AI Tools Should Use Environment Configuration

**AI Tools Workflow:**

1. **First Priority: Read Existing Configuration**
   - Check if `env.local.md` exists in the **magento-ai-agent-prompts repository root directory**
   - If found, read and parse the configuration file
   - Use the stored environment information for all operations
   - Skip environment setup if configuration is complete and valid

2. **Second Priority: Create New Configuration (if not exists)**
   - If no `env.local.md` file exists in the **magento-ai-agent-prompts repository root**, proceed with environment setup
   - Ask user for consent to create the configuration file
   - Offer manual configuration or auto-detection options
   - Save configuration to `env.local.md` in the **magento-ai-agent-prompts repository root directory**

3. **When running commands, AI tools should:**
   - Check if `env.local.md` exists
   - Parse the file to extract environment variables
   - Use the saved paths for running commands

4. **Use the saved paths for commands:**
   - Use `PHP_PATH` from config for PHP commands
   - Use `COMPOSER_PATH` from config for Composer commands
   - Use `NPM_PATH` from config for npm commands
   - Verify paths exist before using them

5. **Leverage stored information to avoid repeated checks:**
   - **Magento Mode**: Use `MAGENTO_MODE` instead of running mode checks
   - **Git Info**: Use `GIT_REPOSITORY` and `GIT_BRANCH` instead of running git commands
   - **PHP Extensions**: Use `PHP_EXTENSIONS` instead of checking extensions repeatedly
   - **User Preferences**: Use `PREFERRED_CODING_STANDARD` for code formatting
   - **Project Settings**: Use `PREFERRED_MODULE_NAMESPACE` for new module creation
   - **Tool Availability**: Use `DOCKER_AVAILABLE` to know if Docker commands are available

---

## 📋 Purpose
This file instructs AI tools to efficiently prepare the Magento development environment by focusing on the two most critical pieces of information: PHP path and Composer path. Other environment details are discovered dynamically during task execution to save time and focus on the actual work. The process saves settings to a separate `env.local.md` file with user consent and avoids modifying any Magento project files.

**Key Benefits:**
- **Fast Setup**: Focus only on critical PHP and Composer paths for immediate task execution
- **Dynamic Discovery**: Discover other environment details as needed during tasks
- **Time Efficiency**: Avoid lengthy environment setup processes
- **Progressive Enhancement**: Build environment knowledge incrementally
- **Task Focus**: Get to the actual work quickly without exhaustive environment analysis

**Local Storage File Pattern (`.local.md`):**
- **File Type**: Local Storage File (`.local.md`) - Standard pattern for AI agent data persistence
- **Location**: `env.local.md` in the **magento-ai-agent-prompts repository root directory** (NOT in the Magento project directory)
- **Naming**: Use snake_case lowercase naming (e.g., `env.local.md`, `task_name.local.md`)
- **Format**: Proper Markdown with tables, sections, and metadata for easy reading and parsing
- **Scope**: Environment configuration that persists across AI tool sessions
- **Purpose**: Store environment data that AI tools need to remember between sessions
- **Size Limit**: Must be under 200 lines (split if needed)
- **Link Formatting**: Use clickable links when referencing other files

**Standard `.local.md` Structure:**
1. **Header**: File type, purpose, generation date, project info
2. **Configuration Sections**: Organized in markdown tables
3. **User Preferences**: Stored preferences and settings
4. **Metadata**: Version, timestamps, setup method
5. **Usage Instructions**: How AI tools should use the file
6. **Notes**: Important information about the file

**Configuration File Updates:**
AI tools should update the configuration file when they discover new information during task execution:
- **Magento Version**: Update when running `php bin/magento --version`
- **Magento Mode**: Update when running `php bin/magento deploy:mode:show`
- **Git Info**: Update when running git commands
- **Project Path**: Update when discovering current working directory
- **Node.js/npm**: Update when running frontend commands
- **Docker**: Update when running container commands
- **User Preferences**: Update when user expresses preferences during conversations

**Extending the `.local.md` Pattern:**
For future tasks that need data persistence, AI tools should:
1. **Create new `.local.md` files** following the same structure and format
2. **Use snake_case lowercase names** like `{task_name}.local.md` or `{category}_{task_name}.local.md`
3. **Follow the standard format** with headers, tables, metadata, and usage instructions
4. **Store in the magento-ai-agent-prompts repository root directory** for easy access
5. **Include clear documentation** about what the file contains and how to use it
6. **Keep files under 200 lines** (split if needed)
7. **Use clickable links** when referencing other files or folders

**Examples of Additional `.local.md` Files:**
- `modules.local.md` - Track created modules and their configurations
- `debugging.local.md` - Store debugging history and solutions
- `customizations.local.md` - Track custom code and modifications
- `testing.local.md` - Store test configurations and results
- `api_integrations.local.md` - Store API integration configurations
- `performance_optimizations.local.md` - Track performance improvements

---

## 🎯 Environment Preparation Workflow

### Step 1: Check for Existing Environment Configuration
**AI tools will first check for saved environment configuration:**
- Check if `env.local.md` exists in the magento-ai-agent-prompts repository root
- If found, read and parse the configuration file
- Use stored environment information for all operations
- Skip environment setup if configuration is complete and valid

### Step 2: 🚨 MANDATORY - Ask Human for Environment Paths
**AI tools MUST ALWAYS ask the human for PHP and Composer paths FIRST:**
- **NEVER attempt auto-detection without asking the human first**
- **ALWAYS request these two critical pieces of information:**
  - **PHP Path**: Ask human to provide the PHP executable path
  - **Composer Path**: Ask human to provide the Composer executable path
- **Only proceed with auto-detection if human explicitly cannot provide the paths**

### Step 3: Environment Setup Options
**AI tools MUST ALWAYS ask the human for PHP and Composer paths FIRST before any auto-detection:**

**🚨 MANDATORY: Ask Human First**
- **ALWAYS ask the human to provide PHP and Composer paths before attempting any auto-detection**
- **Request these two essential pieces from the human:**
  - **PHP Path**: [e.g., /usr/bin/php, /opt/homebrew/bin/php] (will reveal PHP version)
  - **Composer Path**: [e.g., /usr/local/bin/composer, /opt/homebrew/bin/composer] (will reveal Composer version)

**Option 1: Manual Configuration (Recommended)**
- Human provides the two critical environment details directly for maximum accuracy
- **Use the paths provided by the human**
- **Verify the paths work correctly**

**Option 2: Auto-Detection (Only if human cannot provide paths)**
- **ONLY attempt auto-detection if the human explicitly cannot provide the paths**
- **ALWAYS ask first - never auto-detect without asking**
- May not be 100% accurate but provides a starting point
- **Focus only on detecting:**
  - PHP path and version
  - Composer path and version

### Step 3: Save Configuration (With User Consent)
**AI tools will save the configuration only after user consent:**
- Save to `env.local.md` in the **magento-ai-agent-prompts repository root directory**
- Include PHP and Composer paths/versions in structured markdown format
- Add metadata and usage instructions
- **Leave other environment fields as "Unknown" or "To be discovered"**

### Step 4: Dynamic Environment Discovery During Tasks
**AI tools will discover and update environment information during task execution:**
- **Magento Version**: Discover when running `php bin/magento --version`
- **Magento Mode**: Discover when running `php bin/magento deploy:mode:show`
- **Git Info**: Discover when running git commands
- **Project Path**: Discover from current working directory
- **Other Tools**: Discover Node.js, npm, Docker, etc. when needed
- **Update env.local.md** whenever new environment information is discovered

---

## ✅ Mandatory Validation Checklist

### Initial Setup (Focus on Critical Paths)
- [ ] **Human asked for PHP path** (MANDATORY - ask before auto-detection)
- [ ] **Human asked for Composer path** (MANDATORY - ask before auto-detection)
- [ ] **PHP path obtained** (from human or auto-detection only if human cannot provide)
- [ ] **Composer path obtained** (from human or auto-detection only if human cannot provide)
- [ ] **PHP version discovered** from PHP path
- [ ] **Composer version discovered** from Composer path
- [ ] **env.local.md created** with basic information
- [ ] **User consent obtained** for saving configuration

### Dynamic Discovery (During Tasks)
- [ ] **Magento version discovered** when running Magento commands
- [ ] **Magento mode discovered** when checking deployment mode
- [ ] **Git information discovered** when running git commands
- [ ] **Project path discovered** from current working directory
- [ ] **Other tools discovered** as needed during task execution
- [ ] **env.local.md updated** with new discoveries

### Error Handling
- [ ] **PHP path verified** to be accessible and working
- [ ] **Composer path verified** to be accessible and working
- [ ] **Critical errors identified** and addressed
- [ ] **Environment ready** for development tasks

---

## 🚫 Common Issues and Solutions

### PHP Version Issues
**Problem**: PHP version incompatible with Magento version
**Solution**: 
- Ask user to switch to compatible PHP version
- Ask user to update Magento to compatible version
- Ask user to use PHP version manager (phpbrew, phpenv)

### Environment Mode Issues
**Problem**: Wrong deployment mode for development
**Solution**: Switch to developer mode for development tasks

### Cache Issues
**Problem**: Cache not clearing properly
**Solution**: Clear all cache directories and regenerate static content

### Composer Issues
**Problem**: Dependency conflicts or outdated packages
**Solution**: Update dependencies and optimize autoloader

### Multiple Environment Issues
**Problem**: Multiple PHP/Composer installations causing confusion
**Solution**: Ask user to specify which environment to use

---

## 📝 Response Template

### Environment Preparation Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ✅ Confirmed: I will follow the environment preparation workflow

## 🔧 Environment Preparation Complete

### Critical Environment Information
- **PHP Path**: [path] (Version: [X.X.X]) - Obtained from human
- **Composer Path**: [path] (Version: [X.X.X]) - Obtained from human
- **Configuration Saved**: ✅ `env.local.md` created in magento-ai-agent-prompts repository root

### Dynamic Discovery Ready
- **Magento Version**: Will discover during task execution
- **Magento Mode**: Will discover during task execution
- **Git Info**: Will discover during task execution
- **Other Tools**: Will discover as needed during tasks

### Preparation Steps Completed
1. ✅ Human asked for PHP path (MANDATORY)
2. ✅ Human asked for Composer path (MANDATORY)
3. ✅ PHP path obtained and verified
4. ✅ Composer path obtained and verified
5. ✅ Environment configuration saved
6. ✅ User consent obtained
7. ✅ Ready for dynamic discovery during tasks

### Environment Status
✅ **Ready for development tasks - will discover additional environment details as needed**
```

### Environment Complexity Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ✅ Confirmed: I will follow the environment preparation workflow

## 🔍 Environment Complexity Detected

I found multiple development environments on your system that need clarification:

**PHP Versions Available:**
[List detected PHP versions]

**Composer Installations:**
[List detected composer installations]

**Development Tools:**
[List detected tools]

**Questions for you:**
1. Which PHP version should I use for this Magento project?
2. Which Composer installation should I use?
3. Are there any specific environment variables or configurations I should be aware of?
4. Are you using any containerization (Docker, etc.) for this project?

Please provide the correct environment details so I can proceed with the proper setup.
```

---

## 🔗 Related Resources

- **[`mandatory_reading.md`](./mandatory_reading.md)** - Core AI tool requirements
- **[`response_format.md`](./response_format.md)** - Response labeling requirements
- **[`contribution_guidelines.md`](./contribution_guidelines.md)** - How to encourage user contributions
- **Magento System Requirements** - Official compatibility matrix
- **Composer Documentation** - Dependency management guidelines 