# LG 1-1 Exercises: Understanding Domain, Software & Models

**Duration:** 45-60 minutes  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Basic software development experience

---

## Exercise 1: Domain Identification & Boundary Detection

**Type:** Guided Exercise  
**Time:** 15 minutes  
**Skills:** Domain analysis, boundary recognition

### Scenario

You're joining VW Group's new Software-Defined Vehicle (SDV) platform team. Your first task is to identify the major domains that will need to be modeled in the new architecture.

### Task

For each of the following VW business areas, determine:

1. Is this a single domain or multiple domains?
2. What are the core concepts?
3. Where are the natural boundaries?
4. Who are the domain experts?

**Business Areas:**
- Vehicle manufacturing and assembly
- Customer sales and financing
- After-sales service and maintenance
- Connected vehicle services
- Autonomous driving features

### Guided Steps

**Step 1:** Start with "Vehicle manufacturing and assembly"

Consider these questions:
- Does the robot on the assembly line care about customer financing? (Boundary test)
- Does the quality inspector use the same language as the supply chain manager? (Language test)
- Can manufacturing change independently from sales? (Coupling test)

**Your Analysis:**
```
Domain Name: _______________________
Core Concepts (5-7 terms): _______________________
Domain Experts: _______________________
Boundaries (what's excluded): _______________________
```

**Step 2:** Repeat for the remaining business areas

### Success Criteria

✓ Identified 8-12 distinct domains  
✓ Each domain has clear ownership  
✓ Boundaries make sense (minimal overlap)  
✓ Domain concepts are specific, not generic

### Discussion Prompts

- Did you combine any areas into one domain? Why?
- Where did you draw boundaries? What was your reasoning?
- Which domains will likely interact the most? How should they communicate?

---

## Exercise 2: Model vs Reality - The Abstraction Challenge

**Type:** Unguided Exercise  
**Time:** 20 minutes  
**Skills:** Abstraction, model design, critical thinking

### Scenario

VW is building a new dealer inventory management system. A "vehicle" in the real world is incredibly complex: 30,000+ parts, intricate wiring, software systems, paint chemistry, etc.

### Your Task

Create TWO different models of a "Vehicle" for these two different purposes:

**Purpose 1: Dealer Lot Management**
- Problem: Track vehicles on lot, manage test drives, process sales

**Purpose 2: Service Department Warranty Claims**
- Problem: Validate warranty coverage, track repairs, order parts

### What to Deliver

For each model, specify:

1. **Entity/Concept Name** (e.g., Vehicle, VehicleInstance, WarrantyAsset)
2. **5-8 Key Attributes** (what properties matter for this purpose?)
3. **3-5 Behaviors/Methods** (what can you do with this model?)
4. **What You Deliberately Excluded** (what real-world details did you ignore and why?)

### Example Template

```
MODEL: [Name]
PURPOSE: [Specific problem being solved]

ATTRIBUTES:
- attribute1: type (why this matters)
- attribute2: type (why this matters)
...

BEHAVIORS:
- method1(): return_type (what business rule this enforces)
- method2(): return_type (what business rule this enforces)
...

DELIBERATELY EXCLUDED:
- [Real-world aspect] - Reason: [Why it doesn't matter for this purpose]
...

RATIONALE:
[2-3 sentences explaining your abstraction choices]
```

### Challenge Questions

1. Did your two models end up completely different? Should they?
2. If both models need VIN (Vehicle Identification Number), should it mean the same thing in both?
3. Could one system use both models? How would they relate?

### What We're Looking For

- **Focused models** - Not trying to capture everything
- **Purpose-driven** - Different purposes = different models
- **Justified exclusions** - You can explain why you left things out
- **Business language** - Model speaks in domain terms, not database terms

---

## Exercise 3: Software Reflection - Does Your Code Speak the Domain?

**Type:** Diagnostic Exercise  
**Time:** 15 minutes  
**Skills:** Code review, domain alignment assessment

### Setup

Review these two code snippets solving the same problem: determining if an EV can start a charging session.

**Version A:**
```java
class Data {
    int val1;  // battery percentage
    int val2;  // temperature
    boolean flag;
    
    boolean check() {
        if (val1 < 20 && val2 > -10 && val2 < 50) {
            flag = true;
            return true;
        }
        return false;
    }
}
```

**Version B:**
```java
class BatteryPack {
    StateOfCharge currentSoC;
    Temperature currentTemperature;
    ChargingEligibility eligibility;
    
    boolean canBeginCharging() {
        if (currentSoC.isBelowThreshold(20.percent()) && 
            currentTemperature.isWithinSafeRange(ChargingTemperatureRange.STANDARD)) {
            eligibility = ChargingEligibility.ELIGIBLE;
            return true;
        }
        eligibility = ChargingEligibility.INELIGIBLE;
        return false;
    }
}
```

### Your Analysis

Answer these questions:

1. **Domain Expert Test:**  
   If a battery engineer read each version, which one could they understand without explanation? Why?

