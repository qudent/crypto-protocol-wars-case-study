# The Cypherpunks, the Companies, and the Code

## A case study in decision-making around the control of cryptography and internet architecture

March 2026

---

## Abstract

This paper examines the dynamics of control and decision-making surrounding the development of strong cryptography and internet protocols from the 1970s through the present day.

Well before the internet became the backbone of global commerce and communication, some people — predominantly mathematicians, computer scientists, and engineers — foresaw that the ability to encrypt communications and to design open network architectures would be among the most consequential technical capabilities of the modern era. They understood that governments, particularly intelligence agencies, would seek to restrict or control these technologies. A loosely connected network of researchers, activists, and eventually companies dedicated much of their professional lives to ensuring that strong cryptography and open protocols would be available to ordinary people.

They partially succeeded. Unlike the nuclear scientists studied by Burja and Lerangis (2018), who failed almost entirely to shape the political decisions surrounding nuclear weapons, the cryptographers and internet engineers achieved a mixed but meaningful victory. Strong encryption is now ubiquitous in consumer technology. The internet runs on open protocols rather than government-mandated standards. Yet the battle is not over: governments continue to push for backdoors, surveillance capabilities, and control over digital infrastructure, as the March 2026 standoff between the U.S. Department of Defense and Anthropic vividly illustrates.

We propose that the partial success of the technologists in this case — in contrast to the total failure of the nuclear scientists — can be attributed to several structural differences: the technologists could *build and deploy* their preferred outcomes rather than merely advise decision-makers; the technology was dual-use in ways that created powerful commercial constituencies; and the relevant technical community developed a culture that was, if not politically sophisticated, at least strategically aware of the need to create facts on the ground. The analogy to contemporary AI governance is direct and urgent.

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

The NSA's reach was practical, not merely legal. When IBM developed the Data Encryption Standard (DES) in the mid-1970s, the NSA pressured IBM to reduce the key length from its original 128 bits down to 56 bits. Cryptographers Whitfield Diffie and Martin Hellman publicly criticized this reduction, arguing the shortened key made the cipher vulnerable to brute-force attack by a well-resourced adversary — i.e., the NSA itself. Their suspicion was vindicated in January 1999, when the EFF and distributed.net publicly cracked a DES key in just 22 hours and 15 minutes using custom-built hardware costing under $250,000.

This assumption of permanent government monopoly was shattered by two developments. In 1976, Diffie and Hellman published "New Directions in Cryptography," which described the concept of public-key cryptography — a method by which two parties could establish a shared secret over an insecure channel without any prior arrangement. This was the most significant breakthrough in cryptography since the development of the one-time pad, and it had been achieved entirely outside the classified world. An NSA employee sent a letter to the publishers warning that the authors could face prison time for violating export control laws, but the paper was published regardless. The NSA had independently developed similar ideas, but had kept them secret. The publication of Diffie-Hellman effectively ended the government's monopoly on cryptographic knowledge. (Diffie and Hellman received the 2015 Turing Award for this work.)

Shortly afterward, Ron Rivest, Adi Shamir, and Leonard Adleman at MIT developed RSA, the first practical public-key cryptosystem. The NSA attempted to discourage publication and to restrict the distribution of RSA, but the academic community resisted, and the algorithm was published and widely disseminated.

Simultaneously, the internet's predecessor networks were being designed. The ARPANET, funded by the Department of Defense's Advanced Research Projects Agency (DARPA), used the TCP/IP protocol suite developed primarily by Vint Cerf and Bob Kahn. The architectural choices made in these protocols — particularly the end-to-end principle, which holds that intelligence should reside at the endpoints of a network rather than in the network itself — would have profound political consequences, though these were not fully appreciated at the time.

### The First Crypto War (1990-2000)

As personal computing and the early internet expanded in the late 1980s and early 1990s, strong cryptography threatened to move from the academic world into consumer products. The U.S. government, led by the NSA and the FBI, attempted to prevent this through several strategies:

**Export controls**: Under ITAR, software containing strong encryption could not be exported from the United States. This effectively prevented American software companies from including strong encryption in their products, since most had international markets. The controls classified cryptographic software alongside tanks and fighter jets.

**The Clipper Chip (1993)**: The Clinton administration proposed a hardware encryption chip for consumer devices that would use an algorithm (Skipjack) designed by the NSA, with a built-in "key escrow" system giving the government access to all encrypted communications. This was the government's most ambitious attempt to maintain its cryptographic monopoly in the face of technological change.

**Criminal prosecution**: Phil Zimmermann, author of the PGP (Pretty Good Privacy) encryption program, was subjected to a three-year criminal investigation for "exporting munitions" — because his software had been uploaded to the internet and downloaded by people outside the United States.

All three strategies failed. The Clipper Chip was abandoned after security researcher Matt Blaze discovered a critical vulnerability in the escrow protocol and after massive opposition from the technology industry and civil liberties organizations. Export controls were progressively relaxed between 1996 and 2000, culminating in their effective removal for mass-market encryption software. The investigation of Zimmermann was dropped without charges.

By 2000, strong encryption was available in every major web browser, email client, and operating system. The first crypto war was over, and the technologists had won.

### The Protocol Wars (1980s-1990s)

Running in parallel with the crypto wars was a less publicized but equally consequential battle over the architecture of global computer networking. Governments and established telecommunications companies, through the International Organization for Standardization (ISO), had developed the Open Systems Interconnection (OSI) model — a seven-layer protocol stack designed through a formal, top-down standards process involving national delegations and official representatives.

