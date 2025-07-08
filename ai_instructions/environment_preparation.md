# 🔧 MANDATORY: AI Tool Environment Preparation

## 🚨 CRITICAL: READ THIS FILE FIRST
**BEFORE performing ANY task, you MUST prepare and verify the Magento development environment. This ensures proper PHP version compatibility, tool availability, and clean development state.**

## 🔧 How AI Tools Should Use Environment Configuration

**AI Tools Workflow:**

1. **First Priority: Read Existing Configuration**
   - Check if `env.local.md` exists in the magento-ai-agent-prompts repository root
   - If found, read and parse the configuration file
   - Use the stored environment information for all operations
   - Skip environment setup if configuration is complete and valid

2. **Second Priority: Create New Configuration (if not exists)**
   - If no `env.local.md` file exists, proceed with environment setup
   - Ask user for consent to create the configuration file
   - Offer manual configuration or auto-detection options
   - Save configuration to `env.local.md` in the magento-ai-agent-prompts repository root

3. **When running commands, AI tools should:**
   - Check if `env.local.md` exists
   - Parse the file to extract environment variables
   - Use the saved paths for running commands

2. **Use the saved paths for commands:**
   ```bash
   # Instead of: php bin/magento cache:clean
   # Use the PHP_PATH from the config file
   
   # Instead of: composer install
   # Use the COMPOSER_PATH from the config file
   
   # Instead of: npm install
   # Use the NPM_PATH from the config file
   ```

3. **Example configuration file format:**
   ```
   # Magento Configuration
   MAGENTO_VERSION=2.4.6
   MAGENTO_EDITION=Community
   PROJECT_PATH=/var/www/html/magento
   
   # PHP Configuration
   PHP_VERSION=8.1
   PHP_PATH=/usr/bin/php
   PHP_MEMORY_LIMIT=2G
   
   # Composer Configuration
   COMPOSER_VERSION=2.5.0
   COMPOSER_PATH=/usr/local/bin/composer
   ```

4. **AI tools should parse this file and use the values to construct commands:**
   - Read `PHP_PATH` and use it for PHP commands
   - Read `COMPOSER_PATH` and use it for Composer commands
   - Read `NPM_PATH` and use it for npm commands
   - Verify paths exist before using them

5. **Leverage stored information to avoid repeated checks:**
   - **Magento Mode**: Use `MAGENTO_MODE` instead of running `php bin/magento deploy:mode:show`
   - **Git Info**: Use `GIT_REPOSITORY` and `GIT_BRANCH` instead of running git commands
   - **PHP Extensions**: Use `PHP_EXTENSIONS` instead of checking extensions repeatedly
   - **User Preferences**: Use `PREFERRED_CODING_STANDARD` for code formatting
   - **Project Settings**: Use `PREFERRED_MODULE_NAMESPACE` for new module creation
   - **Tool Availability**: Use `DOCKER_AVAILABLE` to know if Docker commands are available

---

## 📋 Purpose
This file instructs AI tools to systematically prepare and verify the Magento development environment before executing any development tasks. The process prioritizes user-provided configuration or auto-detection, saves settings to a separate `.magento-ai-agent-prompts.txt` file with user consent, and avoids modifying any Magento project files. This prevents environment-related issues and ensures consistent, reliable development assistance.

**Key Benefits:**
- **Avoid Repeated Checks**: Store environment information to avoid running the same detection commands repeatedly
- **User Preference Caching**: Remember user preferences and project settings
- **Tool Availability Tracking**: Know which development tools are available without checking each time
- **Project Context Preservation**: Store project-specific information like Git repository, branch, and module namespaces
- **Efficiency Improvement**: Reduce setup time and avoid asking users for the same information multiple times

