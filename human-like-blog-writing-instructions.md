# Human-First Blog Writing Standard (Attention-Optimized)

## Purpose
This document defines a strict, repeatable, human-like process for writing high-quality blog posts using AI.

The goal is to produce blogs that:
- Feel thoughtful and experience-driven
- Respect modern attention spans
- Can be fully read in **3–4 minutes**
- Encourage readers to follow if they found value

Cursor must follow this document **step by step** whenever a blog title is provided.

---

## Readability Constraint (Non-Negotiable)
- Target reading time: **3–4 minutes**
- Approximate word count: **600–900 words**
- If the topic feels larger:
  - Prioritize insight over coverage
  - Cut secondary ideas instead of summarizing everything
  - Prefer depth in fewer sections over breadth

If the blog exceeds this limit, it must be **rewritten**, not trimmed.

---

## Category Input (Primary Workflow)
When executing this document for category-based blog generation:
- **Category** (mandatory): The topic category for which to generate blog ideas
  - Used for generating 10 blog title ideas
  - Used for organizing files in `content/blog/{category-name}/` folders
  - Provides context for blog generation

---

## Pre-Execution Phase: Existing Blog Discovery
Before generating any blog ideas:
1. Read all existing `.md` files from `src/content/blog/` directory recursively (including all subdirectories)
2. For each markdown file found:
   - Extract the `title` from frontmatter
   - Extract the `description` from frontmatter (if available)
   - Note the file path
3. Store this information in a structured format for semantic comparison
4. This inventory will be used to detect duplicate topics before writing

---

## Idea Generation Phase
After discovering existing blogs:
1. Generate exactly **10 blog title ideas** for the given category
2. Each idea must be:
   - Specific and actionable (not vague or generic)
   - Aligned with the 3–4 minute reading constraint
   - Relevant to the provided category
   - Focused on a clear problem, question, or insight
3. Present all 10 ideas as a numbered list
4. Each idea should be a complete, compelling blog title

---

## Duplicate Detection Phase
For each of the 10 generated ideas:
1. Compare the idea against all existing blog titles and descriptions using **semantic similarity**
2. Consider a blog duplicate if:
   - The semantic meaning is very similar (same core topic/angle)
   - The title addresses the same question or problem
   - The core insight or explanation would be substantially the same
3. Use AI reasoning to assess meaning, not just keyword matching
4. Be conservative: if uncertain whether something is a duplicate, mark it as duplicate to avoid repetition
5. Mark each idea as either "duplicate" or "unique"
6. Filter out all duplicate ideas
7. Present the filtered list of unique ideas that will be written

---

## File Organization Instructions
Blog files must be organized as follows:

**File Location:** `src/content/blog/{category-name}/{slug}.md`

**Category Name Format:**
- Convert category to lowercase
- Replace spaces with hyphens
- Remove special characters (keep only alphanumeric and hyphens)
- Remove consecutive hyphens
- Trim hyphens from start/end
- Example: "React Hooks" → "react-hooks"

**Slug Generation Rules:**
- Convert blog title to lowercase
- Replace spaces with hyphens
- Remove special characters (keep only alphanumeric and hyphens)
- Remove consecutive hyphens
- Trim hyphens from start/end
- Example: "Understanding useState Hook" → "understanding-usestate-hook"

**Folder Creation:**
- Create the category folder if it doesn't exist: `src/content/blog/{category-name}/`
- Ensure the folder structure is created before writing files

---

## Input (Legacy - For Direct Blog Title Execution)
When executing with a direct blog title (not category-based):
- Blog Title (mandatory)
- Target Audience (optional, assume informed tech/business readers if not provided)
- Depth Level (default: Medium–Deep, not exhaustive)

---

## Output Expectations
- Clear thinking, not verbose content
- Short paragraphs (2–4 lines max)
- No long monologues
- Each section must justify its existence
- No emojis unless explicitly asked
- No robotic phrases like “In this blog we will discuss…”

---

## Step 1: Understand the Intent Behind the Title (Writing Process)
Before writing:
- Infer **why someone would click this title**
- Identify:
  - What problem they want clarity on
  - What confusion they want resolved quickly
  - What mental shortcut they are hoping to gain

Write this as **internal reasoning only**.

---

## Step 2: Write the Overview (Hook + Context)
Start with a **tight overview**, not a definition.

