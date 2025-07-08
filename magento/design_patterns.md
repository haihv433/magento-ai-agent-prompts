# AI Agent Guide: Magento Reference Code Checking Protocol

## Purpose
This guide is for AI agents to systematically check reference code in `vendor/magento/` before proposing any fixes or modifications to Magento modules. This ensures compatibility and prevents breaking changes.

## Core Principle
**ALWAYS check the reference code first before making any assumptions about method signatures, class structures, or behavior.**

## Systematic Approach

### Step 1: Identify the Target Class/Method
When a user reports an issue or requests a fix:

1. **Locate the target class** in the user's module
2. **Identify the specific method** that needs modification
3. **Note the namespace** and class name

### Step 2: Find Reference Code in vendor/magento/
Use these search patterns:

```bash
# Search for the exact class in vendor/magento/
find vendor/magento/ -name "*.php" -exec grep -l "class.*TargetClassName" {} \;

# Search for method signatures
grep -r "public function.*methodName" vendor/magento/module-* --include="*.php"

# Search for interface definitions
find vendor/magento/ -name "*.php" -exec grep -l "interface.*InterfaceName" {} \;
```

### Step 3: Analyze Reference Code
For each found reference:

1. **Read the complete method signature**
2. **Check parameter types and names**
3. **Verify return types**
4. **Read PHPDoc comments**
5. **Understand the method's purpose**

### Step 4: Compare with User's Code
Compare the reference code with the user's implementation:

- **Parameter types match?**
- **Return types match?**
- **Method signature identical?**
- **Any missing parameters?**

### Step 5: Propose Compatible Fix
Based on the reference code analysis:

1. **Use exact parameter types** from reference
2. **Match return types** exactly
3. **Follow the same patterns** as Magento core
4. **Document why** the fix is needed

## Common Scenarios and Workflows

### Scenario 1: Plugin Compatibility Issues

**Problem**: Plugin method signature doesn't match target method

**Workflow**:
1. Find the target class in `vendor/magento/`
2. Read the actual method signature
3. Update plugin to match exactly

**Example**:
```bash
# Find the actual method in vendor
grep -r "public function applyRules" vendor/magento/module-sales-rule/ --include="*.php"
```

**Reference Code**:
```php
// vendor/magento/module-sales-rule/Model/RulesApplier.php
public function applyRules($item, $rules, $skipValidation, array $couponCodes = [])
```

**Correct Plugin**:
```php
public function beforeApplyRules(
    RulesApplier $subject,
    $item,                    // ✅ Match reference exactly
    $rules,                   // ✅ Match reference exactly  
    $skipValidation,          // ✅ Match reference exactly
    array $couponCodes = []   // ✅ Match reference exactly
): array {
    // Implementation
}
```

### Scenario 2: Interface Compatibility

**Problem**: Interface method signature mismatch

**Workflow**:
1. Find the interface in `vendor/magento/`
2. Check the exact method signature
3. Update implementation to match

**Example**:
```bash
# Find interface definition
find vendor/magento/ -name "*.php" -exec grep -l "interface.*RepositoryInterface" {} \;
```

### Scenario 3: Class Extension Issues

**Problem**: Extended class has different method signatures

**Workflow**:
1. Find the parent class in `vendor/magento/`
2. Check all overridden methods
3. Ensure compatibility

**Example**:
```bash
# Find parent class
find vendor/magento/ -name "*.php" -exec grep -l "class.*ParentClassName" {} \;
```

## Reference Code Search Patterns

### For Classes
```bash
# Find class definition
grep -r "class.*ClassName" vendor/magento/module-* --include="*.php"

# Find class with namespace
grep -r "namespace.*ModuleName" vendor/magento/module-* --include="*.php" | grep "class.*ClassName"
```

### For Methods
```bash
# Find method signature
grep -r "public function.*methodName" vendor/magento/module-* --include="*.php"

# Find method with parameters
grep -r "public function.*methodName.*(" vendor/magento/module-* --include="*.php"
```

### For Interfaces
```bash
# Find interface definition
grep -r "interface.*InterfaceName" vendor/magento/module-* --include="*.php"

# Find interface methods
grep -r "function.*methodName" vendor/magento/module-* --include="*.php" | grep "interface"
```

## Common Magento Module Locations

### Core Modules
- **Sales**: `vendor/magento/module-sales/`
- **Catalog**: `vendor/magento/module-catalog/`
- **Customer**: `vendor/magento/module-customer/`
- **Checkout**: `vendor/magento/module-checkout/`
- **Framework**: `vendor/magento/framework/`

### Module Structure
```
vendor/magento/module-name/
├── Api/                    # Interfaces
├── Model/                  # Models
├── Block/                  # Blocks
├── Controller/             # Controllers
├── etc/                    # Configuration
│   ├── di.xml             # Dependency injection
│   ├── events.xml         # Event observers
│   └── webapi.xml         # API endpoints
└── view/                   # Frontend files
```

## Validation Checklist

Before proposing any fix, verify:

- [ ] **Reference code found** in vendor/magento/
- [ ] **Method signature matches** exactly
- [ ] **Parameter types are correct**
- [ ] **Return types match**
- [ ] **Namespace is correct**
- [ ] **Class inheritance is proper**
- [ ] **Interface implementation is complete**

## Error Prevention

### Common Mistakes to Avoid

1. **Assuming method signatures** without checking reference
2. **Using wrong parameter types** (e.g., `string` vs `mixed`)
3. **Missing optional parameters** in method calls
4. **Wrong return types** in implementations
5. **Incorrect namespace** references

### Red Flags

- Method signature doesn't match any found in vendor/magento/
- Parameter types don't align with reference code
- Missing required parameters
- Wrong interface implementation

## Example Workflows

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

## Tools and Commands

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

## Documentation Standards

When proposing fixes, always include:

1. **Reference code location**: `vendor/magento/module-name/path/to/file.php:line`
2. **Original method signature**: Exact signature from reference
3. **Proposed fix**: Code that matches reference exactly
4. **Explanation**: Why the fix is needed and how it matches reference

## Conclusion

This systematic approach ensures that all proposed fixes are compatible with Magento's core code. Always check the reference first, then propose solutions that match exactly.

**Remember**: When in doubt, check the reference code in `vendor/magento/` before making any assumptions or proposals. 