**Local Storage File Pattern (`.local.md`):**
- **File Type**: Local Storage File (`.local.md`) - Standard pattern for AI agent data persistence
- **Location**: `env.local.md` in the magento-ai-agent-prompts repository root directory
- **Naming**: Simple and intuitive naming for environment configuration
- **Format**: Proper Markdown with tables, sections, and metadata for easy reading and parsing
- **Scope**: Environment configuration that persists across AI tool sessions
- **Purpose**: Store environment data that AI tools need to remember between sessions

**Standard `.local.md` Structure:**
1. **Header**: File type, purpose, generation date, project info
2. **Configuration Sections**: Organized in markdown tables
3. **User Preferences**: Stored preferences and settings
4. **Metadata**: Version, timestamps, setup method
5. **Usage Instructions**: How AI tools should use the file
6. **Notes**: Important information about the file

**Configuration File Updates:**
AI tools should update the configuration file when they discover new information:
- **New Module Created**: Update `PREFERRED_MODULE_NAMESPACE` if user creates a new module
- **Coding Standard Changed**: Update `PREFERRED_CODING_STANDARD` if user specifies a different standard
- **Git Branch Changed**: Update `GIT_BRANCH` when switching branches
- **New Tools Installed**: Update tool availability flags when new tools are detected
- **User Preferences**: Update user preferences when they are expressed during conversations

**Extending the `.local.md` Pattern:**
For future tasks that need data persistence, AI tools should:
1. **Create new `.local.md` files** following the same structure and format
2. **Use descriptive names** like `{task-name}.local.md` or `{category}-{task-name}.local.md`
3. **Follow the standard format** with headers, tables, metadata, and usage instructions
4. **Store in the magento-ai-agent-prompts repository root** for easy access
5. **Include clear documentation** about what the file contains and how to use it

**Examples of Additional `.local.md` Files:**
- `modules.local.md` - Track created modules and their configurations
- `debugging.local.md` - Store debugging history and solutions
- `customizations.local.md` - Track custom code and modifications
- `testing.local.md` - Store test configurations and results

**IMPORTANT**: This file provides the framework for environment preparation. The actual commands should only be executed when:
- Performing actual code checking tasks
- User specifically requests environment verification
- Environment-related issues are reported
- Setup operations are needed

For general environment preparation, just ensure the environment is ready without running unnecessary checks.

---

## 🎯 Environment Preparation Workflow

### Step 1: Check for Existing Environment Configuration
**AI tools will first check for saved environment configuration:**

```bash
# Get project name from Magento project directory
MAGENTO_PROJECT_PATH=$(pwd)
PROJECT_NAME=$(basename "$MAGENTO_PROJECT_PATH")
if [ -f "composer.json" ]; then
    COMPOSER_NAME=$(grep -o '"name": "[^"]*"' composer.json | cut -d'"' -f4 | cut -d'/' -f2 2>/dev/null || echo "$PROJECT_NAME")
    PROJECT_NAME=${COMPOSER_NAME:-$PROJECT_NAME}
fi

# Define cache file name (saved to magento-ai-agent-prompts repo root)
CACHE_FILE="env.local.md"

# Check if environment config exists
if [ -f "$CACHE_FILE" ]; then
    echo "✅ Found existing environment configuration"
    echo "Reading configuration from $CACHE_FILE..."
    echo "Configuration loaded successfully"
else
    echo "❌ No environment configuration found"
    echo "Proceeding to environment setup..."
fi
```
```

### Step 2: Environment Setup Options
**AI tools will offer two options for environment setup:**

```
🔧 **Environment Setup Required**

I can help you set up your environment configuration in two ways:

**Option 1: Manual Configuration (Recommended)**
You provide your environment details directly for maximum accuracy.

**Option 2: Auto-Detection**
I can attempt to detect your environment automatically, but this may not be 100% accurate.

**What would you prefer?**

**For Manual Configuration, please provide:**
- Magento Version: [e.g., 2.4.6, 2.4.7]
- Edition: [Community/Enterprise/Adobe Commerce]
- PHP Version: [e.g., 8.1, 8.2]
- PHP Path: [e.g., /usr/bin/php, /opt/homebrew/bin/php]
- Composer Version: [e.g., 2.5.0]
- Composer Path: [e.g., /usr/local/bin/composer]
- Web Server: [Apache/Nginx]
- Database: [MySQL/MariaDB]
- Environment: [Development/Staging/Production]

