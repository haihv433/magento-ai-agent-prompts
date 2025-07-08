# 📚 Magento Core Terminology Guide

## 🎯 Purpose
This file defines core Magento-specific terms, entities, and developer language to ensure AI tools understand user requests accurately.

---

## 🏗️ Core Magento Concepts

### Module System
- **Module** - Self-contained unit of functionality (e.g., `Vendor_ModuleName`)
- **Extension** - Third-party module that extends Magento functionality
- **Plugin** - Magento's way to modify existing functionality without changing core files
- **Observer** - Event-driven way to hook into Magento processes
- **Preference** - Complete replacement of a class with custom implementation
- **Virtual Type** - Dependency injection configuration for shared instances

### Architecture Terms
- **Service Layer** - Business logic layer between controllers and models
- **Repository Pattern** - Data access abstraction layer
- **Entity** - Database table representation (e.g., Product, Customer, Order)
- **Model** - Data model representing business entities
- **Resource Model** - Database interaction layer
- **Collection** - Query builder for retrieving multiple entities
- **Block** - View logic component in MVC pattern
- **Layout** - XML configuration defining page structure
- **Template** - PHTML files containing HTML and PHP for rendering
- **Area** - Application context (frontend, adminhtml, webapi_rest, etc.)
- **Store** - E-commerce store instance
- **Website** - Group of stores sharing same domain
- **Store View** - Store frontend with specific language/currency
- **Admin** - Backend administration interface
- **Frontend** - Customer-facing store interface

---

## 🛍️ E-commerce Specific Terms

### Product System
- **Simple Product** - Basic product with single SKU
- **Configurable Product** - Product with multiple options (size, color, etc.)
- **Bundle Product** - Product composed of multiple simple products
- **Grouped Product** - Collection of simple products sold together
- **Virtual Product** - Non-physical product (downloadable, service)
- **Downloadable Product** - Digital product with downloadable files
- **SKU** - Stock Keeping Unit (unique product identifier)
- **Attribute Set** - Group of attributes for products
- **Attribute** - Product characteristic (color, size, weight, etc.)
- **Category** - Product classification hierarchy
- **Stock Item** - Inventory management for products
- **Inventory** - Stock quantity and availability
- **Stock Status** - Product availability (in stock, out of stock)
- **Price** - Product pricing (regular, special, tier, group)
- **Tier Price** - Quantity-based pricing discounts
- **Group Price** - Customer group-specific pricing
- **Special Price** - Temporary promotional pricing
- **Cost** - Product cost for profit calculations

### Order System
- **Order** - Customer purchase record
- **Invoice** - Payment record for an order
- **Shipment** - Shipping record for an order
- **Credit Memo** - Refund record for an order
- **Quote** - Shopping cart before checkout
- **Checkout** - Purchase completion process
- **Payment Method** - Way to pay (credit card, PayPal, etc.)
- **Shipping Method** - Way to deliver (FedEx, UPS, etc.)
- **Tax Class** - Tax category for products/customers
- **Order Status** - Current state of order (pending, processing, complete, etc.)
- **Order State** - Internal order workflow state
- **Customer** - Registered user account
- **Customer Group** - Customer classification for pricing/permissions
- **Guest Checkout** - Purchase without account registration
- **Billing Address** - Payment address
- **Shipping Address** - Delivery address
- **Subtotal** - Order total before tax/shipping
- **Grand Total** - Final order total including all charges

---

## 🔧 Development Terms

### Code Organization
- **Namespace** - PHP namespace (e.g., `Vendor\Module\Model`)
- **Class** - PHP class definition
- **Interface** - PHP interface definition
- **Trait** - PHP trait for code reuse
- **Dependency Injection** - Magento's way of managing object dependencies
- **Factory** - Class that creates instances of other classes
- **Proxy** - Lazy-loaded class wrapper
- **Interceptor** - Generated class that wraps original class with plugins
- **Virtual Type** - DI configuration for shared instances
- **Preference** - Complete class replacement in DI
- **Plugin** - Method interception for modifying behavior
- **Observer** - Event-driven code execution
- **Event** - System notification for specific actions
- **Cron Job** - Scheduled task execution
- **Command** - CLI command implementation

### File Structure
- **etc/** - Configuration files (module.xml, di.xml, etc.)
- **Model/** - Business logic classes
- **Block/** - View logic classes
- **Controller/** - Request handling classes
- **view/** - Frontend files (templates, layouts, static files)
- **Api/** - API interfaces and implementations
- **Setup/** - Database schema and data patches
- **Console/** - CLI command implementations
- **Helper/** - Utility classes for common functionality
- **Observer/** - Event observer classes
- **Plugin/** - Plugin classes (though usually in Model/Block/Controller)
- **ResourceModel/** - Database interaction classes
- **Ui/** - UI component classes
- **view/adminhtml/** - Admin interface files
- **view/frontend/** - Store frontend files
- **view/base/** - Base theme files

### Configuration
- **di.xml** - Dependency injection configuration
- **module.xml** - Module declaration and dependencies
- **registration.php** - Module registration file
- **routes.xml** - URL routing configuration
- **events.xml** - Event observer configuration
- **crontab.xml** - Scheduled task configuration
- **webapi.xml** - REST API configuration
- **system.xml** - Admin configuration fields
- **default.xml** - Default configuration values
- **scope** - Configuration level (default, websites, stores, store views)
- **scope code** - Unique identifier for website/store/store view
- **scope id** - Numeric identifier for scope level
- **config.xml** - Legacy configuration file (M1)
- **local.xml** - Local environment configuration
- **env.php** - Environment-specific configuration

---

## 📝 Common Abbreviations

- **M2** - Magento 2
- **M1** - Magento 1
- **CE** - Community Edition
- **EE** - Enterprise Edition
- **B2B** - Business-to-Business
- **B2C** - Business-to-Consumer
- **CMS** - Content Management System
- **CRUD** - Create, Read, Update, Delete
- **MVC** - Model-View-Controller
- **ORM** - Object-Relational Mapping
- **ACL** - Access Control List
- **API** - Application Programming Interface
- **CLI** - Command Line Interface
- **CRON** - Scheduled task execution
- **DI** - Dependency Injection
- **EEA** - Enterprise Edition Advanced
- **EES** - Enterprise Edition Starter
- **PWA** - Progressive Web Application

---

## 🔗 Related Files

- **[`terminology_advanced.md`](./terminology_advanced.md)** - Advanced Terms and Usage Guidelines
- **[`patterns_overview.md`](./patterns_overview.md)** - Core approach and scenarios
- **[`scope_and_structure.md`](./scope_and_structure.md)** - Project structure and work scope 