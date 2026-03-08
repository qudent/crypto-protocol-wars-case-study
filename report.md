# The Cypherpunks, the Companies, and the Code

## A case study in decision-making around the control of cryptography and internet architecture

March 2026

---

## Abstract

This paper examines the dynamics of control and decision-making surrounding the development of strong cryptography and internet protocols from the 1970s through the present day.

Well before the internet became the backbone of global commerce and communication, some people — predominantly mathematicians, computer scientists, and engineers — foresaw that the ability to encrypt communications and to design open network architectures would be among the most consequential technical capabilities of the modern era. They understood that governments, particularly intelligence agencies, would seek to restrict or control these technologies. A loosely connected network of researchers, activists, and eventually companies dedicated much of their professional lives to ensuring that strong cryptography and open protocols would be available to ordinary people.

They partially succeeded. Unlike the nuclear scientists studied by Burja and Lerangis (2018), who failed almost entirely to shape the political decisions surrounding nuclear weapons, the cryptographers and internet engineers achieved a mixed but meaningful victory. Strong encryption is now ubiquitous in consumer technology. The internet runs on open protocols rather than government-mandated standards. Yet the battle is not over: governments continue to push for backdoors, surveillance capabilities, and control over digital infrastructure, as the March 2026 standoff between the U.S. Department of Defense and Anthropic illustrates.

We propose that the partial success of the technologists in this case — in contrast to the total failure of the nuclear scientists — can be attributed to several structural differences: the technologists could *build and deploy* their preferred outcomes rather than merely advise decision-makers; the technology created value for a dispersed commercial constituency with independent political power (unlike nuclear weapons, whose value accrued to the state itself); and the prior battle over network architecture had already shifted the terrain in their favor by making distribution far more permissionless than it otherwise would have been. The protocol wars made the crypto wars much easier to fight. This case offers a useful, urgent analogy for AI governance, while also highlighting structural differences that limit the comparison.

---

## Contents

