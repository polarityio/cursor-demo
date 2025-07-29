# Cursor Folder Revamp Plan
*Comprehensive link verification and inline linking for all .cursor files*

**Created:** 2025-01-27 15:30 PST  
**Scope:** All files in `/Users/jonp/code/projects/cursor-demo/.cursor`  
**Goal:** 100% link verification with inline cross-references

---

## 📋 Project Overview

### **Objective**
Revamp every file in the `.cursor` folder to ensure:
- ✅ All links are verified (200 status or local references)
- ✅ Inline linking on every document reference
- ✅ Cross-references between related files
- ✅ Proper link validation and testing

### **Files to Process (16 total)**
```
.cursor/
├── README.md (1 file)
├── rules/
│   ├── always-on/ (5 files)
│   │   ├── communication-standards.mdc
│   │   ├── conversation-driven.mdc
│   │   ├── personal-profile.mdc
│   │   ├── problem-solving.mdc
│   │   └── security-practices.mdc
│   └── manual/ (6 files)
│       ├── development-workflow.mdc
│       ├── link-context-gathering.mdc
│       ├── quality-control.mdc
│       └── tracking/ (3 files)
│           ├── manual-testing-tracking-agent.mdc
│           ├── plan-execute-verify.mdc
│           ├── plan-generation.mdc
│           └── transcript-formatting-agent.mdc
└── docs/transcripts/ (4 .gitkeep files)
```

---

## 🎯 Phase 1: Link Audit & Mapping

### **Step 1.1: Current Link Analysis**
**Task:** Audit all existing links in each file
**Files:** All 12 .mdc and .md files
**Deliverable:** Link inventory with status codes

**Process:**
1. Extract all links from each file
2. Test external links for 200 status
3. Verify local file references exist
4. Document broken/missing links

### **Step 1.2: Cross-Reference Mapping**
**Task:** Map relationships between files
**Deliverable:** Dependency matrix

**Mapping Categories:**
- **Always-On Rules** → **Manual Rules** references
- **Manual Rules** → **Always-On Rules** references  
- **Tracking Rules** → **Other Rules** references
- **README.md** → **All Rules** references

---

## 🔗 Phase 2: Inline Link Implementation

### **Step 2.1: Always-On Rules (5 files)**
**Priority:** High (core system files)

**Files to Update:**
1. `communication-standards.mdc`
   - Add links to: `quality-control.mdc`, `problem-solving.mdc`
   - Reference: `@quality-control.mdc`, `@problem-solving.mdc`

2. `conversation-driven.mdc`
   - Add links to: `transcript-formatting-agent.mdc`, `plan-execute-verify.mdc`
   - Reference: `@transcript-formatting-agent.mdc`, `@plan-execute-verify.mdc`

3. `personal-profile.mdc`
   - Add links to: `communication-standards.mdc`, `security-practices.mdc`
   - Reference: `@communication-standards.mdc`, `@security-practices.mdc`

4. `problem-solving.mdc`
   - Add links to: `communication-standards.mdc`, `quality-control.mdc`
   - Reference: `@communication-standards.mdc`, `@quality-control.mdc`

5. `security-practices.mdc`
   - Add links to: `personal-profile.mdc`, `development-workflow.mdc`
   - Reference: `@personal-profile.mdc`, `@development-workflow.mdc`

### **Step 2.2: Manual Rules (3 files)**
**Priority:** High (workflow files)

**Files to Update:**
1. `development-workflow.mdc`
   - Add links to: `quality-control.mdc`, `problem-solving.mdc`, `plan-execute-verify.mdc`
   - Reference: `@quality-control.mdc`, `@problem-solving.mdc`, `@plan-execute-verify.mdc`

2. `link-context-gathering.mdc`
   - Add links to: `communication-standards.mdc`, `quality-control.mdc`, `problem-solving.mdc`
   - Reference: `@communication-standards.mdc`, `@quality-control.mdc`, `@problem-solving.mdc`

3. `quality-control.mdc`
   - Add links to: `communication-standards.mdc`, `problem-solving.mdc`, `development-workflow.mdc`
   - Reference: `@communication-standards.mdc`, `@problem-solving.mdc`, `@development-workflow.mdc`

### **Step 2.3: Tracking Rules (4 files)**
**Priority:** Medium (specialized files)

**Files to Update:**
1. `manual-testing-tracking-agent.mdc`
   - Add links to: `transcript-formatting-agent.mdc`, `plan-execute-verify.mdc`
   - Reference: `@transcript-formatting-agent.mdc`, `@plan-execute-verify.mdc`

2. `plan-execute-verify.mdc`
   - Add links to: `manual-testing-tracking-agent.mdc`, `transcript-formatting-agent.mdc`
   - Reference: `@manual-testing-tracking-agent.mdc`, `@transcript-formatting-agent.mdc`

3. `plan-generation.mdc`
   - Add links to: `plan-execute-verify.mdc`, `manual-testing-tracking-agent.mdc`
   - Reference: `@plan-execute-verify.mdc`, `@manual-testing-tracking-agent.mdc`

