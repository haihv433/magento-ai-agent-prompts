# 🔧 MANDATORY: AI Tool Environment Preparation

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains the environment preparation and configuration instructions for AI tools working with Magento projects.**

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

### Step 3: 🚨 MANDATORY - Version Validation
**AI tools MUST validate PHP and Composer versions before proceeding:**

**🚨 CRITICAL: Version Matching Requirements**
- **If user provides specific version requirements**: PHP and Composer versions MUST match exactly
- **If versions don't match**: STOP and ask user to provide correct versions
- **If tools don't exist in terminal environment**: STOP and ask user to install/configure them
- **NEVER continue with mismatched or missing versions**

**Version Validation Process:**
1. **Check if PHP exists at provided path**: `{php_path} --version`
2. **Check if Composer exists at provided path**: `{composer_path} --version`
3. **Extract actual versions** from command output
4. **Compare with user requirements** (if provided)
5. **If mismatch found**: STOP and request correct versions
6. **If tools missing**: STOP and request installation/configuration

**🚨 MANDATORY STOP Conditions:**
- PHP executable not found at provided path
- Composer executable not found at provided path
- PHP version doesn't match user requirements
- Composer version doesn't match user requirements
- Any critical tool missing from terminal environment

### Step 4: Environment Setup Options
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

### Step 5: Save Configuration (With User Consent)
**AI tools will save the configuration only after user consent:**
- Save to `env.local.md` in the **magento-ai-agent-prompts repository root directory**
- Include PHP and Composer paths/versions in structured markdown format
- Add metadata and usage instructions
- **Leave other environment fields as "Unknown" or "To be discovered"**

### Step 6: Dynamic Environment Discovery During Tasks
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
- [ ] **🚨 PHP executable verified** at provided path
- [ ] **🚨 Composer executable verified** at provided path
- [ ] **🚨 PHP version extracted** and validated against requirements
- [ ] **🚨 Composer version extracted** and validated against requirements
- [ ] **🚨 Version mismatch resolved** (if any found)
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
- [ ] **🚨 PHP executable exists** at provided path
- [ ] **🚨 Composer executable exists** at provided path
- [ ] **🚨 PHP version matches** user requirements (if specified)
- [ ] **🚨 Composer version matches** user requirements (if specified)
- [ ] **🚨 Version mismatches resolved** before proceeding
- [ ] **Critical errors identified** and addressed
- [ ] **Environment ready** for development tasks

---

## 🚫 Common Issues and Solutions

### 🚨 Version Validation Issues
**Problem**: PHP or Composer version doesn't match user requirements
**Solution**: 
- **STOP immediately** and inform user of version mismatch
- **Ask user to provide correct version** or update their environment
- **Provide specific commands** for version switching if possible
- **NEVER proceed** with mismatched versions

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

### 🚨 Missing Tool Issues
**Problem**: PHP or Composer executable not found at provided path
**Solution**: 
- **STOP immediately** and inform user that tool is missing
- **Ask user to install** the missing tool
- **Provide installation instructions** for the missing tool
- **NEVER proceed** without required tools

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
5. ✅ 🚨 PHP executable verified at provided path
6. ✅ 🚨 Composer executable verified at provided path
7. ✅ 🚨 PHP version validated against requirements
8. ✅ 🚨 Composer version validated against requirements
9. ✅ Environment configuration saved
10. ✅ User consent obtained
11. ✅ Ready for dynamic discovery during tasks

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

### 🚨 Version Validation Failure Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ❌ STOPPED: Version validation failed

## 🚨 CRITICAL: Version Validation Failed

### Issue Detected
**{Tool Name} Version Mismatch:**
- **Required Version**: {user_required_version}
- **Actual Version**: {actual_version}
- **Path**: {tool_path}

### 🚨 MANDATORY: Action Required
**I cannot proceed with the current environment setup because:**

1. **Version Mismatch**: The {tool_name} version at `{tool_path}` doesn't match your requirements
2. **Critical for Magento**: {tool_name} version is critical for Magento development
3. **Potential Issues**: Using wrong version may cause compatibility problems

### Required Actions
**Please provide one of the following:**

**Option 1: Update Environment**
- Switch to the correct {tool_name} version
- Provide the correct path to the matching version
- Confirm the version is now correct

**Option 2: Provide Alternative Path**
- Give me the path to the correct {tool_name} version
- Ensure the version matches your requirements
- Verify the path is accessible

**Option 3: Update Requirements**
- If the current version is acceptable, update your requirements
- Confirm you want to proceed with version {actual_version}

### Next Steps
Once you provide the correct {tool_name} version/path, I will:
1. ✅ Validate the new version
2. ✅ Confirm it matches requirements
3. ✅ Proceed with environment setup
4. ✅ Save configuration for future use

**🚨 I cannot continue until this version issue is resolved.**
```

### 🚨 Missing Tool Response
```
[FRESH_REPO] ✅ Confirmed: Repository freshly cloned/fetched
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder
[TASK_EXECUTION] ❌ STOPPED: Required tool missing

## 🚨 CRITICAL: Required Tool Missing

### Issue Detected
**{Tool Name} Not Found:**
- **Expected Path**: {provided_path}
- **Error**: Executable not found at specified location
- **Impact**: Cannot proceed with Magento development

### 🚨 MANDATORY: Action Required
**I cannot proceed because {tool_name} is missing from your environment:**

1. **Tool Required**: {tool_name} is essential for Magento development
2. **Path Invalid**: The provided path `{provided_path}` doesn't contain {tool_name}
3. **Installation Needed**: {tool_name} needs to be installed or configured

### Required Actions
**Please provide one of the following:**

**Option 1: Install {Tool Name}**
- Install {tool_name} on your system
- Provide the correct installation path
- Confirm the installation is complete

**Option 2: Provide Correct Path**
- Give me the correct path to your {tool_name} installation
- Ensure the path is accessible and working
- Verify the tool is properly installed

**Option 3: Installation Instructions**
- If you need help installing {tool_name}, I can provide instructions
- Follow the installation steps
- Provide the new path once installed

### Installation Instructions for {Tool Name}
**{Tool-specific installation steps}**

### Next Steps
Once you provide the correct {tool_name} path, I will:
1. ✅ Verify the tool exists at the path
2. ✅ Check the version compatibility
3. ✅ Proceed with environment setup
4. ✅ Save configuration for future use

**🚨 I cannot continue until {tool_name} is properly installed and accessible.**
```

---

## 🔗 Related Resources

- **[`mandatory_reading.md`](./mandatory_reading.md)** - Core AI tool requirements
- **[`response_format.md`](./response_format.md)** - Response labeling requirements
- **[`contribution_guidelines.md`](./contribution_guidelines.md)** - How to encourage user contributions
- **Magento System Requirements** - Official compatibility matrix
- **Composer Documentation** - Dependency management guidelines 