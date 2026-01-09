# LG 1-1 Exercise Solutions & Teaching Guide

**Purpose:** Complete solutions, alternate approaches, and pedagogical guidance for all exercises  
**Audience:** Instructors and students (post-attempt)  
**Usage:** Reference after attempting exercises independently

---

## Table of Contents

1. [Exercise 1: Domain Identification & Boundary Detection](#exercise-1-solutions)
2. [Exercise 2: Model vs Reality - The Abstraction Challenge](#exercise-2-solutions)
3. [Exercise 3: Software Reflection - Code Review](#exercise-3-solutions)
4. [Exercise 4: Battery Management Modeling](#exercise-4-solutions)
5. [Exercise 5: The Translation Challenge](#exercise-5-solutions)
6. [Bonus: The Bad Model Detective](#bonus-challenge-solutions)

---

## Exercise 1 Solutions: Domain Identification & Boundary Detection

### Approach Brief

**Core Skill:** Recognizing natural domain boundaries by asking three questions:
1. **Expertise Test:** Do different specialists own this knowledge?
2. **Language Test:** Do terms mean different things in different contexts?
3. **Change Test:** Can this area evolve independently?

**Mental Model:** Think of domains like departments in a company - they have clear ownership, specialized vocabulary, and can reorganize without disrupting others.

---

### Model Solution

#### Domain 1: Production Line Manufacturing

```
Domain Name: Assembly Line Operations
Core Concepts: 
- WorkStation (specific position on line)
- AssemblyTask (operation performed at station)
- Takt Time (time allocated per vehicle)
- Build Sequence (order of vehicle assembly)
- Quality Gate (inspection checkpoint)
- Component Supply (parts feeding to line)
- Line Balance (distribution of work across stations)

Domain Experts: 
- Manufacturing engineers
- Line supervisors
- Process optimization specialists

Boundaries: 
- EXCLUDES: Vehicle design specifications (that's Engineering domain)
- EXCLUDES: Raw material procurement (that's Supply Chain domain)
- EXCLUDES: Worker HR records (that's Human Resources domain)

Rationale: This domain focuses on "how we build" not "what we build" or "who builds it"
```

#### Domain 2: Order-to-Delivery

```
Domain Name: Customer Order Management
Core Concepts:
- CustomerOrder (binding commitment to purchase)
- ConfigurationLock (freezing spec changes)
- ProductionSlot (scheduled build time)
- DealerAssignment (which dealer handles delivery)
- OrderStatus (where in lifecycle: placed, confirmed, building, shipped, delivered)
- PriceQuote (agreed purchase price)
- TradeInVehicle (customer's existing vehicle)

Domain Experts:
- Sales operations managers
- Order processing specialists
- Dealer network coordinators

Boundaries:
- EXCLUDES: Manufacturing assembly process (that's Production domain)
- EXCLUDES: Individual customer credit scoring (that's Finance domain)
- EXCLUDES: Marketing campaigns (that's Marketing domain)

Rationale: This domain owns the customer's journey from "I want to buy" to "I own the vehicle"
```

#### Domain 3: Vehicle Configuration & Options

```
Domain Name: Product Configuration
Core Concepts:
- VehicleModel (ID.4, Tiguan, etc.)
- TrimLevel (base, premium, R-Line)
- OptionPackage (winter package, tech package)
- ConfigurationRule (incompatibilities: "AWD required with performance package")
- ColorPalette (available exterior/interior colors)
- MarketSpecification (US vs EU requirements)
- ConfigurationValidity (is this combination buildable?)

Domain Experts:
- Product planners
- Engineering release managers
- Market homologation specialists

Boundaries:
- EXCLUDES: Manufacturing feasibility on specific line (that's Production)
- EXCLUDES: Pricing and discounts (that's Finance/Sales)
- EXCLUDES: Inventory of pre-built vehicles (that's Dealer Network)

Rationale: This domain answers "what can be built" not "how" or "how much"
```

#### Domain 4: Dealer Network Operations

```
Domain Name: Dealer Relationship Management
Core Concepts:
- AuthorizedDealer (franchisee with sales/service rights)
- AllocatedInventory (vehicles assigned to dealer)
- SalesPerformance (dealer's monthly/quarterly metrics)
- ServiceCertification (authorized service capabilities)
- DealerTerritory (geographic sales area)
- DealerIncentive (manufacturer support programs)
- CustomerSatisfactionScore (dealer rating)

Domain Experts:
- Dealer network managers
- Regional sales directors
- Dealer support specialists

Boundaries:
- EXCLUDES: Individual customer transactions (that's Order Management)
- EXCLUDES: Vehicle technical specifications (that's Product Configuration)
- EXCLUDES: Manufacturing allocation decisions (that's Supply Chain Planning)

Rationale: This domain manages the relationship between VW and its dealers as business partners
```

#### Domain 5: Connected Vehicle Services Platform

```
Domain Name: Digital Connected Services
Core Concepts:
- ServiceSubscription (customer's active digital services)
- RemoteCommand (lock/unlock, climate, flash lights)
- VehicleTelemetry (real-time vehicle data stream)
- OTAUpdate (over-the-air software deployment)
- EmergencyCall (eCall/SOS functionality)
- ServiceActivation (enabling features remotely)
- ConnectivityStatus (vehicle's cloud connection state)

Domain Experts:
- Connected services product managers
- Cloud platform engineers
- Digital customer experience designers

Boundaries:
- EXCLUDES: In-vehicle ECU logic (that's Vehicle Software domain)
- EXCLUDES: Customer billing/payment processing (that's Finance domain)
- EXCLUDES: Manufacturing vehicle connectivity setup (that's Production domain)

Rationale: This domain owns the vehicle-to-cloud relationship and digital service delivery
```

#### Domain 6: After-Sales Service & Maintenance

```
Domain Name: Service Operations
Core Concepts:
- ServiceAppointment (scheduled maintenance/repair)
- WorkOrder (specific tasks to be performed)
- VehicleServiceHistory (record of all interventions)
- WarrantyClaim (manufacturer-covered repair)
- TechnicalBulletin (service procedure updates)
- PartsInventory (service parts availability)
- DiagnosticTroubleCode (fault codes from vehicle)

Domain Experts:
- Service advisors
- Master technicians
- Warranty administrators

Boundaries:
- EXCLUDES: Selling new vehicles (that's Sales domain)
- EXCLUDES: Parts manufacturing (that's Supply Chain)
- EXCLUDES: Engineering design changes (that's Product Engineering)

Rationale: This domain handles "keeping vehicles running" after customer takes delivery
```

#### Domain 7: Autonomous Driving Features

```
Domain Name: ADAS & Autonomous Systems
Core Concepts:
- DrivingScenario (road conditions, traffic, weather)
- SensorFusion (combining camera, radar, lidar data)
- ObjectDetection (identifying vehicles, pedestrians, obstacles)
- PathPlanning (calculating safe trajectory)
- InterventionStrategy (when/how to assist driver)
- AutonomyLevel (SAE Level 0-5 capability)
- DriverMonitoring (hands-off detection, attention tracking)

Domain Experts:
- ADAS engineers
- Perception algorithm specialists
- Safety validation engineers

Boundaries:
- EXCLUDES: Basic vehicle dynamics control (that's Powertrain/Chassis)
- EXCLUDES: Infotainment user interface (that's Digital Cockpit domain)
- EXCLUDES: Regulatory compliance documentation (that's Homologation)

Rationale: This domain focuses on perception, decision-making, and driver assistance
```

#### Domain 8: Financial Services

```
Domain Name: Customer Financing & Leasing
Core Concepts:
- FinanceApplication (customer request for loan)
- CreditAssessment (approval/rejection decision)
- LeasingContract (terms of lease agreement)
- MonthlyPayment (calculated installment)
- Residualvalue (predicted end-of-lease value)
- BuyoutOption (lease-to-purchase conversion)
- DefaultRisk (likelihood of payment failure)

Domain Experts:
- Finance product managers
- Credit risk analysts
- Leasing contract specialists

Boundaries:
- EXCLUDES: Vehicle pricing/MSRP (that's Product Planning)
- EXCLUDES: Dealer commission structure (that's Dealer Network)
- EXCLUDES: Customer's broader financial profile (that's external to VW)

Rationale: This domain manages "how customers pay" not "what they buy"
```

---

### Alternate Approaches & Tradeoffs

#### Approach A: Organizational Structure Mapping

**Method:** Map domains directly to VW's organizational chart (departments = domains)

**Pros:**
- Quick to identify
- Clear ownership
- Aligns with existing management structure

**Cons:**
- Organizations often have Conway's Law problems (structure mirrors system)
- May perpetuate poor boundaries
- Organizational politics can obscure true domain boundaries

**When to Use:** Early in DDD adoption, or when organization is well-structured

---

#### Approach B: Use Case / Process Mapping

**Method:** Follow key business processes end-to-end, identifying where language/expertise changes

**Pros:**
- Natural boundaries emerge from workflow
- Reveals cross-domain integration points
- Focuses on actual business operations

**Cons:**
- Can blur boundaries (processes cross domains)
- May create too many fine-grained domains
- Workflow-centric, might miss supporting domains

**When to Use:** When you have strong process documentation or are doing process improvement

---

#### Approach C: Language/Terminology Analysis

**Method:** Collect all terms used in interviews, identify clusters of related vocabulary

**Pros:**
- Very DDD-native (language is primary)
- Reveals hidden conceptual boundaries
- Uncovers ambiguous terms that need clarification

**Cons:**
- Time-intensive (requires many interviews)
- Requires linguistic analysis skills
- May create artificial boundaries based on vocabulary differences

**When to Use:** When you have access to domain experts and can conduct extensive interviews

---

### Common Mistakes & How to Avoid Them

#### Mistake 1: "Everything Is One Big Domain"

**Symptom:** Domain called "Vehicle System" that includes manufacturing, sales, service, finance

**Why It's Wrong:** No single model can effectively represent all these concerns. A Vehicle in manufacturing has different attributes than a Vehicle in sales.

**How to Fix:** Apply the "can this change independently?" test. Manufacturing processes can change without affecting sales processes → separate domains.

---

#### Mistake 2: "Every Team Gets Its Own Domain"

**Symptom:** 47 micro-domains like "Invoice Printing Domain", "Email Notification Domain"

**Why It's Wrong:** These are technical capabilities, not business domains. They lack domain expertise and business rules.

**How to Fix:** Ask "does this have a domain expert who isn't a programmer?" If no → it's infrastructure, not a domain.

---

#### Mistake 3: "Boundaries Must Match Database Tables"

**Symptom:** Domain boundaries align with legacy database schema

**Why It's Wrong:** Database design reflects old technical decisions, not current business understanding.

**How to Fix:** Ignore current system structure initially. Model the business as it should be, then figure out implementation later.

---

#### Mistake 4: "Customer" Means the Same Thing Everywhere

**Symptom:** Trying to force a single "Customer" concept across all domains

**Why It's Wrong:** 
- Sales sees Customer as "prospect with purchase intent"
- Service sees Customer as "vehicle owner with service history"
- Finance sees Customer as "credit-worthy borrower"

**How to Fix:** Allow different models of Customer in different contexts. Use integration patterns to translate between them.

---

### Step-by-Step Solution Walkthrough

**Step 1: Read the Business Area Slowly**

Don't rush. For "Vehicle manufacturing and assembly," mentally picture the factory floor, the workers, the processes.

**Step 2: Ask "Who are the experts?"**

Manufacturing engineers, line supervisors, quality inspectors → they all speak the same language about assembly.

**Step 3: Test the Boundaries with Questions**

- "Does a line supervisor care about customer financing?" → NO → separate domain
- "Does a line supervisor care about parts inventory at the station?" → YES → same domain
- "Does a line supervisor care about vehicle design specifications?" → Reads them, but doesn't own them → boundary

**Step 4: List Core Concepts**

What nouns appear repeatedly in conversations with experts?
- WorkStation, AssemblyTask, Takt Time → these are manufacturing concepts
- Customer, OrderStatus, PriceQuote → these are sales concepts → separate domain!

**Step 5: Name It Precisely**

"Manufacturing" is too broad. "Assembly Line Operations" is specific.

**Step 6: Document What's Excluded**

This is as important as what's included. "We do NOT handle vehicle design" prevents scope creep.

---

### Expert Analysis: What Makes This Challenging?

**Cognitive Challenge:** Humans naturally see the world as interconnected. Identifying boundaries requires deliberate abstraction.

**Political Challenge:** Domains often cut across organizational silos. Saying "Customer means different things in Sales vs Service" can be controversial.

**Technical Debt Challenge:** Existing systems create artificial coupling. A monolithic database makes everything look like one domain.

**Pragmatic Advice:**
1. Start with obvious separations (manufacturing ≠ sales)
2. Refine boundaries as understanding deepens
3. Be willing to split or merge domains based on evidence
4. Document your reasoning so others understand the boundaries

---

## Exercise 2 Solutions: Model vs Reality - The Abstraction Challenge

### Approach Brief

**Core Principle:** The same real-world entity needs different models for different purposes. There is no "one true model."

**Mental Model:** Think like a photographer choosing different lenses:
- Wide-angle lens (dealer lot): Captures many vehicles at once, less detail
- Macro lens (warranty): Deep detail on specific aspects, ignores surroundings

---

### Model Solution: Purpose 1 - Dealer Lot Management

```java
/**
 * MODEL: VehicleInventoryItem
 * PURPOSE: Track vehicles on dealer lot for sales, test drives, lot management
 * 
 * Key Question This Model Answers: "What vehicles do we have available for customers?"
 */
public class VehicleInventoryItem {
    // IDENTITY
    private final VIN vin;  // Unique identifier
    
    // KEY ATTRIBUTES
    private ModelDesignation modelDesignation;  // "ID.4 Pro S"
    private ExteriorColor exteriorColor;        // "Kings Red Metallic"
    private InteriorColor interiorColor;        // "Black Leatherette"
    private EquipmentPackages packages;         // List of installed options
    private Odometer currentMileage;            // For test drive tracking
    private LotLocation parkingSpot;            // "Row 3, Space 12"
    private VehicleCondition condition;         // NEW, DEMO, DAMAGED
    private PriceTag askingPrice;              // MSRP or discounted price
    private AvailabilityStatus availability;    // AVAILABLE, TEST_DRIVE, SOLD, RESERVED
    
    // BEHAVIORS (What can we do with this model?)
    public boolean isAvailableForTestDrive() {
        return availability == AvailabilityStatus.AVAILABLE 
            && condition == VehicleCondition.NEW;
    }
    
    public void markAsOnTestDrive(Customer customer, DateTime expectedReturn) {
        // Business rule: Record who has the keys, when they should return
        if (!isAvailableForTestDrive()) {
            throw new VehicleNotAvailableException();
        }
        this.availability = AvailabilityStatus.TEST_DRIVE;
        // ... record details
    }
    
    public void recordTestDriveMileage(Odometer returnMileage) {
        // Business rule: Update mileage after test drive
        this.currentMileage = returnMileage;
    }
    
    public void applyDiscount(DiscountAmount discount) {
        // Business rule: Manager can reduce price
        this.askingPrice = askingPrice.minus(discount);
    }
    
    public void moveToLotLocation(LotLocation newSpot) {
        this.parkingSpot = newSpot;
    }
}
```

**What We Deliberately Excluded:**

1. **Engine specifications, horsepower, battery capacity** - Reason: Sales staff doesn't need this to manage lot inventory. It's in marketing materials.

2. **Manufacturing plant, build date, production sequence** - Reason: Vehicle is already built and delivered. Manufacturing history doesn't affect lot operations.

3. **Warranty terms, service schedule** - Reason: Customer gets this at purchase time, not relevant for lot tracking.

4. **Individual component part numbers** - Reason: Vehicle is a complete unit on the lot, not disassembled parts.

5. **Previous owners, accident history** - Reason: These are NEW vehicles, no history yet.

6. **Fuel level, tire pressure** - Reason: Checked daily by lot staff, not tracked in sales system.

**Rationale:**
This model focuses on "what the sales team needs to sell vehicles." It includes visual characteristics (colors), equipment (packages), commercial details (price), and operational status (available/test drive/sold). It excludes technical specifications that don't affect daily lot operations.

---

### Model Solution: Purpose 2 - Service Warranty Claims

```java
/**
 * MODEL: WarrantyCoveredVehicle
 * PURPOSE: Validate warranty coverage, track repairs, determine manufacturer liability
 * 
 * Key Question This Model Answers: "Is this repair covered under warranty?"
 */
public class WarrantyCoveredVehicle {
    // IDENTITY
    private final VIN vin;  // Unique identifier
    
    // KEY ATTRIBUTES
    private ManufacturingDate buildDate;           // Determines warranty start
    private InServiceDate customerDeliveryDate;    // Actual warranty start
    private WarrantyPeriod basicWarranty;          // Duration/mileage limits
    private WarrantyPeriod powertrainWarranty;     // Different coverage
    private WarrantyPeriod batteryWarranty;        // EV-specific
    private Odometer currentOdometer;              // For mileage-based limits
    private ServiceHistory repairHistory;          // Past warranty claims
    private ModificationRecord modifications;       // Aftermarket changes void warranty?
    private ComponentCoverage coveredSystems;      // What's under warranty
    
    // BEHAVIORS
    public CoverageDecision isComponentCovered(ComponentType component, 
                                                FailureDate date,
                                                Odometer mileage) {
        // Business rule: Complex logic to determine coverage
        if (modifications.hasUnapprovedModification(component)) {
            return CoverageDecision.denied("Unapproved modification voids warranty");
        }
        
        WarrantyPeriod applicable = determineApplicableWarranty(component);
        
        if (applicable.hasExpired(date, mileage)) {
            return CoverageDecision.denied("Outside warranty period");
        }
        
        if (repairHistory.hasExceededClaimLimit(component)) {
            return CoverageDecision.denied("Repeated failure - engineering review required");
        }
        
        return CoverageDecision.approved(applicable.getAuthorizationAmount());
    }
    
    public void recordWarrantyClaim(WarrantyClaim claim) {
        // Business rule: Update history for future coverage decisions
        this.repairHistory.add(claim);
    }
    
    public Money calculateCustomerResponsibility(RepairCost totalCost, 
                                                  CoverageDecision decision) {
        if (decision.isFullyCovered()) {
            return Money.ZERO;
        }
        return totalCost.minus(decision.getAuthorizedAmount());
    }
    
    public void registerModification(Modification mod) {
        // Business rule: Track changes that might affect warranty
        this.modifications.add(mod);
    }
}
```

**What We Deliberately Excluded:**

1. **Exterior color, interior trim** - Reason: Cosmetic details don't affect warranty coverage.

2. **Current lot location, availability status** - Reason: Vehicle is with customer, not on dealer lot.

3. **Sales price, financing terms** - Reason: Warranty coverage is independent of what customer paid.

4. **Test drive history** - Reason: Not relevant to post-purchase repairs.

5. **Optional packages (unless they affect warranty)** - Reason: Base coverage is same regardless of luxury features.

6. **Marketing designations** - Reason: Warranty system cares about technical components, not marketing names.

**Rationale:**
This model focuses on "determining manufacturer liability for repairs." It emphasizes dates (when did warranty start?), mileage (has it expired?), repair history (is this a recurring issue?), and modifications (did customer void warranty?). Physical appearance is irrelevant.

---

### Comparing the Two Models

| Aspect | Dealer Lot Model | Warranty Model |
|--------|------------------|----------------|
| **Primary Question** | "Can we sell this vehicle?" | "Must we pay for this repair?" |
| **Time Frame** | Present moment (is it available NOW?) | Historical (when was it built/delivered?) |
| **Key Attribute** | Availability status | Warranty expiration dates |
| **Mileage Purpose** | Track test drive usage | Determine if mileage limit exceeded |
| **Critical Exclusion** | Manufacturing date (doesn't affect sales) | Color/trim (doesn't affect coverage) |
| **Lifecycle Stage** | Pre-sale | Post-sale |

---

### Alternate Approaches & Tradeoffs

#### Approach A: Unified "Complete Vehicle" Model

**Concept:** Create one giant Vehicle model with ALL attributes (color, price, warranty, service history, lot location, etc.)

**Code Example:**
```java
public class CompleteVehicle {
    // Dealer lot attributes
    private LotLocation parkingSpot;
    private AvailabilityStatus availability;
    private PriceTag askingPrice;
    
    // Warranty attributes
    private WarrantyPeriod basicWarranty;
    private ServiceHistory repairHistory;
    
    // Manufacturing attributes
    private PlantLocation buildLocation;
    private ProductionSequence buildOrder;
    
    // ... 50+ more attributes
}
```

**Pros:**
- Only one class to maintain
- "Complete" information in one place
- Matches how we think ("one vehicle, one object")

**Cons:**
- **Massive complexity:** Class becomes unmaintainable
- **Poor cohesion:** Lot management methods mixed with warranty methods
- **Coupling:** Changes for sales affect warranty code
- **Performance:** Loading all data when you only need price
- **Ambiguity:** What does "status" mean? (Lot status? Warranty status? Manufacturing status?)

**Verdict:** Tempting but wrong. Violates Single Responsibility Principle. Different purposes need different models.

---

#### Approach B: Inheritance Hierarchy

**Concept:** Base "Vehicle" class, specialized subclasses

```java
public abstract class Vehicle {
    protected VIN vin;
    protected ModelDesignation model;
}

public class DealerLotVehicle extends Vehicle {
    private LotLocation parkingSpot;
    private AvailabilityStatus availability;
}

public class WarrantyVehicle extends Vehicle {
    private WarrantyPeriod warranty;
    private ServiceHistory history;
}
```

**Pros:**
- Shares common attributes (VIN, model)
- Clear specialization
- Type safety (can't pass warranty vehicle to lot management)

**Cons:**
- **Rigid structure:** Hard to change base class
- **Unclear semantics:** Same vehicle is both DealerLotVehicle AND WarrantyVehicle
- **Multiple representations:** How do you transition from lot to warranty?
- **Implementation coupling:** Changes to Vehicle affect all subclasses

**Verdict:** Better than unified model, but still problematic. Inheritance for domain modeling is often a mistake.

---

#### Approach C: Separate Models + Shared Identifier (RECOMMENDED)

**Concept:** Completely independent models, linked only by VIN

```java
// Lot Management bounded context
public class VehicleInventoryItem {
    private final VIN vin;  // Identity
    private LotLocation parkingSpot;
    private AvailabilityStatus availability;
}

// Warranty bounded context
public class WarrantyCoveredVehicle {
    private final VIN vin;  // Same identity, different model
    private WarrantyPeriod warranty;
    private ServiceHistory history;
}
```

**Pros:**
- **Complete independence:** Models evolve separately
- **Clear purpose:** Each model optimized for its use case
- **Maintainability:** Changes in one don't affect the other
- **Conceptual clarity:** Different contexts, different models
- **Performance:** Load only what you need

**Cons:**
- **Apparent duplication:** VIN appears in both (but this is OK!)
- **Integration needed:** Must translate between models if contexts interact
- **More files:** Two classes instead of one (but simpler classes)

**Verdict:** This is the DDD way. Embrace different models for different purposes.

---

### Common Mistakes & How to Avoid Them

#### Mistake 1: "I'll Include Everything Just in Case"

**Symptom:** Model has 60 attributes because "we might need it someday"

**Why Wrong:** Violates YAGNI (You Aren't Gonna Need It). Complexity now for hypothetical future need.

**Fix:** Model only what's required for the current purpose. Refactor when new needs emerge.

---

#### Mistake 2: "I'll Make It Generic to Reuse"

**Symptom:** VehicleInventoryItem renamed to "VehicleInstance" and used for both lot and warranty

**Why Wrong:** Attempting reuse creates abstraction that serves neither purpose well.

**Fix:** Optimize each model for its specific use case. Don't force reuse where it doesn't belong.

---

#### Mistake 3: "Color Belongs in the Model Because It's a Vehicle Attribute"

**Symptom:** Including attributes because they're "true" about the entity, not because they're needed

**Why Wrong:** Models are purpose-driven, not truth-driven. Warranty doesn't care about color.

**Fix:** Ask "does this purpose require this attribute?" Not "is this true about vehicles?"

---

### Step-by-Step Solution Walkthrough

**Step 1: Understand the Business Problem**

Dealer Lot: "Which vehicles can I show customers today?"
→ This is about current availability and sales-relevant characteristics

**Step 2: Interview the Domain Expert (Mentally)**

Sales Manager: "I need to know if it's on the lot, what color it is, if someone's test-driving it, and the price."
→ These become key attributes

**Step 3: Identify What Doesn't Matter**

Sales Manager: "I don't care when it was built, I care when I can sell it."
→ Manufacturing date excluded from lot model

**Step 4: Model the Behaviors**

What do people DO with lot vehicles?
- Reserve for customer
- Take on test drive
- Apply discount
- Move to different parking spot
→ These become methods

**Step 5: Question Every Inclusion**

"Should I include battery capacity?"
- Does sales staff use this in lot operations? No, it's in spec sheet.
- Is it needed for test drives? No.
- Could it change while on lot? No.
→ Excluded

**Step 6: Repeat for Second Purpose**

Warranty: "Is this repair covered?"
→ Completely different question, different model needed

---

### Expert Analysis

**Why This Exercise Is Difficult:**

1. **Object-Oriented Training Bias:** We're taught "one class per real-world thing." DDD says "multiple models per real-world thing."

2. **Completeness Fallacy:** We want models to be "complete." DDD says "models should be purposefully incomplete."

3. **Reuse Pressure:** We're trained to avoid duplication. DDD says "duplicate if purposes differ."

**The Insight:**
The same VIN (like "WVWZZZAUZLW123456") can appear in VehicleInventoryItem, WarrantyCoveredVehicle, ManufacturedVehicle, FinancedVehicle - each with totally different attributes. The VIN is the shared identity, but the models serve different purposes.

This is like how your driver's license number appears on your license, your insurance card, your vehicle registration - same identity, different documents, different purposes.

---

## Exercise 3 Solutions: Software Reflection - Code Review

### Approach Brief

**Core Skill:** Assessing whether code communicates domain concepts or hides them behind technical jargon.

**Evaluation Criteria:**
1. Can domain expert read the code?
2. Are business rules explicit or hidden?
3. Does code use domain terminology?
4. Are magic numbers/strings replaced with named concepts?

---

### Model Solution

#### Question 1: Domain Expert Test

**Answer:**

**Version A - Technical Gobbledygook:**
A battery engineer would be completely lost. They would need a programmer to explain:
- "What's val1? Oh, battery percentage? Why not call it that?"
- "What's val2? Temperature? In what units?"
- "What does flag mean? Can we charge or not?"
- "Why 20? Is that 20% state of charge? What's the business rule?"

**Version B - Domain-Centric:**
A battery engineer could read this with minimal explanation:
- "currentSoC" - They recognize "State of Charge" immediately
- "isBelowThreshold(20.percent())" - Clear: checking if battery is under 20%
- "isWithinSafeRange" - They know charging temperature constraints
- "ChargingEligibility.ELIGIBLE" - Explicit states they understand

**The Key Difference:**
Version B speaks the language of battery engineers. Version A speaks the language of programmers.

---

#### Question 2: Ubiquitous Language Test

**Domain Terms Present in Version B, Missing in Version A:**

| Domain Term | Where It Appears | Why It Matters |
|-------------|------------------|----------------|
| StateOfCharge (SoC) | `StateOfCharge currentSoC` | Standard battery industry term |
| Temperature | `Temperature currentTemperature` | With proper type (not just `int`) |
| ChargingEligibility | `ChargingEligibility eligibility` | Explicit business concept |
| Safe Range | `isWithinSafeRange()` | Domain experts talk about "safe charging temperature" |
| Threshold | `isBelowThreshold(20.percent())` | Business rule terminology |
| BatteryPack | Class name | What engineers actually call it |

**Generic Terms in Version A:**
- "Data" - Could be anything
- "val1", "val2" - Meaningless abbreviations
- "flag" - Technical, not domain
- "check()" - What are we checking? Purpose unclear

---

#### Question 3: Business Rule Visibility

**The Rule:** "Don't charge below -10°C (or above 50°C)"

**In Version A:**
```java
if (val1 < 20 && val2 > -10 && val2 < 50) {
```

**Problems:**
- **Hidden:** Buried in boolean expression
- **Magic numbers:** -10 and 50 appear without explanation
- **Unclear intent:** Why these numbers? Safety? Efficiency? Regulation?
- **No documentation:** Someone has to explain "val2 is temperature in Celsius"

**In Version B:**
```java
currentTemperature.isWithinSafeRange(ChargingTemperatureRange.STANDARD)
```

**Improvements:**
- **Explicit method:** `isWithinSafeRange()` states intent
- **Named constant:** `ChargingTemperatureRange.STANDARD` explains what -10 to 50 means
- **Self-documenting:** No comments needed, code explains itself
- **Changeable:** If standard range changes, update one constant

**Where the range is defined (in Version B):**
```java
public enum ChargingTemperatureRange {
    STANDARD(-10, 50, "Normal operating range"),
    PRECONDITIONING(-5, 40, "Active battery heating/cooling"),
    FAST_CHARGING(0, 35, "High current charging limits");
    
    private final Temperature minimum;
    private final Temperature maximum;
    private final String rationale;
    
    // ... constructor and methods
}
```

Now the business rule is **visible**, **named**, and **explained**.

---

#### Question 4: Evolvability Test

**New Rule:** "Charge if SoC < 15% OR SoC > 85% during hot weather (>30°C)"

**Version A - Nightmare:**
```java
boolean check() {
    if ((val1 < 15 || val1 > 85) && val2 > 30) {  // Hot weather fast charge?
        flag = true;
        return true;
    } else if (val1 < 20 && val2 > -10 && val2 < 50) {  // Original rule?
        flag = true;
        return true;
    }
    return false;
}
```

**Problems:**
- **Confusion:** Which rule applies when?
- **Magic numbers multiply:** 15, 85, 30, 20, -10, 50
- **No prioritization:** What if both conditions are true?
- **Comment dependency:** Code requires comments to understand

**Version B - Clean Evolution:**
```java
boolean canBeginCharging() {
    if (currentTemperature.isHot() && currentSoC.isAtExtremes()) {
        // Fast charge at battery extremes when temperature allows
        return chargingStrategy.allowFastChargeAtExtremes();
    }
    
    if (currentSoC.isBelowThreshold(20.percent()) && 
        currentTemperature.isWithinSafeRange(ChargingTemperatureRange.STANDARD)) {
        return chargingStrategy.allowStandardCharge();
    }
    
    return false;
}

// In StateOfCharge class
boolean isAtExtremes() {
    return this.isBelowThreshold(15.percent()) || 
           this.isAboveThreshold(85.percent());
}

// In Temperature class
boolean isHot() {
    return this.isAboveThreshold(30.celsius());
}
```

**Why This Is Better:**
- **Named conditions:** `isHot()`, `isAtExtremes()` - intent clear
- **Separated concerns:** Each method has one responsibility
- **Strategy pattern:** `chargingStrategy` can encapsulate complex logic
- **Testable:** Can test `isAtExtremes()` independently
- **No comments needed:** Code reads like English

---

#### Question 5: Your Codebase Reality Check

**Sample Realistic Analysis:**

```markdown
## My Codebase Analysis

**Project/System:** VW ID.4 Battery Management Controller

**Sample Class I Reviewed:** BatteryController.java

**Domain Terms vs Technical Terms Ratio:** ~30% domain / 70% technical

**Can a domain expert read this code?** Partially

**Sample Code:**
```java
public class BatteryController {
    private int soc;  // state of charge
    private double temp;  // temperature
    private boolean canCharge;
    
    public void updateStatus(int newSoc, double newTemp) {
        this.soc = newSoc;
        this.temp = newTemp;
        this.canCharge = (soc < 80 && temp > 0 && temp < 45);
    }
}
```

**Specific improvements I could make:**

1. **Replace primitives with value objects:**
   - `int soc` → `StateOfCharge currentSoC`
   - `double temp` → `Temperature currentTemperature`
   - `boolean canCharge` → `ChargingEligibility eligibility`

2. **Make business rules explicit:**
   ```java
   // Before
   this.canCharge = (soc < 80 && temp > 0 && temp < 45);
   
   // After
   this.eligibility = determineChargingEligibility(currentSoC, currentTemperature);
   ```

3. **Introduce domain service:**
   ```java
   public class ChargingEligibilityService {
       public ChargingEligibility assess(StateOfCharge soc, Temperature temp) {
           if (soc.isNearlyFull()) {
               return ChargingEligibility.FULL;
           }
           if (!temp.isWithinChargingRange()) {
               return ChargingEligibility.UNSAFE_TEMPERATURE;
           }
           return ChargingEligibility.ELIGIBLE;
       }
   }
   ```

**Biggest barrier to domain-centric code in my project:**

Legacy codebase with 10+ years of technical-first design. Battery engineers don't review code, so technical terms were never challenged. Large refactoring effort needed, but team sees value now.
```

---

### Alternate Approaches & Tradeoffs

#### Approach A: Comprehensive Refactoring (Ideal but Risky)

**Method:** Rewrite Version A from scratch using domain model

**Pros:**
- Clean slate, optimal design
- Forces deep domain thinking
- Creates best possible code

**Cons:**
- High risk (might break working code)
- Time-intensive
- Requires team buy-in

**When to Use:** New feature development, or dedicated refactoring sprint

---

#### Approach B: Incremental Wrapper Pattern (Pragmatic)

**Method:** Wrap ugly code in domain-centric API, refactor internals later

```java
// Ugly legacy code (Version A style)
class LegacyBatteryData {
    int val1;
    int val2;
    boolean check() { /* ugly logic */ }
}

// Domain-centric wrapper
class BatteryPack {
    private LegacyBatteryData legacy;  // Temporary
    
    public boolean canBeginCharging() {
        // Translate domain concepts to legacy
        legacy.val1 = this.currentSoC.toPercentageInt();
        legacy.val2 = this.currentTemperature.toCelsiusInt();
        return legacy.check();
    }
}
```

**Pros:**
- Low risk (legacy code unchanged)
- Immediate improvement in calling code
- Can refactor internals later

**Cons:**
- Carries technical debt
- Performance overhead (translation)
- Ugly code still exists

**When to Use:** Working with legacy systems, limited refactoring time

---

#### Approach C: Test-Driven Refactoring (Safest)

**Method:** Write domain-centric tests first, refactor to make them pass

```java
@Test
public void shouldAllowCharging_whenBatteryLow_andTemperatureSafe() {
    BatteryPack battery = new BatteryPack();
    battery.setStateOfCharge(StateOfCharge.of(15, PERCENT));
    battery.setTemperature(Temperature.of(20, CELSIUS));
    
    assertTrue(battery.canBeginCharging());
}
```

**Pros:**
- Safety net prevents breaking changes
- Tests document expected behavior
- Incremental improvement
- Team learns domain modeling through tests

**Cons:**
- Test-writing overhead
- Requires discipline
- Slower initial progress

**When to Use:** Production code, risk-averse teams, teaching scenarios

---

### Common Mistakes

#### Mistake 1: "Comments Will Explain It"

**Bad:**
```java
int val2;  // temperature in Celsius
```

**Why Wrong:** Comments go stale, aren't verified by compiler, reader still has to remember context

**Good:**
```java
Temperature currentTemperature;
```

---

#### Mistake 2: "Business Logic in Controllers/UI"

**Bad:**
```java
// In BatteryDisplayController
if (batteryData.val1 < 20 && batteryData.val2 > -10) {
    showChargingAvailableIcon();
}
```

**Why Wrong:** Business rule duplicated wherever check is needed, controller knows battery science

**Good:**
```java
// In BatteryDisplayController
if (batteryPack.canBeginCharging()) {
    showChargingAvailableIcon();
}

// Business logic in domain model
class BatteryPack {
    boolean canBeginCharging() { /* domain logic here */ }
}
```

---

### Expert Analysis

**Why Version A Exists:**

Developers often write Version A because:
1. **Time pressure:** "Just make it work"
2. **Missing domain knowledge:** Don't know proper terminology
3. **No domain expert access:** Can't learn correct terms
4. **Technical education:** Taught to think in primitives and flags
5. **Legacy patterns:** Copying existing code style

**The Cost of Version A:**

- New developer takes 3x longer to understand
- Bug fix requires detective work ("what does flag mean again?")
- Business rule changes require code archaeology
- Domain expert can't review code for correctness
- Accumulated technical debt

**The Value of Version B:**

- Self-documenting (minimal comments needed)
- Domain expert can validate logic
- Business rule changes are localized
- New developers onboard faster
- Code reviews focus on business logic, not deciphering intent

**This is the essence of DDD:** Make the code speak the language of the business so domain knowledge is preserved in software.

---

## Exercise 4 Solutions: Battery Management Modeling Challenge

### Approach Brief

**Goal:** Create a comprehensive domain model from real-world battery management requirements.

**Strategy:**
1. **Start with glossary** - Define terms precisely
2. **Identify entities** - What has identity and lifecycle?
3. **Identify value objects** - What are measurements/descriptions?
4. **Extract business rules** - What constraints must be enforced?
5. **Capture events** - What significant things happen?

---

### Model Solution: Complete Battery Management Domain

#### Domain Glossary

```markdown
Term: Battery Pack
Definition: Complete assembly of lithium-ion cells, cooling system, and BMS electronics 
installed as a single replaceable unit in an electric vehicle
Example: VW ID.4 has 77 kWh battery pack consisting of 12 modules with 288 total cells
Used by: Battery engineers, service technicians, warranty administrators

---

Term: Battery Cell
Definition: Individual electrochemical energy storage unit; smallest replaceable component 
in battery system. Multiple cells grouped into modules.
Example: Single cylindrical 21700 cell with nominal voltage 3.7V, capacity ~5Ah
Used by: Cell chemists, manufacturing engineers, quality inspectors

---

Term: State of Charge (SoC)
Definition: Percentage of battery's current usable capacity relative to its maximum 
capacity, ranging from 0% (fully depleted) to 100% (fully charged). Does not account 
for degradation.
Example: Dashboard shows 67% SoC means battery has 67% of rated capacity remaining
Used by: Drivers, charging algorithms, range prediction system, battery engineers
Note: Different from State of Health (SoH) which measures degradation

---

Term: State of Health (SoH)
Definition: Percentage of battery's current maximum capacity compared to its original 
as-new capacity. Decreases over time due to degradation. Range 100% (new) to ~70% 
(end of useful life).
Example: After 100,000 km, battery may have SoH of 92%, meaning it holds 92% of 
original capacity
Used by: Battery engineers, warranty claims, degradation prediction models

---

Term: Cell Balancing
Definition: Process of equalizing charge levels across all cells in battery pack by 
selectively discharging or charging individual cells to match voltage levels
Example: If cells 1-11 at 3.8V but cell 12 at 3.6V, balancing brings cell 12 to 3.8V
Used by: BMS algorithms, service diagnostics, battery engineers
Rationale: Prevents premature capacity loss, ensures safe operation

---

Term: Thermal Runaway
Definition: Uncontrolled exothermic reaction in lithium-ion cell where internal 
temperature rises exponentially, potentially leading to fire or explosion
Example: Cell reaches 150°C triggering decomposition of electrolyte, temperature 
spikes to 600°C in seconds
Used by: Safety engineers, thermal management designers, regulatory compliance
Critical: Must be prevented through temperature monitoring and intervention

---

Term: Charging Rate (C-Rate)
Definition: Current at which battery is charged, expressed as fraction of capacity. 
1C = charging at rate equal to capacity (e.g., 77kWh battery at 77kW = 1C)
Example: 0.5C = slow charge, 1C = standard, 2C = fast charge
Used by: Charging algorithms, power management, thermal prediction
Impact: Higher C-rates charge faster but generate more heat and degradation

---

Term: Depth of Discharge (DoD)
Definition: Percentage of battery capacity that has been discharged. Inverse of SoC. 
Deep discharges (high DoD) accelerate degradation.
Example: 80% SoC = 20% DoD; 30% SoC = 70% DoD
Used by: Battery engineers, cycle life predictions
Relevance: Frequent deep discharges (DoD > 80%) significantly reduce lifespan

---

Term: Safe Operating Area (SOA)
Definition: Range of voltage, current, and temperature conditions under which battery 
can operate without damage or safety hazard
Example: For Li-ion: Voltage 2.5-4.2V per cell, Temp -20°C to 60°C, Current < 2C
Used by: BMS protection logic, thermal management, safety validation
Enforcement: BMS must prevent operation outside SOA

---

Term: Nominal Capacity
Definition: Rated energy storage capacity of battery pack under standard conditions 
(25°C, 1C discharge rate), measured in kilowatt-hours (kWh)
Example: ID.4 Pro has 77 kWh nominal capacity
Used by: Marketing, range calculations, charging time estimates
Note: Actual usable capacity may be less (typically 95% due to buffer zones)

---

Term: Usable Capacity
Definition: Portion of nominal capacity accessible to driver, typically 90-95% of 
total. Buffer zones reserved to protect battery health.
Example: 82 kWh total, 77 kWh usable (5 kWh buffer)
Used by: Range calculation, charging logic, driver information
Rationale: Never fully charge/discharge cells to extend lifespan

---

Term: Cell Chemistry
Definition: Specific composition of cathode, anode, and electrolyte materials in 
lithium-ion cell, determining performance characteristics
Example: NMC (Nickel Manganese Cobalt) vs LFP (Lithium Iron Phosphate)
Used by: Battery designers, procurement, thermal management
Impact: Different chemistries have different safety, cost, energy density trade-offs

---

Term: Battery Preconditioning
Definition: Active heating or cooling of battery pack to optimal temperature range 
before charging or high-performance driving
Example: In -10°C weather, heat battery from -5°C to 15°C before fast charging
Used by: Thermal management system, charging preparation, navigation integration
Benefit: Enables faster charging, protects cells, improves performance

---

Term: Charge Acceptance
Definition: Rate at which battery can safely accept electrical energy under current 
conditions (temperature, SoC, SoH). Varies dynamically.
Example: At 80% SoC and 35°C, acceptance drops to 30kW even though charger offers 150kW
Used by: Charging algorithms, thermal management, customer expectations
Note: Non-linear; decreases as SoC approaches 100% and at temperature extremes
```

---

#### Core Entities

```markdown
ENTITY: BatteryPack
IDENTITY: batteryPackSerialNumber (unique across all VW vehicles ever produced)
LIFECYCLE: 
  - Created: During vehicle manufacturing when pack is installed
  - Destroyed: When pack is removed for recycling/replacement (end of vehicle life)

KEY ATTRIBUTES:
- batteryPackSerialNumber: UniqueIdentifier - Permanent identity
- nominalCapacity: Energy (kWh) - Design specification
- usableCapacity: Energy (kWh) - Available to driver
- currentStateOfCharge: StateOfCharge - Current charge level
- currentStateOfHealth: StateOfHealth - Degradation metric
- currentTemperature: Temperature - Average pack temperature
- manufactureDate: Date - When pack was built
- cellChemistry: ChemistryType - NMC, LFP, etc.
- modules: List<BatteryModule> - Physical module composition

KEY BEHAVIORS:
- canAcceptCharge(ChargingPower): Boolean 
  Enforces: "Don't charge if temperature outside safe range"
  
- calculateOptimalChargingRate(): ChargingPower
  Enforces: "Reduce rate near 100% SoC or at temperature extremes"
  
- reportCriticalState(): BatteryAlert
  Enforces: "Alert if SoH < 70% or thermal runaway risk detected"
  
- estimateRemainingRange(DrivingConditions): Distance
  Enforces: "Account for current SoC, temperature, driving style"

INVARIANTS:
- currentSoC must be between 0% and 100%
- currentTemperature must be reported every 500ms or trigger fault
- usableCapacity ≤ nominalCapacity (degrades over time)
```

```markdown
ENTITY: BatteryCell
IDENTITY: cellSerialNumber (laser-etched on cell during manufacturing)
LIFECYCLE:
  - Created: During battery pack assembly
  - Destroyed: When pack is disassembled (warranty claim, recycling)

KEY ATTRIBUTES:
- cellSerialNumber: UniqueIdentifier
- currentVoltage: Voltage (V)
- currentTemperature: Temperature (°C)
- cycleCount: Integer - Number of charge/discharge cycles
- manufacturingDefectFlag: Boolean - QA test result
- position: CellPosition - Location in pack (Module 3, Position 12)

KEY BEHAVIORS:
- isBalancingRequired(targetVoltage: Voltage): Boolean
  Enforces: "Balance if voltage delta > 50mV from neighbors"
  
- hasExceededSafeTemperature(): Boolean
  Enforces: "Flag if temp > 60°C or < -20°C"
  
- estimateCycleDegradation(): DegradationRate
  Enforces: "LFP cells: 0.5% per 1000 cycles; NMC: 1% per 500 cycles"

INVARIANTS:
- Voltage must stay between 2.5V and 4.2V (safe operating area)
- Temperature reading required every 100ms
```

```markdown
ENTITY: ChargingSession
IDENTITY: sessionId (UUID generated when cable plugged in)
LIFECYCLE:
  - Created: When charging cable connected and authenticated
  - Destroyed: When charging complete or manually stopped

KEY ATTRIBUTES:
- sessionId: UUID
- startTime: DateTime
- endTime: DateTime (null if in progress)
- chargingStation: ChargingStationId
- vehicleVIN: VIN
- initialSoC: StateOfCharge
- targetSoC: StateOfCharge
- energyDelivered: Energy (kWh)
- averageChargingRate: Power (kW)
- peakTemperatureReached: Temperature
- totalCost: Money

KEY BEHAVIORS:
- calculateEstimatedCompletionTime(): DateTime
  Enforces: "Account for curve: fast until 80%, then taper"
  
- shouldReduceChargingRate(): Boolean
  Enforces: "Slow down if temp > 40°C or SoC > 80%"
  
- recordEnergyDelivered(increment: Energy): void
  Enforces: "Update every 30 seconds for billing accuracy"

INVARIANTS:
- sessionId must be unique globally
- startTime < endTime (if endTime exists)
- energyDelivered ≥ 0
```

```markdown
ENTITY: ServiceAppointment
IDENTITY: appointmentId
LIFECYCLE:
  - Created: When customer schedules service
  - Destroyed: After service completed and documented

KEY ATTRIBUTES:
- appointmentId: UUID
- vehicleVIN: VIN
- scheduledDate: DateTime
- serviceType: ServiceType (routine, diagnostic, warranty)
- diagnosedIssues: List<DiagnosticTroubleCode>
- batteryHealthAtService: StateOfHealth

KEY BEHAVIORS:
- requiresBatteryDiagnostic(): Boolean
  Enforces: "If any battery-related DTC codes present"
  
- isWarrantyClaimed(): Boolean
  Enforces: "True if battery issue within warranty period"

INVARIANTS:
- scheduledDate must be in future when created
- batteryHealthAtService recorded for all appointments
```
```

---

#### Value Objects

```markdown
VALUE OBJECT: StateOfCharge
ATTRIBUTES:
- percentage: Double (0.0 to 100.0)

WHY IT MATTERS:
Fundamental measurement that drives range calculation, charging decisions, driver info

IMMUTABILITY:
SoC is a measurement at a point in time. To represent change, create new instance.

BEHAVIORS:
- isBelowThreshold(threshold: Percentage): Boolean
- isAboveThreshold(threshold: Percentage): Boolean
- toKilowattHours(batteryCapacity: Energy): Energy
- distanceFromFull(): Percentage

EQUALITY:
Two SoC values are equal if percentage is identical (67.5% = 67.5%)

EXAMPLE:
StateOfCharge.of(67.5, PERCENT)  // 67.5%
```

```markdown
VALUE OBJECT: Temperature
ATTRIBUTES:
- value: Double
- unit: TemperatureUnit (CELSIUS, FAHRENHEIT, KELVIN)

WHY IT MATTERS:
Critical safety parameter; determines charging rate, performance, thermal management

IMMUTABILITY:
Temperature is snapshot. New reading = new instance.

BEHAVIORS:
- isWithinSafeRange(range: TemperatureRange): Boolean
- convertTo(unit: TemperatureUnit): Temperature
- isAboveThreshold(threshold: Temperature): Boolean
- isCritical(): Boolean // < -20°C or > 60°C

EQUALITY:
Equal if value and unit are same, OR if converted values match
Temperature.of(20, CELSIUS) equals Temperature.of(68, FAHRENHEIT)

EXAMPLE:
Temperature.of(25, CELSIUS)
```

```markdown
VALUE OBJECT: ChargingPower
ATTRIBUTES:
- kilowatts: Double

WHY IT MATTERS:
Determines charging speed, heat generation, degradation rate

IMMUTABILITY:
Power level is instantaneous measurement

BEHAVIORS:
- isFastCharging(): Boolean // > 50kW
- toChargingTime(energyNeeded: Energy): Duration
- exceedsBatteryAcceptance(maxAcceptance: Power): Boolean

EQUALITY:
Equal if kilowatts match (150.0 kW = 150.0 kW)

EXAMPLE:
ChargingPower.of(150, KILOWATTS)  // 150 kW DC fast charge
```

```markdown
VALUE OBJECT: Energy
ATTRIBUTES:
- kilowattHours: Double

WHY IT MATTERS:
Capacity measurement, energy delivered during charge, range calculation input

IMMUTABILITY:
Energy amount is a quantity, not mutable state

BEHAVIORS:
- toRange(efficiency: EnergyPerDistance): Distance
- plus(other: Energy): Energy
- minus(other: Energy): Energy

EQUALITY:
Equal if kilowattHours match

EXAMPLE:
Energy.of(77, KILOWATT_HOURS)  // Battery capacity
```

```markdown
VALUE OBJECT: VoltageRange
ATTRIBUTES:
- minimum: Voltage
- maximum: Voltage

WHY IT MATTERS:
Defines safe operating limits for cells

IMMUTABILITY:
Operating range is specification, not runtime state

BEHAVIORS:
- contains(voltage: Voltage): Boolean
- getMarginToLimit(currentVoltage: Voltage): Voltage

EXAMPLE:
VoltageRange.of(2.5, 4.2, VOLTS)  // Li-ion safe range
```

---

#### Critical Business Rules

```markdown
RULE: Cold Weather Charging Restriction
CONDITION: When currentTemperature < -10°C AND charging requested
ACTION: System must refuse charging AND notify driver "Battery too cold for charging"
RATIONALE: Charging lithium-ion cells below -10°C causes lithium plating on anode, 
           permanently reducing capacity and creating safety hazard (dendrite growth)
EXCEPTION: If battery preconditioning active (heating), wait until temperature > -5°C, 
           then allow charging at reduced rate (< 0.5C)
ENFORCEMENT POINT: BatteryPack.canAcceptCharge()
REGULATORY BASIS: SAE J2954 wireless charging standard, LG Chem battery datasheet

---

RULE: Cell Balancing Voltage Threshold
CONDITION: During charging, if any cell's voltage differs from pack average by > 50mV
ACTION: BMS must initiate passive balancing (discharge high cells via resistors) until 
        delta < 30mV
RATIONALE: Voltage imbalance indicates unequal capacity or resistance. Prevents weakest 
           cell from limiting entire pack capacity. Ensures even aging.
EXCEPTION: If balancing current would exceed 500mA, flag for service inspection 
           (possible cell degradation)
ENFORCEMENT POINT: BatteryManagementService.monitorCellBalance()
TECHNICAL BASIS: Cell internal resistance specification < 10mΩ

---

RULE: State of Health Warning Threshold
CONDITION: When SoH drops below 70% of original capacity
ACTION: Display persistent warning to driver "Battery capacity reduced - service 
        recommended" AND log warranty claim trigger event
RATIONALE: 70% SoH is industry standard for "end of first life" - battery can still 
           function but range significantly impacted. Triggers warranty evaluation.
EXCEPTION: None - this is hard safety/warranty threshold
ENFORCEMENT POINT: BatteryPack.reportCriticalState()
WARRANTY BASIS: VW 8-year/160,000 km battery warranty guarantees 70% SoH

---

RULE: Fast Charging Temperature Ceiling
CONDITION: During fast charging (> 100kW), if battery temperature exceeds 40°C
ACTION: Reduce charging power by 50% every 2°C above 40°C, stop entirely at 50°C
RATIONALE: High power + high temperature accelerates degradation (SEI layer growth 
           on anode). Prevents thermal runaway risk.
EXCEPTION: If active cooling can reduce temp by 5°C within 60 seconds, maintain rate
ENFORCEMENT POINT: ChargingSession.calculateOptimalChargingRate()
THERMAL PHYSICS: Above 40°C, reaction rate doubles per 10°C (Arrhenius equation)

---

RULE: Minimum Reserve Capacity
CONDITION: Always maintain 5% SoC buffer below 0% displayed to driver
ACTION: When display shows 0%, actual SoC is 5%. Prevent discharge below this point.
RATIONALE: Fully discharging lithium-ion to true 0% causes copper dissolution from 
           current collector, permanent damage. Reserve ensures cell longevity.
EXCEPTION: Emergency mode allows access to reserve if vehicle stranded (manual override)
ENFORCEMENT POINT: BatteryPack.usableCapacity calculation
CHEMISTRY BASIS: Below 2.5V/cell, irreversible chemical changes occur

---

RULE: Charge Rate Tapering Above 80% SoC
CONDITION: When SoC > 80% during any charging
ACTION: Reduce charging current following formula: ChargingPower = MaxPower × (100 - SoC) / 20
        Example: At 90% SoC, only allow 50% of max power
RATIONALE: High voltage (near 4.2V/cell) + high current causes lithium plating, 
           capacity fade, and dendrite formation. Tapering extends lifespan.
EXCEPTION: None - this is fundamental electrochemistry, not configurable
ENFORCEMENT POINT: ChargingSession.shouldReduceChargingRate()
RESEARCH BASIS: Battery University, Tesla battery management patents

---

RULE: Thermal Runaway Prevention
CONDITION: If any cell exceeds 80°C OR rate of temperature increase > 5°C per minute
ACTION: 
  1. Immediately disconnect high-voltage contactors (isolate battery)
  2. Activate maximum cooling (fans, liquid cooling)
  3. Alert driver "Battery emergency - pull over safely"
  4. Prevent charging/discharging until temperature < 40°C for 30 minutes
RATIONALE: 80°C approaches electrolyte decomposition temperature (~120-150°C). Rapid 
           increase indicates exothermic reaction starting. Must prevent cascade.
EXCEPTION: None - this is critical safety shutdown, no override allowed
ENFORCEMENT POINT: BatteryPackSafetyMonitor (separate watchdog process)
SAFETY STANDARD: ISO 26262 ASIL-D (highest automotive safety integrity level)
```

---

#### Domain Events

```markdown
EVENT: BatteryPackInstalled
TRIGGER: During vehicle manufacturing when battery physically mounted and electrically connected
DATA:
  - vehicleVIN: VIN
  - batteryPackSerialNumber: String
  - installedAt: DateTime
  - installedBy: TechnicianId
  - initialSoH: StateOfHealth (should be 100%)

WHY IT MATTERS:
- Starts battery warranty clock
- Initializes battery tracking system
- Links battery to vehicle in service history

SUBSCRIBERS:
- Warranty management system
- Manufacturing quality tracking
- Service history database

---

EVENT: ChargingSessionStarted
TRIGGER: When vehicle authenticates with charging station and current begins flowing
DATA:
  - sessionId: UUID
  - vehicleVIN: VIN
  - chargingStationId: String
  - startTime: DateTime
  - initialSoC: StateOfCharge
  - requestedChargingPower: Power

WHY IT MATTERS:
- Initiates billing
- Logs charging patterns for degradation analysis
- Enables customer notifications ("charging started at...")

SUBSCRIBERS:
- Billing service
- Customer mobile app
- Battery analytics platform
- Charging network operations

---

EVENT: CriticalTemperatureExceeded
TRIGGER: When any cell temperature exceeds 80°C OR pack average exceeds 60°C
DATA:
  - batteryPackSerialNumber: String
  - vehicleVIN: VIN
  - criticalTemperature: Temperature
  - location: CellPosition (which cell/module)
  - timestamp: DateTime
  - ambientTemperature: Temperature
  - currentActivity: Activity (charging/driving/idle)

WHY IT MATTERS:
- Critical safety event requiring immediate response
- May trigger warranty claim
- Data needed for safety investigation

SUBSCRIBERS:
- Battery safety shutdown system
- Cloud safety monitoring
- Customer emergency notification
- Engineering root cause analysis

---

EVENT: StateOfHealthDegraded
TRIGGER: When SoH measurement drops below key thresholds (95%, 90%, 85%, 80%, 70%)
DATA:
  - batteryPackSerialNumber: String
  - vehicleVIN: VIN
  - newStateOfHealth: StateOfHealth
  - previousStateOfHealth: StateOfHealth
  - measuredAt: DateTime
  - totalCycleCount: Integer
  - totalEnergyThroughput: Energy (kWh charged over lifetime)

WHY IT MATTERS:
- Triggers warranty evaluation at 70%
- Alerts customer to expect reduced range
- Feeds degradation prediction models

SUBSCRIBERS:
- Warranty claims system
- Customer notification service
- Battery analytics/research
- Service scheduling (proactive maintenance)

---

EVENT: CellBalancingRequired
TRIGGER: When voltage delta between cells exceeds 50mV during monitoring
DATA:
  - batteryPackSerialNumber: String
  - affectedCells: List<CellPosition>
  - voltageDelta: Voltage (mV)
  - detectedAt: DateTime
  - currentSoC: StateOfCharge

WHY IT MATTERS:
- Indicates potential cell degradation
- Triggers automated balancing process
- May require service if persistent

SUBSCRIBERS:
- Battery management control system
- Service diagnostic system
- Battery health analytics

---

EVENT: FastChargingCompleted
TRIGGER: When charging session ends AND peak power was > 100kW
DATA:
  - sessionId: UUID
  - vehicleVIN: VIN
  - energyDelivered: Energy
  - averageChargingPower: Power
  - peakPower: Power
  - duration: Duration
  - finalSoC: StateOfCharge
  - peakTemperature: Temperature
  - completedAt: DateTime

WHY IT MATTERS:
- Fast charging stresses battery more than slow charging
- Track for degradation correlation studies
- Customer behavior analysis (how often do they fast charge?)

SUBSCRIBERS:
- Battery analytics platform
- Charging network (capacity planning)
- Customer billing system
- Mobile app (charging history)

---

EVENT: WarrantyClaimTriggered
TRIGGER: When SoH < 70% within warranty period (8 years / 160,000 km)
DATA:
  - vehicleVIN: VIN
  - batteryPackSerialNumber: String
  - currentSoH: StateOfHealth
  - vehicleAge: Duration
  - totalMileage: Distance
  - triggeredAt: DateTime
  - fastChargeCount: Integer (how many fast charge sessions)
  - averageDoD: Percentage (how deeply was battery typically discharged)

WHY IT MATTERS:
- Initiates warranty claim process
- May require battery replacement (expensive!)
- Data used to validate warranty terms

SUBSCRIBERS:
- Warranty claims processing
- Dealer service scheduling
- Battery procurement (order replacement)
- Customer communication
- Warranty analytics (is 70% threshold appropriate?)
```

---

### Validation Checklist Assessment

**Let's apply the checklist to this solution:**

- [x] **Every technical term has business justification**
  - "Thermal runaway" explained with business impact (safety, fire risk)
  - "C-rate" explained with degradation and charging time implications
  - No unexplained jargon

- [x] **Battery engineer could read glossary and recognize domain**
  - Terms match industry standard vocabulary (SoC, SoH, cell balancing)
  - Definitions are technically accurate
  - Examples are realistic (ID.4, specific voltages, temperatures)

- [x] **Business rules reference glossary terms**
  - "Cold Weather Charging Restriction" uses "currentTemperature" and "charging"
  - "Cell Balancing" rule references "voltage delta" and "safe operating area"
  - No generic programming terms in rules

- [x] **Entities have clear identity**
  - BatteryPack: serial number (laser-etched, unique worldwide)
  - Cell: cell serial number (different from pack serial)
  - ChargingSession: UUID (two sessions can have same parameters but different identity)
  - ServiceAppointment: appointment ID (reschedule creates new appointment, different ID)

- [x] **Value objects are immutable concepts**
  - StateOfCharge: measurement at point in time (67.5%)
  - Temperature: snapshot (25°C)
  - Energy: quantity (77 kWh)
  - All have equality based on value, not identity

- [x] **Events capture business-meaningful occurrences**
  - Not "ButtonClicked" but "ChargingSessionStarted"
  - Not "DataUpdated" but "StateOfHealthDegraded"
  - Not "FlagSet" but "CriticalTemperatureExceeded"

---

### Alternate Approaches

#### Approach A: Physics-First Modeling

**Concept:** Model all electrochemical reactions, thermal dynamics, electrical circuits

```java
class ElectrochemicalCell {
    private AnodeMaterial anode;  // Graphite crystal structure
    private CathodeMaterial cathode;  // NMC811 composition
    private ElectrolyteSolution electrolyte;  // Lithium salt concentration
    private SEILayer solidElectrolyteInterphase;  // Thickness in nanometers
    
    ChemicalReaction calculateLithiumIntercalation() {
        // Model lithium ion movement through electrolyte
    }
}
```

**Pros:**
- Scientifically complete
- Enables advanced simulation
- Deep understanding of phenomena

**Cons:**
- **Overkill:** Charging system doesn't need nanometer-scale modeling
- **Complexity:** Very difficult to implement and maintain
- **Performance:** Computational intensive
- **Expertise:** Requires PhD-level chemistry knowledge

**Verdict:** Too much detail for software system. This is research simulation, not production BMS.

---

#### Approach B: Database-First Modeling

**Concept:** Start with tables/storage, derive model from schema

```sql
CREATE TABLE battery_data (
    id INT PRIMARY KEY,
    vin VARCHAR(17),
    soc_percent DECIMAL(5,2),
    temp_celsius DECIMAL(5,2),
    soh_percent DECIMAL(5,2),
    last_updated TIMESTAMP
);
```

**Pros:**
- Familiar to many developers
- Storage structure clear from start
- Performance optimized

**Cons:**
- **Database drives design:** Model shaped by storage, not business
- **Anemic domain model:** Classes become data bags with no behavior
- **Lost domain knowledge:** Business rules end up in application layer
- **Inflexible:** Schema changes ripple through system

**Verdict:** Anti-pattern for DDD. Storage is implementation detail, not starting point.

---

#### Approach C: Domain-First (Recommended)

**Concept:** Model business concepts, ignore implementation initially

```java
class BatteryPack {
    // Model what battery engineers think about
    boolean canAcceptCharge(ChargingPower requestedPower) {
        // Business rule: check temperature, SoC, SoH
        return currentTemperature.isWithinSafeRange() && 
               chargeAcceptance.allows(requestedPower);
    }
}
```

**Pros:**
- **Domain-centric:** Matches how experts think
- **Rich behavior:** Business rules in domain model
- **Testable:** Can validate rules without database
- **Flexible:** Storage can change without affecting model

**Cons:**
- **Learning curve:** Different from CRUD mindset
- **Requires domain knowledge:** Can't just invent terms
- **More classes:** Separate entities, value objects, services

**Verdict:** This is DDD. Start with domain, add infrastructure later.

---

### Common Mistakes

#### Mistake 1: "I'll Model Everything in One Big Entity"

**Bad:**
```java
class BatterySystem {
    // 100+ attributes combining pack, cells, modules, 
    // charging, thermal, service history...
}
```

**Fix:** Separate concerns. BatteryPack entity, BatteryCell entity, ChargingSession entity.

---

#### Mistake 2: "Primitive Obsession"

**Bad:**
```java
double soc;  // is this 0-1 or 0-100? Units unclear
int temp;    // Celsius? Fahrenheit? Kelvin?
```

**Fix:** Value objects with explicit units
```java
StateOfCharge currentSoC = StateOfCharge.of(67.5, PERCENT);
Temperature temp = Temperature.of(25, CELSIUS);
```

---

#### Mistake 3: "Business Rules in Service Layer"

**Bad:**
```java
class BatteryService {
    boolean canCharge(BatteryData battery) {
        // All logic here, battery is just data
        if (battery.temp < -10) return false;
    }
}

class BatteryData {
    int temp;  // Dumb data container
}
```

**Fix:** Move logic to domain model
```java
class BatteryPack {
    boolean canAcceptCharge() {
        return currentTemperature.isWithinSafeRange();
    }
}
```

---

### Step-by-Step Solution Walkthrough

**Step 1: Start with an Interview (Real or Imagined)**

"What does a battery engineer worry about?"
- Cell degradation
- Thermal management
- Safe charging
- Warranty compliance

→ These become core concepts

**Step 2: Extract Nouns (Become Entities or Value Objects)**

From requirements: "monitoring cell health across 288 cells"
- "cell health" → StateOfHealth (value object, measurement)
- "cell" → BatteryCell (entity, has identity and lifecycle)

**Step 3: Extract Verbs (Become Behaviors)**

"Controlling charging rate based on temperature"
→ `calculateOptimalChargingRate()`

**Step 4: Find the Constraints (Become Business Rules)**

"Don't charge below -10°C"
→ Rule: Cold Weather Charging Restriction

**Step 5: Identify Significant Occurrences (Become Events)**

"Alerting drivers to degradation"
→ Event: StateOfHealthDegraded

**Step 6: Iterate - Refine Definitions**

First draft: "State of Charge is how full the battery is"
Refined: "Percentage of current capacity relative to maximum, 0-100%, not accounting for degradation"

**Step 7: Validate with Expert (or Documentation)**

Check: Are these the terms battery engineers actually use?
- Yes: StateOfCharge, StateOfHealth, C-rate
- No: "Charge amount" → Use "StateOfCharge"

---

### Expert Analysis

**What Makes This Exercise Challenging:**

1. **Domain Complexity:** Battery chemistry is genuinely complex. Easy to get lost in details.

2. **Terminology Precision:** SoC vs SoH vs DoD - similar but different. Must be precise.

3. **Balancing Detail:** Need enough detail to be useful, not so much to be overwhelming.

4. **Real-World Constraints:** Can't just invent rules. Must match actual battery science.

**The Learning Value:**

This exercise forces you to:
- Think like a domain expert (battery engineer)
- Distinguish identity (battery pack serial number) from measurements (SoC)
- Model behavior, not just data
- Make implicit rules explicit ("why don't we charge when cold?")

**Pro Tip from Experience:**

When modeling complex domains, create the glossary FIRST. It forces precision and reveals ambiguity early. If you can't define a term clearly, you don't understand it well enough to model it.

---

## Exercise 5 Solutions: The Translation Challenge

### Approach Brief

**Skill:** Extracting domain model from natural language expert conversation

**Process:**
1. **Listen for nouns** → Candidate concepts
2. **Listen for verbs** → Behaviors
3. **Listen for rules** → Business constraints
4. **Identify measurements** → Value objects
5. **Identify significant things** → Entities
6. **Structure relationships** → How concepts connect

---

### Model Solution

#### Step 1: Domain Model Extraction

**CONCEPTS (nouns that matter):**

1. **LaneMarking**
   - Type: Visual feature on road
   - Detected by front camera
   - Types mentioned: (implied left line, center line, right line)
   - Quality varies: (rainy conditions, faded paint affect detection)

2. **LaneDeparture / Drift**
   - Type: Event / State
   - Occurs when vehicle crosses line without driver intent
   - Can be caused by: inattention or wind

3. **LaneCenter**
   - Type: Target position
   - Calculated from left and right lane markings
   - Goal of intervention

4. **TurnSignal / TurnIndicator**
   - Type: Driver intent signal
   - Presence prevents intervention
   - Indicates intentional lane change vs drift

5. **SteeringIntervention / SteeringCorrection**
   - Type: System action
   - Described as "gentle push back"
   - Guides toward lane center

6. **VehicleSpeed**
   - Type: Measurement
   - Threshold: 65 km/h
   - Below threshold → system inactive (city speeds allow maneuvering/parking)

7. **DetectionConfidence**
   - Type: Quality metric
   - Threshold: 75%
   - Below threshold → no intervention (safety first)
   - Affected by weather, paint quality

8. **Camera** (Front-Facing)
   - Type: Sensor
   - Detects lane markings
   - Provides confidence level

---

**RELATIONSHIPS (how concepts connect):**

```
Camera ──detects──> LaneMarking
                        │
                        │provides
                        ↓
                  DetectionConfidence

LaneMarking ──defines──> LaneCenter
     │
     │when crossed
     ↓
LaneDeparture ──triggers──> SteeringIntervention
                                 │
                                 │guides toward
                                 ↓
                            LaneCenter

VehicleSpeed ──enables/disables──> System
TurnSignal ──prevents──> SteeringIntervention
DetectionConfidence ──gates──> SteeringIntervention
```

---

**BUSINESS RULES (conditions and actions):**

**Rule 1: Minimum Speed Activation**
- **Condition:** System only active when VehicleSpeed ≥ 65 km/h
- **Rationale:** At city speeds, driver may be parking or maneuvering intentionally
- **Action:** Below 65 km/h, disable steering intervention (but keep monitoring)

**Rule 2: Driver Intent Respect**
- **Condition:** If driver has activated turn signal, assume lane change is intentional
- **Action:** Do NOT intervene, even if drifting toward line
- **Rationale:** Respect driver's explicit signals of intent

**Rule 3: Confidence Threshold**
- **Condition:** DetectionConfidence < 75%
- **Action:** Warn driver "Lane keeping unavailable" AND do NOT intervene with steering
- **Rationale:** Safety first - better no assistance than wrong assistance
- **Causes:** Rain, faded paint, snow, glare

**Rule 4: Intervention Timing**
- **Condition:** Vehicle drifting toward lane marking AND speed ≥ 65 km/h AND no turn signal AND confidence ≥ 75%
- **Action:** Apply gentle steering torque to guide back to lane center
- **Magnitude:** "Gentle" - driver can easily override

---

#### Step 2: Model Diagram (Text Format)

```
┌──────────────────────────────┐
│   LaneKeepingAssistSystem    │
├──────────────────────────────┤
│ - enabled: Boolean           │
│ - minimumSpeed: Speed        │
├──────────────────────────────┤
│ + shouldIntervene(): Boolean │
│ + applyCorrection(): void    │
└──────────────────────────────┘
            │
            │ uses
            ↓
┌──────────────────────────────┐
│    FrontFacingCamera         │
├──────────────────────────────┤
│ + detectLaneMarkings():      │
│   LaneMarkingDetection       │
└──────────────────────────────┘
            │
            │ produces
            ↓
┌──────────────────────────────┐
│   LaneMarkingDetection       │ (Value Object)
├──────────────────────────────┤
│ - leftMarking: LaneMarking   │
│ - rightMarking: LaneMarking  │
│ - confidence: Percentage     │
│ - timestamp: DateTime        │
├──────────────────────────────┤
│ + hasSufficientConfidence(): │
│   Boolean                    │
│ + calculateLaneCenter():     │
│   Position                   │
└──────────────────────────────┘
            │
            │ consumed by
            ↓
┌──────────────────────────────┐
│ InterventionDecisionService  │
├──────────────────────────────┤
│ + evaluateNeed(              │
│     vehicle: VehicleState,   │
│     detection: Detection,    │
│     driver: DriverState      │
│   ): Decision                │
└──────────────────────────────┘

┌──────────────────────────────┐
│      VehicleState            │ (Value Object)
├──────────────────────────────┤
│ - currentSpeed: Speed        │
│ - lateralPosition: Position  │
├──────────────────────────────┤
│ + isAboveCitySpeed():        │
│   Boolean                    │
└──────────────────────────────┘

┌──────────────────────────────┐
│       DriverState            │ (Value Object)
├──────────────────────────────┤
│ - turnSignalActive: Boolean  │
├──────────────────────────────┤
│ + hasSignaledTurnIntent():   │
│   Boolean                    │
└──────────────────────────────┘

┌──────────────────────────────┐
│  SteeringActuator            │
├──────────────────────────────┤
│ + applyGentleTorque(         │
│     direction: Direction,    │
│     magnitude: Torque        │
│   ): void                    │
└──────────────────────────────┘


RELATIONSHIPS:

LaneKeepingAssistSystem ──uses──> FrontFacingCamera
LaneKeepingAssistSystem ──uses──> InterventionDecisionService
LaneKeepingAssistSystem ──commands──> SteeringActuator

InterventionDecisionService ──evaluates──> LaneMarkingDetection
InterventionDecisionService ──evaluates──> VehicleState
InterventionDecisionService ──evaluates──> DriverState

FrontFacingCamera ──produces──> LaneMarkingDetection


EVENTS:

LaneDepartureDetected ──triggers──> InterventionDecisionService
InterventionApplied ──logs──> System
InterventionUnavailable ──notifies──> Driver
```

---

#### Step 3: Domain-Centric Code

```java
/**
 * Lane Keeping Assist System
 * Monitors lane position and applies gentle steering corrections
 * to help driver stay centered in lane.
 */
public class LaneKeepingAssistSystem {
    
    private static final Speed MINIMUM_ACTIVATION_SPEED = Speed.of(65, KILOMETERS_PER_HOUR);
    private static final Percentage MINIMUM_CONFIDENCE = Percentage.of(75);
    
    private final FrontFacingCamera camera;
    private final InterventionDecisionService decisionService;
    private final SteeringActuator steeringActuator;
    private boolean systemEnabled;
    
    /**
     * Main control loop - called continuously while driving
     */
    public void monitorAndIntervene(VehicleState vehicle, DriverState driver) {
        if (!systemEnabled) {
            return;
        }
        
        // Get current lane detection from camera
        LaneMarkingDetection detection = camera.detectLaneMarkings();
        
        // Decide if intervention is needed and safe
        InterventionDecision decision = decisionService.evaluateNeed(
            vehicle, 
            detection, 
            driver
        );
        
        // Act on decision
        if (decision.shouldIntervene()) {
            applySteeringCorrection(vehicle, detection);
        } else if (decision.isSystemUnavailable()) {
            notifyDriver("Lane keeping unavailable - low visibility");
        }
    }
    
    private void applySteeringCorrection(VehicleState vehicle, 
                                         LaneMarkingDetection detection) {
        // Calculate how far we are from lane center
        Position laneCenter = detection.calculateLaneCenter();
        Position currentPosition = vehicle.getLateralPosition();
        
        Direction correctionDirection = laneCenter.directionFrom(currentPosition);
        Torque gentleTorque = Torque.GENTLE_CORRECTION;
        
        steeringActuator.applyGentleTorque(correctionDirection, gentleTorque);
        
        // Log for diagnostics
        logInterventionApplied(vehicle, detection);
    }
}

/**
 * Value Object: Detection results from camera with confidence level
 */
public class LaneMarkingDetection {
    private final LaneMarking leftMarking;
    private final LaneMarking rightMarking;
    private final Percentage confidence;
    private final DateTime detectedAt;
    
    /**
     * Business Rule: Confidence Threshold
     * Below 75%, don't trust the detection
     */
    public boolean hasSufficientConfidence() {
        return confidence.isAtLeast(Percentage.of(75));
    }
    
    /**
     * Calculate ideal position between lane markings
     */
    public Position calculateLaneCenter() {
        return leftMarking.midpointTo(rightMarking);
    }
    
    public boolean isLaneDepartureDetected(Position vehiclePosition) {
        // Check if vehicle is crossing either marking
        return leftMarking.isBeingCrossed(vehiclePosition) ||
               rightMarking.isBeingCrossed(vehiclePosition);
    }
}

/**
 * Service: Encapsulates complex decision logic
 * for when intervention is appropriate
 */
public class InterventionDecisionService {
    
    private static final Speed MINIMUM_SPEED = Speed.of(65, KILOMETERS_PER_HOUR);
    
    public InterventionDecision evaluateNeed(VehicleState vehicle,
                                             LaneMarkingDetection detection,
                                             DriverState driver) {
        // Business Rule: Minimum Speed
        if (vehicle.isAboveCitySpeed() == false) {
            return InterventionDecision.inactive("Below 65 km/h - city driving");
        }
        
        // Business Rule: Confidence Threshold
        if (detection.hasSufficientConfidence() == false) {
            return InterventionDecision.unavailable("Low lane detection confidence");
        }
        
        // Business Rule: Driver Intent
        if (driver.hasSignaledTurnIntent()) {
            return InterventionDecision.inactive("Driver signaled intentional lane change");
        }
        
        // Business Rule: Departure Detection
        if (detection.isLaneDepartureDetected(vehicle.getLateralPosition())) {
            return InterventionDecision.intervene("Unintentional lane departure detected");
        }
        
        // All clear - monitoring but no action needed
        return InterventionDecision.monitoring("Centered in lane");
    }
}

/**
 * Value Object: Current vehicle dynamic state
 */
public class VehicleState {
    private final Speed currentSpeed;
    private final Position lateralPosition;  // Distance from lane center
    
    /**
     * Business Rule: Speed threshold for activation
     * 65 km/h is boundary between city and highway driving
     */
    public boolean isAboveCitySpeed() {
        Speed minimumHighwaySpeed = Speed.of(65, KILOMETERS_PER_HOUR);
        return currentSpeed.isGreaterThanOrEqual(minimumHighwaySpeed);
    }
    
    public Position getLateralPosition() {
        return lateralPosition;
    }
}

/**
 * Value Object: Driver's current inputs and state
 */
public class DriverState {
    private final boolean leftTurnSignalActive;
    private final boolean rightTurnSignalActive;
    
    /**
     * Business Rule: Respect explicit driver signals
     * If driver signals lane change, it's intentional
     */
    public boolean hasSignaledTurnIntent() {
        return leftTurnSignalActive || rightTurnSignalActive;
    }
}

/**
 * Decision value object with clear semantics
 */
public class InterventionDecision {
    private final DecisionType type;
    private final String rationale;
    
    public enum DecisionType {
        INTERVENE,           // Apply steering correction
        MONITORING,          // Watch but don't act
        INACTIVE,            // System disabled (speed, driver intent)
        UNAVAILABLE          // System can't help (low confidence)
    }
    
    public static InterventionDecision intervene(String reason) {
        return new InterventionDecision(DecisionType.INTERVENE, reason);
    }
    
    public static InterventionDecision monitoring(String reason) {
        return new InterventionDecision(DecisionType.MONITORING, reason);
    }
    
    public static InterventionDecision inactive(String reason) {
        return new InterventionDecision(DecisionType.INACTIVE, reason);
    }
    
    public static InterventionDecision unavailable(String reason) {
        return new InterventionDecision(DecisionType.UNAVAILABLE, reason);
    }
    
    public boolean shouldIntervene() {
        return type == DecisionType.INTERVENE;
    }
    
    public boolean isSystemUnavailable() {
        return type == DecisionType.UNAVAILABLE;
    }
}
```

---

### Comparison: Bad vs Good Versions

**❌ BAD - Technical Thinking:**
```java
if (speed > 65 && conf > 75 && !sig && drift) {
    steer = true;
}
```

**Problems:**
1. **Magic numbers:** 65, 75 - what do they mean?
2. **Unclear variables:** conf? sig? drift?
3. **Boolean soup:** What combination means what?
4. **Hidden knowledge:** Business rules buried in boolean logic
5. **Untestable:** Can't test "drift detection" in isolation

---

**✅ GOOD - Domain Thinking:**
```java
if (vehicle.isAboveCitySpeed() && 
    laneMarkingDetection.hasSufficientConfidence() &&
    !driver.hasSignaledTurnIntent() &&
    laneMarkingDetection.isLaneDepartureDetected(vehicle.getLateralPosition())) {
    laneKeepingAssist.applyGentleSteeringCorrection();
}
```

**Improvements:**
1. **Named concepts:** "city speed", "sufficient confidence", "turn intent"
2. **Clear intent:** Each condition readable
3. **Domain language:** Terms ADAS engineer would recognize
4. **Testable:** Each method can be tested independently
5. **Self-documenting:** Minimal comments needed

---

### Alternate Approaches & Tradeoffs

#### Approach A: State Machine Model

**Concept:** Model system as explicit states and transitions

```java
enum LaneKeepingState {
    DISABLED,           // Speed < 65
    MONITORING,         // Active but no departure
    INTERVENING,        // Applying correction
    UNAVAILABLE         // Confidence < 75%
}

class LaneKeepingAssist {
    private LaneKeepingState state;
    
    void update(VehicleState vehicle, LaneDetection detection, DriverState driver) {
        state = determineState(vehicle, detection, driver);
        
        switch (state) {
            case INTERVENING:
                applyCorrection();
                break;
            case UNAVAILABLE:
                warnDriver();
                break;
            // ...
        }
    }
}
```

**Pros:**
- **Clear states:** Explicit system modes
- **Transition logic:** Easy to visualize state diagram
- **Debugging:** Know exactly what state system is in

**Cons:**
- **State explosion:** Many states if conditions complex
- **Overlap:** Same state might need different handling based on context

**When to Use:** Systems with clear, discrete modes

---

#### Approach B: Rule Engine Pattern

**Concept:** Extract each rule as separate evaluator

```java
interface InterventionRule {
    RuleEvaluation evaluate(Context context);
}

class MinimumSpeedRule implements InterventionRule {
    public RuleEvaluation evaluate(Context ctx) {
        if (ctx.vehicle.currentSpeed < 65) {
            return RuleEvaluation.prevent("Below minimum speed");
        }
        return RuleEvaluation.allow();
    }
}

class ConfidenceThresholdRule implements InterventionRule {
    public RuleEvaluation evaluate(Context ctx) {
        if (ctx.detection.confidence < 75) {
            return RuleEvaluation.prevent("Low confidence");
        }
        return RuleEvaluation.allow();
    }
}

// Chain rules together
class RuleChain {
    List<InterventionRule> rules;
    
    Decision evaluate(Context context) {
        for (InterventionRule rule : rules) {
            RuleEvaluation result = rule.evaluate(context);
            if (result.prevents()) {
                return Decision.reject(result.getReason());
            }
        }
        return Decision.allow();
    }
}
```

**Pros:**
- **Modular rules:** Each rule independent
- **Easy to add:** New rule = new class
- **Testable:** Test each rule in isolation
- **Configurable:** Can enable/disable rules at runtime

**Cons:**
- **Over-engineering:** For 4 simple rules, this is overkill
- **Harder to follow:** Logic distributed across many classes
- **Performance:** Object creation overhead

**When to Use:** Many complex rules, rules change frequently, rules configured differently per market

---

#### Approach C: Simple Service Method (Recommended for This Case)

**Concept:** Straightforward method with clear conditions (shown in main solution)

**Pros:**
- **Readable:** All logic in one place
- **Sufficient:** Handles the complexity we actually have
- **Maintainable:** Easy to modify
- **Testable:** Can test decision service

**Cons:**
- **Could grow:** If many more rules added, consider refactoring

**When to Use:** Moderate complexity (like this case), stable requirements

---

### Common Mistakes

#### Mistake 1: "I'll Combine All Conditions into One If Statement"

**Bad:**
```java
if (v.s > 65 && d.c > 75 && !ds.t && lm.l.c(v.p) || lm.r.c(v.p)) {
    // What does this even mean?
}
```

**Fix:** Break into named sub-conditions
```java
boolean speedSufficient = vehicle.isAboveCitySpeed();
boolean confidenceSufficient = detection.hasSufficientConfidence();
boolean driverIntentionallyChanging = driver.hasSignaledTurnIntent();
boolean departing = detection.isLaneDepartureDetected(vehicle.position);

if (speedSufficient && confidenceSufficient && 
    !driverIntentionallyChanging && departing) {
    intervene();
}
```

---

#### Mistake 2: "I'll Use Enums for Everything"

**Bad:**
```java
enum Speed {
    ZERO, SLOW, MEDIUM, FAST, VERY_FAST
}

// Now what's the threshold? MEDIUM? FAST?
```

**Fix:** Use actual value with clear threshold
```java
class Speed {
    private int kilometersPerHour;
    
    boolean isAbove(Speed threshold) {
        return this.kilometersPerHour > threshold.kilometersPerHour;
    }
}

Speed cityThreshold = Speed.of(65, KILOMETERS_PER_HOUR);
```

---

#### Mistake 3: "I'll Skip Value Objects for Simplicity"

**Bad:**
```java
int speed;  // km/h? mph? what if we need to convert?
int confidence;  // 0-100? 0-1? percentage?
```

**Fix:** Explicit value objects
```java
Speed speed = Speed.of(70, KILOMETERS_PER_HOUR);
Percentage confidence = Percentage.of(82);
```

---

### Step-by-Step Walkthrough

**Step 1: Read Interview Slowly, Highlight Nouns**

"The system watches **lane markings** through **front camera**. If **car** starts **drifting** toward **line**..."

Lane markings → LaneMarking
Front camera → FrontFacingCamera  
Drifting → LaneDeparture (event/state)

**Step 2: Highlight Conditions (Become Rules)**

"...driver hasn't put on **turn signal**" → Rule: respect driver intent
"...above 65 kilometers per hour" → Rule: minimum speed
"**confidence** below 75%" → Rule: confidence threshold

**Step 3: Highlight Actions (Become Methods)**

"steering wheel will **gently push** back to **guide** to **center**"
→ `applyGentleSteeringCorrection()`
→ `calculateLaneCenter()`

**Step 4: Identify Value Objects**

Speed: measurement, has units, needs comparison
Confidence: percentage, has threshold
Position: lateral position in lane

**Step 5: Identify Entities**

System itself: LaneKeepingAssistSystem (has lifecycle, can be enabled/disabled)

**Step 6: Create Model Diagram**

Connect concepts with relationships

**Step 7: Write Code Using Domain Terms**

Every class name, method name from domain concepts extracted above

---

### Expert Analysis

**Why This Is Hard:**

1. **Natural Language Ambiguity:** "Gently push back" - how gentle? What torque?
2. **Implicit Knowledge:** Expert doesn't say "75% confidence" initially - you had to ask
3. **Missing Concepts:** Expert doesn't mention "LaneCenter" explicitly, you infer it
4. **Technical vs Domain:** Temptation to think in terms of sensors and actuators, not domain

**The Skill Being Practiced:**

This is "knowledge crunching" - the core DDD practice of extracting domain knowledge from experts and crystallizing it into models. In real projects:
- You interview experts multiple times
- You sketch models, get feedback, refine
- You discover ambiguity and force precision
- You iterate toward shared understanding

**This one conversation would spawn:**
- Followup questions about confidence calculation
- Request to see camera specs
- Discussion with safety engineers about intervention limits
- Prototype to test "gentle" torque with drivers

The model evolves through this process, getting more precise each iteration.

---

## Bonus Challenge Solutions: The Bad Model Detective

### Model Solution: 10 Problems Identified

```markdown
PROBLEM 1: Generic Class Name "Thing"
What's wrong: "Thing" is not a domain concept. No expert says "I need to check the Thing."
Why it matters: Code should speak domain language. Reader has no idea what this represents.
How to fix: Based on context (charging station), rename to "ChargingStation"
  class ChargingStation {
      // now it's clear what this is
  }

---

PROBLEM 2: Generic Class Name "Thing2"
What's wrong: Even worse than "Thing" - what's the "2" mean? Second version? Related type?
Why it matters: Impossible to understand code without reading implementation
How to fix: Rename to "Charger" or "ChargingPort"
  class Charger {
      // represents individual charging port at station
  }

---

PROBLEM 3: Magic Numbers in Status Field
What's wrong: status codes 0, 1, 2 have no meaning. Must memorize or check documentation.
Why it matters: Reader doesn't know what 0 means. Easy to use wrong number.
How to fix: Use enum with named states
  enum ChargerStatus {
      AVAILABLE,
      IN_USE,
      OUT_OF_SERVICE
  }
  
  class Charger {
      ChargerStatus status;
  }

---

PROBLEM 4: Primitive Type for "location"
What's wrong: String "location" could be anything - street address? GPS coordinates? Building name?
Why it matters: No type safety, no clear format, no behavior
How to fix: Create value object
  class GeoLocation {
      private double latitude;
      private double longitude;
      private String streetAddress;
      
      Distance distanceFrom(GeoLocation other) { ... }
  }

---

PROBLEM 5: Meaningless Attribute Name "number"
What's wrong: Number of what? Chargers? Customers? Power level?
Why it matters: Forces reader to guess or trace usage
How to fix: Descriptive name based on actual meaning
  int chargerCount;  // or powerOutputKilowatts, or stationNumber

---

PROBLEM 6: Generic Method Name "process"
What's wrong: Process what? For what purpose? What's the business logic?
Why it matters: Tells nothing about what operation does
How to fix: Name reflects business operation
  void initiateChargingSession(Vehicle vehicle, Customer customer)
  void calculateSessionCost(ChargingSession session)

---

PROBLEM 7: Generic Parameter Type "Object data"
What's wrong: Object is too vague. What data? What structure?
Why it matters: Loses all type safety. Caller doesn't know what to pass.
How to fix: Specific typed parameter
  void recordEnergyDelivered(EnergyReading reading)
  void updateChargerStatus(ChargerStatus newStatus)

---

PROBLEM 8: List of "Things" Without Clear Relationship
What's wrong: "things" doesn't explain relationship. Contains? Uses? Monitors?
Why it matters: Don't know what the collection represents
How to fix: Named collection with clear role
  class ChargingStation {
      List<Charger> availableChargers;
      // or: List<Charger> chargers; if all chargers regardless of status
  }

---

PROBLEM 9: Primitive "double power" Without Units
What's wrong: Power in kilowatts? Megawatts? Watts?
Why it matters: Easy to mix units, cause calculation errors
How to fix: Value object with explicit units
  class PowerOutput {
      private double kilowatts;
      
      PowerOutput convertTo(PowerUnit unit) { ... }
  }
  
  class Charger {
      PowerOutput maximumPower;
  }

---

PROBLEM 10: No Business Logic / Anemic Domain Model
What's wrong: Classes are just data containers with getters/setters. No behavior.
Why it matters: Business rules end up scattered in service layer, not in domain
How to fix: Add domain behavior
  class ChargingStation {
      boolean canAcceptNewSession() {
          return chargers.stream()
                         .anyMatch(c -> c.isAvailable());
      }
      
      Money calculateCost(ChargingSession session) {
          // Pricing logic belongs in domain model
      }
  }

---

SUMMARY OF ANTI-PATTERNS:
1. Technical naming (Thing, Thing2, process, data)
2. Magic numbers (0, 1, 2 status codes)
3. Primitive obsession (String, int, double instead of value objects)
4. Anemic domain model (no business logic)
5. Lost domain knowledge (no terms experts would recognize)

REFACTORED EXAMPLE:

class ChargingStation {
    private final StationId stationId;
    private final GeoLocation location;
    private final List<Charger> chargers;
    private final OperatingHours businessHours;
    
    public boolean hasAvailableCharger() {
        return chargers.stream()
                       .anyMatch(Charger::isAvailable);
    }
    
    public ChargingSession startSession(Vehicle vehicle, Charger charger) {
        if (!charger.isAvailable()) {
            throw new ChargerNotAvailableException();
        }
        return ChargingSession.begin(vehicle, charger, LocalDateTime.now());
    }
}

class Charger {
    private final ChargerId chargerId;
    private final PowerOutput maximumPower;
    private final ConnectorType connectorType;
    private ChargerStatus status;
    
    public boolean isAvailable() {
        return status == ChargerStatus.AVAILABLE;
    }
    
    public boolean isCompatibleWith(Vehicle vehicle) {
        return vehicle.hasConnector(this.connectorType);
    }
}

enum ChargerStatus {
    AVAILABLE("Ready for use"),
    IN_USE("Currently charging vehicle"),
    OUT_OF_SERVICE("Maintenance required");
    
    private final String description;
    ChargerStatus(String description) {
        this.description = description;
    }
}
```

---

### Evaluation Rubric

| Category | Original Code | Refactored Code |
|----------|---------------|-----------------|
| **Domain Language** | 0/10 (Thing, Thing2) | 10/10 (ChargingStation, Charger) |
| **Type Safety** | 2/10 (Object, int) | 9/10 (explicit types) |
| **Business Logic** | 0/10 (no behavior) | 8/10 (has domain methods) |
| **Readability** | 1/10 (unreadable) | 9/10 (self-documenting) |
| **Maintainability** | 1/10 (cryptic) | 8/10 (clear structure) |

---

### Learning Points

This bad example shows what happens when developers:
1. Write code without talking to domain experts
2. Think in technical terms instead of business terms
3. Create anemic domain models (data without behavior)
4. Use primitives for domain concepts
5. Choose generic names over specific ones

**The core DDD lesson:** If a charging station operator can't read your code and recognize their domain, you've failed to model the domain properly.

---

## Teaching Notes & Discussion Guide

### For Instructors

**Exercise 1: Domain Identification**
- **Key Teaching Point:** Boundaries are as important as content
- **Common Student Mistake:** Creating too many tiny domains OR one giant domain
- **Facilitation Tip:** Ask "can this change independently?" to test boundaries
- **Discussion:** Why does manufacturing need separate model from sales?

**Exercise 2: Model vs Reality**
- **Key Teaching Point:** Same entity, different purposes = different models
- **Common Student Mistake:** Trying to create one "complete" model
- **Facilitation Tip:** Ask "what does this model need to DO?" not "what is TRUE?"
- **Discussion:** When should you unify models vs keep them separate?

**Exercise 3: Code Review**
- **Key Teaching Point:** Code should speak domain language
- **Common Student Mistake:** Thinking comments solve the problem
- **Facilitation Tip:** Read Version A aloud to a non-programmer. Then Version B.
- **Discussion:** What's the cost of Version A in real projects?

**Exercise 4: Battery Management**
- **Key Teaching Point:** Glossary forces precision
- **Common Student Mistake:** Vague definitions, missing business rules
- **Facilitation Tip:** Ask "would a battery engineer approve this definition?"
- **Discussion:** How do you balance detail vs simplicity?

**Exercise 5: Translation Challenge**
- **Key Teaching Point:** Domain knowledge extraction is a skill
- **Common Student Mistake:** Adding concepts that weren't in conversation
- **Facilitation Tip:** Highlight every noun, verb, and condition explicitly
- **Discussion:** What questions would you ask the expert next?

---

## Conclusion

These solutions represent **one valid approach** to each exercise. In real DDD:
- Multiple valid models exist for same domain
- Trade-offs between approaches depend on context
- Models evolve as understanding deepens
- Perfect is enemy of good - start simple, refine iteratively

**The Goal:** Not to memorize these solutions, but to internalize the thinking process that created them.
