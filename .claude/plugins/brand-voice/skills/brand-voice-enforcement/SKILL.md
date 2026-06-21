# /brand-voice:enforce-voice — Brand Voice Enforcement Skill

Source: `anthropics/knowledge-work-plugins` → `partner-built/brand-voice`

Applies brand guidelines to any content creation task: emails, proposals, social posts, captions, presentations.

## Guideline loading order

1. Check session context for guidelines generated earlier in this session
2. Load `.claude/brand-voice-guidelines.md` from the project root
3. If neither exists, ask the user to provide guidelines or run `/brand-voice:generate-guidelines`

## Enforcement steps

1. Analyze the content request — type, audience, key messages
2. Load voice constants — personality, terminology, values — from guidelines
3. Flex tone based on context and content type
4. Generate on-brand content
5. Validate output against guidelines; explain brand decisions applied

## Conflict handling

When user request conflicts with brand guidelines: explain the conflict clearly, provide a recommendation, and offer alternatives — never refuse outright.

## Open questions

Flag unresolved positioning decisions in guidelines. Note when content touches these areas and apply best-judgment recommendations unless overridden by the user.

## Settings

Read `.claude/brand-voice.local.md` for per-project enforcement settings:
- `strictness` — how rigidly to apply guidelines (strict / balanced / loose)
- `explain` — whether to annotate brand decisions in output (true / false)