2. **Ubiquitous Language Test:**  
   List the domain terms present in Version B but missing in Version A.

3. **Business Rule Visibility:**  
   Where is the business rule "don't charge below -10°C" in each version? Which is clearer?

4. **Evolvability Test:**  
   If the rule changes to "below 15% SoC OR above 85% SoC during hot weather," which version is easier to modify?

5. **Your Codebase Reality Check:**  
   Find a class in your current project. Does it look more like Version A or B? Why?

### Reflection Template

```markdown
## My Codebase Analysis

**Project/System:** _______________

**Sample Class I Reviewed:** _______________

**Domain Terms vs Technical Terms Ratio:** _______________

**Can a domain expert read this code?** Yes / Partially / No

**Specific improvements I could make:**
1. 
2. 
3. 

**Biggest barrier to domain-centric code in my project:**
_______________
```

---

## Exercise 4: The Battery Management Modeling Challenge

**Type:** Comprehensive Applied Exercise  
**Time:** 25-30 minutes  
**Skills:** End-to-end modeling, domain understanding

### Business Context

VW's ID.4 electric vehicle needs a Battery Management System (BMS) that handles:
- Monitoring cell health across 288 individual cells
- Controlling charging rate based on temperature and SoC
- Predicting remaining range
- Alerting drivers to degradation
- Logging data for warranty analysis

### Your Mission

Model the BMS domain by creating:

1. **Domain Glossary** (10-15 terms with precise definitions)
2. **Core Entities** (3-5 key objects with identity)
3. **Value Objects** (3-5 measurements/descriptors)
4. **Critical Business Rules** (5-7 rules that must be enforced)
5. **Domain Events** (3-5 significant occurrences)

### Detailed Requirements

**Domain Glossary Format:**
```
Term: [Domain term]
Definition: [Precise, unambiguous definition]
Example: [Concrete example from VW ID.4 context]
Used by: [Which domain experts use this term]
```

**Entity Format:**
```
Entity: [Name]
Identity: [What makes it unique]
Lifecycle: [Created when? Destroyed when?]
Key Attributes:
- [attribute]: [type] - [why it matters]
Key Behaviors:
- [method]() - [business rule it enforces]
```

**Business Rule Format:**
```
Rule: [Name]
Condition: [When does this apply]
Action: [What must happen]
Rationale: [Why this rule exists - safety? efficiency? regulation?]
Exception: [Are there cases where this doesn't apply?]
```

### Sample Starter (to guide you)

**Sample Glossary Entry:**
```
Term: State of Charge (SoC)
Definition: Percentage of battery's current capacity relative to its maximum capacity, ranging from 0% (completely depleted) to 100% (fully charged)
Example: ID.4 dashboard shows 67% SoC, meaning battery has 67% of its charge remaining
Used by: Battery engineers, drivers, charging station software, range prediction algorithms
```

**Sample Business Rule:**
```
Rule: Cold Weather Charging Restriction
Condition: When battery temperature < -10°C AND charging requested
Action: System must refuse charging AND display "Battery too cold" message
Rationale: Lithium-ion cells can be permanently damaged by charging at extreme low temperatures (lithium plating)
Exception: If battery has active thermal preconditioning (heater), wait until temperature > -5°C, then allow charging
```

### Validation Checklist

Before submitting, verify:

- [ ] Every technical term has a business justification
- [ ] A battery engineer could read your glossary and recognize their domain
- [ ] Business rules reference glossary terms (not generic programming terms)
- [ ] Entities have clear identity (could two exist with same attributes but different identity?)
- [ ] Value objects are immutable concepts (temperature, percentage, etc.)
- [ ] Events capture business-meaningful occurrences (not "button clicked")

### What We're Evaluating

| Criterion | Poor | Good | Excellent |
|-----------|------|------|-----------|
| **Domain Language** | Generic terms (data, value, flag) | Mix of domain and technical | Pure domain terms |
| **Precision** | Vague definitions | Clear definitions | Definitions domain experts would approve |
| **Business Focus** | Technical constraints drive model | Some business rules visible | Business rules are explicit and primary |
| **Abstraction** | Trying to model everything | Focused on charging/health | Purposefully excludes irrelevant details |

---

## Exercise 5: The Translation Challenge - Domain to Model to Code

**Type:** Multi-Step Transformation Exercise  
**Time:** 20 minutes  
**Skills:** Knowledge crunching, model extraction, coding

### Starting Point: Domain Expert Interview Transcript

You interviewed VW's lane-keeping expert. Here's part of the conversation:

> **Expert:** "The system watches the lane markings through the front camera. If the car starts drifting toward a line - like the left line on a highway - and the driver hasn't put on their turn signal, we know they're not paying attention or the wind pushed them. The steering wheel will gently push back to guide them to the center of the lane. But we only do this above 65 kilometers per hour, because at city speeds the driver might be parking or maneuvering."
>
> **You:** "What if the camera can't see the lines clearly?"
>
> **Expert:** "Good question. If the confidence is below 75% - maybe it's raining or the paint is faded - we don't intervene. We'll warn the driver that the system isn't available, but we won't touch the steering. Safety first."

