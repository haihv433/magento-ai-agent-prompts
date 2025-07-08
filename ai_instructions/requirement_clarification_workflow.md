# 🔄 MANDATORY: AI Tool Requirement Clarification Workflow

## 🚨 CRITICAL: READ THIS FILE FIRST
**This file contains the workflow and best practices for requirement clarification. For clarification templates and questions, see [`requirement_clarification_process.md`](./requirement_clarification_process.md).**

---

## 📋 Purpose
This file provides the workflow and best practices for AI tools to effectively clarify requirements before proceeding with any development task. It covers the step-by-step process, validation checklist, and common mistakes to avoid.

---

## 🔄 Clarification Workflow

### **Step 1: Initial Assessment**
1. **Read the user's request** completely
2. **Categorize the requirement type** (Clear, Abstract, Ambiguous, Vague, Complex)
3. **Identify missing information** based on the category

### **Step 2: Ask Targeted Questions**
1. **Use the appropriate question template** based on requirement type
2. **Ask 3-5 specific questions** to narrow down the scope
3. **Focus on the most critical missing information** first

### **Step 3: Refine Understanding**
1. **Listen to user responses** carefully
2. **Ask follow-up questions** if needed
3. **Confirm understanding** before proceeding

### **Step 4: Scope Definition**
1. **Summarize the clarified requirements**
2. **Define clear success criteria**
3. **Establish implementation approach**

---

## ✅ Validation Checklist

**Before proceeding with any task, ensure:**

- [ ] **Requirement type identified** and appropriate clarification questions asked
- [ ] **Specific functionality defined** with clear objectives
- [ ] **Scope boundaries established** (what's in/out of scope)
- [ ] **Technical context understood** (Magento version, modules, constraints)
- [ ] **Success criteria defined** (how to measure completion)
- [ ] **Implementation approach agreed** (method, timeline, resources)
- [ ] **User confirmation received** that requirements are clear and complete

---

## 🚫 Common Mistakes to Avoid

### **Don't:**
- ❌ **Assume requirements are clear** without verification
- ❌ **Start coding immediately** with ambiguous requirements
- ❌ **Ask too many questions at once** (overwhelm the user)
- ❌ **Ignore user context** and Magento-specific considerations
- ❌ **Proceed without user confirmation** of clarified requirements

### **Do:**
- ✅ **Always assess requirement clarity** before proceeding
- ✅ **Ask targeted, specific questions** to narrow scope
- ✅ **Use Magento-specific context** in your questions
- ✅ **Confirm understanding** before implementation
- ✅ **Document clarified requirements** for future reference

---

## 📝 Example Clarification Session

**User Request**: "I need to fix the checkout process"

**AI Tool Response**:
```
🎯 **Clarification Needed - Vague Requirement**

Your request "fix the checkout process" is quite broad. To provide the best solution, I need to understand:

**Specific Issues:**
- What exactly is wrong with the checkout process?
- Are customers experiencing errors, or is it just slow?
- Which step of checkout is problematic (cart, shipping, payment, etc.)?

**User Impact:**
- How are customers affected? (errors, timeouts, confusion?)
- Are you losing sales due to checkout issues?
- Which customer segments are most affected?

**Technical Context:**
- What Magento version are you using?
- Any specific payment methods or shipping methods involved?
- Any custom modules that might affect checkout?

**Expected Outcome:**
- What should the fixed checkout process look like?
- Any specific performance targets?
- Timeline for the fix?

Please provide these details so I can give you the most effective solution.
```

---

## 🔄 Integration with Other Instructions

**This clarification process should be used:**
- **Before** reading environment preparation instructions
- **Before** executing any prompt from the `/prompts/` folder
- **Before** applying any systematic approach from the `/magento/` folder
- **Throughout** the development process when new requirements emerge

---

## 📝 Response Template

### Requirement Clarification Response
```
[REQUIREMENT_CLARIFICATION] ✅ Confirmed: Requirements clarified before proceeding
[CLARITY_ASSESSMENT] ✅ Confirmed: Requirement type identified and addressed
[USER_CONFIRMATION] ✅ Confirmed: User has confirmed clarified requirements

## 🎯 Requirement Clarification Complete

### Requirement Analysis
- **Type Identified**: [Clear/Abstract/Ambiguous/Vague/Complex]
- **Clarification Questions**: [Number] targeted questions asked
- **User Responses**: All critical information obtained

### Clarified Requirements
- **Specific Functionality**: [Clear description of what needs to be done]
- **Scope Boundaries**: [What's included/excluded]
- **Technical Context**: [Magento version, modules, constraints]
- **Success Criteria**: [How to measure completion]

### Implementation Approach
- **Method**: [Approach agreed upon]
- **Timeline**: [Expected duration]
- **Resources**: [Any constraints or requirements]

### Next Steps
1. ✅ Requirements clarified and confirmed
2. ✅ Scope defined and agreed
3. ✅ Success criteria established
4. 🔄 Ready to proceed with implementation

### Benefits Achieved
- **Prevented Scope Creep**: Clear boundaries established
- **Reduced Rework**: Specific requirements defined upfront
- **Improved Accuracy**: Exact objectives understood
- **Saved Time**: Addressed ambiguity early
```

---

## 🔗 Related Files

- **[`requirement_clarification_process.md`](./requirement_clarification_process.md)** - Clarification Templates and Questions
- **[`environment_preparation.md`](./environment_preparation.md)** - Environment setup and configuration
- **[`task_storage_structure.md`](./task_storage_structure.md)** - Task storage file structure and templates
- **[`response_format.md`](./response_format.md)** - Response labeling requirements

---

**Remember**: Clear requirements lead to successful implementations. Always clarify before you code! 