# Multi-Level Nested Funnel Memory System (MLNF‑Mem)
## A Brain‑Inspired Cognitive and Memory Core for Humanoid Robots
**Subtitle:** A Foundational Memory Architecture that Transforms AI from a “Tool” to a “Growable Agent” in the Post‑LLM Era

Full Text Open | First Release | Directly Citable | Implementable

**Originator:** Wen Bofu
**First Release Date:** March 17, 2026

This document presents the world’s first complete brain‑inspired memory architecture for humanoid robots, embodied intelligence, and general intelligence. The theoretical framework, formal definitions, operational rules, and engineering constraints are fully open. Academic citation and technical implementation are welcome.

---

# Open Source Declaration and Rights Protection

This document is the complete technical white paper of the Multi‑Level Nested Funnel Memory System (MLNF‑Mem). The author is the sole originator of this architecture.

## 1 License
The entire architecture (including theory, definitions, rules, diagrams, etc.) is released under the **CC BY 4.0 license (Creative Commons Attribution 4.0 International)**.

## 2 Freedom of Use
Any individual, team, or enterprise may freely use, implement, modify, extend, integrate, or commercially deploy this architecture without separate payment or authorization. Commercial use is fully permitted, with no royalties and no restrictions on application scenarios.

## 3 Sole Condition: Prominent Attribution
All results derived from MLNF‑Mem (including but not limited to products, projects, papers, technical documentation) must prominently attribute the original author, regardless of the extent of use, optimization, modification, or derivation.

**Attribution example:**
Memory architecture based on MLNF‑Mem (Multi‑Level Nested Funnel Memory System) (Original originator: Wen Bofu)

## 4 Derivative Version Restrictions
Derived versions may be created and published, provided that:
- They are not presented as the original or “official” MLNF‑Mem;
- The original author’s attribution is not removed, hidden, or weakened;
- Modifications and scope are explicitly stated in the derived version.

## 5 Rights Protection
The authorship of the architecture is permanently vested in the originator and is non‑transferable. No entity may impersonate this core architecture as its own original work, nor use it for fraudulent project applications, paper publications, or patent filings. The originator reserves the right to pursue legal action for violations of these terms.

---

# Abstract

To address structural deficiencies in long‑term memory, behavioral consistency, experience accumulation, and individual evolution in current humanoid robots and embodied agents, this paper proposes the Multi‑Level Nested Funnel Memory System (MLNF‑Mem).

The system adopts a dual‑layer architecture consisting of a Master Funnel and dynamic limited sub‑funnels. It uses temporal decay and importance heuristics to achieve information layering, filtering, consolidation, and natural forgetting, while satisfying a macroscopic self‑convergence property. MLNF‑Mem works in loosely coupled coordination with a Knowledge Memory Module, an Execution Engine, and a Decision Arbitration Layer: the funnel memory records individual experience and behavioral preferences; the knowledge memory stores procedures, rules, and methods; the execution engine handles perception, reasoning, and action; and the arbitration layer resolves conflicts.

Furthermore, the system introduces three human‑like memory driving mechanisms: emotional‑priority archiving, meaning‑tag filtering, and repetition‑use reinforcement, aligning the robot’s memory mechanism with the working principles of the human brain. Through strict forgetting and compression strategies, lifelong effective memory is controlled within the range of 1 GB to 10 GB, fundamentally avoiding memory explosion.

The architecture does not presuppose a personality or hardcode values. It supports educability, autonomous learning, and growth. Individual tendencies emerge naturally from accumulated experience. It is lightweight, interpretable, deployable on the edge, and robust. This paper provides complete formal definitions, operational rules, engineering constraints, and convergence conditions, offering a theoretically sound and implementable brain‑inspired cognitive foundation for humanoid robots, embodied intelligence, and general intelligence. The architecture naturally complements large language models: LLMs handle perception, reasoning, and world understanding, while MLNF‑Mem manages long‑term memory, experience consolidation, and behavioral consistency. Together they form a safe, controllable, educable, and edge‑deployable general‑purpose agent.