**For Auto-Detection, just say "auto-detect" and I'll attempt to detect your environment.**

**⚠️ IMPORTANT**: This information will be saved to `env.local.md` in the magento-ai-agent-prompts repository root directory. 
This file will be used by AI tools to understand your environment without repeated setup.
Do you consent to creating this file for future environment checks?
```

### Step 3: Auto-Detection Process (If User Chooses)
**AI tools will attempt to detect environment automatically:**

```bash
# Auto-detection commands (only if user consents and chooses auto-detect)
if [ "$AUTO_DETECT" = "true" ]; then
    echo "🔍 Auto-detecting your environment..."
    
    # Detect Magento version and mode
    if [ -f "composer.json" ]; then
        MAGENTO_VERSION=$(grep -o '"magento/product-community-edition": "[^"]*"' composer.json | cut -d'"' -f4 | cut -d'-' -f2)
        MAGENTO_EDITION="Community"
    elif [ -f "composer.json" ] && grep -q "magento/product-enterprise-edition" composer.json; then
        MAGENTO_VERSION=$(grep -o '"magento/product-enterprise-edition": "[^"]*"' composer.json | cut -d'"' -f4 | cut -d'-' -f2)
        MAGENTO_EDITION="Enterprise"
    else
        MAGENTO_VERSION="Unknown"
        MAGENTO_EDITION="Unknown"
    fi
    
    # Detect Magento mode
    if [ -f "bin/magento" ]; then
        MAGENTO_MODE=$(php bin/magento deploy:mode:show 2>/dev/null | grep "Current application mode" | cut -d':' -f2 | xargs || echo "Unknown")
    else
        MAGENTO_MODE="Unknown"
    fi
    
    # Detect PHP version and path
    PHP_PATH=$(which php 2>/dev/null || echo "Unknown")
    PHP_VERSION=$(php -r "echo PHP_MAJOR_VERSION . '.' . PHP_MINOR_VERSION;" 2>/dev/null || echo "Unknown")
    PHP_MEMORY_LIMIT=$(php -r "echo ini_get('memory_limit');" 2>/dev/null || echo "Unknown")
    
    # Detect Composer version and path
    COMPOSER_PATH=$(which composer 2>/dev/null || echo "Unknown")
    COMPOSER_VERSION=$(composer --version 2>/dev/null | head -1 | cut -d' ' -f3 || echo "Unknown")
    
    # Detect Node.js and npm (for frontend tools)
    NODE_PATH=$(which node 2>/dev/null || echo "Unknown")
    NODE_VERSION=$(node --version 2>/dev/null || echo "Unknown")
    NPM_PATH=$(which npm 2>/dev/null || echo "Unknown")
    NPM_VERSION=$(npm --version 2>/dev/null || echo "Unknown")
    
    # Detect Git
    GIT_PATH=$(which git 2>/dev/null || echo "Unknown")
    GIT_VERSION=$(git --version 2>/dev/null | cut -d' ' -f3 || echo "Unknown")
    GIT_REPOSITORY=$(git config --get remote.origin.url 2>/dev/null || echo "Unknown")
    GIT_BRANCH=$(git branch --show-current 2>/dev/null || echo "Unknown")
    
    # Detect web server
    if [ -f ".htaccess" ]; then
        WEB_SERVER="Apache"
    elif [ -f "nginx.conf" ] || [ -f "nginx.conf.sample" ]; then
        WEB_SERVER="Nginx"
    else
        WEB_SERVER="Unknown"
    fi
    
    # Detect database (basic check)
    if [ -f "app/etc/env.php" ] && grep -q "mysql" app/etc/env.php; then
        DATABASE="MySQL"
    else
        DATABASE="Unknown"
    fi
    
    ENVIRONMENT="Development"
    PROJECT_PATH=$(pwd)
    
    # Detect additional tools
    DOCKER_AVAILABLE=$(which docker >/dev/null 2>&1 && echo "Yes" || echo "No")
    DOCKER_COMPOSE_AVAILABLE=$(which docker-compose >/dev/null 2>&1 && echo "Yes" || echo "No")
    
    # Detect user information
    USER_NAME=$(whoami 2>/dev/null || echo "Unknown")
    USER_TIMEZONE=$(date +%Z 2>/dev/null || echo "Unknown")
    
    echo "✅ Auto-detection completed:"
    echo "- Magento: $MAGENTO_VERSION $MAGENTO_EDITION (Mode: $MAGENTO_MODE)"
    echo "- PHP: $PHP_VERSION ($PHP_PATH)"
    echo "- Composer: $COMPOSER_VERSION ($COMPOSER_PATH)"
    echo "- Node.js: $NODE_VERSION ($NODE_PATH)"
    echo "- Git: $GIT_VERSION ($GIT_PATH) - Branch: $GIT_BRANCH"
    echo "- Server: $WEB_SERVER"
    echo "- Database: $DATABASE"
    echo "- Docker: $DOCKER_AVAILABLE, Docker Compose: $DOCKER_COMPOSE_AVAILABLE"