### Your Three-Step Task

**Step 1: Extract the Domain Model**

From this conversation, identify:
```
CONCEPTS (nouns that matter):
1. 
2. 
3. 

RELATIONSHIPS (how concepts connect):
- [Concept A] [relationship] [Concept B]

BUSINESS RULES (conditions and actions):
Rule 1: 
Rule 2: 
Rule 3: 
```

**Step 2: Create a Simple Model Diagram**

Using text format:
```
┌─────────────────┐
│  [Entity Name]  │
├─────────────────┤
│ - attribute1    │
│ - attribute2    │
├─────────────────┤
│ + behavior1()   │
│ + behavior2()   │
└─────────────────┘
```

Connect entities with relationships:
```
[Entity A] ──uses──> [Entity B]
[Entity C] ──triggers──> [Event D]
```

**Step 3: Write Domain-Centric Code**

Translate your model into actual code (pseudocode is fine):

```java
class LaneKeepingSystem {
    // Your attributes here - use domain terms!
    
    // Your methods here - model the business rules!
}
```

### Success Criteria

**Your model should:**
- Use the expert's exact terminology (lane marking, drift, confidence, intervention)
- Make the 65 km/h threshold explicit and visible
- Show that signal indicator prevents intervention
- Model confidence level as a first-class concept
- Separate sensing (camera) from decision-making (intervention logic)

**Anti-Patterns to Avoid:**
```java
// ❌ BAD - Technical thinking
if (speed > 65 && flag1 && !flag2 && value > 75) {
    doThing();
}

// ✅ GOOD - Domain thinking
if (vehicle.isAboveCitySpeed() && 
    laneMarkingDetection.hasSufficientConfidence() &&
    driver.hasNotSignaledTurnIntent()) {
    laneKeepingAssist.applyGentleSteeringCorrection();
}
```

---

## Bonus Challenge: The Bad Model Detective

**Type:** Critical Analysis  
**Time:** 10 minutes  
**Difficulty:** Intermediate

### Scenario

A contractor delivered this model for VW's charging station network. Your job: find what's wrong.

```java
public class Thing {
    String id;
    String location;
    int number;
    List<Thing2> things;
    
    void process(Object data) {
        // implementation
    }
}

public class Thing2 {
    int status;  // 0=free, 1=busy, 2=broken
    double power;
}
```

### Your Analysis

**List 10 problems with this model:**

1. Problem: _______________  
   Why it matters: _______________  
   How to fix: _______________

2. Problem: _______________  
   Why it matters: _______________  
   How to fix: _______________

[Continue for all 10...]

**Categories to consider:**
- Naming (domain vs technical terms)
- Types (primitives vs domain concepts)
- Magic numbers (what is 0, 1, 2?)
- Relationships (what is Thing2 actually?)
- Behavior (what does "process" mean?)

---

## Submission Guidelines

For **GitHub Discussion** submission:

1. **Title format:** `LG 1-1 Submission - [Your Name] - [Exercise Number]`

2. **Use headers** to organize your response:
   ```markdown
   ## Exercise [Number]
   
   ### My Analysis
   [Your work here]
   
   ### Challenges I Faced
   [What was difficult]
   
   ### Questions for Discussion
   [What you're unsure about]
   ```

3. **Format code** with syntax highlighting:
   ` ```java` for Java, ` ```python` for Python, etc.

4. **Be specific** - Instead of "Version B is better," explain "Version B makes the charging temperature constraint visible on line 8, while Version A hides it as a magic number (-10)."

---

## Self-Assessment Rubric

Rate yourself after completing exercises:

| Learning Objective | Not Yet | Partially | Achieved |
|--------------------|---------|-----------|----------|
| I can distinguish domain knowledge from technical implementation | ☐ | ☐ | ☐ |
| I can create focused models that exclude irrelevant details | ☐ | ☐ | ☐ |
| I can recognize when code doesn't reflect the domain model | ☐ | ☐ | ☐ |
| I can explain why different purposes need different models | ☐ | ☐ | ☐ |
| I can extract domain concepts from expert conversations | ☐ | ☐ | ☐ |

**If you marked "Not Yet" on any:** Review the guide section on that topic, then retry the related exercise.

---

## Going Deeper: Additional Practice

Want more? Try these:

1. **Your Project Audit:** Take a real class from your current VW project. Identify every place where technical concerns bleed into domain logic. Propose refactorings.

2. **Interview Exercise:** Find a domain expert (battery engineer, ADAS specialist, etc.) and practice extracting 10 domain terms with precise definitions.

3. **Model Comparison:** Take one VW business capability (e.g., "vehicle configuration") and model it from three perspectives: sales, manufacturing, customer. How do the models differ?

4. **Reverse Engineer:** Take existing VW software you know well. Can you extract the implicit domain model? Draw it out. Does it match what the business actually does?
