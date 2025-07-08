# 🔧 MANDATORY: AI Tool Environment Preparation

## 🚨 CRITICAL: READ THIS FILE FIRST
**BEFORE performing ANY task, you MUST prepare and verify the Magento development environment. This ensures proper PHP version compatibility, tool availability, and clean development state.**

---

## 📋 Purpose
This file instructs AI tools to systematically prepare and verify the Magento development environment before executing any development tasks. This prevents environment-related issues and ensures consistent, reliable development assistance.

**IMPORTANT**: This file provides the framework for environment preparation. The actual commands should only be executed when:
- Performing actual code checking tasks
- User specifically requests environment verification
- Environment-related issues are reported
- Setup operations are needed

For general environment preparation, just ensure the environment is ready without running unnecessary checks.

---

## 🎯 Environment Preparation Workflow

### Step 1: Magento Version and PHP Compatibility Check

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