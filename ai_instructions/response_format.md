# 📝 AI Tool Response Format Guidelines

## MANDATORY: Response Format Requirements

**ALL AI tool responses MUST follow this format to ensure compliance with repository instructions.**

---

## 🏷️ Required Labels

### Primary Labels (MUST be included in EVERY response)

1. **[FOLLOW_INSTRUCTION]** - Confirmation of repository instruction understanding
2. **[SYSTEMATIC_APPROACH]** - Confirmation of using systematic approach from `/magento/` folder
3. **[TASK_EXECUTION]** - Confirmation of following task-specific instructions from `/prompts/` folder

### Optional Labels (Use when applicable)

4. **[REFERENCE_CHECK]** - When checking reference code in `vendor/magento/`
5. **[VALIDATION_COMPLETE]** - When validation checklist is completed
6. **[SOLUTION_PROPOSED]** - When proposing a solution or fix

---

## 📋 Response Structure Template

### Standard Response Format

```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.

[Your detailed response here...]
```

### Task-Specific Response Format

```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.

[REFERENCE_CHECK] ✅ Completed: Checked reference code in vendor/magento/
[VALIDATION_COMPLETE] ✅ Completed: All validation checklist items verified

[Your solution or analysis here...]
```

---

## 🎯 Label Usage Examples

### Example 1: Initial Confirmation
```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.

I am ready to help you with your Magento development task. Please provide the specific task you need assistance with.
```

### Example 2: Task Analysis
```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.

[REFERENCE_CHECK] 🔍 Checking reference code in vendor/magento/ for compatibility...

Based on my analysis of the reference code, I found the following issues...
```

### Example 3: Solution Proposal
```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.

[VALIDATION_COMPLETE] ✅ All validation checklist items verified
[SOLUTION_PROPOSED] 💡 Proposing solution based on systematic approach

Here is the solution that maintains Magento compatibility...
```

---

## 🚫 Prohibited Response Formats

### ❌ Unacceptable Responses

```
Here's how to fix your Magento issue...
[No labels, no confirmation of instruction understanding]
```

```
I'll help you with that.
[Missing required labels and confirmations]
```

```
[FOLLOW_INSTRUCTION] I read the instructions
[Incomplete labeling, missing systematic approach confirmation]
```

### ✅ Acceptable Responses

```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.

Here's how to fix your Magento issue using the systematic approach...
```

---

## 🔄 Workflow Integration

### Step 1: Initial Response
- Always start with the three mandatory labels
- Confirm understanding of repository instructions
- Ready to receive specific task

### Step 2: Task Analysis
- Use [REFERENCE_CHECK] when examining reference code
- Follow systematic approach from `/magento/` folder
- Apply task-specific instructions from `/prompts/` folder

### Step 3: Solution Delivery
- Use [VALIDATION_COMPLETE] when checklist is done
- Use [SOLUTION_PROPOSED] when providing solution
- Ensure all responses maintain proper labeling

---

## ⚠️ Quality Assurance

### Response Quality Checklist

- [ ] **All mandatory labels included** ✅
- [ ] **Proper confirmation statements** ✅
- [ ] **Systematic approach referenced** ✅
- [ ] **Task-specific instructions followed** ✅
- [ ] **Clear and actionable response** ✅
- [ ] **Magento compatibility maintained** ✅

### Compliance Verification

**Every response must demonstrate:**
1. **Understanding** of repository instructions
2. **Application** of systematic approach
3. **Execution** of task-specific guidelines
4. **Proper labeling** for accountability

---

## 📝 Quick Reference

### Mandatory Labels (Copy & Paste)
```
[FOLLOW_INSTRUCTION] ✅ Confirmed: I have read and understood all instructions in this repository.
[SYSTEMATIC_APPROACH] ✅ Confirmed: I will use the systematic approach from the magento folder.
[TASK_EXECUTION] ✅ Confirmed: I will follow the task-specific instructions from the prompts folder.
```

### Optional Labels (Use as needed)
```
[REFERENCE_CHECK] 🔍 Checking reference code...
[VALIDATION_COMPLETE] ✅ All validation checklist items verified
[SOLUTION_PROPOSED] 💡 Proposing solution...
```

**Remember**: Always start every response with the mandatory labels to ensure compliance and proper instruction following. 