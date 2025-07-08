# 🔧 AI Agent Guide: Magento Implementation Workflows and Tools

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains implementation workflows and tools for Magento reference code checking. For the core approach and scenarios, see [`patterns_overview.md`](./patterns_overview.md).**

---

## 📋 Purpose
This file provides detailed implementation workflows, tools, and examples for AI agents to effectively check and match Magento reference code. It includes practical commands, example workflows, and documentation standards.

---

## 🔄 Example Workflows

### Workflow 1: Fixing Plugin Parameter Mismatch

**User Issue**: "Plugin method signature doesn't match"

**AI Agent Steps**:
1. Find target class in vendor/magento/
2. Read actual method signature
3. Compare with user's plugin
4. Propose exact match fix

**Example**:
```bash
# Step 1: Find the method
grep -r "public function applyRules" vendor/magento/module-sales-rule/ --include="*.php"

# Step 2: Read the actual signature
# vendor/magento/module-sales-rule/Model/RulesApplier.php:110
public function applyRules($item, $rules, $skipValidation, array $couponCodes = [])

# Step 3: Fix plugin to match exactly
```

### Workflow 2: Interface Implementation

**User Issue**: "Interface method not implemented correctly"

**AI Agent Steps**:
1. Find interface in vendor/magento/
2. Read all required methods
3. Check implementation completeness
4. Propose missing methods

### Workflow 3: Class Extension

**User Issue**: "Extended class has compatibility issues"

**AI Agent Steps**:
1. Find parent class in vendor/magento/
2. Check all overridden methods
3. Verify method signatures
4. Propose compatible overrides

---

## 🛠️ Tools and Commands

### Essential Search Commands
```bash
# Find class definitions
find vendor/magento/ -name "*.php" -exec grep -l "class.*ClassName" {} \;

# Find method signatures
grep -r "public function.*methodName" vendor/magento/module-* --include="*.php"

# Find interface definitions
find vendor/magento/ -name "*.php" -exec grep -l "interface.*InterfaceName" {} \;

# Search in specific module
grep -r "searchTerm" vendor/magento/module-specific-name/ --include="*.php"
```

### File Reading Commands
```bash
# Read specific file
cat vendor/magento/module-name/Model/ClassName.php

# Read specific lines
sed -n '100,120p' vendor/magento/module-name/Model/ClassName.php

# Find method in file
grep -n "public function" vendor/magento/module-name/Model/ClassName.php
```

### Advanced Search Patterns
```bash
# Find methods with specific parameter types
grep -r "public function.*methodName.*string.*" vendor/magento/module-* --include="*.php"

# Find methods with array parameters
grep -r "public function.*methodName.*array.*" vendor/magento/module-* --include="*.php"

# Find methods with return types
grep -r "public function.*methodName.*:.*" vendor/magento/module-* --include="*.php"
```

---

## 📝 Documentation Standards

When proposing fixes, always include:

1. **Reference code location**: `vendor/magento/module-name/path/to/file.php:line`
2. **Original method signature**: Exact signature from reference
3. **Proposed fix**: Code that matches reference exactly
4. **Explanation**: Why the fix is needed and how it matches reference

### Example Documentation Format
```php
/**
 * Fix: Plugin method signature mismatch
 * 
 * Reference: vendor/magento/module-sales-rule/Model/RulesApplier.php:110
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

## 🔍 Advanced Search Techniques

### Finding Related Classes
```bash
# Find classes that extend a specific class
grep -r "extends.*ClassName" vendor/magento/module-* --include="*.php"

# Find classes that implement an interface
grep -r "implements.*InterfaceName" vendor/magento/module-* --include="*.php"

# Find classes in specific namespace
grep -r "namespace.*Magento\\ModuleName" vendor/magento/module-* --include="*.php"
```

### Finding Configuration
```bash
# Find DI configuration
find vendor/magento/ -name "di.xml" -exec grep -l "ClassName" {} \;

# Find event observers
find vendor/magento/ -name "events.xml" -exec grep -l "eventName" {} \;

# Find API endpoints
find vendor/magento/ -name "webapi.xml" -exec grep -l "serviceName" {} \;
```

### Finding Dependencies
```bash
# Find where a class is used
grep -r "use.*ClassName" vendor/magento/module-* --include="*.php"

# Find method calls
grep -r "->methodName(" vendor/magento/module-* --include="*.php"

# Find static method calls
grep -r "::methodName(" vendor/magento/module-* --include="*.php"
```

---

## 🎯 Specific Module Workflows

### Sales Module Workflows
```bash
# Find sales-related classes
find vendor/magento/module-sales/ -name "*.php" -exec grep -l "class.*Order" {} \;

# Find order processing methods
grep -r "public function.*Order" vendor/magento/module-sales/ --include="*.php"

# Find invoice methods
grep -r "public function.*Invoice" vendor/magento/module-sales/ --include="*.php"
```

### Catalog Module Workflows
```bash
# Find product-related classes
find vendor/magento/module-catalog/ -name "*.php" -exec grep -l "class.*Product" {} \;

# Find category methods
grep -r "public function.*Category" vendor/magento/module-catalog/ --include="*.php"

# Find attribute methods
grep -r "public function.*Attribute" vendor/magento/module-catalog/ --include="*.php"
```

### Customer Module Workflows
```bash
# Find customer-related classes
find vendor/magento/module-customer/ -name "*.php" -exec grep -l "class.*Customer" {} \;

# Find address methods
grep -r "public function.*Address" vendor/magento/module-customer/ --include="*.php"

# Find group methods
grep -r "public function.*Group" vendor/magento/module-customer/ --include="*.php"
```

---

## ✅ Quality Assurance

### Before Proposing Any Fix
- [ ] **Reference code verified** in vendor/magento/
- [ ] **Method signature matches** exactly
- [ ] **Parameter types confirmed** correct
- [ ] **Return types verified** match
- [ ] **Namespace checked** for accuracy
- [ ] **Inheritance chain** understood
- [ ] **Interface compliance** confirmed

### Common Validation Commands
```bash
# Verify class exists
find vendor/magento/ -name "*.php" -exec grep -l "class.*ExactClassName" {} \;

# Verify method exists
grep -r "public function.*exactMethodName" vendor/magento/module-* --include="*.php"

# Verify interface exists
find vendor/magento/ -name "*.php" -exec grep -l "interface.*ExactInterfaceName" {} \;
```

---

## 🚫 Troubleshooting

### When Reference Code Can't Be Found
1. **Check module name** - ensure correct module path
2. **Verify class name** - check for typos or case sensitivity
3. **Search broader** - try partial matches
4. **Check version** - ensure Magento version compatibility
5. **Look in framework** - some classes are in framework module

### Common Issues
- **Module not installed** - check if module exists in vendor/
- **Wrong namespace** - verify namespace structure
- **Method renamed** - check for method name changes between versions
- **Interface changed** - verify interface compatibility

---

## 🔗 Related Files

- **[`patterns_overview.md`](./patterns_overview.md)** - Core Approach and Scenarios
- **[`terminology.md`](./terminology.md)** - Magento terms and concepts
- **[`scope_and_structure.md`](./scope_and_structure.md)** - Project structure and work scope

---

**Remember**: When in doubt, check the reference code in `vendor/magento/` before making any assumptions or proposals. 