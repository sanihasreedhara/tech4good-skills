# Calibrated AI Coding Mentor Research Thesis

<!-- Relevant Research Threads, Theory Recommendations, Gaps & Opportunities, and Knowledge Contribution Framing. Owned by /define-research -->

*Deep literature review and Related Work preparation: see [research-thesis-prompt.md](./research-thesis-prompt.md).*

## Relevant Research Threads

### 1. The Scaffolding-vs-Overhead Tradeoff in LLM Code Hinting (Computing Education / ICER / SIGCSE)
- **Core Tension:** How can pedagogical AI agents provide hints that preserve developer agency without either (a) revealing code solutions directly, or (b) imposing extraneous cognitive load on students who must decipher plausible-yet-misaligned advice?
- **What the field knows:** Recent computing education research (Denny et al., 2023; Prather et al., 2023; Kazemitabaar et al., 2023) establishes that LLMs can generate effective code explanations and hints, but uncritical auto-completion risks creating over-reliance where novices copy-paste code without mastering architecture. MacNeil et al. (2023) and Liffiton et al. (2023) showed that explanation-focused AI improves student learning, but hint quality degrades rapidly when agents misinterpret task context.
- **Open Tensions:** Existing pedagogical hint tools operate under the implicit assumption that the agent's internal task model is correct. The field lacks understanding of how hint-based agents handle architectural context ambiguity and whether intent-checking mechanisms reduce student diagnostic overhead.

### 2. Passive Codebase Indexing vs. Conversational Intent Capture (HCI / Software Engineering / CHI / UIST)
- **Core Tension:** Does passive context retrieval (AST parsing, open tabs, vector RAG) adequately capture a developer's intended design direction, or is active conversational intent verification necessary to align AI guidance with uncommitted code changes?
- **What the field knows:** Modern AI programming environments (Barke et al., 2023; Ross et al., 2023; Copilot Workspace, Cursor) rely on indexing open tabs, git history, and AST trees. However, passive context indexing reflects past decisions (existing code) rather than uncommitted architectural design directions.
- **Open Tensions:** How should AI coding agents represent, reason about, and verify developer intent before providing guidance? What interaction mechanisms successfully capture uncommitted design intent without introducing excessive conversational friction?

### 3. Selective Mixed-Initiative Gating & Trust Calibration for LLMs (Human-AI Interaction / CHI / CSCW)
- **Core Tension:** When should an AI assistant actively interrupt user flow to verify its contextual assumptions versus when should it answer directly to maintain fluid interaction momentum?
- **What the field knows:** Mixed-initiative interaction heuristics (Horvitz, 1999) and AI trust calibration literature (Amershi et al., 2019; Lee & See, 2004) demonstrate that uncalibrated AI confidence leads to over-reliance when correct and swift abandonment when misaligned. Recent LLM studies (Vasconcelos et al., 2023; Passi & Vorvoreanu, 2022) confirm that conversational fluency masks context blindness.
- **Open Tensions:** Prior mixed-initiative models focus on GUI widgets or task execution rather than selective gating for conversational code scaffolding. The field lacks empirically tested heuristics for when to gate AI hints on user intent confirmation.

## Theory Recommendations

<!-- Four primary theoretical lenses that ground the problem, mechanism, interaction design, and learning outcomes of selective intent verification. -->

### 1. Wood's Contingency Principle of Instructional Scaffolding (Wood, Bruner, & Ross, 1976) — *For pedagogical hint generation*
- **Why this theory, specifically:** Explains why AI hints must be aligned with the developer's exact goal state. Contingency Theory predicts that tutoring scaffolding is effective *only when hints are continuously contingent on the learner's current understanding and intention*. When an agent generates hints without verifying intent, it violates the Contingency Principle and breaks the learning scaffold.
- **Key reference:** Wood, D., Bruner, J. S., & Ross, G. (1976). The role of tutoring in problem solving. *Journal of Child Psychology and Psychiatry*, 17(2), 89-100.
- **Alternative considered:** Direct Instruction Theory — Rejected because direct code synthesis strips away developer agency and fails to support architectural learning.

### 2. Extraneous Cognitive Load Theory (Sweller, 1988) — *For evaluating the cost of misaligned AI guidance*
- **Why this theory, specifically:** Predicts the negative cost of context blindness: evaluating plausible-in-isolation but context-misaligned AI hints imposes extraneous cognitive load on students, forcing them to spend mental energy deciphering whether the AI's advice fits their architecture rather than solving the programming task.
- **Key reference:** Sweller, J. (1988). Cognitive load during problem solving: Effects on learning. *Cognitive Science*, 12(2), 257-285.
- **Alternative considered:** Cognitive Flexibility Theory — Secondary, but Cognitive Load Theory offers a more direct metric for diagnostic friction and evaluation overhead.

