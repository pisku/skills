# Troubleshooting Skills

## Skill Won't Upload

**Error**: "Could not find SKILL.md"
- Cause: File must be exactly `SKILL.md` (case-sensitive)
- Fix: Rename file to SKILL.md (uppercase)

**Error**: "Invalid frontmatter"
- Cause: YAML formatting issues
- Fix: Check for missing `---`, unclosed quotes, proper indentation

**Error**: "Invalid skill name"
- Cause: Must be kebab-case (lowercase, hyphens only)
- Fix: Rename skill folder to use kebab-case

## Skill Doesn't Trigger

**Symptom**: Claude never uses the skill
- Cause 1: Description too generic ("Helps with documents")
- Cause 2: Missing trigger phrases in description
- Debug: Ask Claude "When would you use the [skill-name] skill?"

**Fix**:
- Add specific triggers to description
- Include key terms users might say
- Test with paraphrased queries

## Skill Triggers Too Often

**Symptom**: Skill activates for unrelated tasks
- Cause: Description too broad

**Fix**:
- Add negative triggers: "Use for X, NOT for Y"
- Be more specific about scope
- Add "Do NOT use for [alternative]" language

## MCP Connection Issues

**Symptom**: Skill can't find MCP tools
- Cause 1: Server not connected (Settings > Extensions)
- Cause 2: Authentication issues (API keys, tokens)
- Cause 3: Tool names not fully qualified
- Cause 4: Tool names case-sensitive

**Fix**:
- Verify server is connected in Settings
- Check MCP server authentication
- Use fully qualified tool names: `ServerName:tool_name`
- Test MCP independently

## Instructions Not Followed

**Symptom**: Claude doesn't follow skill instructions
- Cause 1: Instructions too verbose → Keep concise, use bullets
- Cause 2: Instructions buried → Put critical at top, use ## Critical headers
- Cause 3: Ambiguous language → Be explicit and deterministic
- Cause 4: Model cutoff → For long tasks, add performance notes

**Fix**:
- Simplify verbose sections
- Use headers for critical info
- Be explicit: "ALWAYS do X", "NEVER do Y"
- Add "Take your time" notes for complex tasks

## Large Context Issues

**Symptom**: Context fills up, performance degrades
- Cause: Too many skills loaded, SKILL.md too large

**Fix**:
- Keep SKILL.md under 5,000 words
- Move detailed docs to `references/`
- Disable unused skills (recommend 20-50 max)
