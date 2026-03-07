# Detailed Comparison: Nuclear Weapons, Cryptography, and AI

## Three Cases of Technologists vs. the State

This document provides a structured comparison across three cases of conflict between technologists and the state over the control of transformative technology:

1. **Nuclear weapons** (1939-1950s) — analyzed by Burja & Lerangis (2018)
2. **Cryptography and internet protocols** (1970s-present) — analyzed in the companion report
3. **Artificial intelligence** (2020s-present) — emerging, with the Anthropic-DoD standoff as the pivotal early case

---

## Side-by-Side Comparison

### The Technology

| | Nuclear | Crypto/Protocols | AI |
|---|---------|-----------------|-----|
| **Nature** | Physical (requires fissile material, industrial infrastructure) | Mathematical (algorithms, software) | Computational (requires data, compute, algorithms) |
| **Reproducibility** | Very difficult (decades for each new nuclear state) | Crypto software: trivial (copy and install). Network protocols: specification freely available (RFCs), but deploying infrastructure required major investment — though the physical layer was protocol-agnostic | Moderate (models can be open-sourced, but frontier models require massive compute) |
| **Dual-use** | Weapons + energy, but weapons were primary | Security/privacy + surveillance, but civilian use was primary | Nearly everything; military and civilian uses deeply intertwined |
| **State monopoly at origin** | Yes (Manhattan Project was classified) | Partial (NSA had monopoly on practice, but academic research was open) | No (developed primarily by private companies) |
| **Commercial value** | Limited (nuclear energy, but weapons had no commercial market) | Enormous (all of e-commerce) | Enormous (potentially all knowledge work) |

### The Technologists

