# 🏗️ Magento Scope and Structure Guide

## 🎯 Purpose
This file defines the scope of work for AI tools in Magento projects, including where to add code, where to fix bugs, and which areas are strictly for reference only.

---

## 📂 Magento Project Structure Overview

### Root Directory Structure
```
magento-project/
├── app/                    # APPLICATION CODE (AI TOOLS WORK HERE)
├── bin/                    # CLI tools (reference only)
├── dev/                    # Development tools (reference only)
├── generated/              # Generated code (reference only)
├── lib/                    # Magento library (reference only)
├── pub/                    # Web root (reference only)
├── setup/                  # Installation scripts (reference only)
├── var/                    # Runtime data (reference only)
├── vendor/                 # THIRD-PARTY CODE (REFERENCE ONLY - NEVER MODIFY)
├── composer.json           # Dependencies (reference only)
├── composer.lock           # Lock file (reference only)
└── .env                    # Environment config (reference only)
```

---

## ✅ AI TOOLS WORK AREAS

### 🎯 Primary Work Area: `/app/` Directory

**This is where AI tools should add code, fix bugs, and make modifications.**

#### `/app/code/` - Custom Module Development
```
app/code/
├── Vendor/                 # Your company namespace
│   └── ModuleName/         # Your custom module
│       ├── etc/            # Configuration files
│       ├── Model/          # Business logic classes
│       ├── Block/          # View logic classes
│       ├── Controller/     # Request handling
│       ├── view/           # Frontend files
│       ├── Api/            # API interfaces
│       ├── Setup/          # Database schema
│       └── Console/        # CLI commands
```

**AI Tools Should:**
- ✅ Create new modules in `app/code/Vendor/ModuleName/`
- ✅ Modify existing custom modules
- ✅ Add new functionality to custom modules
- ✅ Fix bugs in custom modules
- ✅ Update configuration files (di.xml, module.xml, etc.)

#### `/app/design/` - Theme Customization
```
app/design/
├── frontend/               # Store frontend themes
│   ├── Package/            # Theme package
│   │   └── theme/          # Theme name
│   │       ├── etc/        # Theme configuration
│   │       ├── web/        # Static files (CSS, JS, images)
│   │       ├── layout/     # Layout XML files
│   │       └── templates/  # PHTML template files
└── adminhtml/              # Admin themes
    └── Package/
        └── theme/
```

**AI Tools Should:**
- ✅ Create custom themes
- ✅ Modify theme templates and layouts
- ✅ Add custom CSS/JavaScript
- ✅ Override existing theme files
- ✅ Fix frontend display issues

#### `/app/etc/` - Application Configuration
```
app/etc/
├── config.php              # Application configuration
├── env.php                 # Environment configuration
├── di.xml                  # Global dependency injection
└── modules.php             # Module list
```

**AI Tools Should:**
- ✅ Modify `di.xml` for global DI configuration
- ✅ Update application configuration as needed
- ⚠️ **Be careful** with `env.php` and `config.php`

---

## 🚫 REFERENCE ONLY AREAS (NEVER MODIFY)

### `/vendor/` Directory - THIRD-PARTY CODE
**⚠️ CRITICAL: AI TOOLS MUST NEVER MODIFY ANYTHING IN THE VENDOR FOLDER**

```
vendor/
├── magento/                # Magento core modules
├── third-party/            # Third-party packages
├── autoload.php            # Composer autoloader
└── composer/               # Composer files
```

**AI Tools Should:**
- ✅ **READ** vendor code for reference and understanding
- ✅ **STUDY** Magento core patterns and implementations
- ✅ **LEARN** from existing code structure
- ❌ **NEVER** modify any files in vendor/
- ❌ **NEVER** add code to vendor/
- ❌ **NEVER** delete files from vendor/

**Why Vendor is Off-Limits:**
- **Composer managed** - Changes will be overwritten on updates
- **Core functionality** - Modifying breaks upgrade compatibility
- **Best practice** - Use proper override mechanisms instead

