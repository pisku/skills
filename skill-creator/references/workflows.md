# Workflow Patterns

## Sequential Workflows

For complex tasks, break operations into clear, sequential steps. It is often helpful to give Claude an overview of the process towards the beginning of SKILL.md:

```markdown
Filling a PDF form involves these steps:

1. Analyze the form (run analyze_form.py)
2. Create field mapping (edit fields.json)
3. Validate mapping (run validate_fields.py)
4. Fill the form (run fill_form.py)
5. Verify output (run verify_output.py)
```

## Conditional Workflows

For tasks with branching logic, guide Claude through decision points:

```markdown
1. Determine the modification type:
   **Creating new content?** → Follow "Creation workflow" below
   **Editing existing content?** → Follow "Editing workflow" below

2. Creation workflow: [steps]
3. Editing workflow: [steps]
```

## Pattern 5: Iterative Refinement

For tasks requiring quality improvement through multiple passes.

**When to use**: Code generation, document drafting, content optimization

**Structure**:
1. Explicit quality criteria
2. Iterative improvement loop
3. Validation scripts or checkpoints
4. Clear stopping condition

**Example**:
```markdown
## Report generation workflow

Copy this checklist and check off items as you complete them:

```
Generation Progress:
- [ ] Step 1: Generate initial draft
- [ ] Step 2: Validate against requirements
- [ ] Step 3: Refine based on validation
- [ ] Step 4: Final verification
```

**Step 1: Generate initial draft**
Use the template to create initial content.

**Step 2: Validate against requirements**
Run: `python scripts/validate_report.py draft.md`
Fix any validation errors.

**Step 3: Refine based on validation**
Address validation feedback and improve content.

**Step 4: Final verification**
Run validation again. Only proceed when all checks pass.
```
```