fi
```

### Step 4: Save Configuration (With User Consent)
**AI tools will save the configuration only after user consent:**

```bash
# Save configuration to {project-name}.local.md in magento-ai-agent-prompts repo (only if user consents)
if [ "$USER_CONSENT" = "true" ]; then
    cat > "$CACHE_FILE" << EOF
# Magento AI Agent - Local Storage File

> **File Type**: Local Storage File (`.local.md`)  
> **Purpose**: Environment configuration and user preferences for AI agent optimization  
> **Generated**: $(date)  
> **Project**: ${PROJECT_NAME}  
> **Setup Method**: ${SETUP_METHOD:-"Manual"}

---

## 🔧 Environment Configuration

### Magento Settings
| Setting | Value |
|---------|-------|
| **Version** | ${MAGENTO_VERSION:-"Unknown"} |
| **Edition** | ${MAGENTO_EDITION:-"Unknown"} |
| **Mode** | ${MAGENTO_MODE:-"Unknown"} |
| **Project Path** | ${PROJECT_PATH:-"$(pwd)"} |
| **Base URL** | ${MAGENTO_BASE_URL:-"Unknown"} |

### PHP Configuration
| Setting | Value |
|---------|-------|
| **Version** | ${PHP_VERSION:-"Unknown"} |
| **Path** | ${PHP_PATH:-"Unknown"} |
| **Memory Limit** | ${PHP_MEMORY_LIMIT:-"Unknown"} |
| **Extensions** | ${PHP_EXTENSIONS:-"Unknown"} |

### Composer Configuration
| Setting | Value |
|---------|-------|
| **Version** | ${COMPOSER_VERSION:-"Unknown"} |
| **Path** | ${COMPOSER_PATH:-"Unknown"} |
| **Auth File** | ${COMPOSER_AUTH_FILE:-"Unknown"} |

### Node.js Configuration
| Setting | Value |
|---------|-------|
| **Node Version** | ${NODE_VERSION:-"Unknown"} |
| **Node Path** | ${NODE_PATH:-"Unknown"} |
| **npm Version** | ${NPM_VERSION:-"Unknown"} |
| **npm Path** | ${NPM_PATH:-"Unknown"} |

### Git Configuration
| Setting | Value |
|---------|-------|
| **Version** | ${GIT_VERSION:-"Unknown"} |
| **Path** | ${GIT_PATH:-"Unknown"} |
| **Repository** | ${GIT_REPOSITORY:-"Unknown"} |
| **Branch** | ${GIT_BRANCH:-"Unknown"} |