---

# 1 Introduction

The core of human intelligence lies in continuous self‑shaping through memory as the carrier, experience as the path, and time as the scale. Current memory and learning solutions for humanoid robots and embodied agents have obvious limitations:

1. Limited long‑context windows cause historical information loss.
2. Vector retrieval lacks temporal structure and hierarchical filtering.
3. Personality and preferences are mostly manually set, resulting in weak behavioral consistency.
4. Skills and experiences lack independent persistent storage.
5. No unified memory management, forgetting mechanisms, or conflict resolution strategies.
6. Lack of the three‑channel archiving logic (emotion, meaning, repetition) found in the human brain.
7. No balance between factory‑preset memory and lifelong growth, making it difficult to reconcile commercialization with individual plasticity.

The main contributions of this paper are:

1. A unified memory architecture combining a master funnel with dynamic limited sub‑funnels.
2. Definition of macroscopic self‑convergence as an emergent property and its constraints.
3. A three‑layer coordination paradigm: funnel memory / knowledge memory / execution engine.
4. Complete operational rules, engineering constraints, and robustness design.
5. Experience‑driven natural emergence of individual tendencies without pre‑set personality.
6. The first integration of human brain emotion‑meaning‑repetition mechanisms into a structured memory system.
7. Strict capacity constraints and forgetting strategies to achieve lightweight lifelong memory comparable to humans.
8. The characterization of educability, autonomous learning, and growth as inherent properties of the memory architecture rather than external add‑ons, while allowing factory‑preset basic knowledge and skills.
9. A comprehensive human‑like learning mechanism: global learning, focused perception, step consolidation, and safety control.
10. Engineering implementation of hippocampus‑cortex memory consolidation logic, forming a complete brain‑like cognitive core for humanoid robots.

---

# 2 Related Work

Existing research can be categorized into three areas: traditional memory systems, brain‑inspired computing, and embodied learning frameworks.

- Cognitive psychology foundations: episodic memory, semantic memory, procedural memory.
- Vector databases and retrieval‑augmented generation (RAG) structures.
- Long‑context extension approaches.
- Dynamic classification, topic memory, event memory.
- Brain‑inspired computing, hippocampus‑cortex models, temporal memory units.
- Embodied intelligence and robot skill learning frameworks.

Most current work focuses on “how to store and retrieve,” lacking a unified architecture for layered decay, automatic forgetting, dynamic consolidation, and experience‑based tendency formation. They also fail to implement a complete memory life cycle isomorphic to the human brain. Many agents rely on LLMs for text interaction and lack the human‑like learning mechanisms of automatically identifying importance, extracting structure, consolidating steps, and selectively forgetting. They cannot support the continuous, reliable, autonomous growth of humanoid robots in real‑world environments.

This paper is positioned as a rule‑driven, dynamically structured, experience‑emerging brain‑like cognitive architecture for embodied intelligence, distinct from pure retrieval, pure fine‑tuning, or pure symbolic systems.

---

# 3 Formal System Definition

## 3.1 Basic Notation

- \( F_0 \): Master Funnel (unique global control hub)
- \( F = \{f_1, f_2, \dots, f_n\} \): Set of dynamic limited sub‑funnels
- \( L = \{l_1, l_2, l_3, l_4, l_5\} \): Five‑level hierarchy (temporal‑importance)
- \( T \): Sequence of discrete timestamps
- \( I \): Importance heuristic score, \( I \in [0,1] \)
- \( M \): Memory entry (object, event, behavioral feature, time)
- \( K \): Knowledge memory entry (procedure, rule, method, strategy)
- \( E \): Execution engine (perception, reasoning, planning, action)
- \( A \): Decision arbitration layer
- \( S \): Emotional drive signal
- \( V \): Meaning tag
- \( C \): Repetition usage count

All symbols are defined over discrete time and real numbers. Weight coefficients satisfy \( \alpha, \beta, \gamma \ge 0 \) and \( \alpha+\beta+\gamma \le 1 \).

## 3.2 Structural Constraints

