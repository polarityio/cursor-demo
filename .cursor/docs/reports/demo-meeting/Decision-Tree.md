# Cursor Training Decision Tree: Technique Selection Guide

**🎯 Purpose:** Guided selection framework for Jonathan Penwood's Cursor techniques  
**👥 Target Audience:** Anyone implementing Cursor methodology  
**📅 Based on:** July 29, 2025 Meeting Demonstration  
**⏱️ Usage Time:** 2-5 minutes per decision

---

## 🌳 **Master Decision Tree**

### **START: What are you trying to accomplish?**

```
🎯 CURSOR TECHNIQUE SELECTION GUIDE

1. DEFINE YOUR GOAL
   ├─ 🐛 Fix repeated AI mistakes → GO TO: A1 (Create Rule)
   ├─ 📚 Provide domain knowledge → GO TO: B1 (Create Document)  
   ├─ 💬 Get help with current task → GO TO: C1 (Conversational Assistance)
   ├─ 📋 Execute complex project → GO TO: D1 (Plan File Workflow)
   ├─ 🖥️ Optimize work environment → GO TO: E1 (Interface Management)
   └─ 📝 Record learning/decisions → GO TO: F1 (Transcript Creation)

2. ASSESS COMPLEXITY
   ├─ Simple (< 30 mins) → Quick techniques
   ├─ Medium (30 mins - 4 hours) → Standard methodology 
   └─ Complex (> 4 hours) → Full methodology with transfer learning

3. CHOOSE INTERACTION MODE
   ├─ Exploration/Brainstorming → Voice input preferred
   ├─ Precision/Implementation → Manual input required
   └─ Mixed workflow → Voice + Precision integration
```

---

## 🔧 **Detailed Decision Flows**

### **A1: Creating Rules (Corrective Guidance)**

**When to Use:**
- AI repeatedly makes the same mistakes
- Team needs consistent coding standards
- Want to prevent specific anti-patterns
- Need negative feedback loop correction

**Decision Path:**
```
📋 RULE CREATION FLOW

START: AI making repeated mistakes?
├─ YES → Continue
└─ NO → Consider B1 (Document) instead

SCOPE: What type of mistakes?
├─ Code Style → Create coding-standards.mdc
├─ Architecture → Create architecture-patterns.mdc  
├─ Security → Create security-guidelines.mdc
└─ General → Create general-corrections.mdc

FORMAT: How specific is the guidance?
├─ File-specific → Use globs: ["path/to/files/**"]
├─ Project-wide → Use globs: ["**/*"]
└─ Language-specific → Use globs: ["**/*.js", "**/*.ts"]

IMPLEMENTATION:
1. Create .cursor/rules/[name].mdc
2. Add frontmatter with description and globs
3. Document specific corrections and anti-patterns
4. Test with AI to ensure guidance is followed
5. Iterate based on AI behavior changes
```

**Example Use Cases:**
- AI suggests `var` instead of `let/const` → Create variable-declaration.mdc
- AI generates insecure authentication → Create auth-security.mdc
- AI violates team naming conventions → Create naming-standards.mdc

### **B1: Creating Documents (Domain Knowledge)**

**When to Use:**
- AI needs context about business domain
- Want to build positive knowledge base
- Sharing successful patterns across team
- Documenting architecture decisions

**Decision Path:**
```
📚 DOCUMENT CREATION FLOW

START: Need to provide positive knowledge?
├─ YES → Continue
└─ NO → Consider A1 (Rule) for corrections

CONTENT TYPE: What knowledge to capture?
├─ Business Logic → Create domain-knowledge.md
├─ Architecture → Create system-architecture.md
├─ APIs/Integrations → Create api-documentation.md
└─ Procedures → Create process-documentation.md

AUDIENCE: Who will use this knowledge?
├─ AI Only → Focus on clear, structured information
├─ Team + AI → Include examples and explanations
└─ Cross-team → Add context and background

IMPLEMENTATION:
1. Create .cursor/docs/[name].md
2. Structure information clearly and logically
3. Include examples and use cases
4. Reference from @docs in conversations
5. Refine based on usage and effectiveness
```

**Example Use Cases:**
- Complex business rules → Create business-logic.md
- API integration patterns → Create api-patterns.md
- Database schema explanations → Create data-model.md

### **C1: Conversational Assistance (Interactive Help)**

**When to Use:**
- Need immediate help with current work
- Exploring solutions or approaches
- Learning new concepts or tools
- Quick questions or clarifications

