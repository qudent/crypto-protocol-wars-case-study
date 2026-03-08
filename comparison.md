# Detailed Comparison: Nuclear Weapons, Cryptography, and AI

## Three Cases of Technologists vs. the State

This document provides a structured comparison across three cases of conflict between technologists and the state over the control of transformative technology:

1. **Nuclear weapons** (1939-1950s) — analyzed by Burja & Lerangis (2018)
2. **Cryptography and internet protocols** (1970s-present) — analyzed in the companion report
3. **Artificial intelligence** (2020s-present) — emerging, with the Anthropic-DoD standoff as an early high-profile case

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
| **Relationship to state** | Employees/contractors | Complex: TCP/IP engineers were DARPA-funded; cryptographers were independent and often adversarial to the same government that funded the internet they used | Contractors/vendors, complex dependency |
| **Primary leverage** | Intellectual prestige | Ability to build and deploy; commercial value | Commercial value; some contractual and technical control over access |
| **Culture** | Academic, internationalist | Libertarian, anti-authoritarian, hacker ethic | Safety-conscious, but also commercially driven |
| **Political sophistication** | Low (cultural misfit with statesmen) | Medium (developed EFF, industry lobbying) | Medium-high (Anthropic's leadership includes policy professionals) |

### The Conflict

| | Nuclear | Crypto/Protocols | AI (Anthropic-DoD) |
|---|---------|-----------------|---------------------|
| **Government's goal** | Maintain weapons monopoly; use bomb as geopolitical tool | Maintain surveillance capability; promote more governable network arrangements | Broader military use of frontier AI without vendor-imposed restrictions |
| **Technologists' goal** | Prevent catastrophic use; international control | Strong encryption for all; open internet architecture | Restrict certain military and surveillance uses |
| **Mechanism of government control** | Classification, military hierarchy | Export controls, criminal prosecution, mandated standards | Procurement contracts, supply chain designation, executive pressure |
| **Mechanism of technologist resistance** | Petitions, memos, lobbying | Writing code, publishing papers, litigation, market forces | Usage policies, contract terms, technical controls, litigation |
| **Outcome** | Government won almost completely | Technologists won partially | Ongoing; initial government retaliation, but outcome uncertain |

### The Decisive Factors

| Factor | Nuclear (favored state) | Crypto (favored technologists) | AI (?) |
|--------|------------------------|-------------------------------|--------|
| **Could technologists act unilaterally?** | No | Crypto software: yes (publish code, deploy encryption). Protocol wars: not individually — required a funded research community (DARPA, Berkeley, NSF) — but decisive action was at the software layer, not the physical infrastructure layer | Partially (can set AUP terms, but state can switch vendors) |
| **Was there a commercial constituency?** | No independent one; major commercial interests were aligned with the state | Yes (massive and largely independent of the state) | Yes (massive, but the state is also a major customer) |
| **Could the state enforce restrictions?** | Yes (control fissile material) | Only partially; published mathematics and software distribution were hard to monopolize | Partially (can blacklist or pressure vendors, but not fully monopolize the field) |
| **Was the public engaged?** | No (classified project) | Partially (crypto wars had public dimension) | Yes (highly public, politically polarized) |
| **Were there alternative suppliers?** | No (U.S. monopoly briefly) | Yes (non-U.S. crypto products) | Yes (OpenAI immediately stepped in) |
| **Timeframe for decisions** | Compressed (wartime) | Extended (decades) | Compressed (days in the standoff, but broader debate ongoing) |

---

## Key Analytical Insights

### 1. The "Facts on the Ground" Thesis

The single most important variable across all three cases is **whether the technologists could create facts on the ground** — deploying their preferred outcome before the government could prevent it.

- **Nuclear**: Impossible. You cannot unilaterally prevent the use of a weapon you do not control.
- **Crypto software**: Largely possible. PGP was released before the government could stop it.
- **Protocols**: A different kind of "facts on the ground" — and ones that the military itself created. The DoD mandated TCP/IP on ARPANET in 1983; DARPA funded the free BSD implementation that gave it an unassailable installed base. No individual could build a TCP/IP network, but the military's patronage gave a small research community the institutional backing to ship a superior implementation and let market dynamics displace OSI. The decisive artifact was software, not physical infrastructure — the same cables could carry either protocol. The irony is that by creating these facts on the ground, the military built the platform that cypherpunks would later use to resist government control of cryptography.
- **AI**: Ambiguous. Anthropic can refuse some terms, but the government can switch to a competitor. The relevant "facts on the ground" are contract terms and technical controls that may be removed, modified, or bypassed through procurement decisions.

### 2. The Substitutability Problem

A critical new dynamic in the AI case is **substitutability**. In the crypto wars, non-U.S. products could substitute for restricted American encryption, but this worked *in favor* of the technologists' goals (more encryption everywhere). In the AI case, substitutability works *against* the safety-conscious technologist: OpenAI stepped in to fill the gap left by Anthropic, potentially without the same restrictions.

This is the "race to the bottom" dynamic that Schneier identifies. When one company takes a principled stand, a competitor can profit by being less principled. This dynamic was weaker in the crypto wars because the main activist and commercial coalitions broadly converged on the same direction of travel (more encryption), and absent in the nuclear case because there was no comparable open market.

### 3. The Contractor vs. Creator Distinction

Nuclear scientists were *employees* of the state. Cryptographers were *independent actors* creating public goods. AI companies are *contractors/vendors* — neither employees nor fully independent. This intermediate position gives them more leverage than the nuclear scientists had (they can walk away from the contract) but less than the cryptographers (they depend on government contracts and regulatory goodwill).

Anthropic's position is structurally closest to a defense contractor who refuses a category of military work. That is an awkward position: if one contractor refuses, another may take the work.

### 4. The Role of Secrecy

- **Nuclear**: Total secrecy prevented public debate, deprived scientists of allies, and concentrated power in a tiny group of decision-makers.
- **Crypto**: Partial secrecy (NSA activities classified, but the debate itself was public). The public nature of the debate was essential to the technologists' success.
- **AI**: Highly public from the start. The Anthropic-DoD standoff played out in real time on social media, in news coverage, and in leaked memos. This public visibility has mixed effects: it generates public scrutiny and potential support, but also enables performative political retaliation.

### 5. Burja's "Owned Power" vs. "Borrowed Power"

Burja distinguishes between "owned power" (power that cannot be taken away) and "borrowed power" (power that depends on someone else's permission). The nuclear scientists had only borrowed power — their influence depended entirely on the willingness of statesmen to listen.

The cryptographers developed owned power: once PGP was released, no one could un-release it. The code was the power. The protocol wars involved a different scale of owned power: no individual "deployed TCP/IP" — it required DARPA funding, university teams, and eventually commercial ISPs. But the decisive artifact was software (the BSD sockets implementation), not physical infrastructure, and once TCP/IP reached critical mass, it became very difficult to reverse. The key distinction is that this owned power was created by a *community* with institutional backing, not by individuals — yet it was still far more resistant to state reversal than the nuclear scientists' influence was.

Anthropic's position is intermediate. Its intellectual property (the Claude model) is owned power in one sense — the government cannot simply seize the capability by fiat. But its revenue depends on contracts that the government can cancel, and its regulatory environment depends on political goodwill that the government can withdraw. The supply chain risk designation is therefore an attempt to diminish the practical value of that owned power by making the company harder to use.

---

## Implications for the Future

### If the Crypto Wars Are the Right Analogy

If AI governance follows something like the crypto wars trajectory, we should expect:
- Initial government overreach and industry resistance
- Gradual establishment of legal and market norms
- Government adaptation to new equilibrium (finding alternative surveillance/control mechanisms)
- One plausible outcome: some AI safety features become standard through a mix of market demand, technical norms, and selective regulation
- Ongoing, never-fully-resolved tension between government access demands and safety/privacy concerns

### If the Nuclear Weapons Case Is the Right Analogy

If AI governance follows something closer to the nuclear trajectory, we should expect:
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

The crypto-vs-protocol distinction is illuminating here. AI model *weights*, once released as open source, behave like crypto software — trivially copyable, impossible to un-release, individual-scale deployment. But *training* frontier AI models behaves more like the protocol wars — requiring institutional-scale resources (compute clusters, data pipelines, research teams). The difference is that the protocol wars' institutional resources came from the military (DARPA) and research institutions (universities, NSF), and their interests happened to align with open architecture — the military wanted robust, general-purpose networking and got it, without foreseeing that this would create the platform for cypherpunk resistance. Frontier AI training is funded by *commercial* companies whose interests may or may not align with safety or openness, and by a government that now has the crypto wars as a cautionary tale about funding open infrastructure.

The critical variable may be **whether open-source AI models become "good enough"** for most purposes. If they do, AI governance may follow more of the crypto trajectory — the technology becomes too widely distributed to control cleanly, and the government must adapt. If frontier models maintain a decisive advantage over open-source alternatives, and remain concentrated in a handful of companies, AI governance may follow more of the nuclear trajectory — with stronger government control pursued through regulation, procurement, and coercion of a small number of actors.

The Anthropic-DoD standoff of March 2026 is an important early test case. Its resolution will be an early signal, not a final verdict.