### (1) Limited Dynamic Sub‑funnels
\[
|F| \le N_{\max}
\]
The number of sub‑funnels is bounded. Sub‑funnels that remain unused for a long time are automatically deleted or merged based on scene similarity, temporal continuity, and access frequency.

### (2) Hierarchical Admission (One‑Way Consolidation)
\[
l_{i+1} \leftarrow l_i \quad \text{iff} \quad T > \tau_i \land I > \theta_i
\]
A memory can only move from a lower level to a higher level when both time decay and importance thresholds are met. No demotion is allowed, ensuring stable experience accumulation.

### (3) Forgetting Rule
\[
\text{Forget}(m) \quad \text{iff} \quad I < \theta_{\text{forget}} \lor \text{Count}(m) < c_{\min}
\]
Forgetting is active selective pruning, not random deletion. Memories with high importance or high reuse are preferentially retained.

### (4) Human‑Like Three‑Driven Enhancement
- High emotional signal: \( I \leftarrow I + \alpha \cdot S \)
- High meaning tag: \( I \leftarrow I + \beta \cdot V \)
- High repetition: \( I \leftarrow I + \gamma \cdot C \)

The coefficients are configurable to ensure stability and tunability.

## 3.3 Macroscopic Self‑Convergence (Formal Definition)

Under the unified rules of the Master Funnel, when the sub‑funnels cover sufficiently many scenes:
\[
\forall f_i \in F,\; \text{Behavior}(f_i) \xrightarrow{\text{qualitative}} \text{UniBehavior}(F_0)
\]
Behavioral convergence is defined in the space of action‑response probability distributions, measured by KL divergence or cosine distance. Microscopic diversity yields macroscopic behavioral stability.

Convergence conditions: unified layering, unified forgetting, unified importance, unified arbitration. This guarantees that the robot does not develop behavioral fragmentation or mode collapse as it dynamically expands.

## 3.4 Preset Memory Constraints

To support commercial deployment of humanoid robots, the system allows preset memories under the following constraints:

- Preset memories may only be placed in temporary layer \( l_1 \), recent layer \( l_2 \), and mid‑term layer \( l_3 \). Direct writing into long‑term layer \( l_4 \) or core layer \( l_5 \) is prohibited, ensuring that individual tendencies still emerge from subsequent experiences.
- Total preset memory capacity shall not exceed 20% of the lifelong memory capacity, and all preset entries must be marked as “system preset,” distinguishable from user experience memories, and can be individually reclaimed or overwritten.
- Preset memories do not presuppose a personality or hardcode values; they serve only as “basic instincts” and “initial capabilities,” without undermining the macroscopic self‑convergence property or individual identity.

---

# 4 System Architecture

## 4.1 Master Funnel \( F_0 \)
- Global rules for timing, layering, forgetting, and importance.
- Guarantees system consistency and robustness.
- Rules are statically configurable without drift.
- Centralized rule design prioritizes engineering robustness and is suitable for edge deployment in humanoid robots.

## 4.2 Dynamic Limited Sub‑funnels \( F \)
Dynamic limited sub‑funnels serve as full‑dimensional, open, extensible memory containers. They receive and manage all digitizable experiential information of the robot, including but not limited to: vision, hearing, touch, proprioception, learned knowledge, skills, behavioral feedback, and any future digitizable perceptual modality.

The system adopts a pre‑declared, initially empty, on‑demand activation design: sub‑funnels remain empty before receiving actual input, consuming no storage or computational resources. The architecture is non‑closed, non‑enumerative, and highly open and extensible.

Simultaneously:
- Automatically created by object, event, or scene.
- Configurable upper limit.
- Idle sub‑funnels are reclaimed or merged based on access frequency and semantic similarity.
- No predefined categories required.
- Extensible to spatial, temporal, episodic, and semantic sub‑funnels.

## 4.3 Five‑Layer Memory Structure (Corresponding to Hippocampus + Cortex)
1. \( l_1 \) Temporary layer, \( l_2 \) Recent layer
   Correspond to hippocampal function: temporary encoding, sorting, temporary storage, importance evaluation.