**Decision Path:**
```
💬 CONVERSATIONAL ASSISTANCE FLOW

START: What's the interaction goal?
├─ Quick Question → C2 (Contextual Chat)
├─ Exploration → C3 (Research Mode)
├─ Implementation → C4 (Code Assistance)
└─ Learning → C5 (Educational Mode)

C2: CONTEXTUAL CHAT
├─ Select relevant code/text
├─ Press Command+L for instant context
├─ Ask specific question about selection
└─ Apply suggestions immediately

C3: RESEARCH MODE  
├─ Use @web for external information
├─ Apply 3-link strategy (overview → specific → examples)
├─ Verify source quality and authority
└─ Document useful findings in .cursor/docs

C4: CODE ASSISTANCE
├─ Choose appropriate chat window mode:
│   ├─ Sidemounted → Quick edits, simple tasks
│   ├─ Windowed → Complex operations, refactoring
│   └─ Tab Mode → Multiple contexts, comparisons
├─ Provide sufficient context (@codebase, active files)
├─ Be specific about requirements and constraints
└─ Validate suggestions before applying

C5: EDUCATIONAL MODE
├─ Ask for explanations with examples
├─ Request step-by-step breakdowns
├─ Use @web for additional resources
└─ Create documents to capture learning
```

### **D1: Plan File Workflow (Structured Execution)**

**When to Use:**
- Complex projects with multiple steps
- Want systematic progress tracking
- Need transfer learning documentation
- Working on unfamiliar problem domains

**Decision Path:**
```
📋 PLAN FILE WORKFLOW

START: Project complexity assessment
├─ Simple (< 5 tasks) → Consider C1 (Conversational) instead
├─ Medium (5-15 tasks) → Continue with plan file
└─ Complex (15+ tasks) → Break into multiple plan files

PLANNING PHASE:
1. Define clear objectives and success criteria
2. Break down work into specific, measurable tasks
3. Identify dependencies and constraints
4. Add checkboxes for progress tracking
5. Include transfer learning section

EXECUTION PHASE:
1. Work through tasks systematically
2. Check off completed items
3. Document insights and decisions
4. Note what works well and what doesn't
5. Update transfer learning notes

COMPLETION PHASE:
1. Review completed work against objectives
2. Extract patterns for future use
3. Create templates for similar projects
4. Update rules/docs based on learnings
5. Archive plan with lessons learned
```

**Plan File Template Selection:**
```
PROJECT TYPE → TEMPLATE
├─ Feature Implementation → feature-development-plan.md
├─ Bug Investigation → debugging-plan.md
├─ Refactoring → refactoring-plan.md
├─ Research → research-plan.md
└─ Custom → custom-project-plan.md
```

### **E1: Interface Management (Optimize Environment)**

**When to Use:**
- Workflow feels inefficient or clunky
- Need better context management
- Want to optimize for specific task types
- Integrating voice control or accessibility

**Decision Path:**
```
🖥️ INTERFACE OPTIMIZATION FLOW

START: What's the primary inefficiency?
├─ Chat Window Management → E2 (Window Modes)
├─ Context Switching → E3 (Context Strategy)
├─ Input Method → E4 (Voice Integration)
└─ Screen Real Estate → E5 (Layout Optimization)

E2: WINDOW MODES
Current Task Type:
├─ Quick Questions → Sidemounted (default)
├─ Complex Implementation → Windowed (more space)
├─ Multiple Conversations → Tab Mode (separate contexts)
└─ Team Collaboration → Windowed (screen sharing)

E3: CONTEXT STRATEGY
Context Requirements:
├─ Current File Only → Active tab context sufficient
├─ Multiple Files → Select specific files manually
├─ Whole Project → Use @codebase strategically
├─ External Info → Use @web with 3-link strategy
└─ Team Knowledge → Reference @rules and @docs

E4: VOICE INTEGRATION
Workflow Type:
├─ Brainstorming → Voice for natural exploration
├─ Implementation → Voice + manual for precision
├─ Review/Editing → Manual for exact control
└─ Documentation → Voice for explanation, manual for structure

E5: LAYOUT OPTIMIZATION
Screen Setup:
├─ Single Monitor → Sidemounted chat, maximize code space
├─ Dual Monitor → Windowed chat on second monitor
├─ Ultrawide → Tab mode with side panels
└─ Mobile/Small → Focus mode with minimal UI
```

### **F1: Transcript Creation (Knowledge Capture)**

**When to Use:**
- Important conversations to remember
- Complex debugging sessions
- Learning new techniques or patterns
- Team knowledge sharing needs

**Decision Path:**
```
📝 TRANSCRIPT CREATION FLOW

START: What's the capture goal?
├─ Personal Learning → F2 (Learning Transcript)
├─ Team Sharing → F3 (Collaborative Transcript)  
├─ Decision Record → F4 (Decision Transcript)
└─ Debugging Log → F5 (Debug Transcript)

F2: LEARNING TRANSCRIPT
Content Focus:
├─ Key insights and breakthroughs
├─ Successful patterns and approaches
├─ Mistakes and how they were corrected
└─ Resources and references discovered

F3: COLLABORATIVE TRANSCRIPT
Team Elements:
├─ Clear problem statement and context
├─ Solution approach and rationale
├─ Implementation steps and validation
├─ Lessons learned and next steps
└─ Formatted for easy team consumption

F4: DECISION TRANSCRIPT
Decision Elements:
├─ Options considered and criteria used
├─ Trade-offs and risk assessments
├─ Final decision and justification
├─ Implementation plan and success metrics
└─ Review timeline and checkpoints

F5: DEBUG TRANSCRIPT
Debug Elements:
├─ Problem symptoms and reproduction steps
├─ Investigation approach and tools used
├─ Findings and root cause analysis
├─ Solution implementation and testing
└─ Prevention strategies for future
```