### Server Configuration
| Setting | Value |
|---------|-------|
| **Web Server** | ${WEB_SERVER:-"Unknown"} |
| **Database** | ${DATABASE:-"Unknown"} |
| **Database Host** | ${DATABASE_HOST:-"Unknown"} |
| **Database Name** | ${DATABASE_NAME:-"Unknown"} |
| **Environment** | ${ENVIRONMENT:-"Development"} |

### Development Tools
| Tool | Available |
|------|-----------|
| **IDE** | ${IDE:-"Unknown"} |
| **Docker** | ${DOCKER_AVAILABLE:-"Unknown"} |
| **Docker Compose** | ${DOCKER_COMPOSE_AVAILABLE:-"Unknown"} |

---

## 🎯 User Preferences

### Project Preferences
| Preference | Value |
|------------|-------|
| **Module Namespace** | ${PREFERRED_MODULE_NAMESPACE:-"Unknown"} |
| **Coding Standard** | ${PREFERRED_CODING_STANDARD:-"PSR-12"} |
| **Testing Framework** | ${PREFERRED_TESTING_FRAMEWORK:-"Unknown"} |

### User Information
| Setting | Value |
|---------|-------|
| **Name** | ${USER_NAME:-"Unknown"} |
| **Email** | ${USER_EMAIL:-"Unknown"} |
| **Timezone** | ${USER_TIMEZONE:-"Unknown"} |

---

## 📋 Metadata

| Field | Value |
|-------|-------|
| **Config Version** | 1.0 |
| **Last Updated** | $(date) |
| **Setup Method** | ${SETUP_METHOD:-"Manual"} |
| **File Type** | Local Storage File |

---

## 🔄 Usage Instructions