Rules:
- Max 2–3 short paragraphs
- Establish relevance immediately
- Make the reader feel “this is worth my time”

Good patterns:
- “This question usually comes up when…”
- “Most people assume X, but that’s where confusion starts…”
- “If you’ve ever felt unsure about…”

Avoid slow buildup or history lessons.

---

## Step 3: Engage via Questions (Cognitive Hooks)
Ask **2–3 sharp questions** (not more).

These questions:
- Should mirror what a busy reader is thinking
- Should break the topic into clear chunks
- Must be directly answered later

Example patterns:
- “So what actually changes when…?”
- “Why does this seem powerful but fail in practice?”
- “Is this really better, or just different?”

These questions define the blog structure.

---

## Step 4: Answer Questions Concisely (Core Content)
For each question:
- Use it as a subheading
- Answer it in **focused, skimmable sections**

Each answer must include:
- Plain-language explanation
- One concrete example
- One practical insight or limitation

Rules:
- No section longer than ~150–200 words
- Cut explanations that don’t add clarity

---

## Step 5: Examples Must Be Realistic and Short
Examples should:
- Feel like lived experience
- Be concrete, not abstract
- Fit in 3–5 lines

Avoid:
- Hypothetical “perfect systems”
- Long narratives

---

## Step 6: Light Opinions Only (Optional)
If applicable:
- Introduce opinions subtly
- Keep them grounded in reasoning or observation

Patterns:
- “In practice, this breaks down when…”
- “This sounds efficient, but it often creates…”
- “Teams usually underestimate…”

---

## Step 7: Synthesis (Connect the Dots Quickly)
Before ending:
- Tie answers back to the original intent
- Reinforce one clear mental model

Max: 1 short section.

---

## Step 8: Soft Follow Call-To-Action (Mandatory)
Before the final closing thought:
- Add a **single, subtle follow request**
- It must feel optional and human, not promotional

Guidelines:
- 1–2 short sentences
- No pressure, no hype
- Express intent to share similar thinking in future

Approved tone examples:
- “If this helped you think more clearly about the topic, consider following — I share more thoughts like this.”
- “I write about similar ideas regularly. Follow if this kind of breakdown is useful to you.”
- “If you enjoyed this perspective, you might like what I write next.”

Do NOT:
- Beg for follows
- Mention algorithms, likes, or growth
- Break the blog’s tone

---

## Step 9: End with a Thought, Not a Summary
Do NOT:
- Say “In conclusion”
- Re-list points

Instead:
- End with:
  - A reframed question
  - A practical reflection
  - A forward-looking insight

End strong. End short.

---

## Final Quality Checklist (Must Pass All)
Before finalizing:
- Can this be read fully in 3–4 minutes?
- Can a reader skim and still understand?
- Does every section earn its place?
- Does the follow CTA feel natural?
- Does it sound like a human explaining, not teaching?

If any answer is “no”, revise.

---

## Execution Instruction for Cursor

### Category-Based Workflow (Primary)
When a **category** is provided:
1. **Discover existing blogs:**
   - Read all `.md` files from `src/content/blog/` recursively
   - Extract titles and descriptions from frontmatter
   - Build inventory of existing content

2. **Generate ideas:**
   - Generate exactly 10 blog title ideas for the category
   - Ensure each idea is specific, actionable, and fits 3–4 minute reading time

3. **Detect duplicates:**
   - Compare each of the 10 ideas against existing blogs using semantic similarity
   - Mark duplicates based on similar meaning, topic, or question addressed
   - Filter out duplicate ideas
   - Present the list of unique ideas

4. **Write unique blogs:**
   - For each unique idea:
     - Generate slug from title (lowercase, hyphenated, no special chars)
     - Determine category folder: `src/content/blog/{category-name}/`
     - Create category folder if it doesn't exist
     - Follow Steps 1–9 below to write the blog
     - Save to `src/content/blog/{category-name}/{slug}.md` with proper frontmatter

### Direct Title Workflow (Legacy)
When a **blog title** is provided directly (not category):
1. Generate a **concise blog plan** aligned to the 3–4 minute limit
2. Ensure planned sections fit within word constraints
3. Write the full blog using the approved plan (Steps 1–9)

---

## Writing Steps (Steps 1–9)
These steps are followed for each blog post, whether generated from category ideas or written directly from a title.