The U.S. government mandated the use of OSI protocols through the Government OSI Profile (GOSIP), requiring all government computer networks to adopt OSI standards. European governments pushed even harder for OSI adoption. The expectation was that OSI would become the global standard, and TCP/IP — developed by a small community of researchers through the informal Internet Engineering Task Force (IETF) — would be relegated to a historical footnote.

TCP/IP won decisively. The reasons are instructive: it was simpler, it worked, and — crucially — it was already deployed. While OSI committees debated protocol specifications in formal meetings, internet engineers were building and connecting networks. The IETF's philosophy of "rough consensus and running code" proved devastatingly effective against the top-down standards process. By the mid-1990s, even governments that had mandated OSI were quietly connecting to the TCP/IP internet.

### The Second Crypto War (2013-present)

The Edward Snowden revelations of 2013 demonstrated the scale of government surveillance enabled by the internet's original design — which, despite the end-to-end principle, left most communications unencrypted in practice. The response from the technology industry was dramatic: within a few years, Apple enabled full-disk encryption by default on iPhones, WhatsApp deployed end-to-end encryption for over a billion users, and the HTTPS protocol (encrypting web traffic) went from being used on a minority of websites to the overwhelming majority.

This "second crypto war" saw the government largely on the defensive. The FBI's 2016 confrontation with Apple over an encrypted iPhone used by the San Bernardino shooter ended in a draw — the FBI found an alternative way into the phone and dropped its legal challenge, but Apple's encryption remained unbroken. The "going dark" rhetoric of FBI Director James Comey, warning that encryption was creating spaces beyond the reach of lawful surveillance, failed to produce legislation mandating backdoors.

However, the government achieved partial victories through other means. The Five Eyes intelligence alliance continued to press for "lawful access" to encrypted communications. Australia passed the Assistance and Access Act in 2018, granting authorities the power to compel companies to provide technical assistance in accessing encrypted data. The UK's Investigatory Powers Act was used in 2025 to demand that Apple create a backdoor into its iCloud encryption, though Apple chose to withdraw the feature from the UK rather than comply. The EARN IT Act, introduced multiple times in the U.S. Congress, threatened to weaken encryption protections by conditioning legal liability shields on compliance with government access requirements.

### The DNS and Governance Wars

Control over the internet's naming system — the Domain Name System (DNS) — was another arena of conflict. Jon Postel, a computer scientist at USC's Information Sciences Institute, had informally administered the Internet Assigned Numbers Authority (IANA) since the early days of the ARPANET. As the internet grew into a commercial and geopolitical force, control over DNS became increasingly contested.

The U.S. government, through the Department of Commerce's National Telecommunications and Information Administration (NTIA), asserted authority over the DNS root zone. Other nations, particularly through the International Telecommunication Union (ITU), pushed for multilateral control.

The most dramatic moment came on January 28, 1998, when Postel emailed eight of the twelve operators of the internet's regional root nameservers and instructed them to change their root zone authority from Network Solutions' server to IANA's. The operators complied — demonstrating that the internet community's informal trust relationships, not government contracts, were the real basis of DNS authority. Postel soon received a furious call from Ira Magaziner, President Clinton's senior science advisor, who reportedly threatened: *"You'll never work on the Internet again."* Postel reversed the change. Within a week, the NTIA issued a "Green Paper" asserting the U.S. government's definitive authority over the DNS root.

The eventual creation of ICANN (Internet Corporation for Assigned Names and Numbers) in 1998 — with its original board members chosen by Postel himself before his death in October of that year — and the IANA transition in 2016 that moved oversight away from the U.S. government to a multi-stakeholder model, represented a compromise — but one in which the internet community's preferred governance model (multi-stakeholder rather than multilateral) largely prevailed.

---

## Relevant Players

### Technologists and Advocates

**Whitfield Diffie**: Co-inventor of public-key cryptography. A deeply private person who spent years working on the problem of key distribution essentially alone before his breakthrough with Hellman. Later became Sun Microsystems' chief security officer and a persistent advocate for strong encryption.

**Martin Hellman**: Stanford professor and co-inventor of public-key cryptography. Unlike many of his peers, Hellman was willing to engage publicly with the political implications of his work, including testifying before Congress and debating NSA officials.

**Phil Zimmermann**: Creator of PGP (Pretty Good Privacy), the first widely available strong encryption software for personal computers. An anti-nuclear activist who saw cryptography as a tool for individual empowerment. His decision to release PGP as free software, and the three-year criminal investigation that followed, made him a cause celebre in the technology community and beyond.

**Matt Blaze**: Bell Labs and later University of Pennsylvania researcher who discovered a critical flaw in the Clipper Chip's key escrow mechanism in 1994. His paper was a decisive blow against the Clipper proposal, demonstrating that the system's security was fundamentally compromised.

**Tim May**: Intel physicist and co-founder of the cypherpunk movement. Author of "The Crypto Anarchist Manifesto" (1988), which predicted that cryptography would fundamentally alter the relationship between individuals and the state. His vision was more radical than most: he saw cryptography as a tool for dismantling state power entirely.

**Eric Hughes**: UC Berkeley mathematician and co-founder of the cypherpunk mailing list. Author of "A Cypherpunk's Manifesto" (1993), which articulated the movement's core philosophy: "Cypherpunks write code. We know that someone has to write software to defend privacy, and since we can't get privacy unless we all do, we're going to write it."