---

## ⚖️ **Context-Dependent Decisions**

### **Always-On vs Manual Control**

```
DECISION: When to use Always-On vs Manual control?

ALWAYS-ON APPROPRIATE FOR:
├─ Code completion and syntax suggestions
├─ Real-time error detection and linting
├─ Automatic context inclusion for familiar projects
├─ Formatting and style corrections
└─ Documentation generation for standard patterns

MANUAL CONTROL REQUIRED FOR:
├─ Architecture and design decisions
├─ Security-sensitive implementations
├─ Performance-critical optimizations
├─ Complex refactoring operations
├─ Business logic requiring domain expertise
└─ New or experimental approaches

DECISION CRITERIA:
├─ Risk Level → High risk = Manual control
├─ Complexity → Complex = Manual oversight
├─ Learning Value → Educational = Manual involvement
├─ Team Impact → Shared code = Manual review
└─ Domain Specificity → Specialized knowledge = Manual guidance
```

### **Voice vs Precision Input**

```
DECISION: When to use Voice vs Precision input?

VOICE INPUT OPTIMAL FOR:
├─ Initial brainstorming and exploration
├─ Explaining complex problems or requirements
├─ Natural conversation flow with AI
├─ Accessibility needs or ergonomic preferences
└─ Rapid idea capture and iteration

PRECISION INPUT REQUIRED FOR:
├─ Exact technical specifications
├─ Code review and detailed editing
├─ Security or compliance requirements
├─ Mathematical or logical precision
└─ Final implementation and validation

HYBRID APPROACH:
1. Voice for problem exploration and ideation
2. Precision for requirement specification
3. Voice for implementation discussion
4. Precision for code review and refinement
5. Voice for documentation and explanation
```

### **Individual vs Team Context**

```
DECISION: How to adapt techniques for team vs individual use?

INDIVIDUAL FOCUS:
├─ Personal rules and documents for learning
├─ Flexible experimentation with techniques
├─ Custom workflow optimization
├─ Private knowledge building and iteration
└─ Personal productivity acceleration

TEAM FOCUS:
├─ Shared rules and documents in version control
├─ Standardized approaches and conventions
├─ Collective knowledge building and sharing
├─ Team onboarding and training processes
└─ Consistent methodology across projects

SCALING STRATEGY:
1. Individual → Master personal methodology
2. Pair → Share techniques with colleague
3. Team → Standardize successful approaches
4. Organization → Scale across multiple teams
5. Community → Contribute to shared knowledge
```

---

## 🚀 **Quick Reference Decision Matrix**

| Situation | Technique | Time | Complexity | Output |
|-----------|-----------|------|------------|---------|
| **AI making repeated errors** | Create Rule | 15 min | Low | .mdc file |
| **Need domain knowledge** | Create Document | 30 min | Medium | .md file |
| **Quick code help** | Contextual Chat | 5 min | Low | Immediate assistance |
| **Complex feature** | Plan File | 2-8 hours | High | Structured execution |
| **Workflow inefficiency** | Interface Optimization | 10 min | Low | Better productivity |
| **Important conversation** | Transcript | 20 min | Medium | Knowledge capture |
| **Learning new concept** | Research Mode | 30 min | Medium | External knowledge |
| **Team standardization** | Shared Rules/Docs | 1 hour | Medium | Team consistency |
| **Architecture decision** | Manual + Documentation | 2 hours | High | Deliberate choice |
| **Routine implementation** | Always-On + Validation | 30 min | Low | Accelerated development |

---

## 🎯 **Common Scenarios & Recommendations**

### **Scenario 1: New to Cursor**
**Path:** Start with C1 (Conversational) → Practice E1 (Interface) → Build A1/B1 (Rules/Docs) → Advanced D1 (Plans)

### **Scenario 2: Experienced Developer, New Team**
**Path:** E1 (Interface Setup) → B1 (Team Docs) → A1 (Team Rules) → D1 (Complex Projects)

### **Scenario 3: Complex Debugging Session**
**Path:** C1 (Conversational Research) → F1 (Debug Transcript) → B1 (Document Findings) → A1 (Prevent Recurrence)

### **Scenario 4: Team Onboarding**
**Path:** Share existing A1/B1 (Rules/Docs) → E1 (Interface Training) → C1 (Guided Practice) → D1 (First Project)

### **Scenario 5: Performance Optimization**
**Path:** Manual control + C3 (Research) → F4 (Decision Record) → B1 (Document Patterns) → Team sharing

---

**📋 Remember:** This decision tree is a guide, not a rigid prescription. Adapt techniques based on your specific context, team needs, and project requirements. The goal is systematic acceleration, not mechanical following of rules.

**⏰ Last Updated:** January 30, 2025  
**📋 Source:** Jonathan Penwood Gemini Meeting Demonstration  
**🎯 Target:** Systematic technique selection for optimal Cursor usage 