# AI Agent Instruction: Fix Outdated Module/Code

## 🚨 CRITICAL: READ ALL MAGENTO FOLDER INSTRUCTIONS FIRST

**BEFORE performing any task, you MUST read and understand ALL instructions in the [`/magento/`](../magento/) folder.**

### Required Reading Order:
1. **[`design_patterns.md`](../magento/design_patterns.md)** - Complete systematic approach for Magento development
2. **Any other files in [`/magento/`](../magento/) folder** - Additional Magento-specific guidelines

**Do not proceed with any code changes until you have completed this reading.**

---

## 📋 Task Overview

This instruction guides AI agents through identifying and fixing outdated Magento module code while maintaining compatibility with the current Magento version.

## 🎯 Common Outdated Code Scenarios

- **Deprecated Method Signatures** - Method parameters, return types, or names changed
- **Interface Changes** - New methods added, old ones deprecated
- **Class Structure Updates** - Parent class changes, new abstract methods required
- **Configuration Updates** - XML structure changes, new required attributes
- **Plugin/Interceptor Changes** - Method signature mismatches, new plugin types

---

## 🔍 Analysis Process

### Step 1: Identify the Issue
1. Locate the problematic file/class/method
2. Identify the specific issue (error message, deprecation warning, etc.)
3. Note the current Magento version being used

### Step 2: Reference Code Analysis
**Follow the systematic approach from [`design_patterns.md`](../magento/design_patterns.md):**

- Find the target class/method in `vendor/magento/`
- Read the complete reference implementation
- Compare with the outdated code
- Identify differences in signatures, parameters, return types

### Step 3: Version Compatibility
- Determine the target Magento version
- Check if the method/class exists in the target version
- Research migration guides if needed

### Step 4: Propose Compatible Fix
- Use exact signatures from reference code
- Match parameter types precisely
- Follow Magento coding standards

---

## 🛠️ Implementation Workflows

### Workflow 1: Fixing Deprecated Method Calls
1. Find the method in `vendor/magento/` (current version)
2. Read the new signature
3. Update all calls to match the new signature

### Workflow 2: Updating Interface Implementations
1. Find the interface in `vendor/magento/`
2. Identify all required methods
3. Implement missing methods to match exactly

### Workflow 3: Plugin Compatibility
1. Find target class in `vendor/magento/`
2. Read actual method signature
3. Update plugin to match exactly

### Workflow 4: Configuration Updates
1. Check current Magento configuration examples
2. Update XML structure to match
3. Remove deprecated nodes

---

## ✅ Validation Checklist

Before proposing any fix, verify:

- [ ] **All [`/magento/`](../magento/) folder instructions read and understood**
- [ ] **Reference code found in `vendor/magento/`**
- [ ] **Method signature matches exactly**
- [ ] **Parameter types are correct**
- [ ] **Return types match**
- [ ] **Namespace is correct**
- [ ] **No deprecated methods used**
- [ ] **Configuration XML is current**

---

## 🚫 Common Mistakes to Avoid

- **Skipping reference code check** - Always verify against `vendor/magento/`
- **Assuming method signatures** - Never guess, always check
- **Using wrong parameter types** - Match reference exactly
- **Missing optional parameters** - Include all parameters from reference
- **Wrong return types** - Use exact types from reference

---

## 🎯 Success Criteria

A successful outdated code fix should:

1. **Eliminate all deprecation warnings**
2. **Maintain full functionality**
3. **Pass all existing tests**
4. **Follow current Magento standards**
5. **Be compatible with target Magento version**

---

## ⚠️ Important Reminders

- **Always check reference code first**
- **Never assume method signatures**
- **Follow Magento coding standards**
- **Test thoroughly after changes**

**Remember**: When in doubt, check the reference code in `vendor/magento/` before making any assumptions or proposals. 