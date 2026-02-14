# The 2029 Quantum Roadmap: Jay Gambetta on Building the Future of Computing

**Source:** [Smart Talks with IBM - Malcolm Gladwell interviews Jay Gambetta](https://youtu.be/F1dLNmNS1cc)  
**Who:** Jay Gambetta, Director of IBM Research (promoted Oct 2025)  
**Date Captured:** 2025-02-14

---

## TL;DR

Jay Gambetta, IBM's new research chief, lays out the concrete roadmap to fault-tolerant quantum computing by 2029. The key insight: quantum isn't about replacing classical computers — it's about solving a **different class of problems** that classical math can't touch efficiently. IBM's roadmap: module (2026) → two modules (2027) → scaled system (2029).

---

## The Core Insight: A New Kind of Math

Gambetta reframes quantum computing not as "faster" but as **fundamentally different**:

> "I actually feel superposition and entanglement are a bit of a distraction. Think of quantum computing as bringing a new primitive to computer science."

### Classical vs Quantum — The Real Difference

**Classical computers:** Excellent at problems that can be represented numerically.

**Quantum computers:** Step outside to a class of problems that **don't have a simple numerical representation**.

> "If you were to try to represent it with classical computers, it takes exponential time."

### The Non-Commuting Operations Insight

Gambetta explains quantum's advantage through **order-dependent operations**:

> "Imagine I got some medicine... If A followed by B gave a different answer than B first followed by A — that means there's an algebra behind it that representing traditionally on classical computers is really really hard."

This is why quantum can solve chemistry and materials problems: molecular interactions don't "commute" — order matters in ways that explode classical computation.

---

## Quantum Complements, Doesn't Replace

A key clarification for anyone confused about quantum's role:

> "People think quantum is going to be replacing classical. If your problem is good at adding numbers together, you should just keep using classical computers."

> "I think the future is going to be **heterogeneous accelerators** and it will definitely have quantum as one."

**Translation:** Future computing = classical + GPU + quantum, each handling what it's best at.

---

## The 2029 Roadmap: Module → Connect → Scale

IBM's concrete path to fault-tolerant quantum computing:

### The Challenge: Error Correction
Quantum systems are noisy. To run large, useful problems, you need to correct errors — which traditionally required massive overhead.

> "We had to reinvent how we wanted to do error correction."

### The Breakthrough
IBM's team discovered a new error correction code that works within existing engineering constraints:

> "Either we were going to have to work out how to cool down a very large piece of silicon... or we had to come up with a different [code]. And once I knew we had one that I didn't need to reinvent any tools to build — the implications are clear."

### The Roadmap (Named After Australian Birds)

| Year | Milestone | Name |
|------|-----------|------|
| 2026 | Single error-corrected module (~1000 qubits) | Kookaburra |
| 2027 | Two modules connected | Cockatoo |
| 2029 | Scaled fault-tolerant system | Starling |

> "By 2029 we'll build the first fault-tolerant quantum computer — one that can completely handle the noise to allow you to run a very, very large problem."

---

## What "Fault-Tolerant" Actually Means

The 2029 milestone isn't about qubit count — it's about **reliability**:

> "For around a couple hundred qubits and 100 million operations, you're talking still interesting science problems like simulating a molecule or calculating a small optimization problem."

**Key distinction:**
- **Today:** We can run quantum circuits that classical computers can't simulate, but results are noisy
- **2029:** Results are **reliable enough** for real scientific problems

> "It'll be at the point where it's beyond — well beyond — any classical approximate method."

---

## The Scientific Tool Era (2025-2029)

Before 2029, we're in what Gambetta calls the "heuristic" phase:

> "Over the next four years, you're going to continue to see more and more heuristic, not provable quantum problems that run on quantum computers."

**Heuristic problems:**
- Can't be proven on paper to have quantum advantage
- Must be tested empirically
- Sometimes lead to formal (provable) problems

> "We're beyond now the point that you can simulate these quantum computers with any classical computer. They're kind of like a scientific tool."

This is the current opportunity: quantum computers as **exploratory instruments**, not production systems.

---

## Problems Quantum Will Solve

### Chemistry & Materials
> "Imagine now we have a machine that you can't simulate. How do you actually discover algorithms in a scientific way?"

Applications:
- Drug discovery (simulating molecular interactions)
- Materials science (battery design, superconductors)
- Catalyst optimization

### The Nature Simulation Advantage
> "Quantum computers compute using the fundamental equations of nature — Schrödinger equation."

Classical computers **approximate** nature. Quantum computers **are** nature (at the relevant scale). Huge difference for simulating physical systems.

---

## What's Already Running

> "It's not that we don't know what to do with a quantum computer. There are hundreds of algorithms. You can go to quantumzoo.com and see many, many algorithms."

Current state:
- **2023:** IBM achieved circuits that can't be simulated classically
- **Now:** 200+ enterprise partners exploring use cases
- **Ongoing:** Scientists discovering new algorithms empirically

---

## Jay's Journey: From Carpenter Dreams to Quantum Chief

Gambetta's path reveals something about innovation:

> "No, I grew up in a pretty normal life. My dreams as a kid was building things. So, I was either going to be a carpenter or a mechanic, but I had some great teachers that inspired me to go to university."

He discovered quantum through **lasers**:
> "I watched a TV show and lasers seemed interesting. So I wanted to learn about lasers and then I realized in trying to understand lasers there was this quantum mechanics."

From Yale PhD (2004-2007) to IBM Research Director — following curiosity, not career planning.

---

## The Leadership Philosophy

On Arvind Krishna (IBM CEO):
> "The beauty of Arvind is he trusts that scientists will do it and so he doesn't really check on us. He empowers us to do really hard problems."

This aligns with what Krishna said in the previous episode: give teams space to push hard, but allow them to push back.

---

## Key Takeaways for Enterprise

### 1. The Timeline Is Real
- 2029: First fault-tolerant quantum computer
- Not hype — specific engineering milestones (Kookaburra → Cockatoo → Starling)

### 2. Start Learning Now
- Quantum is a **new kind of math**, not faster classical
- Understanding the paradigm takes time
- "Heuristic" exploration happening NOW

### 3. Identify Your Quantum Problems
- Not all problems benefit from quantum
- Look for: non-commuting operations, exponential state spaces, nature simulation
- Chemistry, optimization, materials science are prime candidates

### 4. It's Complementary
- Quantum won't replace your classical infrastructure
- Future = heterogeneous computing (classical + GPU + quantum)
- Start thinking about integration, not replacement

---

## Bottom Line

The 2029 fault-tolerant quantum computer isn't a vague promise — it's an engineering roadmap with named milestones and demonstrated progress. The gap between "interesting heuristic" and "proven advantage" will close in the next 4 years.

The question isn't **if** quantum computing will matter. It's **whether you'll be ready** when it does.

---

*Captured from YouTube transcript. Direct quotes are verbatim from the interview.*