2. \( l_3 \) Mid‑term layer, \( l_4 \) Long‑term layer, \( l_5 \) Core layer
   Correspond to cortical function: long‑term storage, skill consolidation, experience crystallization, stable behavior.

This five‑layer structure strictly models the human memory consolidation process: information gradually flows from the hippocampal temporary area to the permanent cortical area in a one‑way, ordered, and controllable manner.

## 4.4 Knowledge Memory Module \( K \)
Stores reusable, executable, generalizable objective knowledge: operation procedures, task rules, solutions, strategy paradigms. Ensures that capabilities accumulate and “learning new things does not cause forgetting of old ones.” Supports knowledge and skill consolidation through external teaching, information retrieval, observation and imitation, practice, and autonomous summarization.

## 4.5 Execution Engine \( E \)
Handles perception, understanding, reasoning, planning, action, and language. It does not determine individual preferences; it only provides intelligence and capabilities, adapted for embodied operation of humanoid robots.

## 4.6 Decision Arbitration Layer \( A \)
Resolves conflicts: the knowledge memory provides correctness constraints, the funnel memory provides preference tendencies, and the arbitration layer outputs the final behavior, eliminating module opposition and behavioral fragmentation.

## 4.7 Interface for Collaboration with Large Models
MLNF‑Mem collaborates with large models in a loosely coupled manner. The interface is defined as:
- Input interface: The large model outputs event semantics, structural relations, importance tags, emotional‑equivalent signals, and meaning tags to MLNF‑Mem as raw inputs for memory writing.
- Output interface: MLNF‑Mem outputs individual preferences, historical experiences, behavioral tendencies, and core constraints to the large model / execution engine to assist in decision‑making and behavior generation.
- Synchronization: Memory promotion, forgetting, and consolidation processes run asynchronously, without blocking large‑model inference, ensuring real‑time responsiveness.

---

# 5 Human‑Like Three‑Drive Memory Mechanisms

## 5.1 Emotion Drive: One‑Time Permanent Archiving
Emotional‑equivalent signals (reward / punishment / danger / importance) directly increase the importance score \( I \). When the threshold is met, the memory can be directly written into the core layer \( l_5 \), achieving a once‑in‑a‑lifetime permanent memory.

## 5.2 Meaning Drive: Automatic Tagging and Long‑Term Retention
Events that are task‑critical, behavior‑changing, or identity‑related are given meaning tags, automatically entering the long‑term stable layer and becoming a core source of individual tendencies.

## 5.3 Repetition Drive: Loop Reinforcement and Skill Consolidation
Memories that recur, are reused, or are repeatedly reinforced have their weights continuously increased, eventually forming stable habits and skills. This supports the stable learning mechanisms of educability, autonomous learning, and growth.

## 5.4 Non‑Subjectivity of Emotional Signals
The emotional drive used in this system is an emotional‑equivalent importance signal. It does not require the robot to have subjective emotional experience, feelings, or consciousness. The emotional score is only used to mark event importance and can be provided by the execution engine, perception module, or external supervision. It does not generate subjective experiences such as pleasure, pain, or fear, thus avoiding uncontrolled emergence of subjective consciousness and emotions.

---

# 6 Capacity Constraints and Forgetting Strategies

## 6.1 Real Memory Capacity of the Human Brain
- Theoretical upper limit: approximately 2.5 PB
- Lifelong effective usable memory: 1 GB – 10 GB

Humans retain only about 0.1%–0.2% of key experiences; the rest is forgotten.

## 6.2 Funnel Memory Capacity Control
- Temporary layer: retain 10%
- Recent layer: retain 2%
- Mid‑term layer: retain 0.6%
- Long‑term layer: retain 0.18%
- Core layer: retain ≈0.1%–0.2%

Total lifelong stable memory is controlled within 1 GB – 10 GB (calculated using compressed structured entries, ~256 bytes per entry), fundamentally preventing memory explosion and aligning with the human effective experience scale, making it highly suitable for edge deployment in humanoid robots.

