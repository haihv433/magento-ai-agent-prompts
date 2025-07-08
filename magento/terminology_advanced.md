# 🎨 Magento Advanced Terminology Guide

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains advanced Magento terms and usage guidelines. For core concepts and basic terms, see [`terminology_core.md`](./terminology_core.md).**

---

## 📋 Purpose
This file defines advanced Magento-specific terms, frontend concepts, integration terminology, and usage guidelines for AI tools to understand complex user requests.

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

## 🔍 Context-Specific Terminology

### Admin Context
- **Admin Panel** - Backend administration interface
- **Admin User** - Backend user with administrative privileges
- **Admin Role** - Permission set for admin users
- **Admin Grid** - Data table in admin interface
- **Admin Form** - Input form in admin interface
- **Admin Menu** - Navigation menu in admin panel
- **Admin ACL** - Access control for admin features

### Frontend Context
- **Store Frontend** - Customer-facing website
- **Customer Account** - User account management
- **Shopping Cart** - Product selection before purchase
- **Checkout Process** - Purchase completion flow
- **Product Page** - Individual product display
- **Category Page** - Product listing by category
- **Search Results** - Product search display

### Development Context
- **Module Development** - Creating custom functionality
- **Theme Development** - Creating custom appearance
- **API Development** - Creating external integrations
- **Plugin Development** - Modifying existing functionality
- **Observer Development** - Event-driven customizations
- **Command Development** - CLI tool creation

---

## 📚 Additional Resources

- [Magento 2 Developer Documentation](https://developer.adobe.com/commerce/docs/)
- [Magento 2 Architecture Guide](https://developer.adobe.com/commerce/php/architecture/)
- [Magento 2 Module Development](https://developer.adobe.com/commerce/php/module-development/)
- [Magento 2 Frontend Development](https://developer.adobe.com/commerce/frontend-core/guide/)

---

## 🔗 Related Files

- **[`terminology_core.md`](./terminology_core.md)** - Core Concepts and Basic Terms
- **[`patterns_overview.md`](./patterns_overview.md)** - Core approach and scenarios
- **[`scope_and_structure.md`](./scope_and_structure.md)** - Project structure and work scope

---

**Remember**: Understanding Magento terminology is crucial for effective communication and problem-solving. Always clarify ambiguous terms and provide context when using technical language. 