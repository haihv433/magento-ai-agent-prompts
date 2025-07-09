# 🏷️ AI Agent Guide: Magento Entity Attribute Patterns

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains essential patterns for working with Magento entity attributes (order, product, customer, etc.). AI tools MUST understand these patterns before attempting any attribute-related fixes or modifications.**

---

## 📋 Purpose
This file provides comprehensive patterns and examples for AI tools to understand how Magento handles entity attributes. This includes getting, setting, and managing attributes on entities like orders, products, customers, and other Magento entities.

---

## 🎯 Core Entity Attribute Patterns

### **Pattern 1: Direct Attribute Access**
**Magento entities allow direct access to attributes using getter/setter methods:**

```php
// Getting attributes
$order->getData('time_to_date');           // Direct data access
$order->getTimeToDate();                   // Magic getter method
$order->getAttribute('time_to_date');      // Attribute object access

// Setting attributes
$order->setData('time_to_date', $value);   // Direct data setting
$order->setTimeToDate($value);             // Magic setter method
$order->setAttribute('time_to_date', $value); // Attribute object setting
```

### **Pattern 2: Custom Attributes Access**
**For custom attributes that don't have magic methods:**

```php
// Getting custom attributes
$order->getCustomAttribute('time_to_date');           // Custom attribute object
$order->getCustomAttribute('time_to_date')->getValue(); // Custom attribute value

// Setting custom attributes
$order->setCustomAttribute('time_to_date', $attributeValue);
```

### **Pattern 3: Extension Attributes Access**
**For extension attributes (newer Magento versions):**

```php
// Getting extension attributes
$extensionAttributes = $order->getExtensionAttributes();
$timeToDate = $extensionAttributes->getTimeToDate();

// Setting extension attributes
$extensionAttributes = $order->getExtensionAttributes();
$extensionAttributes->setTimeToDate($value);
$order->setExtensionAttributes($extensionAttributes);
```

---

## 🔍 Entity Attribute Search Patterns

### **For Order Attributes**
**AI tools should search for:**
- **Order attribute definitions** across all possible locations
- **Order placement observers** that handle attributes
- **Order save plugins** that modify attributes
- **Order attribute configuration** in database and XML

### **For Product Attributes**
**AI tools should search for:**
- **Product attribute definitions** across all possible locations
- **Product save observers** that handle attributes
- **Product attribute sets** and configurations
- **Product attribute frontend/backend models**

### **For Customer Attributes**
**AI tools should search for:**
- **Customer attribute definitions** across all possible locations
- **Customer registration/login observers**
- **Customer attribute forms** and validation
- **Customer attribute display configurations**

---

## 🛠️ Common Attribute Scenarios

### **Scenario 1: Missing Attribute After Save**
**Problem**: Attribute value disappears after entity save

**Common Causes**:
- Attribute not properly configured in database
- Missing observer/plugin for attribute handling
- Incorrect attribute scope or backend model
- Attribute not included in save process

**Search Patterns**:
- Look for attribute configuration in `eav_attribute` table
- Check for observers listening to entity save events
- Verify attribute is assigned to correct entity type
- Check for plugins intercepting save methods

### **Scenario 2: Attribute Not Loading**
**Problem**: Attribute exists but doesn't load properly

**Common Causes**:
- Incorrect attribute access method
- Missing attribute in collection/load process
- Frontend/backend model issues
- Cache problems

**Search Patterns**:
- Check how attribute is accessed in code
- Look for collection loading configurations
- Verify frontend/backend model implementations
- Check cache configuration and clearing

### **Scenario 3: Custom Attribute Creation**
**Problem**: Need to add new custom attribute

**Common Patterns**:
- Use setup scripts to create attributes
- Configure attribute properties (type, scope, etc.)
- Assign attribute to attribute sets
- Create observers for attribute handling

**Search Patterns**:
- Look for existing attribute creation patterns
- Check setup script examples
- Find attribute configuration XML examples
- Look for observer patterns for new attributes

---

## 📝 Attribute Access Examples

