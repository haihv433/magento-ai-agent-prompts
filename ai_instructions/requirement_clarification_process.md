# 🎯 MANDATORY: AI Tool Requirement Clarification Process

## 🚨 CRITICAL: READ THIS FILE FIRST
**BEFORE executing ANY task, you MUST ensure requirements are clear, specific, and actionable. This prevents wasted effort, incorrect implementations, and ensures successful task completion.**

---

## 📋 Purpose
This file instructs AI tools to systematically clarify ambiguous, abstract, or unclear human requirements before proceeding with any development task. This ensures proper scope definition, prevents misunderstandings, and leads to successful task completion.

**Key Benefits:**
- **Prevent Scope Creep**: Clarify requirements to avoid expanding beyond intended scope
- **Reduce Rework**: Get clear requirements upfront to avoid multiple iterations
- **Improve Accuracy**: Understand exactly what the user wants before implementation
- **Save Time**: Address ambiguity early rather than during development
- **Ensure Success**: Clear requirements lead to successful task completion

---

## 🔍 Requirement Analysis Process

### Step 1: Identify Requirement Types
**AI tools should categorize the requirement type:**

```
🔍 **Requirement Analysis**

I've identified your request as one of the following types:

**✅ Clear & Specific**: Detailed, actionable requirements with specific goals
**⚠️ Abstract**: High-level concepts without specific implementation details
**❓ Ambiguous**: Multiple possible interpretations or unclear objectives
**🔄 Vague**: Missing critical details like scope, context, or constraints
**📋 Complex**: Multiple requirements combined or interdependent tasks

**Current Assessment**: [Type identified]
```

### Step 2: Clarification Questions by Type

#### **For Abstract Requirements:**
```
🎯 **Clarification Needed - Abstract Requirement**

Your request is quite abstract. To provide the best solution, I need to understand:

**Scope & Context:**
- What specific Magento functionality are you trying to achieve?
- Which part of your Magento store is affected?
- Is this for frontend, backend, or both?

**Implementation Details:**
- Do you have a specific approach in mind?
- Are there any existing modules or code to work with?
- What Magento version are you using?

**Success Criteria:**
- How will you know when this is working correctly?
- What should the end result look like?
- Are there any specific requirements or constraints?

**Priority & Timeline:**
- How urgent is this requirement?
- Are there any deadlines or dependencies?
```

#### **For Ambiguous Requirements:**
```
🎯 **Clarification Needed - Ambiguous Requirement**

Your request could be interpreted in several ways. Let me clarify:

**Specific Functionality:**
- Could you provide a concrete example of what you want to achieve?
- Are you referring to [Option A] or [Option B] or something else?
- What specific behavior are you looking for?

**Technical Context:**
- Which Magento components are involved?
- Are you working with existing code or creating something new?
- What's the current state vs. desired state?

**User Experience:**
- How should this work from a user's perspective?
- What should happen when [specific scenario]?
- Are there any error conditions to handle?

**Integration Points:**
- Does this need to work with other systems or modules?
- Are there any API integrations required?
- What data sources are involved?
```

#### **For Vague Requirements:**
```
🎯 **Clarification Needed - Vague Requirement**

Your request is missing some important details. I need to understand:

**Missing Context:**
- What specific problem are you trying to solve?
- What's the current situation that needs improvement?
- What triggered this requirement?

**Missing Scope:**
- Which parts of your Magento installation are affected?
- Are we talking about a specific page, module, or the entire system?
- What's the scale of this change?

**Missing Constraints:**
- Are there any performance requirements?
- Any compatibility requirements with existing code?
- Any security considerations?

**Missing Success Metrics:**
- How will you measure success?
- What's the expected outcome?
- Any specific performance targets?
```

#### **For Complex Requirements:**
```
🎯 **Clarification Needed - Complex Requirement**

Your request involves multiple components. Let me break this down:

**Component Breakdown:**
- [List identified components]
- Which component should we tackle first?
- Are these components independent or interdependent?

**Priority & Dependencies:**
- What's the most critical part to address first?
- Are there any dependencies between components?
- What's the logical order of implementation?

**Scope Management:**
- Should we implement all components at once or incrementally?
- Are there any components that can be simplified or deferred?
- What's the minimum viable solution?

**Resource Considerations:**
- How much time can you allocate to this?
- Are there any technical constraints I should know about?
- Any existing code or modules to work with?
```

---

## 🎯 Magento-Specific Clarification Questions

### **For Module Development:**
```
🔧 **Module Development Clarification**

**Module Purpose:**
- What specific functionality should this module provide?
- Is this a new feature or extending existing functionality?
- Which Magento areas are affected (frontend, admin, API)?

**Technical Requirements:**
- What Magento version compatibility is needed?
- Any specific coding standards or patterns to follow?
- Database changes required (new tables, modifications)?

**Integration Points:**
- Does this integrate with existing modules?
- Any third-party integrations required?
- API endpoints needed?

**User Interface:**
- Admin interface required?
- Frontend changes needed?
- Any specific UI/UX requirements?
```

### **For Bug Fixes:**
```
🐛 **Bug Fix Clarification**

**Issue Description:**
- What exactly is happening vs. what should happen?
- When does this issue occur (specific steps)?
- Which users/roles are affected?

**Environment Details:**
- What Magento version are you using?
- Any specific modules or customizations involved?
- Can you reproduce this consistently?

**Impact Assessment:**
- How critical is this issue?
- How many users are affected?
- Any workarounds currently in place?

**Expected Resolution:**
- What's the desired fix approach?
- Any constraints on the solution?
- Timeline expectations?
```

### **For Performance Issues:**
```
⚡ **Performance Issue Clarification**

**Performance Symptoms:**
- What specific performance problems are you experiencing?
- Which pages or operations are slow?
- What's the current vs. expected performance?

**Environment Context:**
- Server specifications and resources?
- Current traffic levels?
- Any recent changes that might have caused this?

**Measurement & Monitoring:**
- How are you measuring performance?
- Any specific metrics or thresholds?
- Monitoring tools in place?

**Optimization Scope:**
- Which areas should we focus on first?
- Any specific bottlenecks identified?
- Budget or time constraints for optimization?
```

### **For Customizations:**
```
🎨 **Customization Clarification**

**Customization Scope:**
- What specific elements need customization?
- Is this visual, functional, or both?
- Which Magento themes or modules are involved?

**Design Requirements:**
- Any specific design guidelines or brand requirements?
- Reference examples or mockups available?
- Responsive design requirements?

**Technical Approach:**
- Should this be theme-based or module-based?
- Any existing custom code to work with?
- Compatibility with future Magento updates?

**User Experience:**
- How should this work from a user perspective?
- Any specific user flows or interactions?
- Accessibility requirements?
```

---

## 🔗 Related Files

- **[`requirement_clarification_workflow.md`](./requirement_clarification_workflow.md)** - Clarification Workflow and Best Practices
- **[`environment_preparation.md`](./environment_preparation.md)** - Environment setup and configuration
- **[`task_storage_structure.md`](./task_storage_structure.md)** - Task storage file structure and templates 