### Other Reference-Only Areas
- **`/bin/`** - CLI tools (read for understanding, don't modify)
- **`/lib/`** - Magento library (reference only)
- **`/generated/`** - Generated code (regenerated automatically)
- **`/pub/`** - Web root (reference only)
- **`/setup/`** - Installation scripts (reference only)

---

## 🔧 Proper Override Mechanisms

### Instead of Modifying Vendor Code, Use:

#### 1. **Plugins** (Preferred Method)
```php
// app/code/Vendor/Module/etc/di.xml
<type name="Magento\Catalog\Model\Product">
    <plugin name="vendor_module_product_plugin" type="Vendor\Module\Plugin\ProductPlugin" />
</type>
```

#### 2. **Preferences** (Complete Class Replacement)
```php
// app/code/Vendor/Module/etc/di.xml
<preference for="Magento\Catalog\Model\Product" type="Vendor\Module\Model\Product" />
```

#### 3. **Observers** (Event-Driven Modifications)
```php
// app/code/Vendor/Module/etc/events.xml
<event name="catalog_product_save_after">
    <observer name="vendor_module_product_save" instance="Vendor\Module\Observer\ProductSave" />
</event>
```

#### 4. **Theme Overrides** (Frontend Modifications)
```
app/design/frontend/Package/theme/Magento_Catalog/templates/product/view.phtml
```

---

## 🎯 AI Tool Workflow for Code Changes

### Step 1: Identify the Target
1. **Determine if it's core functionality** (vendor/) or custom code (app/)
2. **Check if a custom module already exists** for the functionality
3. **Identify the proper override mechanism** to use

### Step 2: Choose Implementation Method
- **New functionality** → Create custom module in `app/code/`
- **Modify existing behavior** → Use plugins, preferences, or observers
- **Frontend changes** → Use theme overrides in `app/design/`
- **Configuration changes** → Modify `app/etc/` files

### Step 3: Follow Magento Patterns
1. **Study vendor code** for reference (but don't modify)
2. **Follow the same patterns** in your custom code
3. **Use proper namespacing** (`Vendor\Module\...`)
4. **Follow Magento coding standards**

---

## 📋 Scope Checklist for AI Tools

### Before Making Any Changes:
- [ ] **Is the target in `app/` directory?** (Safe to modify)
- [ ] **Is the target in `vendor/` directory?** (Reference only - use overrides)
- [ ] **Do I need to create a custom module?** (For new functionality)
- [ ] **Do I need to use plugins/preferences?** (For modifying existing behavior)
- [ ] **Am I following Magento patterns?** (Study vendor code for reference)

### When Working with Code:
- [ ] **I'm only modifying files in `app/` directory**
- [ ] **I'm using proper override mechanisms** (not direct vendor modifications)
- [ ] **I'm following Magento coding standards**
- [ ] **I'm using proper namespacing**
- [ ] **I'm not breaking upgrade compatibility**

---

## 🚨 Critical Rules for AI Tools

### ✅ DO:
- **Work in `app/` directory** for all custom code
- **Study vendor code** for reference and patterns
- **Use proper override mechanisms** (plugins, preferences, observers)
- **Follow Magento coding standards**
- **Create custom modules** for new functionality
- **Use theme overrides** for frontend changes

### ❌ DON'T:
- **Modify any files in `vendor/` directory**
- **Add code directly to vendor modules**
- **Delete files from vendor directory**
- **Copy vendor files to app directory**
- **Ignore Magento patterns and standards**
- **Break upgrade compatibility**

---

## 🔗 Related Resources

- **[`design_patterns.md`](./design_patterns.md)** - Systematic development approach
- **[`terminology.md`](./terminology.md)** - Magento terms and concepts
- **Magento Developer Documentation** - Official development guides
- **Magento Coding Standards** - Code quality guidelines 