### For AI Tools
1. **Read this file** to understand the environment configuration
2. **Use stored paths** for running commands (e.g., \`${PHP_PATH} bin/magento cache:clean\`)
3. **Apply user preferences** for code formatting and module creation
4. **Update this file** when new information is discovered

### For Manual Updates
- Edit this file directly to update configuration
- Follow the markdown table format for consistency
- Update the "Last Updated" timestamp when making changes

---

> **Note**: This is a local storage file (`.local.md`) that contains project-specific configuration.  
> It should not be committed to version control and is intended for AI agent optimization.
EOF

    echo "✅ Environment configuration saved to $CACHE_FILE"
    echo "📝 This file contains your environment settings for future AI agent sessions"
    echo "💡 This file is saved in the magento-ai-agent-prompts repository for easy access"
else
    echo "❌ User did not consent to saving configuration"
    echo "📝 Environment settings will not be saved for future sessions"
fi
```
```

### Step 5: Configuration Update (When Needed)
**AI tools will offer to update configuration if environment changes:**

```bash
# Check if configuration needs updating
if [ -f ".magento-ai-agent-prompts.txt" ]; then
    echo "🔄 Would you like to update your environment configuration?"
    echo "   This is useful if you've changed PHP versions, Magento versions, or other settings."
    echo "   Current configuration:"
    echo "   - Reading from $CACHE_FILE"
    echo "   - Configuration file exists and can be updated"
    echo ""
    echo "   To update, simply provide new environment details when prompted."
fi
```

### Step 6: Magento Version and PHP Compatibility Check

**MANDATORY Commands to execute (ONLY when actual checking is needed):**
```bash
# Check PHP version
php -v

# Check Magento version
php bin/magento --version

# Verify PHP compatibility with Magento version
```

**Note**: Only execute these commands when performing actual code checking or when user specifically requests environment verification. For general environment preparation, just ensure the environment is ready without running these checks.

**Magento 2.4.x PHP Version Requirements:**
- **Magento 2.4.0-2.4.4**: PHP 7.4, 8.1
- **Magento 2.4.5-2.4.6**: PHP 8.1, 8.2
- **Magento 2.4.7+**: PHP 8.1, 8.2, 8.3

**Validation Checklist:**
- [ ] **Environment configuration checked** for existing .magento-ai-agent-prompts.txt file
- [ ] **User consent obtained** for saving configuration
- [ ] **Environment setup completed** (manual or auto-detection)
- [ ] **Configuration saved** to .magento-ai-agent-prompts.txt (if consented)
- [ ] **PHP version detected** and logged
- [ ] **Magento version detected** and logged
- [ ] **Compatibility verified** between PHP and Magento versions
- [ ] **Version mismatch identified** if any (with recommendations)

### Step 2: Multiple Environment Detection

**MANDATORY Commands to execute (ONLY when environment complexity is suspected):**
```bash
# Check for multiple PHP installations
which -a php

# Check common PHP installation locations
ls -la /usr/local/bin/php* 2>/dev/null || echo "No additional PHP versions found in /usr/local/bin/"
ls -la /opt/homebrew/bin/php* 2>/dev/null || echo "No additional PHP versions found in /opt/homebrew/bin/"

# Check for PHP version managers
which phpbrew 2>/dev/null || echo "phpbrew not found"
which phpenv 2>/dev/null || echo "phpenv not found"
which php-version 2>/dev/null || echo "php-version not found"

# Check for multiple Composer installations
which -a composer
ls -la /usr/local/bin/composer* 2>/dev/null || echo "No additional composer versions found in /usr/local/bin/"
ls -la /opt/homebrew/bin/composer* 2>/dev/null || echo "No additional composer versions found in /opt/homebrew/bin/"

# Check for development tools
which node 2>/dev/null || echo "Node.js not found"
which npm 2>/dev/null || echo "npm not found"
which yarn 2>/dev/null || echo "yarn not found"
which grunt 2>/dev/null || echo "grunt not found"
which gulp 2>/dev/null || echo "gulp not found"
which git 2>/dev/null || echo "git not found"
which docker 2>/dev/null || echo "docker not found"
which docker-compose 2>/dev/null || echo "docker-compose not found"
```

**Note**: Only execute these commands when you suspect multiple environments or when user reports environment-related issues. For standard environment preparation, assume single environment unless indicated otherwise.

**Validation Checklist:**
- [ ] **All PHP installations identified** and listed
- [ ] **Version conflicts detected** if any
- [ ] **Current PHP path verified** matches expected version
- [ ] **PHP version managers checked** if present
- [ ] **Multiple Composer installations detected** if any
- [ ] **Development tools availability verified**
- [ ] **Environment complexity assessed**

### Step 3: Environment Complexity Assessment

**If multiple environments detected, ask user for clarification:**

```
🔍 **Environment Complexity Detected**

I found multiple development environments on your system:

**PHP Versions Available:**
- [List detected PHP versions]

**Composer Installations:**
- [List detected composer installations]

**Development Tools:**
- [List detected tools]

**Questions for you:**
1. Which PHP version should I use for this Magento project?
2. Which Composer installation should I use?
3. Are there any specific environment variables or configurations I should be aware of?
4. Are you using any containerization (Docker, etc.) for this project?

Please provide the correct environment details so I can proceed with the proper setup.
```

### Step 4: Magento Environment Mode Verification

**MANDATORY Commands to execute (ONLY when mode verification is needed):**
```bash
# Check current deployment mode
php bin/magento deploy:mode:show 2>/dev/null | grep "Current application mode" || echo "Environment mode check completed"
```

**Note**: Only execute this command when you need to verify the deployment mode or when user reports mode-related issues. For general preparation, assume developer mode unless indicated otherwise.

**Expected Results:**
- **Developer Mode**: ✅ Perfect for development
- **Production Mode**: ⚠️ Should be switched to developer for development tasks
- **Default Mode**: ⚠️ Should be switched to developer for development tasks

**Validation Checklist:**
- [ ] **Environment mode detected** and logged
- [ ] **Mode appropriateness verified** for development tasks
- [ ] **Mode switching recommended** if needed

### Step 5: Cache and Generated Code Cleanup

**MANDATORY Commands to execute (ONLY when cleanup is needed):**
```bash
# Clean Magento cache (suppress deprecation warnings)
php bin/magento cache:clean 2>/dev/null
php bin/magento cache:flush 2>/dev/null

# Clean generated code and cache directories
rm -rf var/cache/* var/page_cache/* var/view_preprocessed/* pub/static/*

# Optional: Clean generated code (use with caution)
# rm -rf generated/*
```

**Note**: Only execute these commands when you need to perform actual cleanup or when user reports cache-related issues. For general preparation, just ensure the environment is ready for cleanup if needed.

**Validation Checklist:**
- [ ] **Cache cleaned** successfully
- [ ] **Generated directories cleaned** successfully
- [ ] **Static files cleaned** successfully
- [ ] **No critical errors** during cleanup process

### Step 6: Composer Dependencies Check

**MANDATORY Commands to execute (ONLY when dependency management is needed):**
```bash
# Check composer status
composer status

# Install/update dependencies (choose appropriate command)
composer install --no-dev --optimize-autoloader
# OR for development
composer install --optimize-autoloader
# OR for updates
composer update --no-dev --optimize-autoloader
```

**Note**: Only execute these commands when you need to manage dependencies or when user reports dependency-related issues. For general preparation, just ensure the environment is ready for dependency management if needed.

**Validation Checklist:**
- [ ] **Composer dependencies verified** and up to date
- [ ] **Autoloader optimized** for performance
- [ ] **No dependency conflicts** detected
- [ ] **Vendor directory integrity** verified

### Step 7: Magento Setup Commands

**MANDATORY Commands to execute (ONLY when setup operations are needed):**
```bash
# Run setup upgrade
php bin/magento setup:upgrade

# Run dependency injection compilation
php bin/magento setup:di:compile

# Deploy static content (if needed)
php bin/magento setup:static-content:deploy -f
```

**Note**: Only execute these commands when you need to perform actual setup operations or when user reports setup-related issues. For general preparation, just ensure the environment is ready for setup operations if needed.

**Validation Checklist:**
- [ ] **Setup upgrade completed** successfully
- [ ] **DI compilation completed** successfully
- [ ] **Static content deployed** if needed
- [ ] **No critical errors** in logs

---

## ✅ Mandatory Validation Checklist

### Environment Verification
- [ ] **PHP version compatible** with Magento version
- [ ] **No PHP version conflicts** detected
- [ ] **Environment mode appropriate** for development
- [ ] **All cache cleared** successfully
- [ ] **Composer dependencies** up to date
- [ ] **Magento setup commands** executed successfully

### Error Handling
- [ ] **Deprecation warnings logged** but not blocking
- [ ] **Critical errors identified** and addressed
- [ ] **Version mismatches resolved** or documented
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
**Solution**:
```bash
php bin/magento deploy:mode:set developer
```

### Cache Issues
**Problem**: Cache not clearing properly
**Solution**:
```bash
rm -rf var/cache/* var/page_cache/* var/view_preprocessed/* pub/static/*
php bin/magento cache:clean
php bin/magento cache:flush
```

### Composer Issues
**Problem**: Dependency conflicts or outdated packages
**Solution**:
```bash
composer update --no-dev --optimize-autoloader
composer dump-autoload --optimize
```

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

### Environment Summary
- **PHP Version**: [X.X.X]
- **Magento Version**: [X.X.X]
- **Compatibility**: ✅ Compatible / ⚠️ Incompatible
- **Environment Mode**: [developer/production/default]
- **PHP Installations**: [Single/Multiple detected]
- **Composer Installations**: [Single/Multiple detected]
- **Development Tools**: [List available tools]

### Preparation Steps Completed
1. ✅ Version compatibility verified
2. ✅ Multiple environments checked
3. ✅ Environment mode verified
4. ✅ Cache and generated code cleaned
5. ✅ Composer dependencies updated
6. ✅ Magento setup commands executed

### Issues Found and Resolved
[List any issues found and how they were resolved]

### Environment Status
✅ **Ready for development tasks**
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