**Vint Cerf and Bob Kahn**: Co-designers of TCP/IP, the protocol suite that powers the internet. While not directly involved in the crypto wars, their architectural decisions — particularly the end-to-end principle — shaped the battlefield on which later conflicts would be fought.

**Jon Postel**: Administrator of IANA and editor of the RFC series. His quiet authority over internet naming and numbering, based entirely on the trust of the engineering community rather than any formal mandate, embodied the internet's original governance model.

**Daniel Bernstein**: Mathematician and cryptographer who, as a graduate student, successfully challenged the constitutionality of encryption export controls. The Bernstein v. United States ruling, which held that source code is protected speech under the First Amendment, was a pivotal legal victory.

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

The cryptographers, by contrast, could write code and publish algorithms. Phil Zimmermann did not need to persuade the President to allow strong encryption — he simply wrote PGP and released it. Diffie and Hellman did not need government permission to publish their paper on public-key cryptography — they published it in an academic journal. The IETF did not need a government mandate to deploy TCP/IP — they just connected more networks.

This capacity to create *facts on the ground* — to make the technology exist and be in use before the government could prevent it — was decisive. The nuclear scientists could not unilaterally decide not to drop the bomb on Japan. But Phil Zimmermann could unilaterally make strong encryption available to anyone with a personal computer.

The cypherpunk slogan "Cypherpunks write code" was not merely aspirational — it was a strategic doctrine. By writing code, the cypherpunks transformed the political question from "should the public have access to strong encryption?" (a question the government could answer "no" to) into "how do you put this genie back in the bottle?" (a question to which the government had no good answer).

**2. Powerful commercial interests aligned with the technologists**

Nuclear weapons had no commercial constituency. There was no consumer demand for atomic bombs, no industry lobby for nuclear proliferation. The scientists were alone in their political advocacy.

Strong cryptography, by contrast, was essential for electronic commerce. Every online transaction required encryption. Every company doing business internationally needed to secure its communications. As the internet grew, the economic costs of weak encryption became enormous, creating a powerful commercial constituency for strong cryptography — a constituency that included some of the most valuable and politically influential companies in the world.

When Netscape could not export its browser with full-strength encryption, that was not an abstract policy concern — it was a competitive disadvantage against non-American companies that faced no such restrictions. When Apple refused to build a backdoor for the FBI, it was not only making a principled stand — it was protecting a key selling point of its products to billions of customers worldwide.

This alignment of commercial and activist interests was not inevitable, and it was not always comfortable. The cypherpunks and the corporations often had different motivations and disagreed on specifics. But on the central question — should strong encryption be widely available? — their interests converged, creating a coalition that was far more politically powerful than the nuclear scientists could ever have assembled.

**3. The technologists developed a strategically aware culture**

Burja and Lerangis attribute the failure of the nuclear scientists in large part to a "cultural misfit" between scientific culture (open, informal, merit-based) and political/military culture (closed, hierarchical, formal). The scientists tried to influence statesmen using the tools of scientific discourse — reason, evidence, prestige — and were repeatedly rebuffed.