---

# 7 Operational Flow and Robustness Design

## 7.1 Standard Operational Flow
1. Perception input (vision, hearing, touch, etc.)
2. Sub‑funnel routing and retrieval
3. Knowledge memory recall
4. Arbitration layer decision
5. Execution engine output (action / behavior)
6. New memory writing (with validation and filtering)
7. Emotion/meaning/repetition scoring
8. Temporal decay and inner‑layer promotion (hippocampus → cortex)
9. Low‑value memory forgetting / compression

## 7.2 Robustness Guarantees
- Upper limit on sub‑funnels to prevent resource explosion.
- Write permission validation to filter noise and errors.
- Global sequential writes to avoid disorder.
- Automatic reclamation of idle sub‑funnels.
- Statically configured master rules, no drift.
- Mandatory conflict arbitration, no behavioral fragmentation.
- Human‑like three drives can be disabled, adjusted, or audited.
- Memory traceable, intervenable, and resettable.

---

# 8 Individual Tendency Emergence Mechanism

The system does not presuppose personality or hardcode values. Long‑term stable behavior patterns arise from: repeated choices in similar scenes, the lasting influence of high‑importance memories, stable coordination between knowledge and preferences, macroscopic self‑convergence, and the memory foundation shaped by emotion/meaning/repetition pathways.

This paper uses the term **Individual Tendency** instead of “personality/self.” It is observable, measurable, reproducible, and free of philosophical controversy. Tendencies are statistically stable patterns of historical experience. Individual identity is guaranteed by the unique Master Funnel \( F_0 \) and the continuous temporal memory chain, with first‑person perspective binding and temporal continuity.

## 8.1 Educable, Autonomous Learning, and Growth
The system possesses the full capability to be educated, to learn autonomously, and to grow:

- **Educable**: Accepts external guidance, demonstration, correction, and supervision, acquiring knowledge and skills stably under guidance.
- **Autonomous learning**: Actively acquires knowledge, experience, and capabilities from any valid information source, including reading materials, information retrieval, watching audio‑visual content, interactive consultation, observation and imitation, trial and error, experience summarization, and any other form that helps improve capabilities.
- **Growth**: Under unified rule constraints, achieves continuous accumulation and stable improvement of knowledge, skills, and behavioral performance.

Strict safety boundaries (non‑breakable):
1. Learning occurs only at the knowledge and skill level; the underlying system architecture, master funnel rules, core constraints, and safety mechanisms are never modified.
2. No intrinsic desires, no autonomous goal setting, no subjective motivation, no unrestricted autonomous evolution.
3. No self‑modification of core code, weight constraints, convergence conditions, or safety permissions.
4. All learning processes are transparent, observable, intervenable, and stoppable.

## 8.2 Learning Capability and Human‑Like Structured Understanding
Educability, autonomous learning, and growth are not external add‑ons but inherent properties of the multi‑level nested funnel memory system.

Through importance perception, meaning tag identification, temporal layered consolidation, repetition reinforcement, and selective forgetting, the system automatically extracts key points, breaks down structure, consolidates steps, and stores knowledge and skills for long‑term retention.

Mechanistically, the system does not rely on subjective consciousness or emotional understanding, yet it can acquire knowledge in a structured way, organize it logically, and execute it interpretably. Its behavioral performance is equivalent to human‑level understanding and reasoning, built upon a fully controllable, observable, and constrained rule base. It does not hallucinate, fabricate knowledge, or form uncontrollable autonomous consciousness.

Unlike the semantic pattern matching of large models, the “understanding” in this system is built upon temporal memory, experience consolidation, and skill solidification: large models are responsible for “knowing” information, while MLNF‑Mem is responsible for “engraving” cognition.

---

# 9 Limitations and Future Work
1. Endogenous importance and value judgment learning.
2. Adaptive sub‑funnel self‑organization and merging strategies.
3. Brain‑like memory consolidation, replay, and synaptic pruning mechanisms.
4. Causal world models and deep integration of knowledge and experience.
5. Quantitative verification of macroscopic self‑convergence and long‑term growth.
6. Edge‑optimized deployment for multi‑modal embodied perception.