4. `transcript-formatting-agent.mdc`
   - Add links to: `manual-testing-tracking-agent.mdc`, `plan-execute-verify.mdc`
   - Reference: `@manual-testing-tracking-agent.mdc`, `@plan-execute-verify.mdc`

### **Step 2.4: README.md**
**Priority:** High (entry point)

**Updates:**
- Add links to all rule categories
- Reference: `@rules/always-on/`, `@rules/manual/`, `@rules/manual/tracking/`
- Include file counts and descriptions

---

## ✅ Phase 3: Link Verification

### **Step 3.1: External Link Testing**
**Process:**
1. Extract all external URLs
2. Test each with curl for 200 status
3. Document any 404/error responses
4. Find alternative sources for broken links

**Tools:**
```bash
# Test external link
curl -I "https://example.com" | head -1

# Batch test multiple links
for url in $(grep -o 'https://[^)]*' file.mdc); do
  echo "$url: $(curl -s -o /dev/null -w "%{http_code}" "$url")"
done
```

### **Step 3.2: Local File Verification**
**Process:**
1. Check all `@filename.mdc` references
2. Verify file paths are correct
3. Test relative path resolution
4. Update broken local references

**Verification:**
```bash
# Check if referenced file exists
ls -la /path/to/referenced/file.mdc

# Test relative path resolution
find . -name "referenced-file.mdc"
```

### **Step 3.3: Link Format Validation**
**Standards:**
- External links: `[Text](https://url.com)`
- Local references: `@filename.mdc`
- Cross-references: `See @filename.mdc for details`
- Inline mentions: `As defined in @filename.mdc`

---

## 📊 Phase 4: Quality Assurance

### **Step 4.1: Link Coverage Audit**
**Metrics:**
- ✅ 100% of files have inline cross-references
- ✅ 100% of external links return 200 status
- ✅ 100% of local references resolve to existing files
- ✅ No orphaned files without incoming references

### **Step 4.2: Documentation Standards**
**Requirements:**
- Each file has clear purpose statement
- Cross-references explain relationships
- Link descriptions provide context
- Consistent formatting across all files

### **Step 4.3: Testing & Validation**
**Process:**
1. Load each file in Cursor
2. Test all `@` references resolve
3. Verify external links work
4. Check formatting consistency

---

## 🚀 Implementation Timeline

### **Week 1: Audit & Planning**
- [ ] Complete link inventory
- [ ] Map cross-references
- [ ] Identify broken links
- [ ] Create implementation schedule

### **Week 2: Core Files**
- [ ] Update always-on rules (5 files)
- [ ] Update manual rules (3 files)
- [ ] Update README.md
- [ ] Test all changes

### **Week 3: Specialized Files**
- [ ] Update tracking rules (4 files)
- [ ] Verify all cross-references
- [ ] Test external links
- [ ] Final validation

### **Week 4: Quality Assurance**
- [ ] Complete link verification
- [ ] Test all references
- [ ] Update documentation
- [ ] Final review

---

## 📈 Success Metrics

### **Quantitative Goals:**
- ✅ 100% link verification (200 status or local)
- ✅ 100% inline cross-references implemented
- ✅ 0 broken local references
- ✅ 0 broken external links

### **Qualitative Goals:**
- ✅ Clear relationship mapping between files
- ✅ Consistent formatting standards
- ✅ Improved navigation and discoverability
- ✅ Enhanced maintainability

### **Validation Checklist:**
- [ ] All external links tested and working
- [ ] All local references resolve correctly
- [ ] Cross-references provide context
- [ ] No orphaned files
- [ ] Consistent formatting applied
- [ ] Documentation updated

---

## 🔧 Tools & Commands

### **Link Testing Script:**
```bash
#!/bin/bash
# test-links.sh
for file in $(find .cursor -name "*.mdc" -o -name "*.md"); do
  echo "Testing links in: $file"
  grep -o 'https://[^)]*' "$file" | while read url; do
    status=$(curl -s -o /dev/null -w "%{http_code}" "$url")
    echo "  $url: $status"
  done
done
```

### **Local Reference Check:**
```bash
#!/bin/bash
# check-local-refs.sh
for file in $(find .cursor -name "*.mdc" -o -name "*.md"); do
  echo "Checking local references in: $file"
  grep -o '@[^[:space:]]*\.mdc' "$file" | while read ref; do
    ref_file=$(echo "$ref" | sed 's/@//')
    if [ ! -f "$ref_file" ]; then
      echo "  BROKEN: $ref in $file"
    fi
  done
done
```

---

## 📝 Notes & Considerations

### **File Organization:**
- Keep existing folder structure
- Maintain clear separation between always-on and manual rules
- Preserve tracking rules in dedicated subfolder

### **Link Standards:**
- Use `@filename.mdc` for local references
- Use full URLs for external links
- Include context with each reference
- Maintain consistent formatting

### **Quality Assurance:**
- Test all changes in Cursor environment
- Verify cross-references work correctly
- Ensure no circular dependencies
- Maintain backward compatibility

---

**Status:** Planning Complete  
**Next Step:** Begin Phase 1 - Link Audit & Mapping  
**Estimated Duration:** 4 weeks  
**Priority:** High - Core system improvement 