The crypto and internet communities, while sharing many features of scientific culture, developed a greater degree of strategic awareness. This was partly a matter of timing: by the 1990s, the cautionary tale of the nuclear scientists was well known. But it was also a matter of practical necessity. The cypherpunks understood that they needed not just to be right but to win, and winning required action on multiple fronts: legal (the Bernstein case, the EFF's litigation), political (industry lobbying, congressional testimony), technical (writing code, deploying systems), and cultural (the cypherpunk mailing list, public advocacy).

The EFF, in particular, represented a new kind of organization — one that combined technical expertise with legal and political sophistication in a way that the nuclear-era scientists' organizations (like the Federation of Atomic Scientists) could not match. The EFF understood that the battle would be fought in courts, in Congress, and in the market, and it organized accordingly.

**4. The technology was decentralized and resistant to control**

Nuclear weapons require enriched uranium or plutonium, massive industrial facilities, and state-level resources. This made them inherently controllable — there were only a handful of sites in the world capable of producing fissile material, and these could be (and were) subjected to international inspection regimes.

Cryptographic algorithms are mathematical ideas. Once published, they cannot be unpublished. Software can be copied at zero marginal cost. The internet is designed to route around damage — and, as John Gilmore famously observed, treats censorship as damage. The fundamental nature of the technology worked against centralized control.

This meant that even when governments "won" in policy terms, enforcement was often impossible. The U.S. could classify encryption as a munition, but it could not prevent a professor from publishing a paper or a programmer from posting code to the internet. The Australian government could pass an anti-encryption law, but it could not force an American company to weaken its global encryption to comply. The UK could demand an Apple backdoor, but Apple could withdraw the feature rather than comply.

### The Culture Clash, Revisited

The culture clash that Burja and Lerangis identify as the central obstacle in the nuclear case was present in the crypto wars as well, but manifested differently.

The cypherpunks and internet engineers shared the nuclear scientists' contempt for political hierarchy, their preference for open discourse, and their tendency to believe that being technically right should be sufficient. Tim May's "Crypto Anarchist Manifesto" was not a document calculated to win friends in Washington. Phil Zimmermann's decision to release PGP was an act of civil disobedience, not political negotiation.

But the crypto community also produced individuals and organizations that could operate effectively in the political arena. The EFF hired lawyers and lobbyists. Technology companies had Washington offices and political action committees. Key individuals — notably former Sun Microsystems executive and later Obama administration official Aneesh Chopra, and various tech industry lobbyists — served as conduits between the technical and political worlds.

Moreover, the crypto community benefited from a crucial structural advantage: their work created economic value that politicians cared about. The nuclear scientists could appeal to morality and to the long-term survival of civilization, but these are abstractions in the world of politics. The cryptographers could point to the economic growth of the internet economy, to American technological leadership, to jobs and tax revenue. These are the currency of political power.

### What the Government Got Right, and Where It Adapted

It would be a mistake to portray the government as uniformly opposed to strong cryptography or open protocols. Many government officials, including within the NSA itself, recognized that the world was changing and that clinging to Cold War-era controls was counterproductive. The relaxation of export controls in the late 1990s was not simply a surrender — it reflected a genuine reassessment of the costs and benefits.

Moreover, the government adapted. Having failed to prevent the deployment of strong encryption, intelligence agencies developed new capabilities: bulk metadata collection, exploitation of implementation vulnerabilities, compromise of key management systems, and partnerships with technology companies under programs like PRISM (revealed by Snowden). The NSA did not win the crypto wars in the sense of preventing strong encryption, but it found ways to maintain significant surveillance capabilities despite it.

The government also learned to fight on different terrain. Rather than directly opposing encryption, recent efforts have focused on requiring "lawful access" through legislation, compelling companies to provide technical assistance through court orders, and creating liability frameworks (like the EARN IT Act) that create indirect pressure against end-to-end encryption.

---

## Example 1: The Clipper Chip — The Government's Bid for Control

In April 1993, the Clinton administration announced the Clipper Chip initiative. The proposal was straightforward: the government would make available a tamper-resistant encryption chip, designed by the NSA, that could be embedded in consumer communications devices — phones, fax machines, modems. The chip would use an 80-bit encryption algorithm called Skipjack, which the NSA claimed was significantly stronger than the commercially available DES standard.

The catch was "key escrow." Each Clipper Chip would contain a unique encryption key, and a copy of that key would be held in escrow by two government agencies (initially the Treasury Department and the National Institute of Standards and Technology). If law enforcement obtained a wiretap warrant, the escrowed keys would allow them to decrypt the communication.

The Clinton administration presented this as a reasonable compromise: strong encryption for consumers, lawful access for law enforcement. Vice President Al Gore championed the proposal.

The response from the technology community was immediate and overwhelmingly negative. The objections were both technical and political:

**Technical**: Computer scientist Matt Blaze of AT&T Bell Labs was given access to Skipjack and the escrow protocol for review. Within months, he published a paper demonstrating a fundamental flaw in the escrow mechanism: a malicious user could bypass the Law Enforcement Access Field (LEAF) that enabled key escrow, obtaining the encryption benefits of the chip without the government access. The chip's security was predicated on a 16-bit checksum that was trivially forgeable.

**Political**: The EFF, the ACLU, and a coalition of technology companies and civil liberties organizations organized opposition. A public petition against the Clipper Chip gathered over 50,000 signatures — an extraordinary number for a technical policy debate in the pre-social-media era. Industry groups argued that key escrow would make the U.S. uncompetitive, since no foreign customer would purchase communications equipment with a built-in U.S. government backdoor.

**Strategic**: Perhaps most importantly, the Clipper Chip was not the only option. Commercial encryption products — weaker than Clipper due to export controls, but improving — were already available. The government was effectively asking consumers and businesses to voluntarily adopt a system with a government backdoor when alternatives existed. This was a fundamentally different proposition from the nuclear case, where the government controlled all the means of production.

The Clipper Chip was never formally withdrawn, but by 1996 it was a dead letter. No significant adoption occurred. The episode demonstrated a pattern that would recur: the government could propose, but it could not compel — and in the absence of compulsion, the market chose the option without the backdoor.

**Comparison to the nuclear case**: The Clipper Chip episode most closely parallels the genesis of the Manhattan Project in its structure — a government attempt to assert control over a transformative technology at an early stage. But where the Manhattan Project succeeded in bringing nuclear weapons development under military control, the Clipper Chip failed entirely. The key difference was that the government could not monopolize the underlying knowledge. Nuclear physics required billion-dollar facilities; cryptography required a personal computer and a textbook.

---

## Example 2: Phil Zimmermann and PGP — Code as Civil Disobedience

Phil Zimmermann was a software engineer and anti-nuclear activist in Boulder, Colorado. In 1991, concerned that proposed legislation (Senate Bill 266) would mandate backdoors in telecommunications equipment, he wrote PGP — Pretty Good Privacy — a free encryption program that implemented the RSA public-key algorithm for use by ordinary people on personal computers.

Zimmermann released PGP in June 1991, initially distributing it through BBS (bulletin board systems). It quickly spread to the internet, and from there to users worldwide. Under ITAR, this constituted the "export" of a munition, and in February 1993, the U.S. Customs Service opened a criminal investigation against Zimmermann.

The investigation lasted three years. During this time, Zimmermann became an international figure. Supporters organized his legal defense (the EFF provided early coordination), and the case became a rallying point for the encryption rights movement. In a notable act of protest, the complete source code of PGP was printed in a hardcover book and exported legally, since printed material was protected under the First Amendment — highlighting the absurdity of treating software as a munition while treating the same information in book form as protected speech.

In January 1996, the investigation was dropped without any charges being filed. The reasons were never officially stated, but the practical reality was clear: the case had become politically untenable. Prosecuting Zimmermann would have created a cause celebre and a First Amendment test case that the government was not confident of winning, particularly in light of the Bernstein litigation already underway.

**Comparison to the nuclear case**: Zimmermann's story most closely parallels Szilard's attempts to shape the Manhattan Project. Both were technically brilliant individuals acting on deep moral conviction, both operated outside formal channels, and both were seen as troublemakers by the authorities. But there is a crucial difference in outcomes. Szilard's influence on the Manhattan Project was effectively nil — he was marginalized, surveilled, and threatened with internment. Zimmermann, by contrast, succeeded in his core objective: PGP exists, is open-source, and is still in use today. The difference is that Szilard could only petition decision-makers, while Zimmermann could build the thing itself.

---

## Example 3: OSI vs TCP/IP — The Protocol Wars

In the 1980s, the future architecture of global computer networking was contested between two incompatible visions.

**The OSI approach**: The International Organization for Standardization (ISO), working with national standards bodies and governments, developed the Open Systems Interconnection model — a comprehensive seven-layer protocol stack that covered everything from the physical layer to application protocols. The process was formal: national delegations met, proposals were debated and voted on, and standards were published as official ISO documents. The work was thorough, theoretically elegant, and extremely slow.

**The TCP/IP approach**: A smaller community of researchers, organized loosely through the Internet Engineering Task Force (IETF), developed the TCP/IP protocol suite. Dave Clark of MIT crystallized the IETF's ethos at the July 1992 IETF plenary with what became the community's unofficial anthem: *"We reject kings, presidents, and voting. We believe in rough consensus and running code."* Anyone could participate, proposals were judged primarily on whether they worked in practice, and standards were documented as "Requests for Comments" (RFCs) — a deliberately humble name suggesting openness to revision. The work was pragmatic, sometimes inelegant, and fast.

Governments worldwide mandated OSI. In the United States, the Government Open Systems Interconnection Profile (GOSIP) required federal agencies to purchase computer systems that supported OSI protocols. European governments, working through ETSI and CEN/CENELEC, pushed even harder. Major telecommunications companies and computer manufacturers invested billions in OSI implementation.

TCP/IP won anyway. As Einar Stefferud, one of the internet's chief advocates, gleefully pronounced: *"OSI is a beautiful dream, and TCP/IP is living it!"*

The reasons are instructive for anyone thinking about the relationship between technical standards and political power:

**Running code beats committee specifications**. TCP/IP was deployed and working. OSI was, for most of the 1980s, a specification on paper. The critical weapon was DARPA's funding of a TCP/IP implementation at UC Berkeley. The 4.2BSD release (August 1983) incorporated Berkeley Sockets — the networking API that became the universal standard. This free, high-quality implementation shipped with BSD Unix and was adopted by workstation vendors due to its permissive licensing. By contrast, the various OSI implementations that existed were fragmentary and it was dubious whether they interoperated in any useful way. When organizations needed to connect their networks *now*, TCP/IP was the only real option. By the time OSI implementations became available, TCP/IP had an enormous installed base.

**Simplicity beats completeness**. TCP/IP was deliberately simple — it specified only what was necessary and left the rest to higher-level protocols. OSI attempted to specify everything comprehensively. In practice, this made TCP/IP easier to implement, easier to debug, and easier to adapt to new uses. The internet's "narrow waist" — the IP layer that sits between the physical network and higher-level applications — proved far more flexible than OSI's more rigid layer structure.

**Open participation beats national delegations**. Anyone could participate in the IETF by showing up to meetings or joining mailing lists. ISO participation was restricted to national delegations, which meant that standards debates were filtered through bureaucratic processes and political considerations. The IETF attracted a broader pool of talent and was more responsive to the needs of actual network operators.

**Market dynamics reinforced the winner**. As TCP/IP networks grew, they attracted more users, which attracted more network operators, which attracted more investment, which made the networks better, which attracted more users. OSI never achieved this kind of positive feedback loop because it never achieved critical mass.

The GOSIP mandate was quietly repealed in 1995. By the late 1990s, even the most committed OSI advocates had conceded defeat. The internet — built on TCP/IP, governed by the IETF, operating on the end-to-end principle — had won.

**Comparison to the nuclear case**: The protocol wars illustrate a mode of victory that was entirely unavailable to the nuclear scientists. The internet engineers did not lobby the government to adopt TCP/IP. They did not write memos to the President. They did not seek meetings with the Vice President. They simply built a network that worked better than the alternative, and waited for reality to impose itself. This is the strategy that Eric Hughes called "writing code" — creating facts on the ground that make the preferred outcome the path of least resistance. The nuclear scientists could not write code; they could only write memos.

---

## Example 4: Apple vs FBI — The Second Crypto War

On December 2, 2015, Syed Rizwan Farook and Tashfeen Malik killed 14 people in a mass shooting in San Bernardino, California. Farook's work-issued iPhone 5C was recovered by investigators, but it was locked with a passcode, and its data was encrypted.

In February 2016, the FBI obtained a court order under the All Writs Act compelling Apple to create a custom version of iOS that would disable the security features preventing brute-force passcode guessing — effectively a government-specific backdoor. FBI Director James Comey framed this as a narrow request concerning a single phone used by a dead terrorist.

Apple CEO Tim Cook refused, publishing an open letter to customers explaining that what the FBI was asking for was not a bypass for one phone but the creation of a master key — a capability that, once built, could not be controlled:

> "The government suggests this tool could only be used once, on one phone. But that's simply not true. Once created, the technique could be used over and over again, on any number of devices."

The case went to federal court but was never resolved on the merits: the FBI found a third-party vendor who could unlock the phone, and the government dropped its legal challenge. The legal question — whether the government can compel a technology company to write software that undermines its own security — remains unanswered.

The Apple case crystallized the dynamics of the second crypto war:

**The government's leverage was limited**. The FBI could apply legal pressure, but it could not compel Apple to write code without a clear legislative mandate — and Congress showed no appetite for such legislation. The All Writs Act, a 1789 statute, was an awkward vehicle for compelling the creation of sophisticated software.

**Public opinion was divided but not decisive**. Polls showed Americans roughly split on the Apple-FBI dispute, with a slight majority initially favoring the FBI. But the technology industry was overwhelmingly behind Apple, and the public arguments about security — that any backdoor could be exploited by adversaries — resonated with a post-Snowden audience.

**The market reinforced encryption**. Apple's stand became a selling point. In the years following the San Bernardino case, encryption became a standard feature across mobile platforms, with both Apple and Google enabling full-disk encryption by default. The FBI's attempt to establish a precedent for compelled backdoors had the paradoxical effect of accelerating the adoption of stronger encryption.

**Comparison to the nuclear case**: The Apple-FBI confrontation most closely parallels Bohr's attempt to lobby Churchill and Roosevelt for international nuclear control (Example 3 in Burja and Lerangis). In both cases, a technically sophisticated actor engaged with the most senior levels of political power on a matter of fundamental importance. But where Bohr was ignored and then threatened with imprisonment, Apple's position prevailed — the FBI backed down, and encryption became stronger rather than weaker. The difference was not that Tim Cook was more politically savvy than Niels Bohr (though Apple's communications team was certainly more sophisticated than a Danish physicist operating in wartime). The difference was that Apple had something the government needed: hundreds of millions of iPhones, a consumer base, a market position, and the capacity to simply refuse. Bohr had only his prestige.

---

## Additional Examples

### Bernstein v. United States: Code as Speech

In 1995, Daniel Bernstein, then a graduate student at UC Berkeley, filed a lawsuit challenging the constitutionality of the export controls that classified encryption source code as a munition. Bernstein had developed an encryption algorithm called Snuffle and wanted to publish both the algorithm and its source code implementation.

The case wound through the courts for years. In 1999, the Ninth Circuit Court of Appeals ruled that source code is a form of expressive speech protected by the First Amendment, and that the export regulations constituted an unconstitutional prior restraint on speech. The ruling was later vacated and remanded, and the case was ultimately mooted by the relaxation of export controls. But the legal principle — that code is speech — has had lasting influence, creating a constitutional barrier to some forms of government regulation of software.

### The Snowden Revelations and the Acceleration of Encryption

In June 2013, Edward Snowden, a contractor for the NSA, leaked thousands of classified documents revealing the scale of government surveillance programs, including PRISM (which provided the NSA with direct access to data held by major technology companies) and the bulk collection of telephone metadata.

The revelations had a galvanizing effect on the technology industry. Companies that had previously cooperated quietly with government surveillance requests — or had been compelled to do so under the Foreign Intelligence Surveillance Act — now had powerful incentives to demonstrate their commitment to user privacy. The result was a dramatic acceleration in the deployment of end-to-end encryption:

- Apple enabled full-disk encryption by default on iOS 8 (September 2014)
- WhatsApp completed the rollout of end-to-end encryption for all messages (April 2016)
- Google enabled full-disk encryption by default on Android (2015)
- Let's Encrypt, a free certificate authority, launched in 2015, making HTTPS adoption trivially easy

The Snowden revelations transformed encryption from a niche concern of privacy advocates into a mainstream commercial imperative.

The ultimate irony came in late 2024, when Chinese state hackers (the "Salt Typhoon" group) compromised major U.S. telecommunications infrastructure — AT&T, Verizon, and Lumen Technologies — in what was described as the most egregious national security breach in U.S. history. In response, the FBI and CISA jointly *recommended* that Americans use end-to-end encrypted messaging apps like Signal and WhatsApp — the very tools these agencies had spent decades opposing. The Salt Typhoon breach vindicated the cryptographers' central argument: any communications infrastructure without end-to-end encryption is vulnerable to exploitation by adversaries, including state-level ones.

### The EARN IT Act

The Eliminating Abusive and Rampant Neglect of Interactive Technologies (EARN IT) Act, first introduced in 2020 and reintroduced in subsequent sessions, represented a more subtle approach to government access than direct encryption mandates. Rather than requiring backdoors, the EARN IT Act would have conditioned Section 230 liability protections (which shield internet platforms from liability for user-generated content) on compliance with "best practices" determined by a government commission.

Critics, including the EFF and a broad coalition of technology companies and civil liberties organizations, argued that the best practices would inevitably include requirements for scanning encrypted content — effectively mandating the weakening of end-to-end encryption. The act has not passed as of March 2026, but its repeated introduction demonstrates the government's continuing interest in finding legislative paths to compelled access.

### Australia's Assistance and Access Act (2018)

In December 2018, Australia became the first Five Eyes nation to pass legislation explicitly granting law enforcement the power to compel companies to provide technical assistance in accessing encrypted communications. The Telecommunications and Other Legislation Amendment (Assistance and Access) Act 2018 created three tiers of notices: Technical Assistance Requests (voluntary), Technical Assistance Notices (mandatory), and Technical Capability Notices (which can require companies to build new capabilities).

The law was controversial even within Australia and was criticized by the technology industry internationally. Its practical effect has been limited by the global nature of technology companies: requiring Apple to build a backdoor for Australia alone is technically difficult and commercially disastrous, since it would undermine security for all users. The law remains on the books but has not produced the sweeping surveillance capabilities its proponents hoped for.

### The UK Investigatory Powers Act and Apple (2025)

In January 2025, the UK Home Office, using powers under the Investigatory Powers Act (the so-called "Snoopers' Charter"), issued a Technical Capability Notice (TCN) demanding that Apple create a backdoor into its iCloud Advanced Data Protection end-to-end encryption.

Apple's response was characteristically blunt: rather than creating a backdoor, it withdrew the Advanced Data Protection feature from the UK entirely. British users lost the ability to encrypt their iCloud data end-to-end, but the encryption system itself remained uncompromised globally. The UK government issued a second, allegedly narrower order in September 2025, but Apple maintained its position.

This episode demonstrated both the power and the limits of state authority over global technology companies. The UK government could deny its own citizens access to a security feature, but it could not compel Apple to weaken the security of its global infrastructure. The political cost fell on the UK government, not on Apple.

### Net Neutrality

The battle over net neutrality — the principle that internet service providers should treat all traffic equally — was another dimension of the struggle over who controls the internet's architecture.

The concept, coined by Columbia law professor Tim Wu in 2003, held that ISPs should not be allowed to discriminate between different types of internet traffic — blocking, throttling, or charging extra for access to particular websites or services. The FCC enacted net neutrality rules in 2015 under the Obama administration, reclassifying broadband ISPs as "common carriers" under Title II of the Communications Act.

The rules were repealed in 2017 under the Trump administration's FCC Chairman Ajit Pai. Various states passed their own net neutrality laws, creating a patchwork of regulations. The Biden administration's FCC restored net neutrality rules in 2024, but these face ongoing legal challenges.

The net neutrality debate illustrates a pattern distinct from the crypto wars: here, the fight was not between technologists and the state, but between technologists (and consumers) and *corporations* seeking to control the network for profit, with the state as a contested mediator. The outcome — a perpetual seesaw of regulation and deregulation — reflects the absence of a clear "facts on the ground" victory of the kind that characterized the crypto and protocol wars. Unlike encryption, which could be deployed unilaterally by technology companies, net neutrality required ongoing regulatory enforcement.

---

## Comparison with the Nuclear Weapons Case

The Burja and Lerangis case study identifies a core pattern: technically brilliant people who foresaw the catastrophic potential of a new technology, gained access to the highest levels of political power, proposed sophisticated solutions, and were almost entirely ignored. Their explanation centers on a cultural misfit between scientific and political elites, and on the inability of scientists to become decision-makers without ceasing to be scientists.

The crypto and protocol wars present a different pattern — one in which technically sophisticated people achieved many of their objectives, despite similar cultural tensions and despite the active opposition of the most powerful intelligence agency in the world. The comparison illuminates what factors determine whether technologists can actually shape the trajectory of a transformative technology.

### Key Structural Differences

| Dimension | Nuclear Weapons | Cryptography & Protocols |
|-----------|----------------|--------------------------|
| **Who could build it** | Only states (massive industrial resources required) | Anyone with a computer and mathematical knowledge |
| **Means of influence** | Advising decision-makers | Building and deploying technology directly |
| **Commercial constituency** | None (no consumer demand for bombs) | Enormous (all of electronic commerce) |
| **Reversibility** | Irreversible once used | Incremental, reversible deployment |
| **Secrecy regime** | Total (classified from inception) | Partial (academic research was public) |
| **International dynamics** | Zero-sum great power competition | Positive-sum global commerce |
| **Speed of proliferation** | Slow (decades for each new nuclear state) | Instant (software can be copied in seconds) |
| **Enforcement of restrictions** | Feasible (monitor fissile material) | Infeasible (cannot monitor mathematical knowledge) |
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

2. **They had no commercial allies**. There was no corporate interest in nuclear arms control. The military-industrial complex was, if anything, aligned against them. The cryptographers had the entire technology industry as an ally.

3. **They operated in a regime of total secrecy**. The Manhattan Project scientists could not appeal to the public because the project's existence was classified. The cryptographers could — and did — make their case publicly, through the press, through lawsuits, and through published code.

4. **The window for influence was extremely narrow**. Key decisions about the bomb — whether to use it, whether to pursue international control — were made in a compressed timeframe during and immediately after a world war, when security considerations overwhelmed all others. The crypto wars played out over decades, in peacetime, allowing for iteration and learning.

---

## Coda: The Anthropic-DoD Standoff and the AI Question

In February-March 2026, a confrontation between the AI company Anthropic and the U.S. Department of Defense brought the dynamics of the crypto wars into vivid contemporary focus — and suggested that the governance of AI may follow a trajectory with elements of both the nuclear and crypto cases.

### The Facts

In July 2025, Anthropic and the Pentagon had entered into a contract worth up to $200 million under which Claude, Anthropic's AI model, became the first frontier model approved for use on classified government networks. As part of the contract, the Pentagon agreed to abide by Anthropic's acceptable use policy (AUP), which prohibited the use of Claude for fully autonomous weapons systems and for mass domestic surveillance of American citizens.

In early 2026, the Pentagon — under Defense Secretary Pete Hegseth and Undersecretary for Research and Engineering Emil Michael — demanded that Anthropic remove these restrictions and allow the military to use Claude "for all lawful purposes" without limitation. Anthropic refused.

On February 19, Pentagon CTO Emil Michael — a Silicon Valley executive turned Trump appointee (tapped in December 2024) — publicly urged Anthropic to "cross the Rubicon" on military AI use cases. On February 24, Hegseth gave Anthropic CEO Dario Amodei a deadline: relent by 5:01 PM on Friday, February 27, and allow unrestricted use for "all legal purposes." On February 26, Amodei stated that the Pentagon's threats "do not change our position."

On February 27, President Trump directed all federal agencies to cease using Anthropic's technology. Hegseth designated Anthropic a "supply chain risk" — a designation traditionally reserved for foreign adversaries like Huawei, and never before applied to an American company. Hours later, OpenAI announced a deal with the Pentagon, with CEO Sam Altman claiming his company's contract would include protections similar to Anthropic's red lines. (It is worth noting that OpenAI president Greg Brockman and his wife had donated $25 million to the MAGA Inc super PAC, and Altman personally donated $1 million to Trump's inauguration.)

Amodei described OpenAI's deal in an internal memo as "maybe 20% real and 80% safety theater," noting that OpenAI embedded safeguards as technical controls within the AI systems themselves rather than requiring explicit contractual limits — a crucial distinction, since technical controls can be quietly modified or removed, while contractual limits are legally enforceable. When the memo leaked, Amodei apologized for its tone, but stood by the substance. He announced his intention to challenge the supply chain risk designation in court, and reportedly sought to return to the negotiating table with Emil Michael — though Michael publicly denied any active negotiations, posting on social media: "There is no active negotiation with Anthropic."

Anthropic's stated position was carefully bounded: they explicitly supported Claude's use for intelligence analysis, operational planning, modeling and simulation, and cyber operations. Their two red lines were narrow: no fully autonomous weapons ("frontier AI systems are not reliable enough to power fully autonomous weapons") and no mass domestic surveillance of American citizens. As Anthropic wrote on its blog: "We have never believed it is the role of any private company to be involved in operational decision-making."

### Analysis: Where Does AI Fall on the Spectrum?

The Anthropic-DoD standoff shares features of both the nuclear weapons case and the crypto wars case, placing it somewhere in between on the spectrum of government-technologist conflict:

**Like the nuclear case**: AI is being developed primarily by a small number of well-funded organizations. The government is a major customer and funder. The technology has potential military applications that the government considers strategically vital. The technologists (Anthropic's leadership, drawn from the AI safety community) are motivated by concerns about catastrophic misuse — echoing Szilard and Bohr.

**Like the crypto case**: The technology is being developed by private companies, not government labs. There are multiple competing providers, creating market alternatives (OpenAI stepped in immediately when Anthropic was blacklisted). The technologists have commercial leverage — the Pentagon needs frontier AI models, and Anthropic's Claude is, at minimum, a leading option. And the technologists can, to some degree, enforce their preferences through technical means (acceptable use policies, terms of service).

**Novel features**: The Anthropic case introduces elements absent from both historical cases. The government is retaliating against a company for *refusing to remove ethical restrictions* — a different dynamic from either the nuclear case (where the government ignored ethical objections) or the crypto case (where the government tried to prevent the deployment of technology). The government is using economic coercion (supply chain risk designation, contract cancellation) rather than criminal prosecution or classification regimes. And the competitive dynamics among AI companies — with OpenAI apparently willing to provide what Anthropic would not — create a "race to the bottom" pressure that neither the nuclear scientists nor the cryptographers faced.

### Lessons for AI Governance

The crypto wars offer several lessons for the emerging AI governance struggle:

**1. Build, don't just advise**. The single most important factor in the cryptographers' success was their ability to create facts on the ground. For AI, this suggests that safety-conscious developers who want to influence how AI is used should focus on building and deploying AI systems with built-in safety features, rather than solely on lobbying for regulations that may never be enacted.

**2. Cultivate commercial allies**. The cryptographers succeeded in part because strong encryption was commercially valuable. AI safety advocates need to demonstrate — and make real — the commercial value of safety. If customers prefer AI systems with appropriate use restrictions, then those restrictions become a market asset rather than a competitive liability.

**3. Win in court**. The Bernstein ruling — that code is speech — was a pivotal victory that constrained the government's ability to regulate encryption. The legal status of AI use restrictions, acceptable use policies, and government compulsion of technology companies is largely untested. Anthropic's announced intention to challenge the supply chain risk designation in court could be consequentially important.

**4. Don't rely on the goodwill of any single company**. Schneier's analysis of the Anthropic situation is apt: the EFF fought to ensure that privacy protections were embedded in law, not dependent on the decisions of individual companies. OpenAI's willingness to fill the gap left by Anthropic's principled stand illustrates the fragility of corporate ethics as a substitute for legal protections.

**5. The window may be narrow**. The cryptographers had decades to fight their battles. AI is developing faster, the stakes may be higher, and the government is moving more aggressively. The time for creating durable governance frameworks — legal, institutional, technical — may be shorter than anyone would like.

---

## Sources

See [sources.md](sources.md) for a full bibliography.