### 3. Principles for Mixed-Initiative Interaction (Horvitz, 1999) — *For selective intent-verification gating*
- **Why this theory, specifically:** Provides explicit design heuristics for interaction timing: an automated system should query the user to resolve context ambiguity when uncertainty is high, but act autonomously when costs of interruption outweigh context risks.
- **Key reference:** Horvitz, E. (1999). Principles of mixed-initiative user interfaces. In *Proceedings of the SIGCHI Conference on Human Factors in Computing Systems* (CHI '99), pp. 159-166.

### 4. Metacognitive Monitoring & Self-Regulation (Flavell, 1979) — *For promoting active architectural reflection*
- **Why this theory, specifically:** Predicts the positive learning outcome: when the agent surfaces its goal interpretation, it prompts the student to engage in metacognitive monitoring—actively reflecting on, articulating, and refining their own architectural design intentions.
- **Key reference:** Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American Psychologist*, 34(10), 906-911.

**How the theories work together:** The four theories form a coherent 4-step chain:
1. *Problem:* Extraneous Cognitive Load Theory explains why misaligned AI hints waste student mental effort.
2. *Mechanism:* Contingency Scaffolding predicts that hints must be contingent on verified developer intent to support learning.
3. *Interaction:* Mixed-Initiative Principles dictate *when* the agent should selectively interrupt execution to verify intent.
4. *Outcome:* Metacognitive Monitoring explains how intent verification prompts students to actively reflect on their architectural decisions.

### Theories to explore further
- **Communities of Practice & Legitimate Peripheral Participation (Lave & Wenger, 1991):** To explore how intent-calibrated agents support student onboarding into lab software architectures.
- **Sensemaking Framework (Dervin, 1998; Russell et al., 1993):** To model the cognitive steps students take when resolving discrepancies between AI hints and project goals.

## Gaps & Opportunities

**How the research threads converge:** Thread 1 (Computing Pedagogy) demonstrates that scaffolding hints are superior to code synthesis for learning, but rely heavily on hint relevance. Thread 2 (HCI/SE) establishes that passive codebase indexing fails to capture uncommitted developer intent. Thread 3 (Human-AI Interaction) shows that uncalibrated AI confidence creates cognitive friction. Together, they reveal an unaddressed intersection: pedagogical agents providing context-blind hints because they lack a mechanism to verify architectural intent.

**The overarching gap:** Prior work in AI coding tools has focused either on improving passive codebase retrieval (indexing more files) or designing conversational tutoring prompts. The field lacks understanding of how interactive agents can selectively represent, state, and verify developer intent before generating scaffolding hints—and whether such selective verification improves guidance applicability without destroying interaction momentum.

### Gap 1: The Architectural Intent-and-Context Alignment Gap in Pedagogical Agents (from Threads 1 & 2)
- **The gap:** The field lacks understanding of how developers evaluate and respond to AI scaffolding hints when the agent's contextual assumptions diverge from their uncommitted architectural intentions—and whether a brief goal-verification interaction reduces diagnostic cognitive load compared to manual hint filtering.
- **Why this project fills it:** Tech4Good research lab deployments provide direct access to student developers working on non-trivial web architectures using hint-based agents.
- **Design knowledge generated:** Empirical principles for how agents can represent and verify developer architectural goals before generating hints to minimize extraneous cognitive load.
- **How we'd observe this:** Comparing hint applicability rates, context-correction frequencies, and student override behavior across intent-verified vs unverified scaffolding interactions.

### Gap 2: Selective Gating Heuristics for Human-AI Intent Verification (from Threads 2 & 3)
- **The gap:** The field does not know whether lightweight, task-type heuristics can selectively gate intent verification on architectural queries without creating unacceptable conversational friction on routine syntax queries.
- **Why this project fills it:** We test lightweight, conditional assumption-checking triggers specifically tuned for architectural, state management, and component-relationship queries in live student workflows.
- **Design knowledge generated:** A validated taxonomy of query types that require intent-verification gating vs those that demand direct execution.
- **How we'd observe this:** Tracking: (1) trigger frequency per query type, (2) student confirmation vs correction rates, and (3) qualitative feedback on perceived conversational momentum.

## Knowledge Contribution Framing

*Note: The statements below are contribution hypotheses — framed as the potential claims we believe the eventual paper will be able to make, based on the gaps identified above. They will be refined or revised once deployment data confirms or challenges them.*

- **Knowledge Contribution (one sentence):** This work demonstrates that in pedagogical AI coding tools, hint applicability for architectural tasks depends not on expanding passive codebase retrieval (ASTs/RAG), but on selectively gating hints through active, lightweight intent verification prior to hint generation.
- **Product Value vs. Research Contribution:** Product value is a smoother, less frustrating scaffolding experience for student developers; research contribution is a generalizable model and interaction mechanism for how AI agents can selectively verify developer intent before providing guidance.
- **Bit Flip:** Most AI coding research assumes context mismatch is a retrieval problem (solved by parsing more files and ASTs); our work demonstrates that it is an intent-alignment problem (solved by selective pre-generation goal verification on architectural queries).
- **Novelty Defense:** Reviewers may argue that "asking clarifying questions is standard LLM prompting." We counter that: (1) commercial tools use preambles as persuasive post-hoc explanations rather than blocking pre-generation gates; (2) existing work does not provide selective triggering heuristics for *when* verification adds value vs friction; and (3) prior systems evaluate code completion speed rather than pedagogical hint applicability.
- **Paper Type:** HCI Systems & Design Research Paper (combining a lightweight interaction mechanism with ecologically valid deployment evaluation in a research lab setting).
- **Target Venue:** ACM CHI (Human Factors in Computing Systems) or ACM COMPASS / ICER (International Computing Education Research).
- **Audience:** HCI researchers studying human-AI collaboration, computing education researchers studying LLM scaffolding, and software engineering researchers focused on AI-assisted development tools.

## Appendix: Research Landscape

### Research Threads

### Theory Recommendations

### Gaps & Opportunities

### Knowledge Contribution Framing
