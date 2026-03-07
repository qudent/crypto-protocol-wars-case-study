# The Cypherpunks, the Companies, and the Code

**A case study in decision-making around the control of cryptography and internet architecture**

> **Disclosure**: This report was 100% researched and written by Claude Code (Anthropic's Claude Opus 4.6) in a single session on March 7, 2026. No human editing has been applied. The prompts used to generate it are included below. All claims should be independently verified.

A companion piece to Bismarck Analysis's *The Scientists, the Statesmen, and the Bomb* (Burja & Lerangis, 2018), examining a case where the technologists partially won their struggle against the state — and what that tells us about AI governance today.

## Structure

- `report.md` — The full case study (~9,400 words)
- `sources.md` — Bibliography and source list (80+ sources)
- `comparison.md` — Detailed comparison with the nuclear weapons case and implications for AI

## Context

The Bismarck Analysis nuclear weapons case study argues that scientists who foresaw the dangers of nuclear weapons tried to influence political decision-making and failed, due to a fundamental cultural misfit between scientists and statesmen. This companion study examines a structurally similar conflict — the struggle over control of cryptography and internet protocols from the 1970s to the present — where the outcome was strikingly different. The technologists did not fully win, but they did not fully lose either.

This case is offered as a counter-narrative and analytical complement, particularly relevant in light of the March 2026 Anthropic-Department of Defense standoff over acceptable use restrictions on AI technology.

## Prompts

The human provided a link to the [Bismarck Analysis nuclear weapons case study PDF](https://www.bismarckanalysis.com/Nuclear_Weapons_Development_Case_Study.pdf) and then gave roughly this direction across a few messages:

> This study is intended as an analogy for the development of AI technology (also see the recent Anthropic - Department of Defense standoff). I feel like there's also a counter story you can tell about the fight between the tech industry and the people who build the internet and the security agencies and the government about encryption. They don't win completely.
>
> Make a research plan, maybe, and then maybe do research and write some kind of report. It doesn't need to be a PDF; markdown is also good. That goes into detail on this, which is kind of analogous to the nuclear weapons development case study, and maybe looks at the differences. Oh, and this should be in Dropbox in a new folder with a git repository structure.

With follow-up clarifications:

> I mean Anthropic - DoD standoff

> And it's not only crypto wars but also protocol wars

Claude Code then fetched and read the full 22-page Bismarck Analysis PDF, dispatched three parallel research agents (crypto wars history, protocol wars history, nuclear-AI analogy + Anthropic-DoD details), performed additional web searches, and wrote the report in the structure of the original case study.

### Substantive review prompts (post-draft)

The human reviewed the draft and provided two substantive corrections:

> You write: "Running in parallel with the crypto wars was a less publicized but equally consequential battle over the architecture of global computer networking..."
>
> I think from this passage it doesn't become clear enough _what political implications_ these architectures had. My understanding is this: If the internet today worked like the telco-designed stuff, there would be no pseudonymity against the state, you need to buy an "EU+" package to access up to 5 websites outside of your home country per day, there would be no VPN that chinese dissidents can use against the state's will because everyone would be tracked (in order to be billed), and setting up a server may require renting server space in a central telco-owned datacenter and 12 months of compliance process for the service (so no internet startups or maybe Wikipedia). Is this correct? You could even say given your report that the crypto wars were tilted in favour of the programmers because the protocol wars had been won, and it was possible to do and publish stuff like the Zimmermann code without going through institutions.

> You write: "Moreover, the crypto community benefited from a crucial structural advantage: their work created economic value that politicians cared about. The nuclear scientists could appeal to morality and to the long-term survival of civilization, but these are abstractions in the world of politics..."
>
> That doesn't seem to make sense to me in this formulation - the politicians certainly cared about the military value of the nuclear bomb.

Then:

> Can you go through the report in more detail, not just these sections, and check how the rest could or would need to be rewritten in light of this or what kind of research would be germane there?

Claude Code identified 11 sections needing revision to propagate the two insights (protocol wars as precondition; constituency alignment, not constituency existence), plus 5 areas for additional research (Minitel, China's Great Firewall, Lessig's "Code is Law", Isenberg's "Rise of the Stupid Network", ITU vs. ICANN at WSIS). All 11 sections were revised; Minitel and the Great Firewall were added as concrete counterfactuals.

Then, correcting the Great Firewall framing:

> Regarding China's great firewall. How exactly do you write this? My point is that thanks to TCP/IP and the infrastructure programmed on it that is "too-big-to-ban", even in 2026 it is possible to circumvent it by a VPN (and lots of people do so without fear of getting thrown into jail). What do you say about this?

The Great Firewall references were rewritten: it proves the TCP/IP thesis, not the opposite. China built censorship *on top of* TCP/IP, and because TCP/IP is permissionless at the protocol level, the firewall is inherently porous — hundreds of millions circumvent it with VPNs. Had the network been built on telco/OSI principles, "VPN" would be a meaningless concept.

Then, distinguishing crypto from protocols on "who could build it":

> You write in the comparison table: "Who could build it — Anyone with a computer and mathematical knowledge." It seems to me like crypto and protocols are different here. After all, I can install OpenSSL but I can't build a telco network.

The comparison tables and analysis sections in both report.md and comparison.md were revised to distinguish between crypto software (individual-scale: Zimmermann wrote PGP alone) and network protocols/infrastructure (institutional-scale: required DARPA funding, university teams like Berkeley BSD, NSF backbone investment). The key insight: the protocol wars were won at the *specification and software implementation* layer — where a small research community could operate — not at the physical infrastructure layer, which required major investment but was protocol-agnostic (same cables carry TCP/IP or OSI). A new analytical paragraph was added to the report explaining this cascading dependency: institutional effort built the platform, but the platform then enabled individual action by the cryptographers. The AI comparison was also refined: open-source model weights behave like crypto software (trivially copyable), while frontier model training behaves more like the protocol wars (institutional-scale resources).

On the same pass, the "Reversibility" row was corrected:

> You write: "Reversibility — Irreversible once used / Incremental, reversible deployment." I think TCP/IP is de facto quite irreversible, as IPv6 shows.

The row was rewritten: crypto software can't be un-released once published; protocol infrastructure is effectively irreversible once at scale — IPv6, a backwards-compatible upgrade, has taken 25+ years and remains incomplete.

Then, catching a misattribution:

> You write: "Schneier's analysis of the Anthropic situation is apt: the EFF fought to ensure that privacy protections were embedded in law, not dependent on the decisions of individual companies." This seems hallucinated to me — I don't see Schneier mentioning the EFF? Or did Schneier talk about courts?

The original sentence conflated two separate sources. Schneier's blog post argued that democratic legal structures, not corporate ethics, should govern AI procurement — but did not mention the EFF. The EFF's post argued that privacy protections "shouldn't depend on the decisions of a few powerful people" and are "properly a role for Congress and the courts" — but did not mention Schneier. The passage was rewritten to correctly attribute each argument to its source, with direct quotes from both.