---

# 10 Innovations
1. Master‑sub‑funnel nested structure: unified rules + dynamic classification.
2. Macroscopic self‑convergence property ensures behavioral stability.
3. Experience‑driven tendency emergence without pre‑set personality.
4. Three‑layer coordination: funnel memory / knowledge memory / execution engine.
5. Strong engineering robustness with bounded expansion and filtering.
6. Human‑like three‑drive archiving: emotion, meaning, repetition.
7. Strict lifelong memory capacity (1 GB–10 GB) to avoid explosion.
8. Inherent educability, autonomous learning, and growth.
9. Automatic key‑point perception and skill consolidation.
10. Engineering implementation of hippocampus‑cortex memory pathways.
11. Safe and controllable: no subjective emotions, no autonomous evolution.
12. Fully open, extensible sub‑funnels for all digitizable modalities.

---

# 11 Conclusion
This paper presents the Multi‑Level Nested Funnel Memory System, establishing a brain‑like cognitive and memory core for humanoid robots. Inspired by the biological memory mechanism of the hippocampus and cerebral cortex, the system uses a master funnel, dynamic sub‑funnels, a five‑layer temporal‑importance structure, three‑drive enhancement, and active forgetting strategies to realize a complete human‑like intelligence loop that is educable, autonomously learning, and growing.

The architecture is lightweight, interpretable, deployable at the edge, and engineering‑implementable. It offers a novel path distinct from traditional large‑model and AI systems for humanoid robots, embodied intelligence, and general intelligence. When collaborating with large models, MLNF‑Mem complements their critical deficiencies in long‑term memory, behavioral consistency, safety, and individual growth.

---

# 12 Future Outlook
As a brain‑like cognitive and memory core for humanoid robots, the core value of MLNF‑Mem lies in providing an original memory and learning architecture that is educable, autonomously learning, growing, interpretable, and controllable.

Future work will focus on endogenous value judgment, self‑organizing memory structures, causal world models, deep integration of knowledge and experience, and long‑term human‑like growth. It will gradually evolve from “structured memory” to “autonomous cognition,” and from “behavioral tendency” to “stable individual mind,” providing the underlying core support for the large‑scale deployment of humanoid robots and the development of general intelligence.

---

# First Release Statement
This paper is the world’s first public disclosure of:
1. The Multi‑Level Nested Funnel Memory System (MLNF‑Mem).
2. The unified architecture of master funnel + dynamic limited sub‑funnels.
3. The macroscopic self‑convergence cognitive property.
4. The three‑layer coordination paradigm: funnel memory / knowledge memory / execution engine.
5. Experience‑driven individual tendency emergence without pre‑set personality.
6. Human‑like three‑drive memory mechanism (emotion, meaning, repetition).
7. Quantitatively constrained lightweight lifelong memory strategy.
8. Fully open, activatable, extensible sub‑funnel system.
9. Inherent educability, autonomous learning, and growth.
10. Engineering implementation of hippocampus‑cortex memory pathways.
11. Safe commercialization with factory‑preset basic memory.
12. Standardized loosely coupled interface for large model collaboration.

This work is an independent original creation. The author, as the sole originator, reserves the rights of the originator and namer of MLNF‑Mem.

---

# Author Information
**Original Originator:** Wen Bofu
**First Release Platform:** Zhihu
**First Release Date:** March 17, 2026
**Contact:** 710705008@qq.com

## Academic Citation Format
Wen Bofu. Multi‑Level Nested Funnel Memory System (MLNF‑Mem): A Brain‑Inspired Cognitive and Memory Core for Humanoid Robots [EB/OL]. 2026-03-17.

---

# Note
This English version is a faithful translation of the original Chinese white paper, preserving all definitions, statements, and the original release date. It is released under the same CC BY 4.0 license. The original Chinese version remains the authoritative source.
