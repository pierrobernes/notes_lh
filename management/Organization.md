# Squad Organization

## Concepts in practice

### Squad

Squad is 
* elastic: size is adjusted depending on workload or specific expertise
* modular: functions can be temporarly removed or added 
* ephemeral: can be assembled & dismantled quickly

Components are shared between all squads
* Specialization of Squad on components can exist at Squad assembling or happens along Squad life 

### Steering commitee

Set the strategic objectives & review them on a regular basis.
These objectives will be confronted with 
* the roadmap & milestones produced by the product owners as presented by the Product Lead
* the tribe lead (COO) & Design Lead (CTO)

Objective of this commitee is then to : 
* (Re-)Budgetize the development efforts allowed by products
* Set the product milestones with regards to business commitmments or plans

### Tribe committee

At least, once per sprint or every two weeks, squad committee gathers.  It involves :
* Design lead
* Squad leaders
* Head of Product
* (Agile coach)

They will based on the product priorities & planning : 
* Review the squad composition and adjust it in chapter presence & size
* Arbitrate on 
    * feature allocation to Squad
    * priorization & pertinence of technical subjects

### Squad committee(s)

Squad leader, Product owner and stakeholders define backlog and short-term planning.
In Agile methodologies, these commitees correspond to the Agile ceremonies

## Squad Organization & Coordination - Situations study

### Initial Squads creation

Cfr. Diagram Squads LH

### New product development 

New squad is assembled or existing one with capacity is reused. 

In such case, Squad assembling starts with dedicated : 
* Squad Lead
* PO 
* (Optionnaly) BA
* DevOps
* QA

Once backlog is mature enough (precision & stability of requirements), development phase starts with the addition in the squad of : 
* Agile Coach**
* Developers (front, back, gw)
* SD-OPS

During the development: 
* Depending on elapsed time vs estimated duration, squad size is reevaluated one sprint in advance.
* Agile coach might be removed as squad agile organization reached maturity

When product becomes mature enough: 
* Marketing & Sales join the Squad temporarily

Need : 
* Precise Product definition & roadmap
* Real & Realistic Milestones defined by market & company business needs
* QA & DevOps strategy defined in the early stages of the development
* Agile Coach to support the Squad Lead until squad reaches mature self-organization
* Constant control of planning to adjust the Squad
* Coordination with other squads in case of dependencies with components

### New feature development 

Assuming an existing product

### Acronyms

* S1 : "Squad 1"
* S2 : "Squad 2"
* Cmp2 : "Component 2"
* Cmp1 : "Component 1"
* Cmp3 : "Component 3"
* F1 : "Feature 1"
* F2 : "Feature 2"
* SSC : "Squad Size Change"


### Concurrence on components

#### 1. Simulataneous development

S1 develops F1 which implies F1 related changes on C1 & C2
S2 develops F2 which implies F2 related changes on C2 & C3

C2 evolves then on 2 separate branches

**General Principle:**
* First branch to merge in MASTER wins

Impact for Squad who merges last 
* Additional effort + potential side-effect leading to delays

Best Practice: 
* Coordination between Squad leaders on changes and potential side-effects
* Design lead anticipates with Squad leaders the mutual side-effects with appropriate design
* Regularly merge changes from other Squads

Need : 
* Permanent communication channel between Squad Leaders + Design Lead.  Ad-Hoc? - Formal?


#### 2. Mutual development

S1 develops F1 which implies F1 related changes on C1 and a general evolution of C2
S2 develops F2 which implies F2 related changes on C3 and a general evolution of C2

Once the Squad must take the lead depending on : 
* Squad workload
* Squad affinity with component

General Principle : 
* When the work can be planned the most specialized squad for this component receives the development
* Optinally the Squad taking the dev receives temporary people from the other Squad(s)
    * Conditions : changes in component is blocking for both, squad to shrink down is not harmed in terms of planning 
* When the work cannot be planned (ex : S1 develops F1 for P1 requiring change on C2 (specialization of S2), S1 can ask S2 to make the dev), a squad can ask another squad (more specialized in the required component) to do the work for him

Need : 
* Arbitration by Trio for adjusting squad size : feature planning delivery & impact on shrinked down squad. 
* Strong collaboration between squads to share efforts. 

### Maintenance of components

#### 1. Pro-active maintenance

For security reasons or technical reasons, components need to involve independently from the features.
These kind of items cannot be captured by the Product Owner but still are required on regular basis.

Need : 
* Each tech lead has to be responsible for pro-active maintenance and propose the right evolution / upgrade with regards to priorities

#### 2. Reactive maintenance

Once discovered on a product a bug is raised and added to a product bug backlog.

**Low-medium criticality bugs**

It would be reasonable that such bugs are solved in next version of product including features. However there might be situation were no short / mid-term features are planned.

In case the bug detected affects several products, the criticality of the bug can be different depending on the product. Example : minor on product A but major on Product B.

**High criticality bugs**

Major bugs need to be resolved within a short time-frame agreed with the SLA / contracts

General principle : 
* Product affected the most is treated first
* PO synchronizes with each others in case of doubts 

Need : 
* Product owner defines regular product releases (even without features) and keeps contingency for bug fixing in his product roadmap

## Roles & Responsibilities

### Squad Lead

TBD

### Chapter Lead

TBD

### Agile Coach

TBD

### Trio

Mutualization of efforts
Timeline definition
Squad re-sizing

## Tooling

### Ticketing system

JIRA with one project per product.
Those JIRA projects employs components that can be shared with multiple products

**Attention point:**

JIRA can only manage release version per project (and thus product in the current model).

**Need:**

Make a link between product version and attached component version.
>Jira [plugin](https://marketplace.atlassian.com/apps/1211548/subcomponents-for-jira?hosting=server&tab=overview) exist for this.

### VCS - Git

Products could be an assembling of components or a component itself employing others.
In any case, it needs to be versioned in the VCS with :
* dependency tree of tested components
* infra as code definition 
* upgrade / initial installation tooling
* docuemntation : product notes, release note, operational procedures

### CI/CD

CI/CD pipelines organized by products managing :
* Component rebuild if required version not present in artifactory
* Automated Code quality review
* Product rebuild if relevant 
* Artifact generation, container creation
* Container deployment
* Integration & non-regression test
* Branch tagging & automated promotion to upper environments

## Challenges

### Human 

1. How to bring collaboration between squads?
2. How to avoid concurrence between key resources?
3. How to bring sane competition between squads?

### Material 

* Importance of non regression tests (fix on C1 for P1 might have side effect on P2)
* Importance of communication between squad leads (if S1 develops F1 for P1 requiring change on C2 (specialization of S2), S1 can ask S2 to make the dev)