### **Order Attribute Examples**
```php
// Getting order attributes
$order = $this->orderRepository->get($orderId);
$timeToDate = $order->getData('time_to_date');
$timeToDate = $order->getTimeToDate(); // If magic method exists

// Setting order attributes
$order->setData('time_to_date', date('Y-m-d H:i:s'));
$order->setTimeToDate(date('Y-m-d H:i:s')); // If magic method exists

// Custom attributes
$customAttribute = $order->getCustomAttribute('time_to_date');
if ($customAttribute) {
    $value = $customAttribute->getValue();
}

// Extension attributes
$extensionAttributes = $order->getExtensionAttributes();
$timeToDate = $extensionAttributes->getTimeToDate();
```

### **Product Attribute Examples**
```php
// Getting product attributes
$product = $this->productRepository->get($sku);
$color = $product->getData('color');
$color = $product->getColor(); // If magic method exists

// Setting product attributes
$product->setData('color', 'red');
$product->setColor('red'); // If magic method exists

// Custom attributes
$customAttribute = $product->getCustomAttribute('custom_field');
if ($customAttribute) {
    $value = $customAttribute->getValue();
}
```

### **Customer Attribute Examples**
```php
// Getting customer attributes
$customer = $this->customerRepository->get($email);
$phone = $customer->getData('phone');
$phone = $customer->getPhone(); // If magic method exists

// Setting customer attributes
$customer->setData('phone', '123-456-7890');
$customer->setPhone('123-456-7890'); // If magic method exists

// Custom attributes
$customAttribute = $customer->getCustomAttribute('preferences');
if ($customAttribute) {
    $value = $customAttribute->getValue();
}
```

---

## 🔧 Attribute Debugging Patterns

### **Check Attribute Configuration**
```php
// Check if attribute exists
$attribute = $this->eavConfig->getAttribute('order', 'time_to_date');
if ($attribute && $attribute->getId()) {
    // Attribute exists
    $attributeCode = $attribute->getAttributeCode();
    $backendType = $attribute->getBackendType();
    $frontendType = $attribute->getFrontendType();
}
```

### **Check Attribute Value**
```php
// Debug attribute value
$order = $this->orderRepository->get($orderId);
$timeToDate = $order->getData('time_to_date');
var_dump($timeToDate);

// Check custom attributes
$customAttributes = $order->getCustomAttributes();
foreach ($customAttributes as $attribute) {
    echo $attribute->getAttributeCode() . ': ' . $attribute->getValue() . "\n";
}
```

### **Check Extension Attributes**
```php
// Debug extension attributes
$extensionAttributes = $order->getExtensionAttributes();
if ($extensionAttributes) {
    $timeToDate = $extensionAttributes->getTimeToDate();
    var_dump($timeToDate);
}
```

---

## ✅ Validation Checklist

**Before proposing any attribute-related fix, verify:**

- [ ] **Attribute exists** in database configuration
- [ ] **Attribute is assigned** to correct entity type
- [ ] **Access method is correct** (getData, magic method, custom, extension)
- [ ] **Attribute scope is appropriate** (global, website, store)
- [ ] **Backend model is correct** for attribute type
- [ ] **Frontend model is configured** if needed
- [ ] **Observers/plugins are in place** for attribute handling
- [ ] **Cache is cleared** after attribute changes

---

## 🚫 Common Mistakes to Avoid

### **Attribute Access Mistakes**
- ❌ **Using wrong access method** for attribute type
- ❌ **Not checking if attribute exists** before accessing
- ❌ **Ignoring attribute scope** (global vs website vs store)
- ❌ **Forgetting to save entity** after setting attributes

### **Attribute Configuration Mistakes**
- ❌ **Not configuring backend model** for custom attribute types
- ❌ **Missing attribute assignment** to entity type
- ❌ **Incorrect attribute scope** for intended use
- ❌ **Not handling custom attributes** properly

### **Attribute Debugging Mistakes**
- ❌ **Not checking database configuration** first
- ❌ **Ignoring cache issues** when attributes don't load
- ❌ **Not verifying attribute assignment** to entity
- ❌ **Missing observer/plugin** for attribute handling

---

## 🔗 Related Files

- **[`patterns_overview.md`](./patterns_overview.md)** - Core approach and scenarios
- **[`patterns_implementation.md`](./patterns_implementation.md)** - Implementation workflows
- **[`terminology_core.md`](./terminology_core.md)** - Core Magento terminology
- **[`terminology_advanced.md`](./terminology_advanced.md)** - Advanced Magento concepts

---

**Remember**: Always check the attribute configuration and access method before assuming the attribute is missing or broken! 