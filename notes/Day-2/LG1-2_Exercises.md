# LG 1-2 Exercises: Establishing Ubiquitous Language

**Duration:** 60-75 minutes  
**Difficulty:** Beginner to Advanced  
**Prerequisites:** Completion of LG 1-1 (Domain, Software, Models)

---

## Table of Contents
1. [Exercise 1: Language Translation Detective](#exercise-1-language-translation-detective)
2. [Exercise 2: Building a Domain Glossary](#exercise-2-building-a-domain-glossary)
3. [Exercise 3: The Ambiguity Hunt](#exercise-3-the-ambiguity-hunt)
4. [Exercise 4: Code Refactoring for Language Alignment](#exercise-4-code-refactoring-for-language-alignment)
5. [Exercise 5: Cross-Context Language Mapping](#exercise-5-cross-context-language-mapping)
6. [Exercise 6: Interview Transcript Analysis](#exercise-6-interview-transcript-analysis)
7. [Exercise 7: Language Evolution Scenario](#exercise-7-language-evolution-scenario)
8. [Bonus Challenge: The Multi-Stakeholder Meeting](#bonus-challenge-the-multi-stakeholder-meeting)

---

## Exercise 1: Language Translation Detective

**Type:** Diagnostic Exercise  
**Time:** 15 minutes  
**Skills:** Identifying language gaps, recognizing translation problems

### Scenario

You're reviewing meeting notes from a VW battery team discussion. Three people were present: Battery Engineer (domain expert), Software Developer, and Product Manager. Read the conversation and identify where language breaks down.

### Meeting Transcript

```
[10:00] Battery Engineer: "We need to implement trickle charging when the pack reaches float voltage to prevent overcharge."

[10:02] Developer: "So when the battery is full, we reduce power?"

[10:03] Engineer: "Not exactly. Float voltage isn't 'full' - it's the voltage where we maintain charge without gassing."

[10:04] Product Manager: "How does this affect charging time estimates for customers?"

[10:05] Developer: "I'll add a flag when battery level hits 100%."

[10:06] Engineer: "No no, float voltage happens around 95% SoC, not 100%."

[10:07] Product Manager: "Wait, so the battery isn't actually full at 100%?"

[10:08] Developer: "I'm confused. Should I check voltage or percentage?"

[10:10] Engineer: "You need to monitor VOLTAGE to detect float condition, which correlates with SoC but isn't the same thing."

[10:12] Product Manager: "Let's step back. Can someone define these terms for me?"
```

### Your Tasks

**Task 1: Identify Communication Breakdowns**

List every instance where someone misunderstood or mistranslated a term. For each, identify:
- What was said
- What was heard/understood
- Why the mismatch occurred

**Task 2: Extract Domain Terms**

Create a list of domain-specific terms that need precise definitions:
```
Term: _______________
Who uses it: _______________
Current ambiguity: _______________
```

**Task 3: Root Cause Analysis**

Answer these questions:
1. Why did the developer think "float voltage" meant "full battery"?
2. What's the difference between SoC (State of Charge) and voltage?
3. Why does the Product Manager need definitions?
4. How could this confusion lead to bugs in production code?

**Task 4: Prevention Strategy**

Propose 3 specific actions this team should take before the next meeting to prevent similar confusion.

### Reflection Questions

- Have you experienced similar conversations in your projects?
- What was the cost (time, rework, bugs) of language misalignment?
- Who is responsible for establishing shared language - the expert or the developer?

---

## Exercise 2: Building a Domain Glossary

**Type:** Guided Construction Exercise  
**Time:** 25 minutes  
**Skills:** Term definition, precision, stakeholder alignment

### Business Context

VW's new ID.Buzz electric van has an advanced thermal management system. The system must keep the battery cool during fast charging, warm during cold weather, and optimize energy efficiency. You're building the software, but first you need a shared language.

### Your Mission

Create a comprehensive domain glossary for the Thermal Management System. For each term, provide:

1. **Term name** (as domain experts use it)
2. **Precise definition** (unambiguous, technical where needed)
3. **Who uses this term** (which roles/teams)
4. **Example usage** (in a sentence, as an expert would say it)
5. **Common misunderstandings** (what people often confuse it with)
6. **Related terms** (how it connects to other concepts)

### Terms to Define

You must define these 12 terms, extracted from thermal engineer interviews:

1. **Ambient Temperature**
2. **Battery Pack Temperature** 
3. **Thermal Runaway**
4. **Cooling Loop**
5. **Heat Exchanger**
6. **Thermal Mass**
7. **Preconditioning**
8. **Temperature Gradient**
9. **Thermal Throttling**
10. **Heat Rejection Rate**
11. **Thermal Soak**
12. **Critical Temperature Threshold**

### Template for Each Entry

```markdown
### Term: [Term Name]

**Definition:**  
[Clear, precise definition that a domain expert would approve]

**Used By:**  
[List roles: thermal engineers, software developers, safety team, etc.]

**Example Usage:**  
"[Quote showing how an expert actually uses this term]"

**Common Misunderstandings:**  
- [What developers often think it means]
- [Why this misunderstanding is dangerous]

**Related Terms:**  
- [Term 1] - [How they're connected]
- [Term 2] - [How they're connected]

**Why This Precision Matters:**  
[Business/safety impact of getting this wrong]
```

### Additional Requirements

**Requirement 1: Precision Test**

After defining each term, ask yourself:
- Could two engineers read this and understand it identically?
- Are there any ambiguous words (like "high," "fast," "significant")?
- Does it specify units, ranges, or thresholds where relevant?

**Requirement 2: Expert Validation (Simulated)**

For 3 of your definitions, write what you imagine a thermal engineer would say if they reviewed it:
- "Yes, this is exactly right because..."
- "No, you're missing that..."
- "Close, but you need to clarify..."

**Requirement 3: Cross-Reference Check**

Create a mini-diagram showing how these 12 terms relate to each other. Use arrows and labels like:
```
Ambient Temperature ──influences──> Battery Pack Temperature
Battery Pack Temperature ──can trigger──> Thermal Runaway
Preconditioning ──prevents──> Thermal Runaway
```

### Challenge Questions

1. **Boundary Question:** Is "fan speed" a domain term or an implementation detail? Why?

2. **Context Question:** Does "temperature" mean the same thing when:
   - Measuring battery cells?
   - Measuring coolant?
   - Measuring cabin air?
   
3. **Evolution Question:** If tomorrow thermal engineers adopt a new term "thermal budget," how would you integrate it into this glossary?

4. **Conflict Question:** What if the thermal engineer says "critical temperature is 60°C" but the safety engineer says "critical temperature is 55°C"? How do you handle conflicting definitions?

---

## Exercise 3: The Ambiguity Hunt

**Type:** Critical Analysis Exercise  
**Time:** 15 minutes  
**Skills:** Detecting imprecision, recognizing context dependency

### Scenario

Below are 10 sentences from VW technical documentation. Each contains ambiguous language that could lead to misunderstandings. Your job: find the ambiguity and fix it.

### Ambiguous Statements

**Statement 1:**  
"The system should charge the battery quickly when the driver needs it."

**Statement 2:**  
"Update the vehicle's location frequently."

**Statement 3:**  
"The lane-keeping system must respond to drift in a timely manner."

**Statement 4:**  
"Store user preferences locally for better performance."

**Statement 5:**  
"The battery management system monitors temperature closely."

**Statement 6:**  
"Alert the driver when the battery is low."

**Statement 7:**  
"The navigation system should provide accurate routing."

**Statement 8:**  
"Charge to full capacity unless the user prefers otherwise."

**Statement 9:**  
"The system adapts to driving style automatically."

**Statement 10:**  
"Engage regenerative braking aggressively to maximize range."

### Your Tasks

For each statement, provide:

**1. Identify the Ambiguity**
```
Ambiguous word/phrase: _______________
Why it's ambiguous: _______________
What could go wrong: _______________
```

**2. Rewrite with Precision**
```
Original: [ambiguous statement]
Precise: [rewritten using ubiquitous language with specifics]
```

**3. Define New Terms (if needed)**
```
If your rewrite introduces domain terms, define them:
Term: _______________
Definition: _______________
```

### Example

**Original:** "The system should charge the battery quickly when the driver needs it."

**Ambiguity Identified:**
- "quickly" - How fast? 30 minutes? 2 hours?
- "when the driver needs it" - How does system know when driver needs it?
- "charge" - To what level? 80%? 100%?

**Precise Rewrite:**  
"The system shall initiate DC fast charging (minimum 100kW) to reach 80% State of Charge within 30 minutes when driver selects 'Rapid Charge' mode or when current SoC drops below 15% and navigation destination exceeds remaining range."

**New Terms Defined:**
- **DC Fast Charging:** Charging using direct current at power levels ≥50kW via CCS connector
- **Rapid Charge Mode:** User-selected charging profile prioritizing speed over battery longevity
- **Remaining Range:** Distance vehicle can travel with current SoC under current driving conditions

### Reflection

After completing all 10:
1. What patterns did you notice in types of ambiguity?
2. Which statement was hardest to make precise? Why?
3. How much longer are the precise versions? Is the extra length worth it?

---

## Exercise 4: Code Refactoring for Language Alignment

**Type:** Hands-On Refactoring Exercise  
**Time:** 20 minutes  
**Skills:** Applying ubiquitous language to code, renaming for clarity

### The Problem

A developer wrote this VW infotainment code without domain knowledge. The code works but doesn't speak the domain language. Your job: refactor it to use ubiquitous language.

### Original Code (What NOT to Do)

```java
class System {
    int val1, val2;
    boolean flag;
    String data;
    
    void process() {
        if (val1 > 50 && !flag) {
            val2 = calculate(data);
            flag = true;
        }
    }
    
    int calculate(String s) {
        // complex logic
        return 42;
    }
    
    void update(int x) {
        val1 = x;
        if (val1 > 80) {
            reset();
        }
    }
    
    void reset() {
        val1 = 0;
        val2 = 0;
        flag = false;
        data = "";
    }
}
```

### Domain Context (From Expert Interview)

After interviewing the infotainment product manager, you learned:

- This system manages **Media Source Selection**
- `val1` represents **User's Volume Level** (0-100)
- `val2` represents **Recommended Volume** based on speed
- `flag` indicates **Speed-Based Volume Adjustment Enabled**
- `data` contains **Current Media Source ID** (radio/bluetooth/usb)
- `process()` should be **Adjust Volume Based On Speed**
- `calculate()` computes **Optimal Volume For Driving Speed**
- `update()` is **Set User Volume Preference**
- `reset()` returns to **Default Audio Settings**

### Your Tasks

**Task 1: Create Ubiquitous Language Glossary**

Before refactoring, define these terms:

```
1. Media Source
2. User Volume Preference  
3. Recommended Volume
4. Speed-Based Volume Adjustment
5. Optimal Volume
6. Default Audio Settings
```

**Task 2: Refactor the Class**

Rewrite the ENTIRE class using ubiquitous language:
- Rename class
- Rename all variables
- Rename all methods  
- Add meaningful comments that use domain terms
- Introduce value objects if appropriate (e.g., VolumeLevel, MediaSource)

**Task 3: Before/After Comparison**

Create a table:

| Element | Before (Technical) | After (Domain) | Why This Matters |
|---------|-------------------|----------------|------------------|
| Class name | System | ??? | ??? |
| val1 | int val1 | ??? | ??? |
| flag | boolean flag | ??? | ??? |
| process() | void process() | ??? | ??? |
| etc... | | | |

**Task 4: Validation**

Write 3 test method names using ubiquitous language:
```java
@Test
public void should___When___() {
    // test using domain terms
}
```

### Challenge Extension

The product manager now says: "We need to remember the user's preferred volume for each media source separately."

How would you extend your refactored code to handle this new requirement? Show:
1. New terms to add to glossary
2. Code changes using those terms
3. How ubiquitous language made this extension clearer

---

## Exercise 5: Cross-Context Language Mapping

**Type:** Advanced Boundary Exercise  
**Time:** 20 minutes  
**Skills:** Context mapping, term disambiguation, translation points

### Business Scenario

VW has discovered that the word **"Vehicle"** means different things in different parts of the organization:

**Manufacturing Context:**
"Vehicle" = Unit being assembled on production line, tracked by build sequence number

**Sales Context:**  
"Vehicle" = Configured product with VIN, pricing, options that customer can purchase

**Service Context:**
"Vehicle" = Asset with maintenance history, owned by specific customer, tracked by mileage

**Connected Services Context:**
"Vehicle" = IoT device with connectivity status, sending telemetry data

**Fleet Management Context:**
"Vehicle" = Business asset with TCO, utilization metrics, assigned to drivers

### Your Tasks

**Task 1: Create Context-Specific Glossaries**

For EACH context, define "Vehicle" with precision:

```markdown
### Context: Manufacturing

**Term:** Vehicle
**Definition in this context:** _______________
**Key Attributes:**
- _______________
- _______________
**What matters here:** _______________
**What doesn't matter:** _______________
```

Repeat for all 5 contexts.

**Task 2: Identify Translation Points**

When information moves between contexts, translation happens. Map it:

```
Manufacturing → Sales
Translation Point: When vehicle completes final quality inspection and enters dealer inventory

What changes:
- "Build Sequence #" becomes "Stock Number"
- "Production Status" becomes "Availability Status"  
- [What else?]

Who is responsible for translation: _______________
What could go wrong: _______________
```

Create translation maps for:
1. Manufacturing → Sales
2. Sales → Connected Services
3. Connected Services → Service
4. Service → Fleet Management

**Task 3: Find the Anti-Corruption Layer**

One of these translations needs an Anti-Corruption Layer (ACL) - a pattern that prevents one context's model from corrupting another.

Which transition needs an ACL? Why? How would you implement it?

**Task 4: Unified Term or Separate Terms?**

Make a decision: Should VW use:
- **Option A:** One term "Vehicle" with context-specific meanings (current state)
- **Option B:** Different terms per context (e.g., "AssemblyUnit", "SalesUnit", "ServiceAsset", "ConnectedDevice", "FleetAsset")

Justify your choice with:
- Pros and cons of each approach
- Impact on communication  
- Impact on code
- Recommendation with rationale

### Advanced Challenge

A new requirement arrives: "We need a dashboard showing the complete lifecycle of every vehicle from manufacturing through to service history."

This crosses ALL contexts. How do you:
1. Name the objects/concepts for this cross-context view?
2. Avoid polluting individual contexts with cross-cutting concerns?
3. Maintain clear ubiquitous language?

---

## Exercise 6: Interview Transcript Analysis

**Type:** Knowledge Crunching Exercise  
**Time:** 20 minutes  
**Skills:** Extracting domain language from conversations, glossary building

### Scenario

You recorded an interview with VW's ADAS (Advanced Driver Assistance Systems) expert about the Traffic Jam Assist feature. Extract ubiquitous language from the conversation.

### Interview Transcript

```
You: Can you explain how Traffic Jam Assist works?

Expert: Sure. TJA is designed for low-speed congestion scenarios on highways. It combines adaptive cruise control with lane centering to basically drive the car for you under specific conditions.

You: What conditions exactly?

Expert: Speed has to be below 60 kilometers per hour, and we need clear lane markings with detection confidence above our threshold - I think it's 75% or 80%, something like that. The driver also has to keep hands on the wheel. We monitor that through torque sensors.

You: What happens if conditions aren't met?

Expert: The system goes into standby mode. We give the driver a visual and audio prompt that says "Traffic Jam Assist unavailable." If they had it active and conditions degrade - say lane markings disappear in construction zone - we do a graduated handover. First a warning, then if no driver response after 5 seconds, we escalate warnings and start reducing speed.

You: How does it handle steering?

Expert: We calculate the optimal path to keep the vehicle centered in lane. The system makes micro-adjustments to steering angle - very smooth, not jerky like early systems. But it's not autopilot. We call it "assistance," not "automation," because the driver must remain engaged and supervise the system at all times.

You: What about edge cases like lane splits or merges?

Expert: Good question. Lane splits confuse the hell out of most systems. If we detect lane ambiguity - like two lanes diverging - we immediately hand back control. Can't guess which lane the driver wants. Same with merge lanes. We consider those outside our operational design domain, or ODD.

You: ODD?

Expert: Operational Design Domain - it's the specific conditions under which the system is designed to function. For TJA, the ODD is: highways with clear lane markings, speeds under 60 kph, moderate traffic density, good weather visibility, and defined lane boundaries. Anything outside that, we gracefully deactivate.
```

### Your Tasks

**Task 1: Extract Domain Terms**

Create a table of every domain-specific term. For each:

| Term | First Appearance | Preliminary Definition | Needs Clarification? |
|------|------------------|------------------------|---------------------|
| TJA | Line 3 | Traffic Jam Assist? | Yes - what's formal name? |
| ... | ... | ... | ... |

Extract at least 15 terms.

**Task 2: Identify Ambiguities**

Find 5 places where the expert's language is imprecise or ambiguous:
1. "something like that" (regarding threshold)
2. ... (find 4 more)

For each, write a follow-up question to get precision.

**Task 3: Build Preliminary Glossary**

Choose 8 most important terms and create full glossary entries:

```markdown
### Term: Operational Design Domain (ODD)

**Definition:** 
The specific set of environmental, traffic, and vehicle conditions under which an automated driving system is designed to function correctly and safely.

**Used By:**
- ADAS engineers
- Safety validation team  
- Regulatory compliance team

**Example from Expert:**
"For TJA, the ODD is: highways with clear lane markings, speeds under 60 kph..."

**Key Characteristics:**
- Defines system boundaries
- Includes environmental conditions (weather, lighting)
- Includes road conditions (lane markings, traffic)
- Includes speed ranges
- Anything outside ODD requires system deactivation

**Related Terms:**
- Standby Mode (what happens when outside ODD)
- Graceful Deactivation (how system exits when ODD violated)
- Graduated Handover (process of returning control to driver)

**Why Precision Matters:**
Safety-critical. If ODD not clearly defined, system might operate in unsafe conditions or drivers might over-rely on it.
```

**Task 4: Follow-Up Questions**

Write 10 questions you would ask in the next interview to clarify terms and eliminate ambiguity. Prioritize by importance.

### Reflection

- How much domain knowledge did you extract from 15 lines of conversation?
- What made certain terms easy vs. hard to define?
- How would you validate these definitions with the expert?

---

## Exercise 7: Language Evolution Scenario

**Type:** Scenario-Based Decision Making  
**Time:** 15 minutes  
**Skills:** Handling language changes, refactoring triggers, team alignment

### Initial State

Six months ago, your team established this ubiquitous language for VW's charging system:

```
Charging Session: Period from cable plug-in to disconnect
Fast Charging: Charging at >50kW
Normal Charging: Charging at <50kW
Session Cost: Total amount billed to customer
Energy Delivered: kWh transferred to battery
```

Your codebase extensively uses these terms.

### The Change

The charging team has new insights from field data and wants to update terminology:

**Proposed Changes:**
1. "Fast Charging" → "DC Rapid Charging" (more precise, aligns with industry)
2. "Normal Charging" → "AC Standard Charging" (distinguishes AC/DC)
3. Add new term: "Ultra-Rapid Charging" (>150kW, new capability)
4. "Session Cost" → "Energy Transaction Cost" (includes taxes, fees, not just energy)
5. Split "Charging Session" into "Connection Session" (physical) and "Billing Session" (financial)

### Your Tasks

**Task 1: Impact Analysis**

For each proposed change, assess:

| Change | Code Impact | Communication Impact | Should We Accept? | Why/Why Not? |
|--------|-------------|---------------------|-------------------|--------------|
| Fast → DC Rapid | Search codebase: 247 occurrences | Customer-facing UI labels | ??? | ??? |
| ... | ... | ... | ... | ... |

**Task 2: Change Management Plan**

You decide to accept changes #1, #2, and #3. Reject #4 and #5 for now. Create a plan:

**Phase 1: Update Glossary**
- When: _______________
- Who: _______________
- Deliverable: _______________

**Phase 2: Communicate Changes**
- Announce to: _______________
- Message: _______________
- Timeline: _______________

**Phase 3: Code Refactoring**
- Rename: "FastCharging" → "DCRapidCharging"
- Affected files: _______________
- Test strategy: _______________  
- Rollout: _______________

**Phase 4: Documentation Update**
- Technical docs: _______________
- User docs: _______________
- API contracts: _______________

**Task 3: Rejection Rationale**

You rejected changes #4 and #5. Write an email to the charging team explaining:
- Why you're rejecting these changes
- What problems they cause
- Alternative solutions
- What would need to change for you to accept them later

**Task 4: Forward Compatibility**

How do you design code so future language changes are less painful?

Provide 3 concrete strategies:
1. _______________
2. _______________
3. _______________

### Discussion Questions

- Should domain experts have final say on terminology changes?
- How do you balance "accuracy" vs. "stability" of language?
- When is it worth refactoring thousands of lines of code for terminology?

---

## Bonus Challenge: The Multi-Stakeholder Meeting

**Type:** Comprehensive Integration Exercise  
**Time:** 30 minutes  
**Skills:** Facilitation, conflict resolution, consensus building

### Scenario

You're facilitating a workshop to establish ubiquitous language for VW's new "Battery Health Optimization" feature. Five stakeholders attend, each with their own vocabulary:

**Battery Engineer (Domain Expert):**
- Talks about "cell impedance," "capacity fade," "cycle depth"
- Very precise, uses industry jargon

**Software Developer:**
- Thinks in terms of "data structures," "algorithms," "optimization functions"
- Wants clean code, not complex domain terms

**Product Manager:**
- Uses customer-facing language: "battery life," "range anxiety," "peace of mind"
- Wants features that sell

**UX Designer:**
- Focuses on "user mental model," "intuitive terminology," "clear communication"
- Wants simplicity for users

**Legal/Compliance:**
- Concerned about "warranty claims," "liability," "regulatory requirements"
- Wants precise, defensible language

### The Discussion

They're trying to define what to call the system feature. Here's the conversation:

```
Battery Engineer: "We're implementing active cell balancing to minimize capacity fade through algorithmic impedance equalization."

Developer: "So... we're making the battery last longer?"

Product Manager: "Can we call it 'Battery Lifespan Extension'? Customers understand that."

UX Designer: "Too technical. How about 'Battery Care'?"

Engineer: "That's way too vague. We're not 'caring' for it, we're actively managing charge distribution."

Legal: "Whatever we call it, we can't promise 'extended life.' That's a warranty claim waiting to happen."

Developer: "Why don't we just call it 'Battery Optimization Service'?"

Everyone: [talks over each other]
```

### Your Tasks

**Task 1: Stakeholder Analysis**

For each stakeholder, document:

```
Stakeholder: Battery Engineer
Primary Concern: Technical accuracy
Language Preference: Precise scientific terms
Fear: Dumbing down loses important nuances
Needs: Must be able to explain feature to peers

[Repeat for all 5]
```

**Task 2: Find Common Ground**

Identify the ONE thing all stakeholders agree on about this feature. Build from there.

**Task 3: Propose Terminology**

Create a two-tier terminology system:

**Internal Ubiquitous Language (Engineers & Developers):**
- Feature Name: _______________
- Core Concepts: _______________
- Technical Precision: HIGH

**External Customer-Facing Language (Product & UX):**
- Feature Name: _______________
- Marketing Message: _______________
- Technical Precision: MEDIUM, Clarity: HIGH

**Legal-Safe Language (Compliance):**
- Feature Name: _______________
- Warranty Language: _______________
- Makes no unsupportable claims: YES/NO

**Task 4: Glossary That Bridges Worlds**

Create glossary entries that satisfy ALL stakeholders:

```markdown
### Term: [Your Proposed Term]

**Technical Definition (Internal):**
[Precise definition for engineers]

**Customer-Facing Definition (External):**
[Clear explanation for users]

**Legal-Approved Wording:**
[Defensible language for warranties/docs]

**Mapping:**
Engineer says: "active cell balancing"
Product says: "battery health optimization"  
UX shows: "Battery Care"
Code uses: [your choice]

All refer to the SAME concept.
```

**Task 5: Meeting Facilitation Guide**

Write a 1-page guide for facilitating similar workshops:
- How to elicit each stakeholder's concerns
- Techniques for finding shared language
- When to create separate internal/external terms
- How to get consensus

### Success Criteria

Your solution is successful if:
- [ ] Battery engineer feels precision is maintained
- [ ] Developer can write clean, understandable code
- [ ] Product manager can sell the feature
- [ ] UX designer can create intuitive interface
- [ ] Legal approves the language
- [ ] All five agree on the glossary

---

## Submission Guidelines

**For GitHub Discussion Submission:**

1. **Title Format:** `LG 1-2 Submission - [Your Name] - [Exercise Number]`

2. **Structure Your Response:**
```markdown
## Exercise [Number]: [Title]

### My Solution
[Your detailed work]

### Approach
[How you tackled it]

### Challenges Encountered
[What was difficult and why]

### Questions for Discussion
[What you're unsure about or want to debate]

### Real-World Connection
[How this applies to your actual VW projects]
```

3. **Use Tables and Formatting:**
   - Tables for comparisons
   - Code blocks for glossary entries
   - Bullet points for lists
   - Bold for emphasis on key terms

4. **Be Specific:**
   - Instead of "This is better," explain "This reduces ambiguity by specifying units (km/h vs mph)"
   - Reference specific lines from exercises
   - Cite domain knowledge sources when possible

---

## Self-Assessment Rubric

Rate yourself after completing exercises:

| Learning Objective | Not Yet | Partially | Achieved | Mastered |
|--------------------|---------|-----------|----------|----------|
| I can identify when language is ambiguous or imprecise | ☐ | ☐ | ☐ | ☐ |
| I can create glossary entries that domain experts would approve | ☐ | ☐ | ☐ | ☐ |
| I can refactor code to use ubiquitous language | ☐ | ☐ | ☐ | ☐ |
| I understand how language differs across bounded contexts | ☐ | ☐ | ☐ | ☐ |
| I can facilitate discussions to establish shared language | ☐ | ☐ | ☐ | ☐ |
| I can handle language evolution without breaking systems | ☐ | ☐ | ☐ | ☐ |

**If you marked "Not Yet" on any:** Review the guide section on that topic, consult solutions, retry the exercise.

**If you marked "Achieved" on all:** You're ready for LG 1-3 (DDD Building Blocks).

---

## Going Deeper: Additional Practice

1. **Your Project Audit:**  
   Take a real meeting transcript or design doc from your VW project. Identify every ambiguous term. Create a glossary.

2. **Code Review for Language:**  
   Review a colleague's code. Count how many class/method names use domain language vs. technical jargon. Propose refactorings.

3. **Stakeholder Interview:**  
   Actually interview a VW domain expert (battery engineer, ADAS specialist, etc.). Practice extracting ubiquitous language. Share your glossary with them for validation.

4. **Cross-Team Glossary:**  
   If you work across multiple teams/contexts, map how the same term means different things. Create a translation guide.

5. **Language Evolution Tracking:**  
   Start a log of how terminology changes in your project over time. Identify patterns. When do changes happen? What triggers them?
