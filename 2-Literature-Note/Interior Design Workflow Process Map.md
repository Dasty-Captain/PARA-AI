---
tags: 
- literature-note
- workflow
- interior-design
- process-map
creation_date: 2025-10-20 10:00
---
## Summary
***
> [!quote] Summary in a few sentences
> > This note provides a comprehensive map of the interior design workflow, from initial client discovery to project implementation. It details each phase, identifies major pain points, lists common software tools, and highlights opportunities for AI automation, based on extensive industry research and user interviews.

## Content
***
🏗️ Interior Design Workflow: Comprehensive Process Map
Based on extensive user interviews (UK architects, Japanese firms, Korean professionals, VMD designers) and industry research, here's the complete interior design workflow from scratch.
---
## 🎯 Overview: Two Main Scenarios
### Scenario A: New Construction (Ground Up)
**Timeline:** 12-24+ months | **Stakeholders:** Architects, Interior Designers, Structural Engineers, MEP Consultants
### Scenario B: Renovation/Remodeling
**Timeline:** 2-6 months | **Stakeholders:** Interior Designers, Contractors, Client
---
## 📋 Phase 1: Initial Planning & Concept (Weeks 1-4)
### 1.1 Client Discovery & Brief
**Activities:**
- Initial consultation meeting (1-2 hours)
- Understanding client vision, budget, timeline
- Site visit and measurement
- Collecting existing drawings (if available)
**Pain Points:**
- **Manual measurement is time-consuming** - often requires multiple site visits
- Missing dimensions lead to rework
- Existing drawings often unavailable or outdated
**Tools Used:** Tape measure, laser measurement tools, photography
---
### 1.2 Feasibility & Legal Review
**Activities:**
- Building code compliance check
- Zoning regulations (floor area ratio, building coverage ratio)
- Parking requirements calculation
- Structural constraints assessment
**Pain Points:**
- **Coordination between architecture and interior is difficult**
- Missing elements in architectural drawings (bathroom fixtures, accessibility features)
- Communication gaps between architects and interior designers
**Key Standards:**
- **UK:** RIBA (Royal Institute of British Architects) Stages 1-7
- **Korea/Asia:** Similar phased approach with local building codes
---
## 🎨 Phase 2: Design Development (Weeks 4-12)
### 2.1 Concept Design (RIBA Stage 2-3)
**Activities:**
- Mood boards and visual presentations
- Multiple design alternatives (typically 2-4 options)
- Space planning and layout options
- Initial material palette selection
**Tools:**
- **Photoshop, InDesign** - for presentations
- **AutoCAD** - for 2D floor plans
- Reference images and inspiration boards
**Pain Points:**
- **Creating multiple design alternatives consumes massive resources**
- Uncertainty about which layout is optimal
- Client often requests to see many variations (5+ revisions typical)
**Timeline:** 2-4 weeks for initial concepts
**Typical Revisions:** 3-5 rounds with client
---
### 2.2 2D Floor Plan Development
**Activities:**
- Creating as-built drawings (existing conditions)
- Demolition plans
- New layout with furniture placeholders
- Door/window locations
- Circulation paths
**Workflow:**
1. **Site measurement** → Manual measurement with tape/laser
2. **CAD drawing** → Create 2D floor plan in AutoCAD
3. **Space allocation** → Place furniture placeholders
4. **Initial review** → Client feedback on layout
**Pain Points:**
- **2D to 3D conversion is time-consuming** (mentioned across all interviews)
- Furniture placement is repetitive for large projects (500+ chairs in office buildings)
- Manual work for each furniture piece
---
### 2.3 3D Modeling (RIBA Stage 3-4)
**Activities:**
- Converting 2D plans to 3D models
- Wall extrusion and room creation
- Furniture and fixture placement
- Material application
- Lighting setup
**Tools Used:**
- **SketchUp** - Most common for interior designers (easy, flexible)
- **Revit** - More common for architectural firms (BIM, collaboration)
- **Enscape** - For visualization
**Typical Workflow:**
```javascript
2D AutoCAD Floor Plan
    ↓
Import to SketchUp/Revit
    ↓
Extrude walls manually
    ↓
Place furniture one by one
    ↓
Apply materials (100+ combinations tested)
    ↓
Create views for rendering
```
**Pain Points:**
- **Material selection takes 2-3 days** - testing 100+ combinations
- **Furniture placement is tedious** - especially for large projects
- **File compatibility issues** between different software (.skt, .rvt, .dwg)
- **Host connections break** when walls move in Revit
- **Collaboration conflicts** when multiple people edit same model
**Time Investment:**
- Wall modeling: 0.5-1 day
- Furniture placement: 1-2 days (small project) to 1+ week (large project)
- Material application: 2-3 days
- **Total: 1-2 weeks for 3D modeling phase**
---
### 2.4 Specification Development
**Activities:**
- Product selection and sourcing
- Material specifications
- Finish schedules
- FF&E (Furniture, Fixtures & Equipment) specifications
**Tools:**
- **Revit families** - Reusable component library
- Product catalogs and databases
- Vendor websites
**Pain Points:**
- **No standardized libraries** for legally-required elements
- **Product information mapping is manual** - barcodes, codes, classifications
- Finding actual purchasable products with pricing is difficult
---
## 🖼️ Phase 3: Visualization & Client Review (Weeks 8-16)
### 3.1 Rendering & Post-Production
**Activities:**
- Creating photo-realistic renders
- Multiple camera angles
- Lighting studies
- Post-processing in Photoshop
**Tools:**
- **Enscape** - Quick rendering from SketchUp
- **V-Ray, Corona** - High-quality rendering
- **Photoshop** - Post-production (most time-consuming)
**Pain Points:**
- **SketchUp rendering quality is limited**
- **Post-processing takes significant time** - manual adjustments
- Creating variations for client requires re-rendering each time
**Timeline:** 3-5 days per design option
---
### 3.2 Client Review & Revisions (RIBA Stage 3-4)
**Activities:**
- Design review meetings (weekly or bi-weekly)
- Presenting 3D renders and walk-throughs
- Collecting feedback and revision requests
- Making design modifications
**Typical Revision Cycle:**
- **Per drawing:** Up to 8 revisions
- **Per project:** 400+ drawings typical for large projects
- **Client meetings:** 10+ times for small residential projects
- **Maximum revisions offered:** Typically 5 rounds (clients usually use all)
**Common Revision Requests:**
- Wall dimension changes (\"make this wall narrower\")
- Material/finish changes (\"lighter wall color\")
- Furniture type changes
- Layout rearrangements
**Pain Points:**
- **Each revision cycle takes 1-2 weeks**
- **No automatic change tracking** in shared models
- **Frequent client changes are normal** - budget 3-5 revision rounds minimum
- **Uncertainty about design decision** - \"Is there a better layout?\"
**Revision Timeline:** 2-3 days per round × 5 rounds = **2-3 weeks total**
---
## 📐 Phase 4: Construction Documentation (Weeks 16-24)
### 4.1 Detailed Drawings
**Activities:**
- Construction drawings at 1:50 or 1:20 scale
- Reflected ceiling plans
- Electrical and lighting plans
- Plumbing fixture locations
- Millwork details
- Section and elevation drawings
**Pain Points:**
- **Architectural drawings often lack interior details**
- **MEP (mechanical, electrical, plumbing) coordination issues** arise on-site
- **Building vs. interior contractor territory conflicts**
---
### 4.2 Coordination & Approval
**Activities:**
- Coordination with architects, engineers, and contractors
- Building department approvals
- Final client sign-off
**Stakeholder Coordination:**
- Architect (building shell)
- Interior Designer (interior fit-out)
- Structural Engineer
- MEP Engineers (often overlooked, causing on-site conflicts)
- General Contractor
- Specialty Contractors
**Timeline:** 1-2 months for coordination and approvals
---
## 🔨 Phase 5: Implementation (Months 6-12+)
### 5.1 Procurement
**Activities:**
- Ordering furniture and fixtures
- Material procurement
- Lead time management
- Quality control
### 5.2 Construction Administration
**Activities:**
- Site visits and inspections
- Answering contractor questions
- Reviewing submittals
- Managing field changes
**Pain Points:**
- **On-site issues from inadequate drawing review**
- **Territory disputes** between building and interior contractors
- Changes discovered during construction requiring redesign
---
## 📊 Key Metrics & Benchmarks
### Project Timelines (from interviews)
**Stage 3 → Stage 4 (UK RIBA):**
- **6+ months typical**
- Complex projects: 12+ months
**Full Project (concept → completion):**
- Small residential: 3-6 months
- Commercial/Office: 12-18 months
- Large mixed-use: 24-36 months
### Resource Allocation
**Samsung Electronics Example (Double Diamond):**
- First Diamond (Concept): 6-7 months, 400 early-stage + 800 production designers
- Second Diamond (Production): 5-6 months, same team
- **Total traditional cycle: 12 months** (can be reduced to 3 months with AI)
### Cost Breakdowns
**Designer Time Allocation:**
- Initial concept & mood boards: 10-15%
- 2D floor planning: 10-15%
- **3D modeling & furniture placement: 25-30%**
- **Material selection & testing: 15-20%**
- **Rendering & post-production: 15-20%**
- Client meetings & revisions: 15-20%
---
## 🔧 Software Ecosystem
### Architecture Firms
**Primary:** Revit (BIM, collaboration, parameter-based)
**Secondary:** AutoCAD (2D), Enscape (visualization)
### Interior Design Studios
**Primary:** SketchUp (flexibility, ease of use, design-focused)
**Secondary:** AutoCAD (2D), Photoshop (post-production)
### Rendering
- Enscape (real-time, SketchUp/Revit plugin)
- V-Ray, Corona (high quality)
- Lumion, Twinmotion (real-time)
### Collaboration Gap
**File exchange format:** DWG (2D drawings)
**Challenge:** Different file formats (.rvt, .skt, .dwg) cause compatibility issues
---
## 🚨 Critical Pain Points Summary
### Top 5 Pain Points (from all interviews)
### 1. **2D → 3D Conversion is Time-Consuming**
- Manual wall extrusion
- One-by-one furniture placement
- Repetitive for every project
- **Time: 3-5 days per project**
### 2. **Material Selection & Testing**
- Testing 100+ material combinations
- No way to preview multiple options quickly
- Post-production in Photoshop time-intensive
- **Time: 2-3 days per project**
### 3. **Design Alternative Generation**
- Creating multiple layout options is resource-intensive
- Uncertainty about which design is optimal
- Going deep into one design then having to start over
- **Impact: Significant rework and wasted effort**
### 4. **Client Revisions are Frequent & Manual**
- 5-8 revision rounds typical
- Each round: 1-2 weeks
- Manual updates to walls, furniture, materials
- **Time: 2-3 weeks total for revisions**
### 5. **Coordination Between Architecture & Interior**
- Architectural drawings lack interior details
- Communication gaps cause on-site issues
- File format incompatibilities
- **Impact: Delays and rework during construction**
---
## 💡 Opportunities for AI Automation
Based on interview insights:
### High-Value Areas:
**1. Automated 2D → 3D Conversion**
- DXF/DWG file input → automatic 3D model generation
- Wall recognition and extrusion
- Furniture auto-placement based on room type
- **Potential time savings: 5% of total project time (initial stages)**
**2. AI-Assisted Material Selection**
- Reference image-based material matching
- Quick generation of multiple material schemes
- **Potential time savings: 2-3 days per project**
**3. Design Alternative Generation**
- Multiple layout options from single brief
- Space optimization algorithms
- Quick iteration on variations
- **Value: Explore more options in less time**
**4. Parametric Revision Management**
- Chat-based design modifications (\"move wall 2 meters\")
- Instant furniture type swapping
- Quick material changes
- **Potential time savings: 50% reduction in revision time**
### Platform Preferences:
**For Interior Market:**
- **SketchUp plugin preferred** (most used by interior designers)
- Revit plugin for architecture firms
- Standalone web tool for initial stages
**Pricing Expectations:**
- \\~\\$40/month per user for SMB interior studios
- Enterprise pricing for large firms
---
## 🌐 Regional Variations
### UK (RIBA Standards)
- Formal 7-stage process (Stage 1-7)
- Strong emphasis on Stage 3-4 (detailed design)
- Photoshop/InDesign heavy for presentations
### Japan
- AI adoption still early in architecture/CAD space
- Focus on ideation phase (not final production)
- Interest in DXF-based 3D generation
### Korea
- Competitive commercial/retail interior market
- Fast turnaround requirements (1-month projects common)
- Price-sensitive (need cost estimation features)
---
## 📈 Industry Trends
### Emerging Technologies:
- **BIM (Building Information Modeling)** - Standard in architecture firms
- **Real-time rendering** - Enscape, Twinmotion adoption growing
- **AI rendering** - Early adoption for concept stages
- **Parametric design** - Grasshopper, Dynamo for complex projects
### Market Drivers:
- **Faster project turnaround** - clients expect quicker delivery
- **More design options** - clients want to see multiple alternatives
- **Better visualization** - photo-realistic renders are standard
- **Cost transparency** - need for accurate pricing early
---
## 🎓 Key Takeaways
1. **Interior design workflow has distinct phases** - Planning → Design → Documentation → Implementation
2. **Pain points are consistent across geographies** - 2D→3D conversion, material selection, revisions
3. **Early stages offer most automation opportunity** - Initial modeling and material application (5% time savings)
4. **Later stages require precision** - Designers prefer manual control for final detailing
5. **SketchUp dominates interior design** - Platform choice critical for market penetration
6. **Client revisions are inevitable** - Tools must support rapid iteration
7. **Architecture ≠ Interior** - Different tools, workflows, and stakeholders
---
*This workflow map synthesized insights from 7 user interviews (UK architects, Japanese firms, Korean professionals, VMD designers) and industry research on interior design processes.*

## References
***
- [Interior Design Workflow: Comprehensive Process Map](https://www.notion.so/ease-teamspace/Interior-Design-Workflow-Comprehensive-Process-Map-71d593afb04e480aa5cc73029c94fab7)

## Related Notes
***
- [[Quick Note/Interior General Work Process.md]]
- [[Clippings/Interior Consulting Market Size.md]]
- [[Clippings/Interior Designers Pain Points.md]]
- [[Clippings/Office Interior Design Problems.md]]
