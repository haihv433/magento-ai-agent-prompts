# 🏗️ AI Agent Guide: Magento Reference Code Checking Protocol

## 🎯 Purpose
This guide is for AI agents to systematically check reference code in multiple locations (`vendor/magento/`, `app/code/`, `dev/`, etc.) before proposing any fixes or modifications to Magento modules. This ensures compatibility and prevents breaking changes.

## 🚨 Core Principle
**ALWAYS check the reference code first before making any assumptions about method signatures, class structures, or behavior.**

---

## 🔍 Systematic Approach

### Step 1: Identify the Target Class/Method
When a user reports an issue or requests a fix:

1. **Locate the target class** in the user's module
2. **Identify the specific method** that needs modification
3. **Note the namespace** and class name

### Step 2: Find Reference Code in Multiple Locations
Search for reference code in all possible locations where Magento classes can exist:

- **Core Magento modules**: `vendor/magento/`
- **Custom modules**: `app/code/`
- **Development modules**: `dev/`
- **Other possible locations**: Any directory containing Magento modules

**AI tools should use their preferred search methods** to locate the target class, method, or interface across these directories.

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

---

## 🔧 Common Scenarios and Workflows

### Scenario 1: Plugin Compatibility Issues

**Problem**: Plugin method signature doesn't match target method

**Workflow**:
1. Find the target class in all possible locations (`vendor/magento/`, `app/code/`, `dev/`)
2. Read the actual method signature
3. Update plugin to match exactly

**Example**:
**AI tools should search for the target method** across all possible locations where Magento classes exist.

**Reference Code**:
```php
// Found in: vendor/magento/module-sales-rule/Model/RulesApplier.php (or app/code/Vendor/Module/...)
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
1. Find the interface in all possible locations (`vendor/magento/`, `app/code/`, `dev/`)
2. Check the exact method signature
3. Update implementation to match

**Example**:
**AI tools should search for the interface definition** across all possible locations where Magento classes exist.

### Scenario 3: Class Extension Issues

**Problem**: Extended class has different method signatures

**Workflow**:
1. Find the parent class in all possible locations (`vendor/magento/`, `app/code/`, `dev/`)
2. Check all overridden methods
3. Ensure compatibility

**Example**:
**AI tools should search for the parent class** across all possible locations where Magento classes exist.

---

## 🔍 Reference Code Search Principles

### For Classes
**AI tools should search for class definitions** across all possible locations where Magento classes exist.

### For Methods
**AI tools should search for method signatures** across all possible locations where Magento classes exist.

### For Interfaces
**AI tools should search for interface definitions** across all possible locations where Magento classes exist.

---

## 📁 Common Magento Module Locations

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

---

## ✅ Validation Checklist

Before proposing any fix, verify:

- [ ] **Reference code found** in all possible locations (vendor/magento/, app/code/, dev/)
- [ ] **Method signature matches** exactly
- [ ] **Parameter types are correct**
- [ ] **Return types match**
- [ ] **Namespace is correct**
- [ ] **Class inheritance is proper**
- [ ] **Interface implementation is complete**

---

## 🚫 Error Prevention

### Common Mistakes to Avoid

1. **Assuming method signatures** without checking reference
2. **Using wrong parameter types** (e.g., `string` vs `mixed`)
3. **Missing optional parameters** in method calls
4. **Wrong return types** in implementations
5. **Incorrect namespace** references

### Red Flags

- Method signature doesn't match any found in all locations (vendor/magento/, app/code/, dev/)
- Parameter types don't align with reference code
- Missing required parameters
- Wrong interface implementation

---

## 🔗 Related Files

- **[`patterns_implementation.md`](./patterns_implementation.md)** - Implementation Workflows and Tools
- **[`terminology.md`](./terminology.md)** - Magento terms and concepts
- **[`scope_and_structure.md`](./scope_and_structure.md)** - Project structure and work scope 