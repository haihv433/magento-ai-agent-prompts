# 📚 Magento Terminology Guide

## 🎯 Purpose
This file defines Magento-specific terms, entities, and developer language to ensure AI tools understand user requests accurately.

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

## 🎨 Frontend Terms

### Theme System
- **Theme** - Visual appearance package
- **Area** - Application area (frontend, adminhtml, webapi_rest, etc.)
- **Package** - Theme package name
- **Template** - PHTML file for rendering HTML
- **Layout** - XML file defining page structure
- **Block** - PHP class handling view logic
- **Widget** - Reusable UI component
- **Static Files** - CSS, JS, images, fonts
- **Less** - CSS preprocessor used by Magento
- **Sass** - Alternative CSS preprocessor
- **Responsive Design** - Mobile-friendly layout
- **Fallback** - Theme inheritance system
- **Parent Theme** - Base theme for inheritance
- **Child Theme** - Theme that extends parent theme
- **Skin** - Legacy theme system (M1)
- **Package** - Theme package directory

### UI Components
- **UI Component** - JavaScript-based UI element
- **Data Provider** - Data source for UI components
- **Form** - Input form with validation
- **Grid** - Data table with sorting/filtering
- **Listing** - Data display component
- **Modal** - Popup dialog component
- **Button** - Action button component
- **Column** - Grid column definition
- **Filter** - Data filtering component
- **Pagination** - Page navigation component
- **Toolbar** - Grid action toolbar
- **Mass Actions** - Bulk operations on grid items
- **Inline Editing** - Direct cell editing in grids
- **Export** - Data export functionality

---

## 🔌 Integration Terms

### API
- **REST API** - HTTP-based API for external integrations
- **SOAP API** - Legacy XML-based API
- **GraphQL** - Modern query language for APIs
- **Webhook** - Event-driven API notifications
- **OAuth** - Authentication for API access
- **Integration** - Third-party system connection

### External Services
- **Payment Gateway** - Payment processing service
- **Shipping Carrier** - Shipping calculation service
- **Tax Service** - Tax calculation service
- **Email Service** - Email delivery service
- **CDN** - Content Delivery Network
- **Cache** - Performance optimization storage
- **Session** - User session storage
- **Cookie** - Browser-based data storage
- **Queue** - Asynchronous task processing
- **Message Queue** - Inter-process communication
- **Cron** - Scheduled task execution
- **Index** - Database optimization for performance
- **Reindex** - Rebuild search/catalog indexes
- **Compile** - Code compilation for performance
- **Deploy** - Static content deployment

---

## 🛠️ Common Developer Requests

### Module Development
- "Create a new module" - Build new functionality
- "Add a custom attribute" - Extend product/customer data
- "Create a custom API" - Build REST/SOAP endpoints
- "Add a custom admin grid" - Create admin data table
- "Create a custom form" - Build input forms
- "Add custom validation" - Implement business rules

### Troubleshooting
- "Fix module compatibility" - Resolve version conflicts
- "Debug performance issues" - Optimize slow operations
- "Fix cache issues" - Resolve caching problems
- "Resolve dependency conflicts" - Fix module conflicts
- "Fix layout issues" - Resolve frontend display problems

### Customization
- "Override core functionality" - Modify existing features
- "Customize checkout process" - Modify purchase flow
- "Add custom payment method" - Integrate new payment option
- "Customize email templates" - Modify notification emails
- "Add custom shipping method" - Integrate new delivery option

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

## 🎯 Usage Guidelines

### For AI Tools
1. **Reference this file** when users mention Magento terms
2. **Ask for clarification** if terms are ambiguous
3. **Use correct terminology** in responses
4. **Understand context** - same term may mean different things in different contexts
5. **Stay updated** - Magento terminology evolves with versions

### For Users
1. **Be specific** about which Magento version you're using
2. **Provide context** when using technical terms
3. **Use standard terminology** from this guide
4. **Clarify abbreviations** if they might be ambiguous

---

## 📚 Additional Resources

- [Magento 2 Developer Documentation](https://developer.adobe.com/commerce/docs/)
- [Magento 2 Architecture Guide](https://developer.adobe.com/commerce/php/architecture/)
- [Magento 2 Module Development](https://developer.adobe.com/commerce/php/module-development/)
- [Magento 2 Frontend Development](https://developer.adobe.com/commerce/frontend-core/guide/) 