| | Nuclear Scientists | Cryptographers/Engineers | AI Developers |
|---|-------------------|------------------------|---------------|
| **Organizational form** | Individual scientists within government projects | Loose community (cypherpunks) + companies + academics | Companies (Anthropic, OpenAI, Google DeepMind) |
| **Relationship to state** | Employees/contractors | Independent, often adversarial | Contractors/vendors, complex dependency |
| **Primary leverage** | Intellectual prestige | Ability to build and deploy; commercial value | Commercial value; technical capability the state cannot replicate |
| **Culture** | Academic, internationalist | Libertarian, anti-authoritarian, hacker ethic | Safety-conscious, but also commercially driven |
| **Political sophistication** | Low (cultural misfit with statesmen) | Medium (developed EFF, industry lobbying) | Medium-high (Anthropic's leadership includes policy professionals) |

### The Conflict

| | Nuclear | Crypto/Protocols | AI (Anthropic-DoD) |
|---|---------|-----------------|---------------------|
| **Government's goal** | Maintain weapons monopoly; use bomb as geopolitical tool | Maintain surveillance capability; control network architecture | Unrestricted military use of AI technology |
| **Technologists' goal** | Prevent catastrophic use; international control | Strong encryption for all; open internet architecture | Prevent autonomous weapons and mass surveillance |
| **Mechanism of government control** | Classification, military hierarchy | Export controls, criminal prosecution, mandated standards | Procurement contracts, supply chain designation, executive orders |
| **Mechanism of technologist resistance** | Petitions, memos, lobbying | Writing code, publishing papers, litigation, market forces | Acceptable use policies, contract terms, litigation |
| **Outcome** | Government won almost completely | Technologists won partially | Ongoing; initial government retaliation, but outcome uncertain |

### The Decisive Factors

| Factor | Nuclear (favored state) | Crypto (favored technologists) | AI (?) |
|--------|------------------------|-------------------------------|--------|
| **Could technologists act unilaterally?** | No | Crypto software: yes (publish code, deploy encryption). Protocol wars: not individually — required a funded research community (DARPA, Berkeley, NSF) — but decisive action was at the software layer, not the physical infrastructure layer | Partially (can set AUP terms, but state can switch vendors) |
| **Was there a commercial constituency?** | No | Yes (massive) | Yes (massive, but state is also a major customer) |
| **Could the state enforce restrictions?** | Yes (control fissile material) | No (can't control math) | Partially (can blacklist, but can't stop the company from existing) |
| **Was the public engaged?** | No (classified project) | Partially (crypto wars had public dimension) | Yes (highly public, politically polarized) |
| **Were there alternative suppliers?** | No (U.S. monopoly briefly) | Yes (non-U.S. crypto products) | Yes (OpenAI immediately stepped in) |
| **Timeframe for decisions** | Compressed (wartime) | Extended (decades) | Compressed (days in the standoff, but broader debate ongoing) |

---

## Key Analytical Insights

### 1. The "Facts on the Ground" Thesis

The single most important variable across all three cases is **whether the technologists could create facts on the ground** — deploying their preferred outcome before the government could prevent it.

- **Nuclear**: Impossible. You cannot unilaterally prevent the use of a weapon you do not control.
- **Crypto software**: Fully possible. PGP was released before the government could stop it.
- **Protocols**: A different kind of "facts on the ground." No individual could build a TCP/IP network, but a funded research community (DARPA, Berkeley) shipped a superior free implementation with BSD Unix and let market dynamics displace OSI. The decisive artifact was software, not physical infrastructure — the same cables could carry either protocol. Not individual action, but not state-directed action either: a middle path where a small community with institutional backing created an irreversible fait accompli.
- **AI**: Ambiguous. Anthropic can refuse to modify its AUP, but the government can switch to a competitor. The "facts on the ground" are the AUP terms embedded in a contract, which the government can cancel.

### 2. The Substitutability Problem

A critical new dynamic in the AI case is **substitutability**. In the crypto wars, non-U.S. products could substitute for restricted American encryption, but this worked *in favor* of the technologists' goals (more encryption everywhere). In the AI case, substitutability works *against* the safety-conscious technologist: OpenAI stepped in to fill the gap left by Anthropic, potentially without the same restrictions.

This is the "race to the bottom" dynamic that Schneier identifies. When one company takes a principled stand, a competitor can profit by being less principled. This dynamic was absent in the crypto wars because all cryptographers shared the same goal (more encryption), and absent in the nuclear case because there was no market.

### 3. The Contractor vs. Creator Distinction

Nuclear scientists were *employees* of the state. Cryptographers were *independent actors* creating public goods. AI companies are *contractors/vendors* — neither employees nor fully independent. This intermediate position gives them more leverage than the nuclear scientists had (they can walk away from the contract) but less than the cryptographers (they depend on government contracts and regulatory goodwill).

Anthropic's position is structurally closest to a defense contractor who refuses to build a weapon — something that has rarely happened in history, because defense contractors that refuse to build what the military wants tend to be replaced by contractors who will.

### 4. The Role of Secrecy

- **Nuclear**: Total secrecy prevented public debate, deprived scientists of allies, and concentrated power in a tiny group of decision-makers.
- **Crypto**: Partial secrecy (NSA activities classified, but the debate itself was public). The public nature of the debate was essential to the technologists' success.
- **AI**: Highly public from the start. The Anthropic-DoD standoff played out in real time on social media, in news coverage, and in leaked memos. This public visibility has mixed effects: it generates public support but also enables political retaliation (Trump's executive order was partly performative).

### 5. Burja's "Owned Power" vs. "Borrowed Power"

Burja distinguishes between "owned power" (power that cannot be taken away) and "borrowed power" (power that depends on someone else's permission). The nuclear scientists had only borrowed power — their influence depended entirely on the willingness of statesmen to listen.

The cryptographers developed owned power: once PGP was released, no one could un-release it. The code was the power. The protocol wars involved a different scale of owned power: no individual "deployed TCP/IP" — it required DARPA funding, university teams, and eventually commercial ISPs. But the decisive artifact was software (the BSD sockets implementation), not physical infrastructure, and once TCP/IP reached critical mass, it was equally irreversible. The key distinction is that this owned power was created by a *community* with institutional backing, not by individuals — yet it was still fundamentally resistant to state reversal in a way that the nuclear scientists' influence was not.

Anthropic's position is intermediate. Its intellectual property (the Claude model) is owned power in one sense — the government cannot take it. But its revenue depends on contracts that the government can cancel, and its regulatory environment depends on political goodwill that the government can withdraw. The supply chain risk designation is a direct attack on Anthropic's owned power, attempting to make it worthless by preventing others from doing business with the company.

---

## Implications for the Future

### If the Crypto Wars Are the Right Analogy

If AI governance follows the crypto wars trajectory, we should expect:
- Initial government overreach and industry resistance
- Gradual establishment of legal and market norms
- Government adaptation to new equilibrium (finding alternative surveillance/control mechanisms)
- Ultimate outcome: AI with safety features becomes standard, not because of regulation but because of market demand and technical norms
- Ongoing, never-fully-resolved tension between government access demands and safety/privacy concerns

### If the Nuclear Weapons Case Is the Right Analogy

If AI governance follows the nuclear trajectory, we should expect:
- Government success in asserting control over the most powerful AI systems
- Safety-conscious developers marginalized or co-opted
- AI development concentrated in a small number of state-affiliated organizations
- International competition (an "AI arms race") driving development decisions
- Safety considerations permanently subordinated to strategic competition
- Outcomes depending on luck as much as on institutional design

### The Most Likely Scenario: A Hybrid

The most realistic expectation is a hybrid outcome. AI shares features of both cases:
- Like nuclear weapons, frontier AI requires massive resources (compute, data), creating natural concentration
- Like cryptography, AI knowledge diffuses rapidly (open-source models, published papers)
- Like the crypto wars, commercial interests create powerful constituencies for certain outcomes
- Like nuclear weapons, the military applications are strategically significant enough to trigger state action

The crypto-vs-protocol distinction is illuminating here. AI model *weights*, once released as open source, behave like crypto software — trivially copyable, impossible to un-release, individual-scale deployment. But *training* frontier AI models behaves more like the protocol wars — requiring institutional-scale resources (compute clusters, data pipelines, research teams). The difference is that the protocol wars' institutional resources came from *research* institutions (DARPA, universities) whose interests happened to align with open architecture, while frontier AI training is funded by *commercial* companies whose interests may or may not align with safety or openness.

The critical variable may be **whether open-source AI models become "good enough"** for most purposes. If they do, AI governance may follow the crypto trajectory — the technology becomes too widely distributed to control, and the government must adapt. If frontier models maintain a decisive advantage over open-source alternatives, and remain concentrated in a handful of companies, AI governance may follow the nuclear trajectory — with government control achieved through regulation, procurement, and coercion of a small number of actors.

The Anthropic-DoD standoff of March 2026 is the first major test case. Its resolution will signal which trajectory is more likely.