1. [Case Study Methodology](#case-study-methodology)
2. [Historical Summary](#historical-summary)
3. [Relevant Players](#relevant-players)
4. [Analysis](#analysis)
5. [Example 1: The Clipper Chip — The Government's Bid for Control](#example-1-the-clipper-chip--the-governments-bid-for-control)
6. [Example 2: Phil Zimmermann and PGP — Code as Civil Disobedience](#example-2-phil-zimmermann-and-pgp--code-as-civil-disobedience)
7. [Example 3: OSI vs TCP/IP — The Protocol Wars](#example-3-osi-vs-tcpip--the-protocol-wars)
8. [Example 4: Apple vs FBI — The Second Crypto War](#example-4-apple-vs-fbi--the-second-crypto-war)
9. [Additional Examples](#additional-examples)
10. [Comparison with the Nuclear Weapons Case](#comparison-with-the-nuclear-weapons-case)
11. [Coda: The Anthropic-DoD Standoff and the AI Question](#coda-the-anthropic-dod-standoff-and-the-ai-question)

---

## Case Study Methodology

We follow the approach outlined by Burja and Lerangis (2018): building analysis from primary sources — in this case, technical memos, published papers, court filings, congressional testimony, and the extensive memoirs and oral histories of participants — rather than relying on previous analyses. For the framework of strategic interaction, we draw on the same concepts of competitive landscape and power dynamics used in the nuclear case study.

The crypto and protocol wars are better documented than early nuclear decision-making in some respects: many of the key documents were published in real time (academic papers, IETF RFCs, Usenet posts, court filings), and many participants are still alive and have written extensively about their experiences. The principal secondary sources are Steven Levy's *Crypto: How the Code Rebels Beat the Government* (2001), which covers the first crypto war in detail, and various accounts of the IETF's history including RFC 3935 and oral histories from internet pioneers.

The crypto and protocol wars also benefit from a feature absent in the nuclear case: the outcome is not entirely settled. The battles described here are ongoing, which means we can observe the dynamics in real time — as the Anthropic-DoD confrontation of February-March 2026 demonstrates.

---

## Historical Summary

### The Prehistory of the Conflict (1970s)

In the 1970s, cryptography was essentially a government monopoly. The National Security Agency (NSA) was the world's largest employer of mathematicians, and strong encryption was classified as a munition under the International Traffic in Arms Regulations (ITAR). The implicit assumption, shared by the intelligence community and much of the political establishment, was that the government would maintain this monopoly indefinitely.

The NSA's reach was practical, not merely legal. IBM's earlier Lucifer-family designs used much longer keys, but the DES standard adopted in 1977 used a 56-bit key after NSA involvement in the standardization process. Cryptographers Whitfield Diffie and Martin Hellman publicly criticized this choice, arguing that 56 bits would eventually be vulnerable to brute-force attack by a well-resourced adversary. Later public cracking efforts confirmed that concern: in January 1999, the EFF and distributed.net publicly broke a DES key in 22 hours and 15 minutes, after the EFF had already shown that a DES-cracking machine could be built for well under $250,000.

This assumption of permanent government monopoly was shattered by two developments. In 1976, Diffie and Hellman published "New Directions in Cryptography," which described the concept of public-key cryptography — a method by which two parties could establish a shared secret over an insecure channel without any prior arrangement. This was the most significant breakthrough in cryptography since the development of the one-time pad, and it had been achieved entirely outside the classified world. The paper did not by itself end government secrecy, but it proved that major cryptographic advances could emerge in open academia. Soon afterward, an NSA employee informally warned the IEEE that some open cryptography presentations could implicate export-control rules, illustrating how seriously the agency viewed the loss of monopoly. The NSA had independently developed similar ideas, but had kept them secret. (Diffie and Hellman later received the 2015 Turing Award for this work.)

Shortly afterward, Ron Rivest, Adi Shamir, and Leonard Adleman at MIT developed RSA, the first practical public-key cryptosystem. RSA was published in the open literature, though patents and export controls later complicated the dissemination of working implementations. By the late 1970s, it was already clear that the government's monopoly on advanced cryptographic knowledge was breaking down.

Simultaneously, the networks that would become the internet were being designed. ARPANET was the key precursor network; TCP/IP was developed during the 1970s by Vint Cerf and Bob Kahn and became ARPANET's common protocol in the January 1, 1983 transition. The architectural choices around packet switching and later internet design principles, including the end-to-end argument articulated by Saltzer, Reed, and Clark, would have profound political consequences. A network that primarily forwards packets rather than centrally managing services leaves fewer built-in chokepoints for censorship, permissioning, or service control. As Lawrence Lessig would later argue in "Code is Law" (2000), the architecture of a network functions as a form of regulation as powerful as any statute. The internet's designers did not create a perfectly free space, but they did create infrastructure with fewer natural control points than the telecom world it was displacing.

### The First Crypto War (1990-2000)

As personal computing and the early internet expanded in the late 1980s and early 1990s, strong cryptography threatened to move from the academic world into consumer products. The U.S. government, led by the NSA and the FBI, attempted to prevent this through several strategies:

**Export controls**: Under ITAR, software containing strong encryption could not be exported from the United States. This effectively prevented American software companies from including strong encryption in their products, since most had international markets. The controls classified cryptographic software alongside tanks and fighter jets.

**The Clipper Chip (1993)**: The Clinton administration proposed a hardware encryption chip for consumer devices that would use an algorithm (Skipjack) designed by the NSA, with a built-in "key escrow" system giving the government access to communications encrypted with Clipper-enabled devices. This was the government's most ambitious attempt to maintain its cryptographic leverage in the face of technological change.

**Criminal investigation**: Phil Zimmermann, author of the PGP (Pretty Good Privacy) encryption program, was subjected to a three-year criminal investigation for "exporting munitions" — because his software had been uploaded to the internet and downloaded by people outside the United States.

All three strategies failed. The Clipper Chip was abandoned after security researcher Matt Blaze discovered a critical vulnerability in the escrow protocol and after massive opposition from the technology industry and civil liberties organizations. Export controls were progressively relaxed between 1996 and 2000, culminating in their effective removal for mass-market encryption software. The investigation of Zimmermann was dropped without charges.

By 2000, strong encryption was broadly available in mainstream web browsers and increasingly available across operating systems and email products. The first crypto war was over, and the technologists had won a substantial, though not total, victory.

### The Protocol Wars (1980s-1990s)

Running in parallel with the crypto wars was a less publicized but equally consequential battle over the architecture of global computer networking — one whose outcome strongly shaped how the crypto wars could be fought.

Governments and established telecommunications companies, through the International Organization for Standardization (ISO) and allied standards bodies, had developed the Open Systems Interconnection (OSI) seven-layer reference model and associated protocol suite through a formal, top-down standards process involving national delegations and official representatives. The OSI effort was not merely a different technical standard — it reflected a fundamentally different political vision of networking, one that mirrored the existing telecommunications order. In the telco model, networks were operated by state monopolies or state-regulated carriers (the European Post, Telegraph and Telephone agencies, or PTTs). Users were identified and billed through operator-controlled systems. The network operator had a larger role in determining what services could run on the network. International connectivity was negotiated between national carriers through bilateral agreements.

Had a more OSI/PTT-style order prevailed, the political economy of global networking would likely have been more centralized than the internet we know. Network operators would probably have had stronger identity, billing, and service-approval chokepoints; pseudonymous publication and cross-border access would likely have been costlier and more contingent on carrier permission; and independent service deployment would have faced higher barriers to entry. The point is not that every familiar internet institution would necessarily have disappeared, but that the architecture would have given states and carriers more natural control points than TCP/IP ultimately did.

This is not purely speculative. Two real-world systems help illustrate the contrast. France's **Minitel** (1978-2012) was a centralized, state-operated data network run by France Télécom: services were mediated through the carrier, users were billed through the network operator, and the system functioned as a centrally managed walled garden rather than a general-purpose, permissionless internet. China's **Great Firewall** illustrates the comparative point from the other direction. TCP/IP did not prevent China from building a powerful censorship regime, but it forced filtering and control to be layered onto a general-purpose internet rather than built into a single globally mandated protocol architecture. That still leaves room for circumvention and workarounds that a more tightly identity-coupled, operator-controlled architecture might have reduced. The open internet is not a law of nature; it is the product of specific architectural choices that were contested and could have gone the other way.

This point has a crucial implication for the crypto wars: **the protocol wars materially improved the technologists' odds in the crypto wars.** Phil Zimmermann could distribute PGP far more quickly and widely because TCP/IP's architecture allowed publication without asking a network operator for permission. The resistance to export controls also relied on academic publishing, print distribution, lawsuits, and offline software exchange, so the protocol victory was not the sole enabling condition. But it greatly expanded the scale and speed of dissident distribution.

But TCP/IP was not a grassroots insurgency against the state. It was a military project. ARPANET, the network on which TCP/IP was developed and deployed, was funded by the Defense Department's Advanced Research Projects Agency (DARPA) from 1969. Vint Cerf and Bob Kahn designed TCP/IP under DARPA funding in the early 1970s; Cerf then served as DARPA program manager for networking from 1976 to 1982, directing the funding that turned the protocol from a specification into a working system. On January 1, 1983 — the "flag day" — the DoD mandated that all ARPANET hosts switch from the older NCP protocol to TCP/IP. Later that year, the military split ARPANET into a civilian research network and MILNET for military traffic, both running TCP/IP. DARPA also funded the critical Berkeley BSD implementation (4.2BSD, August 1983), whose permissive licensing allowed workstation vendors to adopt it freely. By the time the protocol wars with OSI heated up, TCP/IP had years of deployment and a large installed base — thanks to military patronage.

The U.S. government was not a monolith on this question. DARPA and the operational military networking community were committed to TCP/IP — they ran on it. But NBS (later NIST) and the Commerce Department championed OSI through the Government OSI Profile (GOSIP), a federal procurement mandate that took effect in August 1990 — by which point TCP/IP had been the operational standard for seven years. European governments, working through their PTT monopolies and standards bodies, promoted OSI even more aggressively. Within the DoD itself, a 1985 National Research Council report recommended adopting OSI's transport protocol (TP-4) as a co-standard, but the DoD's response amounted to keeping TCP/IP while paying lip service to eventual OSI migration. The expectation in standards bodies was that OSI would become the global standard and TCP/IP would be relegated to a historical footnote.

TCP/IP won decisively. The reasons are instructive: it was simpler, it worked, and — crucially — it was already deployed, with the military's mandate as the decisive early push. While OSI committees debated protocol specifications in formal meetings, internet engineers were building and connecting networks. The IETF's philosophy of "rough consensus and running code" proved devastatingly effective against the top-down standards process. By the mid-1990s, even governments that had mandated OSI were quietly connecting to the TCP/IP internet. GOSIP was effectively relaxed in 1995.

### The Second Crypto War (2013-present)

The Edward Snowden revelations of 2013 demonstrated the scale of government surveillance enabled by the internet's original design — which, despite the end-to-end principle, left most communications unencrypted in practice. The response from the technology industry was dramatic: within a few years, Apple made strong device encryption standard on modern iPhones, WhatsApp deployed end-to-end encryption for over a billion users, and the HTTPS protocol (encrypting web traffic) went from being used on a minority of websites to the overwhelming majority.

This "second crypto war" saw the government largely on the defensive. The FBI's 2016 confrontation with Apple over an encrypted iPhone used by the San Bernardino shooter ended in a draw — the FBI found an alternative way into the phone and dropped its legal challenge, but Apple's encryption remained unbroken. The "going dark" rhetoric of FBI Director James Comey, warning that encryption was creating spaces beyond the reach of lawful surveillance, failed to produce legislation mandating backdoors.

However, the government achieved partial victories through other means. The Five Eyes intelligence alliance continued to press for "lawful access" to encrypted communications. Australia passed the Assistance and Access Act in 2018, granting authorities the power to compel companies to provide technical assistance in accessing encrypted data. In the UK, the Investigatory Powers Act was reportedly used in 2025 to pressure Apple over its iCloud end-to-end encryption features; Apple responded by withdrawing Advanced Data Protection from the UK rather than creating a global backdoor. The EARN IT Act, introduced multiple times in the U.S. Congress, threatened to weaken encryption protections by conditioning legal liability shields on compliance with government access requirements.

### The DNS and Governance Wars

Control over the internet's naming system — the Domain Name System (DNS) — was another arena of conflict. Jon Postel, a computer scientist at USC's Information Sciences Institute, had informally administered the Internet Assigned Numbers Authority (IANA) since the early days of the ARPANET. As the internet grew into a commercial and geopolitical force, control over DNS became increasingly contested.

The U.S. government, through the Department of Commerce's National Telecommunications and Information Administration (NTIA), asserted authority over the DNS root zone. Other nations, particularly through the International Telecommunication Union (ITU), pushed for multilateral control.

The most dramatic moment came in January 1998, when Postel asked several root server operators to begin pulling the root zone from a new IANA-controlled primary server rather than Network Solutions' A-root. The operators complied — demonstrating that the internet community's informal trust relationships, not government contracts alone, were a real basis of DNS authority. Postel soon received a furious call from Ira Magaziner, President Clinton's senior science advisor, who reportedly threatened: *"You'll never work on the Internet again."* Postel reversed the test. Within weeks, the NTIA issued its "Green Paper" asserting a stronger U.S. governmental role over DNS transition and management.

The eventual creation of ICANN (Internet Corporation for Assigned Names and Numbers) in 1998 — with Postel playing a central role in the transition and in the proposal process that led to ICANN's initial board — and the IANA transition in 2016 that moved oversight away from the U.S. government to a multi-stakeholder model, represented a compromise — but one in which the internet community's preferred governance model (multi-stakeholder rather than multilateral) largely prevailed.

---

## Relevant Players

### Technologists and Advocates

**Whitfield Diffie**: Co-inventor of public-key cryptography. A deeply private person who spent years working on the problem of key distribution essentially alone before his breakthrough with Hellman. Later became Sun Microsystems' chief security officer and a persistent advocate for strong encryption.

**Martin Hellman**: Stanford professor and co-inventor of public-key cryptography. Unlike many of his peers, Hellman was willing to engage publicly with the political implications of his work, including testifying before Congress and debating NSA officials.

**Phil Zimmermann**: Creator of PGP (Pretty Good Privacy), the first widely available strong encryption software for personal computers. An anti-nuclear activist who saw cryptography as a tool for individual empowerment. His decision to release PGP as free software, and the three-year criminal investigation that followed, made him a cause celebre in the technology community and beyond.

**Matt Blaze**: Bell Labs and later University of Pennsylvania researcher who discovered a critical flaw in the Clipper Chip's key escrow mechanism in 1994. His paper was a decisive blow against the Clipper proposal, demonstrating that the system's security was fundamentally compromised.

**Tim May**: Intel physicist and co-founder of the cypherpunk movement. Author of "The Crypto Anarchist Manifesto" (1988), which predicted that cryptography would fundamentally alter the relationship between individuals and the state. His vision was more radical than most: he saw cryptography as a tool for dismantling state power entirely.

**Eric Hughes**: UC Berkeley mathematician and co-founder of the cypherpunk mailing list. Author of "A Cypherpunk's Manifesto" (1993), which articulated the movement's core philosophy: "Cypherpunks write code. We know that someone has to write software to defend privacy, and since we can't get privacy unless we all do, we're going to write it."

**Vint Cerf and Bob Kahn**: Co-designers of TCP/IP, the protocol suite that powers the internet. Cerf served as DARPA program manager for networking from 1976 to 1982, directly funding the development and deployment of TCP/IP — making him simultaneously a government official and a technologist building the open internet. While not directly involved in the crypto wars, their architectural decisions — particularly the end-to-end principle — shaped the battlefield on which later conflicts would be fought.

**Jon Postel**: Administrator of IANA and editor of the RFC series. His quiet authority over internet naming and numbering, based entirely on the trust of the engineering community rather than any formal mandate, embodied the internet's original governance model.

**Daniel Bernstein**: Mathematician and cryptographer who, as a graduate student, successfully challenged the constitutionality of encryption export controls. The Bernstein litigation produced influential rulings recognizing source code as protected speech under the First Amendment, even though the case was later mooted before becoming a final Supreme Court precedent.

### Government Actors

**The National Security Agency (NSA)**: The primary government actor in the crypto wars. The NSA's interest was twofold: maintaining its own ability to decrypt foreign communications (signals intelligence, or SIGINT), and preventing adversaries from obtaining strong encryption. The tension between these goals and the demands of a growing digital economy was the central conflict of the first crypto war.

**The Federal Bureau of Investigation (FBI)**: The FBI's interests were domestic: maintaining the ability to conduct lawful wiretaps and search encrypted devices. FBI Director Louis Freeh was a leading advocate for the Clipper Chip in the 1990s; FBI Director James Comey reprised this role in the 2010s with the "going dark" campaign.

**Vice President Al Gore**: Initially supported the Clipper Chip as part of the Clinton administration, but eventually came to champion the relaxation of export controls, reportedly influenced by the arguments of technology industry leaders and the emerging importance of the internet economy.

**Stewart Baker**: NSA General Counsel during the Clipper Chip era. One of the most articulate government advocates for surveillance access to encryption, he argued that the interests of law enforcement and national security should take precedence over absolute privacy.

### Industry Actors

**Netscape Communications**: The company whose browser made the web commercial. Netscape's struggle with export controls — forced to ship a weakened version of its browser internationally — became a powerful argument against the restrictions.

**Apple Inc.**: Became the focal point of the second crypto war in 2016 when the FBI demanded that Apple help unlock the San Bernardino shooter's iPhone. CEO Tim Cook's refusal, framed as a defense of user privacy and security, was the most high-profile corporate stand against government access demands.

**The Electronic Frontier Foundation (EFF)**: Founded in 1990, the EFF was the principal civil liberties organization in the crypto wars, providing legal defense for Zimmermann and Bernstein, opposing the Clipper Chip, and coordinating industry and activist opposition to surveillance access mandates.

### Organizations

**The Internet Engineering Task Force (IETF)**: The informal standards body responsible for the technical standards of the internet. The IETF's culture — open participation, decision by rough consensus, emphasis on running code over formal specifications — was both a product of and a contributor to the internet's decentralized architecture.

**The International Organization for Standardization (ISO)**: The formal, treaty-based standards body that developed the OSI protocol suite. ISO's culture — national delegations, formal voting, years-long standards processes — represented the opposite approach to internet governance.

---

## Analysis

### Why the Technologists Partially Won

The nuclear scientists studied by Burja and Lerangis had four principal objectives: accelerate the Allied bomb program, shape how the bomb was developed, prevent its use on Japan, and establish international control. They achieved only the first, and even that not very effectively. The cryptographers and internet engineers had analogous objectives: develop strong cryptography, make it available to ordinary people, prevent government monopoly control, and establish open governance of internet infrastructure. They achieved all four, at least partially.

The question is: why? What structural differences explain the divergent outcomes?

**1. The technologists could build and deploy, not merely advise**

This is the most fundamental difference. Leo Szilard, Niels Bohr, and their colleagues could only *recommend* courses of action to statesmen who held all the decision-making power. They had to persuade Roosevelt, Truman, Churchill, and Byrnes — and as the nuclear case study documents exhaustively, these statesmen were not interested in being told what to do by scientists.

The cryptographers, by contrast, could write code and publish algorithms. Phil Zimmermann did not need to persuade the President to allow strong encryption — he simply wrote PGP and released it. Diffie and Hellman did not need direct government authorization to publish their work on public-key cryptography — they published it in the open literature. The internet engineers did not need a top-down mandate to prove TCP/IP's viability, though they did need government *research funding* (DARPA, NSF) and institutional footholds to build the initial infrastructure and reference implementation.

This capacity to create *facts on the ground* — to make the technology exist and be in use before the government could prevent it — was decisive. The nuclear scientists could not unilaterally decide not to drop the bomb on Japan. But Phil Zimmermann could unilaterally make strong encryption available to anyone with a personal computer.

The cypherpunk slogan "Cypherpunks write code" was not merely aspirational — it was a strategic doctrine. By writing code, the cypherpunks transformed the political question from "should the public have access to strong encryption?" (a question the government could answer "no" to) into "how do you put this genie back in the bottle?" (a question to which the government had no good answer).

Crucially, TCP/IP amplified this capacity. Zimmermann could upload PGP to the internet and have it reach users quickly because the internet allowed publication without approval from a network operator. Had networking remained more centralized and carrier-controlled, unauthorized encryption software would likely have faced far more friction. But the protocol wars were an amplifier, not the sole enabling condition: academic journals, books, lawsuits, and offline software exchange also mattered.

It is important to note, however, that the crypto wars and the protocol wars involved different scales of effort. Phil Zimmermann could write PGP alone on his laptop. No individual could build a TCP/IP network. The protocol wars required DARPA research funding, university teams (the Berkeley BSD implementation was a decisive artifact), NSF investment in backbone infrastructure, and eventually commercial ISP buildout. But the decisive battles were fought at the *specification and software implementation* layer — where a small research community could operate — not at the physical infrastructure layer, which required major investment but was protocol-agnostic: the same cables could carry TCP/IP or OSI packets. The Berkeley team's decision to ship a free TCP/IP stack with BSD Unix settled the protocol question at a scale where a few dozen engineers were decisive. Once that battle was won, the crypto wars could be fought much more effectively by individuals.

**2. Powerful commercial interests aligned with the technologists — and against the state**

Nuclear weapons did have a commercial constituency — the defense-industrial complex (DuPont, Lockheed, General Electric, and others made enormous profits from weapons production). But this constituency was aligned with the *state's* goals: more weapons, more spending, more secrecy. The scientists who wanted arms control and international cooperation had no commercial allies; the companies that profited from the bomb had every reason to support continued government control over nuclear technology. The scientists were not just alone — they were opposed by a coalition of state power and aligned corporate interest.

Strong cryptography, by contrast, was essential for electronic commerce. Every online transaction required encryption. Every company doing business internationally needed to secure its communications. As the internet grew, the economic costs of weak encryption became enormous, creating a powerful commercial constituency for strong cryptography — a constituency that included some of the most valuable and politically influential companies in the world.

When Netscape could not export its browser with full-strength encryption, that was not an abstract policy concern — it was a competitive disadvantage against non-American companies that faced no such restrictions. When Apple refused to build a backdoor for the FBI, it was not only making a principled stand — it was protecting a key selling point of its products to billions of customers worldwide.

This alignment of commercial and activist interests was not inevitable, and it was not always comfortable. The cypherpunks and the corporations often had different motivations and disagreed on specifics. But on the central question — should strong encryption be widely available? — their interests converged, creating a coalition that was far more politically powerful than the nuclear scientists could ever have assembled.

**3. The technologists developed a strategically aware culture**

Burja and Lerangis attribute the failure of the nuclear scientists in large part to a "cultural misfit" between scientific culture (open, informal, merit-based) and political/military culture (closed, hierarchical, formal). The scientists tried to influence statesmen using the tools of scientific discourse — reason, evidence, prestige — and were repeatedly rebuffed.

The crypto and internet communities, while sharing many features of scientific culture, developed a greater degree of strategic awareness. This was partly a matter of timing: by the 1990s, the cautionary tale of the nuclear scientists was well known. But it was also a matter of practical necessity. The cypherpunks understood that they needed not just to be right but to win, and winning required action on multiple fronts: legal (the Bernstein case, the EFF's litigation), political (industry lobbying, congressional testimony), technical (writing code, deploying systems), and cultural (the cypherpunk mailing list, public advocacy).

The EFF, in particular, represented a new kind of organization — one that combined technical expertise with legal and political sophistication in a way that the nuclear-era scientists' organizations (like the Federation of Atomic Scientists) could not match. The EFF understood that the battle would be fought in courts, in Congress, and in the market, and it organized accordingly.

**4. The technology was decentralized and resistant to control — for two distinct reasons**

Nuclear weapons require enriched uranium or plutonium, massive industrial facilities, and state-level resources. This made them inherently controllable — there were only a handful of sites in the world capable of producing fissile material, and these could be (and were) subjected to international inspection regimes.

Cryptography and internet technology resisted control for two quite different reasons, which are worth distinguishing:

First, *mathematical* resistance: cryptographic algorithms are mathematical ideas. Once independently rediscovered and published, they are unusually hard to monopolize. Software can be copied at zero marginal cost.

Second, *architectural* resistance: the internet was *designed* to be relatively permissionless. This was not an inherent property of networking technology; it was the consequence of specific design choices made by TCP/IP's creators and later internet architects — choices that were contested in the protocol wars. As David Isenberg argued in his 1997 paper "Rise of the Stupid Network," the internet's value came precisely from being "stupid" — a general transport layer that moves packets without centrally managing every service. A more tightly managed telco-style network would have offered the state more natural control points at which to enforce restrictions on what users could publish or access. States can layer censorship on top of TCP/IP, as China's Great Firewall shows, but they do so by imposing control on a general-purpose internet rather than by relying on a single protocol architecture built from the start around identity and service approval.

This meant that even when governments "won" in policy terms, enforcement was often impossible on the actually-existing internet. The U.S. could classify encryption as a munition, but it could not prevent a professor from publishing a paper or a programmer from posting code to the internet. The Australian government could pass an anti-encryption law, but it could not force an American company to weaken its global encryption to comply. The UK could demand an Apple backdoor, but Apple could withdraw the feature rather than comply. But in each case, the enforcement failure depended on the internet's permissionless architecture — an architecture that was the product of the protocol wars, not a law of nature.

### The Culture Clash, Revisited

The culture clash that Burja and Lerangis identify as the central obstacle in the nuclear case was present in the crypto wars as well, but manifested differently.

The cypherpunks and internet engineers shared the nuclear scientists' contempt for political hierarchy, their preference for open discourse, and their tendency to believe that being technically right should be sufficient. Tim May's "Crypto Anarchist Manifesto" was not a document calculated to win friends in Washington. Phil Zimmermann's decision to release PGP was an act of civil disobedience, not political negotiation.

But the crypto community also produced individuals and organizations that could operate effectively in the political arena. The EFF hired lawyers and lobbyists. Technology companies had Washington offices and political action committees. Industry trade groups, civil-liberties lawyers, and policy-savvy executives served as conduits between the technical and political worlds.

Moreover, the crypto community benefited from a crucial structural advantage: their work created economic value for a *dispersed commercial constituency* that had independent political power. The nuclear scientists' work also created enormous value — but military value, concentrated entirely in the hands of the state. Politicians cared intensely about the bomb; the problem was that they cared about it as *their* instrument of power, not as something over which scientists should have a say. The state was simultaneously the producer, the customer, and the sole intended user of nuclear weapons, so there was no external constituency the scientists could mobilize.

The cryptographers' situation was the inverse. Strong encryption was essential not for the state but for millions of businesses and billions of consumers. This created a constituency — the technology industry, the e-commerce sector, the financial services industry — that had its own lobbyists, its own congressional allies, its own political action committees, and its own economic leverage. When the cryptographers argued for strong encryption, they were backed by companies whose revenues, employees, and tax contributions gave politicians concrete reasons to listen. The nuclear scientists had no such allies; the military-industrial complex was, if anything, aligned against them.

### What the Government Got Right, and Where It Adapted

It would be a mistake to portray the government as uniformly opposed to strong cryptography or open protocols. Many government officials, including within the NSA itself, recognized that the world was changing and that clinging to Cold War-era controls was counterproductive. The relaxation of export controls in the late 1990s was not simply a surrender — it reflected a genuine reassessment of the costs and benefits.

Moreover, the government adapted. Having failed to prevent the deployment of strong encryption, intelligence agencies developed new capabilities: bulk metadata collection, exploitation of implementation vulnerabilities, compromise of key management systems, and partnerships with technology companies under programs like PRISM (revealed by Snowden). The NSA did not win the crypto wars in the sense of preventing strong encryption, but it found ways to maintain significant surveillance capabilities despite it.

The government also learned to fight on different terrain. Rather than directly opposing encryption, recent efforts have focused on requiring "lawful access" through legislation, compelling companies to provide technical assistance through court orders, and creating liability frameworks (like the EARN IT Act) that create indirect pressure against end-to-end encryption.

---

## Example 1: The Clipper Chip — The Government's Bid for Control

In April 1993, the Clinton administration announced the Clipper Chip initiative. The proposal was straightforward: the government would make available a tamper-resistant encryption chip, designed by the NSA, that could be embedded in consumer communications devices — phones, fax machines, modems. The chip would use an 80-bit encryption algorithm called Skipjack, which the NSA claimed was significantly stronger than the commercially available DES standard.

The catch was "key escrow." Each Clipper Chip would contain a unique encryption key, and a copy of that key would be held in escrow by two government agencies (initially the Treasury Department and the National Institute of Standards and Technology). If law enforcement obtained a wiretap warrant, the escrowed keys would allow them to decrypt communications conducted with Clipper-enabled devices.

The Clinton administration presented this as a reasonable compromise: strong encryption for consumers, lawful access for law enforcement. Vice President Al Gore championed the proposal.

The response from the technology community was immediate and overwhelmingly negative. The objections were both technical and political:

**Technical**: Computer scientist Matt Blaze of AT&T Bell Labs was given access to Skipjack and the escrow protocol for review. Within months, he published a paper demonstrating a fundamental flaw in the escrow mechanism: a malicious user could bypass the Law Enforcement Access Field (LEAF) that enabled key escrow, obtaining the encryption benefits of the chip without the government access. The chip's security was predicated on a 16-bit checksum that was trivially forgeable.

**Political**: The EFF, the ACLU, and a coalition of technology companies and civil liberties organizations organized opposition. A public petition against the Clipper Chip gathered over 50,000 signatures — an extraordinary number for a technical policy debate in the pre-social-media era. Industry groups argued that key escrow would make the U.S. uncompetitive, since no foreign customer would purchase communications equipment with a built-in U.S. government backdoor.

**Strategic**: Perhaps most importantly, the Clipper Chip was not the only option. Commercial encryption products — weaker than Clipper due to export controls, but improving — were already available. The government was effectively asking consumers and businesses to voluntarily adopt a system with a government backdoor when alternatives existed. This was a fundamentally different proposition from the nuclear case, where the government controlled all the means of production.

The Clipper Chip was never formally withdrawn, but by 1996 it was a dead letter. No significant adoption occurred. The episode demonstrated a pattern that would recur: the government could propose, but it could not easily compel — and in the absence of compulsion, the market chose the option without the backdoor.

**Comparison to the nuclear case**: The Clipper Chip episode most closely parallels the genesis of the Manhattan Project in its structure — a government attempt to assert control over a transformative technology at an early stage. But where the Manhattan Project succeeded in bringing nuclear weapons development under military control, the Clipper Chip failed entirely. The key differences were twofold. First, the government could not monopolize the underlying knowledge: nuclear physics required billion-dollar facilities, while cryptography required a personal computer and a textbook. Second — and less often noted — the Clipper Chip required *voluntary adoption* because consumers and firms had alternatives. In a more tightly carrier-controlled network, the government might have had far stronger chokepoints through which to impose escrowed systems.

---

## Example 2: Phil Zimmermann and PGP — Code as Civil Disobedience

Phil Zimmermann was a software engineer and anti-nuclear activist in Boulder, Colorado. In 1991, concerned that Congress and law enforcement were moving toward mandated access to encrypted communications, he wrote PGP — Pretty Good Privacy — a free encryption program that implemented the RSA public-key algorithm for use by ordinary people on personal computers.

Zimmermann released PGP in June 1991, initially distributing it through BBS (bulletin board systems). It quickly spread to the internet, and from there to users worldwide. Under ITAR, this constituted the "export" of a munition, and in February 1993, the U.S. Customs Service opened a criminal investigation against Zimmermann.

The investigation lasted three years. During this time, Zimmermann became an international figure. Supporters organized his legal defense (the EFF provided early coordination), and the case became a rallying point for the encryption rights movement. In a notable act of protest, the complete source code of PGP was printed in a hardcover book and exported legally, since printed material was protected under the First Amendment — highlighting the absurdity of treating software as a munition while treating the same information in book form as protected speech.

In January 1996, the investigation was dropped without any charges being filed. The reasons were never officially stated, but the practical reality was clear: the case had become politically untenable. Prosecuting Zimmermann would have created a cause celebre and a First Amendment test case that the government was not confident of winning, particularly in light of the Bernstein litigation already underway.

**Comparison to the nuclear case**: Zimmermann's story most closely parallels Szilard's attempts to shape the Manhattan Project. Both were technically brilliant individuals acting on deep moral conviction, both operated outside formal channels, and both were seen as troublemakers by the authorities. But there is a crucial difference in outcomes. Szilard's influence on the Manhattan Project was effectively nil — he was marginalized, surveilled, and threatened with internment. Zimmermann, by contrast, succeeded in his core objective: PGP exists, is open-source, and is still in use today. The difference is that Szilard could only petition decision-makers, while Zimmermann could build the thing itself.

But Zimmermann's success also depended on something Szilard lacked entirely: a relatively permissionless distribution platform. Zimmermann uploaded PGP to a BBS and later to the internet; within days it had spread worldwide, and the government's only recourse was the slow machinery of criminal investigation. Had Zimmermann needed to distribute PGP through tightly controlled institutional channels, the investigation would have had a much better chance of shutting him down before PGP reached a meaningful audience. The internet's architecture amplified Zimmermann's success just as surely as the mathematics of RSA did.

---

## Example 3: OSI vs TCP/IP — The Protocol Wars

In the 1980s, the future architecture of global computer networking was contested between two incompatible visions.

**The OSI approach**: The International Organization for Standardization (ISO), working with national standards bodies and governments, developed the Open Systems Interconnection reference model and associated protocol suite — a comprehensive effort that covered everything from the physical layer to application protocols. The process was formal: national delegations met, proposals were debated and voted on, and standards were published as official ISO documents. The work was thorough, theoretically elegant, and extremely slow.

**The TCP/IP approach**: A smaller community of researchers, organized loosely through the Internet Engineering Task Force (IETF), developed the TCP/IP protocol suite. Dave Clark of MIT crystallized the IETF's ethos at the July 1992 IETF plenary with what became the community's unofficial anthem: *"We reject kings, presidents, and voting. We believe in rough consensus and running code."* Anyone could participate, proposals were judged primarily on whether they worked in practice, and standards were documented as "Requests for Comments" (RFCs) — a deliberately humble name suggesting openness to revision. The work was pragmatic, sometimes inelegant, and fast.

But the popular telling of this story — scrappy hackers vs. bureaucrats — obscures a critical fact: **TCP/IP's most important patron was the U.S. military.** ARPANET, the network on which TCP/IP was developed, was a Defense Department project from 1969. Vint Cerf and Bob Kahn designed TCP/IP under continuous DARPA funding in the early 1970s; Cerf then served as DARPA program manager for networking from 1976 to 1982, directly funding TCP/IP implementations at Stanford, BBN, and University College London. On January 1, 1983 — the "flag day" — the DoD mandated that all ARPANET hosts switch from the older NCP protocol to TCP/IP, cutting off any host that had not migrated. Later that year, the military split ARPANET into a civilian research network and MILNET (which took 68 of 113 nodes) for military traffic — both running TCP/IP. And in 1983, DARPA funded the Berkeley BSD TCP/IP implementation (4.2BSD), whose permissive licensing allowed workstation vendors like Sun Microsystems to adopt it freely.

The military's patronage gave TCP/IP a decisive head start. By the time the protocol wars with OSI heated up in the mid-1980s, TCP/IP had years of deployment and a substantial installed base — not because the market had spoken, but because the DoD had mandated it.

Governments and standards bureaucracies across much of the industrialized world strongly promoted OSI. But the U.S. government was not a monolith. DARPA and the operational military networking community were committed to TCP/IP — they ran on it. NBS (later NIST) and the Commerce Department championed OSI through the Government Open Systems Interconnection Profile (GOSIP), which became a federal procurement requirement in August 1990. European governments, working through ETSI and CEN/CENELEC, pushed OSI even harder. Within the DoD itself, a 1985 National Research Council report recommended adopting OSI's transport protocol (TP-4) as a co-standard with TCP, but the DoD's response (RFC 945) amounted to keeping TCP/IP while paying lip service to eventual OSI migration — noting that TP-4 was "not available at this time as a proven commercial offering." Major telecommunications companies and computer manufacturers invested heavily in OSI implementation.

TCP/IP won anyway. As Einar Stefferud, one of the internet's chief advocates, gleefully pronounced: *"OSI is a beautiful dream, and TCP/IP is living it!"*

The reasons are instructive for anyone thinking about the relationship between technical standards and political power:

**Military mandate created the installed base**. The single most important factor in TCP/IP's victory was that it was already deployed at scale before OSI was ready. The DoD's 1983 flag day mandate, followed by the DARPA-funded BSD implementation that shipped free with Unix, gave TCP/IP a seven-to-eight-year head start over OSI in real-world deployment. This was not a market outcome — it was a government mandate. But it was a mandate from the *research and operational* arm of the military (DARPA), not from the standards and procurement bureaucracy (NIST), which backed the other side.

**Running code beats committee specifications**. TCP/IP was deployed and working. OSI was, for most of the 1980s, a specification on paper. The DARPA-funded Berkeley implementation (4.2BSD, August 1983) incorporated Berkeley Sockets — the networking API that became the universal standard. This free, high-quality implementation shipped with BSD Unix and was adopted by workstation vendors due to its permissive licensing. By contrast, the various OSI implementations that existed were fragmentary and it was dubious whether they interoperated in any useful way. When organizations needed to connect their networks *now*, TCP/IP was the only real option. By the time OSI implementations became available, TCP/IP had an enormous installed base.

**Simplicity beats completeness**. TCP/IP was deliberately simple — it specified only what was necessary and left the rest to higher-level protocols. OSI attempted to specify everything comprehensively. In practice, this made TCP/IP easier to implement, easier to debug, and easier to adapt to new uses. The internet's "narrow waist" — the IP layer that sits between the physical network and higher-level applications — proved far more flexible than OSI's more rigid layer structure.

**Open participation beats national delegations**. Anyone could participate in the IETF by showing up to meetings or joining mailing lists. ISO participation was restricted to national delegations, which meant that standards debates were filtered through bureaucratic processes and political considerations. The IETF attracted a broader pool of talent and was more responsive to the needs of actual network operators.

**Market dynamics reinforced the winner**. As TCP/IP networks grew, they attracted more users, which attracted more network operators, which attracted more investment, which made the networks better, which attracted more users. OSI never achieved this kind of positive feedback loop because it never achieved critical mass. The military's early mandate was the initial push that set this flywheel spinning.

GOSIP was effectively relaxed in 1995. By the late 1990s, even the most committed OSI advocates had conceded defeat. The internet — built on TCP/IP, governed by the IETF, and shaped by end-to-end design principles — had won.

**The military as unwitting enabler**: There is a deep irony in this history. The same U.S. military that funded ARPANET, mandated TCP/IP, and bankrolled the BSD implementation would later find itself fighting the crypto wars against technologists who used that very infrastructure to distribute encryption tools the government wanted to suppress. Phil Zimmermann uploaded PGP to the military-funded internet. The cypherpunk mailing list ran on it. The code-as-speech lawsuits were publicized through it. The military built TCP/IP for resilient command-and-control communications, but the protocol's utility depended on its openness and generality — properties that, once deployed, could not be restricted to military-approved uses without destroying what made the network valuable. The military's "mistake," from a control perspective, was funding a technology whose usefulness was inseparable from its permissionlessness.

**Comparison to the nuclear case**: The protocol wars illustrate a mode of victory that was entirely unavailable to the nuclear scientists — but they also complicate the "technologists vs. the state" framing. The internet engineers did not mainly win by lobbying presidents and cabinet officials. They built and deployed a more usable system. But they did so with military patronage: DARPA funding, a DoD mandate, and institutional footholds that let technical superiority compound into adoption. The nuclear scientists had no such institutional ally. The Manhattan Project scientists worked under generals who opposed their policy preferences; the TCP/IP researchers worked under DARPA program managers who shared their technical vision (and were sometimes the same people). The lesson is not simply "write code" — it is that writing code is far more effective when the state funds your codebase and mandates its deployment before realizing the political implications.

**The protocol wars as precondition for the crypto wars**: The outcome of the protocol wars shaped the battlefield for every subsequent conflict described in this case study. Had more centralized networking models prevailed, dissident distribution of encryption tools likely would have faced much stronger friction, and government-backed approaches like Clipper might have had better odds. The entire structure of the crypto wars — individual technologists against the state, with the open internet as the arena — was strongly conditioned by TCP/IP's victory. In this sense, the protocol wars were among the most consequential of all the battles described here, because they determined the terms on which everything else would be fought. And the military, without intending to, was the decisive force that made TCP/IP's victory possible.

---

## Example 4: Apple vs FBI — The Second Crypto War

On December 2, 2015, Syed Rizwan Farook and Tashfeen Malik killed 14 people in a mass shooting in San Bernardino, California. Farook's work-issued iPhone 5C was recovered by investigators, but it was locked with passcode protections backed by device encryption.

In February 2016, the FBI obtained a court order under the All Writs Act compelling Apple to create a custom signed version of iOS that would disable key passcode-guessing protections for that device model. Apple argued that complying would set a dangerous precedent for compelled insecurity. FBI Director James Comey framed this as a narrow request concerning a single phone used by a dead terrorist.

Apple CEO Tim Cook refused, publishing an open letter to customers explaining that what the FBI was asking for was not a bypass for one phone but the creation of a master key — a capability that, once built, could not be controlled:

> "The government suggests this tool could only be used once, on one phone. But that's simply not true. Once created, the technique could be used over and over again, on any number of devices."

The case went to federal court but was never resolved on the merits: the FBI found a third-party vendor who could unlock the phone, and the government dropped its legal challenge. The legal question — whether the government can compel a technology company to write software that undermines its own security — remains unanswered.

The Apple case crystallized the dynamics of the second crypto war:

**The government's leverage was limited**. The FBI could apply legal pressure, but it could not compel Apple to write code without a clear legislative mandate — and Congress showed no appetite for such legislation. The All Writs Act, a 1789 statute, was an awkward vehicle for compelling the creation of sophisticated software.

**Public opinion was divided but not decisive**. Polls showed Americans roughly split on the Apple-FBI dispute, with a slight majority initially favoring the FBI. But the technology industry was overwhelmingly behind Apple, and the public arguments about security — that any backdoor could be exploited by adversaries — resonated with a post-Snowden audience.

**The market reinforced encryption**. Apple's stand became a selling point. In the years following the San Bernardino case, encryption became more deeply embedded across mobile platforms, with Apple enabling default device encryption on iPhones and Google pushing Android toward default encryption on many newer devices. The FBI's attempt to establish a precedent for compelled backdoors had the paradoxical effect of accelerating the adoption of stronger encryption.

**Comparison to the nuclear case**: The Apple-FBI confrontation most closely parallels Bohr's attempt to lobby Churchill and Roosevelt for international nuclear control (Example 3 in Burja and Lerangis). In both cases, a technically sophisticated actor engaged with the most senior levels of political power on a matter of fundamental importance. But where Bohr was ignored and then threatened with imprisonment, Apple's position prevailed — the FBI backed down, and encryption became stronger rather than weaker. The difference was not that Tim Cook was more politically savvy than Niels Bohr (though Apple's communications team was certainly more sophisticated than a Danish physicist operating in wartime). The difference was that Apple had something the government needed: hundreds of millions of iPhones, a consumer base, a market position, and the capacity to simply refuse. Bohr had only his prestige.

---

## Additional Examples

### Bernstein v. United States: Code as Speech

In 1995, Daniel Bernstein, then a graduate student at UC Berkeley, filed a lawsuit challenging the constitutionality of the export controls that classified encryption source code as a munition. Bernstein had developed an encryption algorithm called Snuffle and wanted to publish both the algorithm and its source code implementation.

The case wound through the courts for years. In 1999, a Ninth Circuit panel ruled that source code is a form of expressive speech protected by the First Amendment, and that the export regulations constituted an unconstitutional prior restraint on speech. That ruling was later vacated and remanded, and the case was ultimately mooted by the relaxation of export controls. But the litigation still had lasting influence: it made "code is speech" a durable constitutional argument against some forms of government regulation of software.

### The Snowden Revelations and the Acceleration of Encryption

In June 2013, Edward Snowden, a contractor for the NSA, leaked thousands of classified documents revealing the scale of government surveillance programs, including PRISM, through which providers were compelled to furnish communications associated with targeted selectors under Section 702, and the bulk collection of telephone metadata.

The revelations had a galvanizing effect on the technology industry. Companies that had previously cooperated quietly with government surveillance requests — or had been compelled to do so under the Foreign Intelligence Surveillance Act — now had powerful incentives to demonstrate their commitment to user privacy. The result was a dramatic acceleration in the deployment of end-to-end encryption:

- Apple made strong device encryption standard on modern iPhones with iOS 8 (September 2014)
- WhatsApp completed the rollout of end-to-end encryption for all messages (April 2016)
- Google pushed Android toward default device encryption on some newer devices (2015)
- Let's Encrypt, a free certificate authority, launched in 2015, making HTTPS adoption trivially easy

The Snowden revelations transformed encryption from a niche concern of privacy advocates into a mainstream commercial imperative.

The ultimate irony came in late 2024, when Chinese state hackers associated with "Salt Typhoon" compromised major U.S. telecommunications infrastructure. In response, U.S. officials urged greater use of end-to-end encrypted communications and stronger mobile-security practices — advice that underscored the cryptographers' long-running argument that transit systems without end-to-end protection are structurally vulnerable to sophisticated adversaries.

### The EARN IT Act

The Eliminating Abusive and Rampant Neglect of Interactive Technologies (EARN IT) Act, first introduced in 2020 and reintroduced in subsequent sessions, represented a more subtle approach to government access than direct encryption mandates. Rather than requiring backdoors, the EARN IT Act would have conditioned Section 230 liability protections (which shield internet platforms from liability for user-generated content) on compliance with "best practices" determined by a government commission.

Critics, including the EFF and a broad coalition of technology companies and civil liberties organizations, argued that the best practices would inevitably include requirements for scanning encrypted content — effectively mandating the weakening of end-to-end encryption. The act has not passed as of March 2026, but its repeated introduction demonstrates the government's continuing interest in finding legislative paths to compelled access.

### Australia's Assistance and Access Act (2018)

In December 2018, Australia became the first Five Eyes nation to pass legislation explicitly granting law enforcement the power to compel companies to provide technical assistance in accessing encrypted communications. The Telecommunications and Other Legislation Amendment (Assistance and Access) Act 2018 created three tiers of notices: Technical Assistance Requests (voluntary), Technical Assistance Notices (mandatory), and Technical Capability Notices (which can require companies to build new capabilities).

The law was controversial even within Australia and was criticized by the technology industry internationally. Its practical effect has been limited by the global nature of technology companies: requiring Apple to build a backdoor for Australia alone is technically difficult and commercially disastrous, since it would undermine security for all users. The law remains on the books but has not produced the sweeping surveillance capabilities its proponents hoped for.

### The UK Investigatory Powers Act and Apple (2025)

In early 2025, the UK Home Office reportedly used powers under the Investigatory Powers Act (the so-called "Snoopers' Charter") to pressure Apple over the end-to-end encryption provided by iCloud Advanced Data Protection.

Apple's response was characteristically blunt: rather than creating a backdoor, it first stopped offering Advanced Data Protection to new UK users and later required existing UK users to disable it. British users lost the ability to end-to-end encrypt those iCloud categories, but the encryption system itself remained uncompromised globally. The UK government reportedly issued a second, narrower order in September 2025, but Apple maintained its position.

This episode demonstrated both the power and the limits of state authority over global technology companies. The UK government could deny its own citizens access to a security feature, but it could not compel Apple to weaken the security of its global infrastructure. The political cost fell on the UK government, not on Apple.

### Net Neutrality

The battle over net neutrality — the principle that internet service providers should treat all traffic equally — was another dimension of the struggle over who controls the internet's architecture.

The concept, coined by Columbia law professor Tim Wu in 2003, held that ISPs should not be allowed to discriminate between different types of internet traffic — blocking, throttling, or charging extra for access to particular websites or services. The FCC enacted net neutrality rules in 2015 under the Obama administration, reclassifying broadband ISPs as "common carriers" under Title II of the Communications Act.

The rules were repealed in 2017 under the Trump administration's FCC Chairman Ajit Pai. Various states passed their own net neutrality laws, creating a patchwork of regulations. The Biden administration's FCC restored net neutrality rules in 2024, but the Sixth Circuit vacated that order in January 2025, leaving state-level rules and a continuing patchwork.

The net neutrality debate can be understood as a *rearguard action in the protocol wars*. The ISPs — the spiritual descendants of the PTT monopolies that backed OSI — were essentially attempting to re-impose more telco-style control at the infrastructure level: a "smart" network that inspects, prioritizes, and charges differently for different types of traffic, rather than a general transport layer that treats packets more equally. Net neutrality advocates were fighting to preserve the permissionless character of the internet that TCP/IP had helped establish — the very architecture that made the crypto wars winnable.

The pattern here is distinct from the crypto wars: the fight was not between technologists and the state, but between technologists (and consumers) and *corporations* seeking to control the network for profit, with the state as a contested mediator. The outcome — a perpetual seesaw of regulation and deregulation — reflects the absence of a clear "facts on the ground" victory of the kind that characterized the crypto and protocol wars. Unlike encryption, which could be deployed unilaterally by technology companies, net neutrality required ongoing regulatory enforcement. This is because the ISPs controlled the physical infrastructure — the one layer of the internet stack where the protocol wars victory could be reversed from below.

---

## Comparison with the Nuclear Weapons Case

The Burja and Lerangis case study identifies a core pattern: technically brilliant people who foresaw the catastrophic potential of a new technology, gained access to the highest levels of political power, proposed sophisticated solutions, and were almost entirely ignored. Their explanation centers on a cultural misfit between scientific and political elites, and on the inability of scientists to become decision-makers without ceasing to be scientists.

The crypto and protocol wars present a different pattern — one in which technically sophisticated people achieved many of their objectives, despite similar cultural tensions and despite the active opposition of the most powerful intelligence agency in the world. The comparison illuminates what factors determine whether technologists can actually shape the trajectory of a transformative technology.

### Key Structural Differences

| Dimension | Nuclear Weapons | Cryptography & Protocols |
|-----------|----------------|--------------------------|
| **Who could build it** | Only states (massive industrial resources required) | Crypto software: any individual (Zimmermann wrote PGP alone). Network protocols: a research community with institutional funding (DARPA, NSF, universities). Network infrastructure: major investment (ISPs, carriers) — but the physical layer was protocol-agnostic, so the decisive battles were fought at the specification and software layers, where small teams could be decisive |
| **Means of influence** | Advising decision-makers | Building and deploying technology directly |
| **Commercial constituency** | Defense-industrial complex — aligned with the *state*, not the dissenting scientists | Dispersed across millions of businesses and billions of consumers — independent of the state |
| **Military's role** | Aligned with the state against the dissenting scientists | Split: DARPA funded TCP/IP and enabled the open internet; NSA/FBI fought the crypto wars against technologists who used that infrastructure |
| **Distribution platform** | Government-controlled (classified labs, military bases) | Permissionless internet — itself a military creation (ARPANET/DARPA), whose openness enabled the very resistance the government later opposed |
| **Reversibility** | Irreversible once used (catastrophically) | Crypto software: can't un-release code once published. Protocol infrastructure: effectively irreversible once at scale — as IPv6 demonstrates, even a backwards-compatible upgrade to the IP layer has taken 25+ years and remains incomplete |
| **Secrecy regime** | Total (classified from inception) | Partial (academic research was public) |
| **International dynamics** | Zero-sum great power competition | Positive-sum global commerce |
| **Speed of proliferation** | Slow (decades for each new nuclear state) | Instant (software can be copied in seconds) |
| **Enforcement of restrictions** | Feasible (monitor fissile material) | Infeasible (mathematical knowledge + permissionless distribution) |
| **Cultural bridging** | Failed (scientists excluded from power) | Partial success (EFF, industry lobbying) |
| **Duration of conflict** | Compressed (1939-1950, key decisions in months) | Extended (1970s-present, ongoing) |

### What Remained the Same

Despite these structural differences, several patterns recurred:

**The government reflexively sought control**. In both cases, the initial government instinct was to assert total control over the new technology: classify nuclear physics, classify cryptography. In both cases, this instinct was driven by genuine security concerns (real enemies who would use the technology against the United States). And in both cases, the attempt at total control was undermined by the nature of the technology itself.

**Technical expertise was necessary but not sufficient for political influence**. In both cases, the technologists understood the technology far better than the decision-makers. In neither case did this understanding translate automatically into political influence. The nuclear scientists were ignored despite their Nobel Prizes; the cryptographers prevailed not because of their technical expertise per se, but because they found ways to translate that expertise into political, legal, and market power.

**Cultural contempt ran both ways**. Politicians dismissed scientists as naive about power; scientists dismissed politicians as ignorant about technology. This mutual contempt was toxic in the nuclear case and was present, though less completely debilitating, in the crypto case. The crypto community's partial success in bridging this gap — through organizations like the EFF, through industry lobbying, through the courts — is one of its most significant achievements.

**The fundamental problem of technology governance remains unsolved**. Neither case produced a durable, satisfactory framework for governing transformative technology. Nuclear weapons are still governed by a patchwork of treaties, deterrence doctrines, and informal norms that could fail catastrophically at any time. Cryptography is still subject to an ongoing tug-of-war between governments and technologists, with the rules being rewritten in every generation. In both cases, the gap between the rate of technological change and the rate of institutional adaptation remains dangerously wide.

### What the Nuclear Scientists Lacked

Viewed through the lens of the crypto wars, the failure of the nuclear scientists becomes even more striking — and more clearly attributable to structural factors rather than personal failings:

1. **They could not create facts on the ground**. Szilard could not unilaterally prevent the use of the bomb on Japan. He could only petition, plead, and protest. The cypherpunks could — and did — unilaterally deploy strong encryption.

2. **They had no commercial allies — only commercial opponents**. The defense-industrial complex (DuPont, General Electric, Lockheed) was a powerful commercial constituency for nuclear weapons — but it was aligned with the state's objectives, not the scientists'. The companies profiting from the bomb had every incentive to support continued government control. The cryptographers, by contrast, had the technology industry as an ally because strong encryption served commercial interests that were *independent of and often opposed to* the state's surveillance goals.

3. **They had no permissionless distribution platform — and the military never built them one**. The Manhattan Project scientists worked within a classified, government-controlled infrastructure. There was no way for Szilard to bypass the chain of command and distribute his ideas directly to the public or to allied scientists in other countries. The cryptographers, by contrast, could appeal to courts, the press, academic journals, books, and, increasingly, the internet — a platform on which publication required much less institutional permission than in legacy telecom systems. This was not an accident but a consequence of the protocol wars: TCP/IP's architecture, by design, reduced gatekeeping at the publication layer. And TCP/IP itself was a military creation — funded by DARPA, mandated by the DoD, implemented with defense research money. The irony is structural: the same military establishment that funded ARPANET and mandated TCP/IP later found the cypherpunks using that infrastructure to distribute the very encryption tools the government wanted to suppress. The nuclear scientists' institutional patron (the military) built infrastructure designed for secrecy and control; the internet engineers' institutional patron (also the military, through DARPA) built infrastructure whose utility depended on openness — and that openness, once deployed, could not be revoked.

4. **They operated in a regime of total secrecy**. The Manhattan Project scientists could not appeal to the public because the project's existence was classified. The cryptographers could — and did — make their case publicly, through the press, through lawsuits, and through published code.

5. **The window for influence was extremely narrow**. Key decisions about the bomb — whether to use it, whether to pursue international control — were made in a compressed timeframe during and immediately after a world war, when security considerations overwhelmed all others. The crypto wars played out over decades, in peacetime, allowing for iteration and learning.

---

## Coda: The Anthropic-DoD Standoff and the AI Question

In February-March 2026, a confrontation between the AI company Anthropic and the U.S. Department of Defense became an unusually clear test case for whether the governance of AI will look more like the crypto story, the nuclear story, or some unstable hybrid of the two.

### The Facts

In July 2025, Anthropic announced a Defense Department partnership worth up to $200 million to prototype frontier AI capabilities for national security, and later said it was the first frontier AI company to deploy models on U.S. government classified networks. According to contemporaneous reporting and Anthropic's own public statements, its defense work incorporated two explicit restrictions: no mass domestic surveillance of Americans and no fully autonomous weapons.

In February 2026, that arrangement broke down. Anthropic said the Pentagon demanded access for "any lawful use"; Anthropic refused, arguing that today's frontier models are not reliable enough for fully autonomous weapons and that mass domestic surveillance should not be normalized by private contract.

On February 19, Pentagon Chief Technology Officer Emil Michael publicly urged Anthropic to "cross the Rubicon" on military AI use cases. By February 24, according to TechPolicy.Press and other contemporaneous outlets, Defense Secretary Pete Hegseth had given Anthropic CEO Dario Amodei a February 27 deadline to accept broader terms. Anthropic's public response was blunt: these threats "do not change our position."

On February 27, President Trump directed federal agencies to stop using Anthropic's technology, and Hegseth moved to classify Anthropic as a supply-chain risk. Subsequent reporting described this as an unprecedented attempt to apply a foreign-supply-chain tool to an American AI company. Anthropic said it would challenge the move in court. OpenAI soon moved to expand its own Pentagon relationship, giving the government an immediate fallback supplier.

A leaked Amodei memo dismissed OpenAI's arrangement as largely "safety theater" and contrasted technical safeguards with explicit contractual restrictions. That distinction may matter, but the relative durability of technical controls, contracts, and procurement rules remains contested. What is clear is that competition among labs weakened Anthropic's leverage the moment another vendor was willing to step in.

Anthropic's public position was narrow rather than absolutist. The company said it supported lawful national-security uses of Claude aside from the two exceptions above, and argued that those exceptions had not blocked any government mission to date.

### Analysis: Where Does AI Fall on the Spectrum?

The Anthropic-DoD standoff shares features of both the nuclear weapons case and the crypto wars case, placing it somewhere in between on the spectrum of government-technologist conflict:

**Like the nuclear case**: AI is being developed primarily by a small number of well-funded organizations. The government is a major customer and funder. The technology has potential military applications that the government considers strategically vital. The technologists (Anthropic's leadership, drawn from the AI safety community) are motivated by concerns about catastrophic misuse — echoing Szilard and Bohr.

**Like the crypto case**: The technology is being developed by private companies, not government labs. There are multiple competing providers, creating market alternatives (OpenAI stepped in immediately when Anthropic was blacklisted). The technologists have commercial leverage — the Pentagon needs frontier AI models, and Anthropic's Claude is, at minimum, a leading option. And the technologists can, to some degree, enforce their preferences through contracts, usage policies, and technical controls.

**More centralized than the early internet**: Here the analysis of the protocol wars becomes directly relevant. Frontier AI models are not distributed on a permissionless platform. They are accessed through cloud APIs, enterprise contracts, app stores, and specialized compute stacks — all of which create chokepoints. That makes frontier AI more governable than PGP-style software distribution, even if the analogy to telco-era networking is only partial. Open-source AI models are the exception: they represent the more crypto-wars-like vector, distributable without as much institutional permission. The critical question for AI governance may therefore be whether open-source models become "good enough" to matter. If they do, AI may follow more of the crypto trajectory. If frontier models maintain a decisive advantage, the government retains more of the chokepoints it needs to enforce its will.

**Novel features**: The Anthropic case also introduces elements absent from both historical cases. The government is retaliating against a company for *refusing to remove ethical restrictions* — a different dynamic from either the nuclear case (where the government ignored ethical objections) or the crypto case (where the government tried to prevent the deployment of technology). The government is using economic coercion (supply chain risk designation, contract cancellation) rather than criminal prosecution or classification regimes. And the competitive dynamics among AI companies — with OpenAI apparently willing to provide what Anthropic would not — create a "race to the bottom" pressure that neither the nuclear scientists nor the cryptographers faced.

### Lessons for AI Governance

The crypto wars offer several lessons for the emerging AI governance struggle:

**1. Build, don't just advise — where durable controls are actually possible**. The single most important factor in the cryptographers' success was their ability to create facts on the ground. For AI, this suggests that safety-conscious developers who want to influence how AI is used should focus on embedding durable constraints in deployed systems where they can. But where market or state pressure can readily remove those constraints, product design is a weaker substitute for law.

**2. Cultivate commercial allies**. The cryptographers succeeded in part because strong encryption was commercially valuable. AI safety advocates need to demonstrate — and make real — the commercial value of safety. If customers prefer AI systems with appropriate use restrictions, then those restrictions become a market asset rather than a competitive liability.

**3. Win in court**. The Bernstein litigation helped establish "code is speech" as a powerful constitutional argument that constrained the government's ability to regulate encryption. The legal status of AI use restrictions, acceptable use policies, and government compulsion of technology companies is largely untested. Anthropic's announced intention to challenge the supply chain risk designation in court could be consequentially important.

**4. Don't rely on the goodwill of any single company**. Both Schneier and the EFF argued, in different ways, that durable guardrails should come from democratically accountable law and procurement rules rather than from private bargaining alone. OpenAI's willingness to fill the gap left by Anthropic's stand illustrates the fragility of corporate ethics as a substitute for legal protections.

**5. The window may be narrow**. The cryptographers had decades to fight their battles. AI is developing faster, the stakes may be higher, and the government is moving more aggressively. The time for creating durable governance frameworks — legal, institutional, technical — may be shorter than anyone would like.

---

## Sources

See [sources.md](sources.md) for a full bibliography.
