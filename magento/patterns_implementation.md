# 🔧 AI Agent Guide: Magento Implementation Workflows and Tools

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains implementation workflows and tools for Magento reference code checking. For the core approach and scenarios, see [`patterns_overview.md`](./patterns_overview.md).**

---

## 📋 Purpose
This file provides universal principles and workflows for AI agents to effectively check and match Magento reference code. It includes conceptual approaches, example workflows, and documentation standards that AI tools can adapt to their preferred implementation methods.

---

## 🔄 Example Workflows

### Workflow 1: Fixing Plugin Parameter Mismatch

**User Issue**: "Plugin method signature doesn't match"

**AI Agent Steps**:
1. Find target class in all possible locations (vendor/magento/, app/code/, dev/)
2. Read actual method signature
3. Compare with user's plugin
4. Propose exact match fix

**Example**:
**Step 1**: AI tools should search for the target method across all possible locations where Magento classes exist.

**Step 2**: Read the actual signature from the found reference code.
```php
// Found in: vendor/magento/module-sales-rule/Model/RulesApplier.php (or app/code/Vendor/Module/...)
public function applyRules($item, $rules, $skipValidation, array $couponCodes = [])
```

**Step 3**: Fix plugin to match the reference signature exactly.

### Workflow 2: Interface Implementation

**User Issue**: "Interface method not implemented correctly"

**AI Agent Steps**:
1. Find interface in all possible locations (vendor/magento/, app/code/, dev/)
2. Read all required methods
3. Check implementation completeness
4. Propose missing methods

### Workflow 3: Class Extension

**User Issue**: "Extended class has compatibility issues"

**AI Agent Steps**:
1. Find parent class in all possible locations (vendor/magento/, app/code/, dev/)
2. Check all overridden methods
3. Verify method signatures
4. Propose compatible overrides

---

## 🛠️ Universal Search Principles

### Essential Search Principles
**AI tools should search for:**
- **Class definitions** across all possible locations where Magento classes exist
- **Method signatures** across all possible locations where Magento classes exist
- **Interface definitions** across all possible locations where Magento classes exist
- **Specific modules** across all possible locations where Magento classes exist

### File Reading Principles
**AI tools should be able to:**
- **Read specific files** to examine class implementations
- **Read specific lines** to focus on relevant code sections
- **Find methods within files** to locate specific functionality

### Advanced Search Principles
**AI tools should search for:**
- **Methods with specific parameter types** across all possible locations
- **Methods with array parameters** across all possible locations
- **Methods with return types** across all possible locations

---

## 📝 Documentation Standards

When proposing fixes, always include:

1. **Reference code location**: `vendor/magento/module-name/path/to/file.php:line` (or `app/code/Vendor/Module/...`)
2. **Original method signature**: Exact signature from reference
3. **Proposed fix**: Code that matches reference exactly
4. **Explanation**: Why the fix is needed and how it matches reference

### Example Documentation Format
```php
/**
 * Fix: Plugin method signature mismatch
 * 
 * Reference: vendor/magento/module-sales-rule/Model/RulesApplier.php:110 (or app/code/Vendor/Module/...)
 * Original: public function applyRules($item, $rules, $skipValidation, array $couponCodes = [])
 * 
 * Issue: Plugin method missing optional parameter
 * Solution: Add missing parameter to match reference exactly
 */

public function beforeApplyRules(
    RulesApplier $subject,
    $item,
    $rules,
    $skipValidation,
    array $couponCodes = []  // ✅ Added missing parameter
): array {
    // Implementation
}
```

---

## 🔍 Advanced Search Principles

### Finding Related Classes
**AI tools should search for:**
- **Classes that extend a specific class** across all possible locations
- **Classes that implement an interface** across all possible locations
- **Classes in specific namespaces** across all possible locations

### Finding Configuration
**AI tools should search for:**
- **DI configuration files** across all possible locations
- **Event observer configurations** across all possible locations
- **API endpoint configurations** across all possible locations

### Finding Dependencies
**AI tools should search for:**
- **Where a class is used** across all possible locations
- **Method calls** across all possible locations
- **Static method calls** across all possible locations

---

## 🎯 Specific Module Principles

### Sales Module Principles
**AI tools should search for:**
- **Sales-related classes** across all possible locations
- **Order processing methods** across all possible locations
- **Invoice methods** across all possible locations

### Catalog Module Principles
**AI tools should search for:**
- **Product-related classes** across all possible locations
- **Category methods** across all possible locations
- **Attribute methods** across all possible locations

### Customer Module Principles
**AI tools should search for:**
- **Customer-related classes** across all possible locations
- **Address methods** across all possible locations
- **Group methods** across all possible locations

---

## ✅ Quality Assurance

### Before Proposing Any Fix
- [ ] **Reference code verified** in all possible locations (vendor/magento/, app/code/, dev/)
- [ ] **Method signature matches** exactly
- [ ] **Parameter types confirmed** correct
- [ ] **Return types verified** match
- [ ] **Namespace checked** for accuracy
- [ ] **Inheritance chain** understood
- [ ] **Interface compliance** confirmed

### Common Validation Principles
**AI tools should verify:**
- **Class exists** across all possible locations where Magento classes exist
- **Method exists** across all possible locations where Magento classes exist
- **Interface exists** across all possible locations where Magento classes exist

---

## 🚫 Troubleshooting

### When Reference Code Can't Be Found
1. **Check module name** - ensure correct module path
2. **Verify class name** - check for typos or case sensitivity
3. **Search broader** - try partial matches
4. **Check version** - ensure Magento version compatibility
5. **Look in framework** - some classes are in framework module

### Common Issues
- **Module not installed** - check if module exists in vendor/, app/code/, or dev/
- **Wrong namespace** - verify namespace structure
- **Method renamed** - check for method name changes between versions
- **Interface changed** - verify interface compatibility

---

## 🔗 Related Files

- **[`patterns_overview.md`](./patterns_overview.md)** - Core Approach and Scenarios
- **[`terminology.md`](./terminology.md)** - Magento terms and concepts
- **[`scope_and_structure.md`](./scope_and_structure.md)** - Project structure and work scope

---

**Remember**: When in doubt, check the reference code in all possible locations (`vendor/magento/`, `app/code/`, `dev/`) before making any assumptions or proposals. 