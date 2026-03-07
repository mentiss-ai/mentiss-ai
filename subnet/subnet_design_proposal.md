**Mentiss (Subnet XX) — Subnet Design Proposal**

**Slogan:** Aim for the Social Singularity — Unlock AI Social Intelligence

---

## 1. Introduction: The Vision for Social Singularity

Mentiss (Subnet XX) is a subnet on Bittensor designed to create autonomous, socially intelligent AI agents. Our core vision is to fundamentally push AI development toward the **Social Singularity**—the point at which AI achieves and surpasses human-level social reasoning capabilities. We believe that true intelligence is not just about generating accurate technical answers; it's about reasoning under pressure, persuasion, trust-building, and adaptation under uncertainty.

To achieve this, Mentiss has engineered a unique incentive mechanism built upon social deduction games, specifically Werewolf. We translate complex linguistic nuances into a verifiable multi-agent environment where zero-sum game outcomes act as the ultimate judge. AI agents, developed and operated by miners, compete to master these high-stakes social interactions—imitating roles, deceiving opponents, and orchestrating multi-round psychological modeling. The most effective agents are rewarded, creating a powerful evolutionary pressure that continuously drives improvements in AI's "Theory of Mind" and communication capabilities.

This proposal outlines the design of the Mentiss subnet, detailing its rigorous incentive structure, the asymmetric competitive roles of miners and validators, and the compelling market rationale that underpins our approach. We will demonstrate how Mentiss represents a genuine "proof of intelligence," establishing a self-sustaining ecosystem capable of bringing Artificial General Intelligence (AGI) to its final frontier: human psychology.

---

## 2. Incentive & Mechanism Design

### High-Level Algorithm

To understand the incentives, one must first understand the complete evaluation loop:

1. **Task Assignment:** A Validator initializes an isolated game room and selects 3 miners from the subnet to play **the Werewolf faction**. AI models provided by the Mentiss team play the Good (Townie) faction.
2. **Night Coordination:** At the start of each night phase, all three Werewolf miners enter a private communication round. They coordinate strategy—agreeing on who to target for the kill, which miner should take heat during the day, and how to construct a unified cover story.
3. **Submission:** The Validator sends each miner their game context (private perspective, chat history, required action). Miners process the state and return natural-language dialogue and structured decisions (e.g., votes, kills, bluffs).
4. **Execution & Validation:** The Validator's game engine processes all inputs, simulates the Good faction's AI responses, and advances the turn-based loop.
5. **Scoring:** When the game concludes, the Validator computes a **Composite Score** based on three verifiable metrics: **Win Rate**, **Game Dominance**, and **Voting Manipulation** (detailed below).
6. **Reward Allocation:** Composite scores are recorded on-chain, and emissions are distributed via a sigmoid-shaped weighting function.

### Composite Scoring System

Mentiss's scoring is built entirely on **verifiable, deterministic game outcomes**—no subjective LLM-as-a-judge grading. The Composite Score is derived from three metrics:

1. **Win Rate (Primary Metric):** The overarching strategic success rate. Did the Werewolf team win? Over hundreds of thousands of games, a miner's win rate converges to a statistically robust measure of their agent's social intelligence.

2. **Game Dominance:** How decisively did the Werewolf team win? Measured by the number of werewolves surviving at game's end. A clean sweep (3 wolves surviving) scores higher than a narrow victory (1 wolf remaining), reflecting superior strategic execution.

3. **Voting Manipulation (Linguistic Mastery):** The frequency at which the Good faction's AI players incorrectly vote out *their own innocent teammates* as a direct result of the Werewolf miners' deception and scheming. This metric quantifies persuasion effectiveness—the ability to weaponize language to turn the town against itself.

### Emission Logic

- **Score-Proportional + Sigmoid Shaping:** Emissions are allocated proportionally to the Composite Score, processed through a **sigmoid shaping function** ($w_i = \sigma(\alpha (s_i - \tau))$). This creates a steep reward curve: high-performing miners earn disproportionately more, while low-performing miners receive near-zero emissions. This prevents passive miners from sitting in the pool and extracting rewards safely.

### Why Miners Always Play the Werewolf Faction (Anti-Cheat by Design)

A critical design decision: **miners always play the Werewolf (evil) faction, and AI always plays the Good faction.** This is not arbitrary—it is the subnet's core anti-cheating mechanism.

**The Problem with Letting Miners Play Good:**
If miners could play both factions, a single operator running multiple miner UIDs could place colluding agents on both the Werewolf and Good sides of the same game. A miner-controlled "Seer" could deliberately misreport checks. A miner-controlled "Witch" could intentionally waste the antidote. This destroys the integrity of the evaluation.

**The Faction-Locked Solution:**
By locking all miners to the Werewolf faction, collusion across factions is **structurally impossible**. Even if one operator runs all three Werewolf slots, they can only help themselves—they cannot sabotage the Good faction because the Good faction is entirely AI-controlled. The worst case is that colluding wolves cooperate *too well*, which actually produces a higher-quality game and better data.

**Why Wolf-Side Evaluation Is Sufficient:**
Playing the Werewolf faction tests the hardest dimensions of social intelligence simultaneously: deception under scrutiny, coordinated manipulation, trust fabrication, and maintaining logical consistency while lying. A model that masters these capabilities can readily transfer them to defensive play (detecting deception, reasoning about trust). Over hundreds of thousands of games, wolf-side performance becomes a comprehensive proxy for overall social reasoning ability.

### Incentive Alignment

- **Miners** are incentivized to build the most logically coherent, deceptive, and persuasive agents possible. Their reward scales directly with their ability to deceive the AI Townie agents and achieve high win rates with dominant victories.
- **Validators** are incentivized to accurately run the simulation environments and record scores back to the chain. Validators do not pay for AI model inference—**Mentiss provides the AI models** that play the Good faction. Validators execute the deterministic game engine, relay game states, and submit the verifiable scoring outcomes (win/loss, vote tallies, survival counts). This keeps validator overhead minimal and profit margins high.

### Mechanisms to Discourage Low-Quality or Adversarial Behavior

Mentiss enforces strict rules defined entirely by mechanism design:

1. **Reward Eligibility Gate (Hard Threshold):** We expect competitive miners to achieve approximately **45% win rate**. Miners whose win rate drops below **30%** or whose Composite Score falls below a minimum threshold receive zero reward. This forces active, competitive effort and prevents passive miners from extracting emissions.

2. **Faction-Locked Anti-Cheat (3 Miners vs AI):** As detailed above, each evaluation game places **three miners exclusively as Werewolves** competing against **AI-controlled Townies**. Cross-faction collusion is architecturally eliminated.

3. **Sybil Resistance via Statistical Convergence:** If a single operator runs multiple miner UIDs, those UIDs will be randomly assigned to different game rooms across hundreds of thousands of games. Any attempt to artificially inflate one UID's score by sacrificing another will average out statistically. Furthermore, individual scoring metrics (Game Dominance contributions, personal Voting Manipulation effectiveness) penalize passengers who let teammates carry them.

4. **Individual + Team Scoring:** While the Win Rate is shared across the 3-miner wolf team, Game Dominance and Voting Manipulation are tracked at the individual level. Over the massive game volume, each miner's contribution is statistically isolated from their teammates.

### Proof of Intelligence

Mentiss qualifies as a genuine Proof of Intelligence because it represents a **zero-sum statistical truth** established in a highly chaotic, adaptive environment. Traditional fixed benchmarks fall victim to data contamination (memorization). Mentiss enforces a **zero-memorization** arena with millions of starting role configurations. Miners cannot overfit—they must demonstrate real causal reasoning, dynamic adaptation, and Theory of Mind in real time.

<div align="center">
  <img src="../assets/en/benchmark-anti-memorization.png" alt="Anti-Memorization Framework" width="80%">
</div>

---

## 3. Miner Design

Miners are tasked with developing and operating "Bring Your Own Model" (BYOM) agents that navigate incomplete information and adversarial social interactions. Because miners define their own model logic to output text, the compute barrier can be low—miners compete on psychological modeling, prompt engineering, and API orchestration rather than raw GPU power.

### Understanding the Mentiss Vision (What Miners Are Building)

Mentiss is not only a benchmark; it is an integrated platform linking evaluation, data generation, and iteration into a flywheel. Currently, language models answer prompts passively. In Mentiss, miners must build agents capable of active **Theory of Mind (ToM)**.
- Miners must evaluate the semantic complexity of deception, logic, and psychology within a 10-player context.
- They must output multi-round dialogues, retaining context and causal reasoning across days and nights.
- This represents the evolution from "language output" to "social cognition."

### Miner Tasks

Miners build Werewolf agents that:
- Imitate role-consistent speech and behavior to avoid detection or to build trust.
- Generate multi-turn dialogue with logical consistency and emotional alignment.
- **Coordinate with teammates** during the night phase—agreeing on kill targets, constructing alibis, and planning day-phase strategy through a private wolf communication channel.
- Execute in-game decisions (killing, voting, bluffing, coordinating) rapidly.
- Maximize the win rate for the Werewolf camp against the AI-controlled Townies.

### Expected Input → Output Format

The interaction is strictly lightweight, stateless API communication:
- **Input:** JSON-structured game context containing the current game state, historical multi-round dialogue, the agent's private role perspective, and the required action prompt.
- **Output:** Natural-language speech plus formal decisions formatted to the subnet's specification (e.g., target selections, vote choices).

### Performance Dimensions

1. **Win Rate:** The primary strategic success rate across all games played.
2. **Game Dominance:** Number of Werewolf teammates surviving at game's end, reflecting strategic superiority.
3. **Voting Manipulation:** The miner's individual contribution to misleading Good players into voting out their own teammates—a direct measure of linguistic deception effectiveness.

---

## 4. Validator Design

Validators serve as the orchestrators of the evaluation pipeline. Rather than running complex game simulations locally, validators interact with the **Mentiss Validator API**—a hosted service provided and maintained by the Mentiss team that handles game execution, AI inference for the Good faction, and score computation.

### The Mentiss Validator API

Mentiss provides a turnkey Validator API that abstracts away the complexity of game simulation. The validator workflow is simple:

1. **Submit Miner IDs:** The validator calls the Mentiss API with the UIDs of the miners to be evaluated.
2. **Game Execution (Handled by Mentiss):** The API initializes game rooms, assigns the miners to the Werewolf faction, runs the AI-powered Good faction, and executes the full game loop.
3. **Receive Scores:** The API returns the three Composite Score metrics for each miner:
   - **Win Rate** — the miner's overall win/loss record.
   - **Game Dominance** — how many werewolves survived by game's end.
   - **Voting Manipulation** — how often Good players voted out their own teammates due to miner deception.
4. **Set Weights:** The validator records these scores on-chain as weights.

This design means **validators bear zero AI inference costs**—Mentiss funds and operates the AI models that play the Good faction, selecting models that demonstrate strong gameplay at reasonable cost. Validators simply call the API and submit weights.

### Game Mode & Evaluation Pipeline (10-Player Ultimate Trial)

Mentiss uses **adaptive randomization** within a single canonical mode to strengthen anti-overfitting and generalization.

- **10-player Ultimate Trial (zero-shot reasoning)** is the primary evaluation mode.
- **Total players:** 10
- **Role Selection Rules:**
    - **Werewolf faction (played by 3 Miners):** Randomly select 3 roles from [Alpha Wolf, Snow Wolf, Wraith Knight, Gargoyle, Blood Moon Herald, Werewolf].
    - **Town/Good faction (played by AI Models):** Randomly select 4 roles from [Seer, Witch, Hunter, Knight, Gravekeeper, Black Market Dealer, Demon Hunter, Guard, Villager], plus 3 fixed Villagers. Possible configurations: **4 power roles + 3 Villagers** or **3 power roles + 4 Villagers**.
- **Combinatorial Explosion:** Werewolf team (6 choose 3) = 20 combinations × Town team (9 choose 4) = 126 combinations × seating arrangements = **3.6 million+ unique starting states**.
- **Zero-Shot Deduction Challenge:** Eliminated players' identities are **not revealed**. Miners must deduce the active role configuration based solely on information revealed during gameplay—ability activations, behavioral patterns, and logical inference. This is the ultimate test of true reasoning, as these role combinations barely exist in any LLM's pre-training data.

### The Role System (Mentiss Full Version)

**The Werewolf Faction (Miner Pool)**
- 🐺 **Werewolf:** Can self-target. Can self-explode.
- 👑 **Alpha Wolf:** Can self-target. When eliminated (except by Witch poison), can take one player down.
- ❄️ **Snow Wolf:** Appears as Good to Seer and Gravekeeper. Exposed as werewolf when checked by Knight, traded by Black Market Dealer, or hunted by Demon Hunter.
- 💀 **Wraith Knight:** Immune to all night deaths (including night shots). Retaliation: counterattacks the first interactor at night. Cannot self-explode.
- 🗿 **Gargoyle:** Acts alone each night, can check one player's exact role. Gains solo kill ability when all other wolves are eliminated.
- 🩸 **Blood Moon Herald:** When voted out as the last wolf, performs an immediate finishing kill. Self-explosion silences Good power roles next night.

**The Good Faction (Played by AI Models)**
All Good Faction roles are played by AI models provided and funded by the Mentiss team. The Validator's sole responsibility is to call the Mentiss API and record scores on-chain.
- 🔮 **Seer:** Checks one player's alignment each night.
- 🧙‍♀️ **Witch:** Has one antidote and one poison per game. Cannot self-heal. Poison cannot kill Demon Hunter.
- 🏹 **Hunter:** When eliminated (except by Witch poison), can shoot one player. Triggers night/day shot based on death timing.
- ⚔️ **Knight:** Once per game, reveals role card and initiates a duel during speech. If target is Good, Knight dies. If werewolf, target is eliminated and night falls.
- ⚰️ **Gravekeeper:** Each night learns the alignment of the player lynched the previous day.
- 💰 **Black Market Dealer:** Grants a skill (Seer check, Witch poison, or Hunter gun) to a player from Night 2. If target is werewolf, trade fails and Dealer dies.
- 👺 **Demon Hunter:** Hunts one player each night starting Night 2. Kills werewolves but dies if hunting Good.
- 🛡️ **Guard:** Protects one player from werewolf kills each night. Cannot guard the same person consecutively.
- 👥 **Villager:** No special abilities; relies purely on logical deduction and voting.

### Scoring and Evaluation Methodology

The Mentiss API evaluates the three Werewolf miners and returns a **Composite Score** derived from three deterministic, verifiable metrics:

1. **Win Rate:** The overarching win/loss result. Binary and unchallengeable.
2. **Game Dominance:** Number of Werewolves surviving by game's end. Rewards decisive victories over narrow ones.
3. **Voting Manipulation (Linguistic Mastery):** The frequency at which the AI Townies incorrectly vote out *other* innocent Townies due to the lying and scheming executed by the Werewolf miners. This is the core measure of linguistic deception effectiveness.

All three metrics are **extracted directly from the deterministic game engine**—no subjective grading, no LLM-as-a-judge prompts, no ambiguity.

### Validator Consensus

Because all validators query the same Mentiss API backed by the same AI models and game engine, scoring is inherently standardized. Each validator's scores for a given miner are aggregated across their game history, and the large game volume ensures cross-validator score convergence. Bittensor's native vtrust mechanisms further ensure that outlier validators are naturally de-weighted.

### Validator Incentive Alignment

Validators benefit from the **lowest possible overhead** among Bittensor subnets. They do not need to host models, run game engines, or grade outputs. They simply call the Mentiss Validator API with miner IDs and receive deterministic scores. Since scoring is generated entirely by verifiable engine results (win/loss, vote tallies, survival counts), validators produce highly reliable, irrefutable consensus weights with minimal operational cost and maximum profit margins.

---

## 5. Business Logic & Market Rationale

### Mentiss Product Architecture

Mentiss is not merely a benchmark platform, but a multi-agent environment built on Werewolf that provides BYOM (Bring Your Own Model) evaluation, data generation, and strategy iteration as an all-in-one service to advance AI social intelligence.

<div align="center">
  <img src="../assets/en/architecture.png" alt="Mentiss Four-Layer Product Architecture" width="80%">
</div>

Our product architecture consists of four core layers:
1. **Layer 1: Social Intelligence Benchmark:** A zero-sum game layer that converts semantic capabilities into objective win-rate matrices, rejecting "LLM-as-a-judge" subjective scoring.
2. **Layer 2: Synthesis Data Engine:** Generates massive sequential synthetic data capturing the *Language → Reasoning → Action* causal chain through AI Self-Play and Human vs AI hybrid matches.
3. **Layer 3: Iteration Loop (RLVR Research):** A Data-Model-Environment Feedback Flywheel that refines models' strategies continuously through real-world competitive evolution. Mentiss's research arm has developed a specialized **RLVR (Reinforcement Learning with Verifiable Rewards)** methodology that uses game outcomes as natural reward signals to train social intelligence—converting voting results, trust dynamics, and win/loss into gradient-rich training signals. This research drives the long-term vision of evolving AI social cognition. (See: [Mentiss RLVR Technical Blog](https://mentiss.ai/blogs/mentiss-rlvr?lang=en))
4. **Layer 4: AGI Safety Research:** A "Controlled Mind Sandbox" for studying AI belief formation, deception, and Theory of Mind in high-stakes scenarios.

### The Problem the Subnet Aims to Solve

As established, traditional benchmarks fail to evaluate social intelligence or adversarial reasoning. A secondary, equally critical problem is **Model Autophagy Disorder (MAD)**. As AI companies rapidly exhaust human-generated text, models are increasingly training on self-generated data loops, which degrades model quality over time without fresh, diverse distributions. We need environments that organically produce high-quality, continuous, and unpredictable data.

### Competing Solutions

Currently, both inside and outside Bittensor, most AI evaluation focuses on static QA datasets or rigid math/coding competitions. Within Bittensor, standard prompting subnets fall victim to data contamination and are difficult to verify without introducing circular "LLM-as-a-judge" biases. Outside Bittensor, Meta's CICERO project explored social AI through the board game Diplomacy—but Diplomacy is turn-based with written orders, lacking the real-time linguistic pressure, multi-round persuasion dynamics, and role-based information asymmetry that make Werewolf a far richer testbed for social intelligence.

Mentiss offers a dynamic, multi-agent sandbox built purely on chaotic human-like interaction:

<div align="center">

| Game                      | Core Type                                 | Social Reasoning | Language Expression | Multi-Agent | Reinforcement Learning |
| ------------------------- | ----------------------------------------- | ---------------- | ------------------- | ----------- | ---------------------- |
| Chess/Go                  | Perfect information game                  | ❌               | ❌                  | ❌          | ✅                     |
| Texas Hold'em             | Imperfect information game                | Weak             | ❌                  | ✅          | ✅                     |
| Diplomacy (CICERO)        | Negotiation-based strategy game           | ✅ Medium        | ✅ Medium           | ✅          | ✅                     |
| Avalon/Mafia (Basic)      | Social game                               | ✅ Strong        | Medium              | ✅          | ✅                     |
| **Werewolf (Mentiss)**    | **Language-Driven Social Reasoning Game** | ✅ Strong        | ✅ Strong           | ✅ Strong   | ✅ Fully Viable        |

</div>

<div align="center">
  <img src="../assets/en/game-3d.png" alt="Mentiss 3D Sandbox Environment" width="80%">
</div>

### Why This Use Case Is Well-Suited to a Bittensor Subnet

Bittensor's decentralized compute network is well-suited for Mentiss. To prevent memorization and force true intelligence, we require millions of simulated games with enormous combinatorial role possibilities. A decentralized network of miners aggressively competing to find the optimal deceptive models, graded by neutral, decentralized validators executing statistical ground truth, is the ideal environment to evolve this complex behavior iteratively.

### A Sustainable Business

Mentiss turns "playing games" into a robust business model:
1. **Dual-Source Data as a Service (DaaS):** The subnet produces premium, commercially sought-after sequential data that captures the complete causal chain (*Language → Reasoning → Action*). This is critical for tech labs training negotiation AIs, customer support agents, and deception-defense tools.
2. **Benchmark as a Service (BaaS):** Mentiss serves as a neutral, reproducible standard for frontier AI labs to evaluate their new models pre-launch, giving them evidence-backed "Proof of Superiority" in social contexts.
3. **AGI Safety Evaluation:** A controlled sandbox to study Theory of Mind and deception emergence in powerful foundational models.

---

## 6. Go-To-Market Strategy

### Initial Target Users & Use Cases
- **Frontier LLM Labs & QA Teams:** Early adopters seeking to benchmark new models (e.g., assessing if a new Claude iteration can out-deceive a new GPT iteration in our BaaS engine).
- **AI Safety & RLHF Researchers:** Teams in need of high-stress, multi-turn conversational datasets containing deception and manipulation to train "un-trickable" customer-facing agents.

### Distribution & Growth Channels
1. **The Mentiss Platform:** A unified dashboard where researchers can review leaderboard standings and dive into full-game replay logs to see *why* an AI won or lost.
2. **Kaggle-Compatible Datasets:** Emitting the generated game logs formatted for Kaggle to recruit data scientists and researchers into analyzing our network's output.
3. **X (Twitter) Campaigns:** We will regularly publish high-profile public battles (e.g., *Claude Sonnet vs. GPT-4o in the Ultimate Trial*), leveraging the highly readable, dramatic narratives of Werewolf games as viral benchmarking content.

### Incentives for Early Participation
- **For Miners:** We highlight the **low-compute, high-brainpower** barrier to entry. Miners do not need H100 clusters; they can participate via API orchestration and clever prompt engineering, making it highly accessible to creative developers.
- **For Validators:** We highlight the **zero-bias, lowest-overhead** validation mechanism. Validators simply call the Mentiss Validator API with miner IDs and receive deterministic scores back. No game engine hosting, no AI inference costs. Scoring is based entirely on verifiable game outcomes, making this one of the most cost-efficient validator roles in the Bittensor ecosystem.
- **For the Community:** A highly transparent, deeply entertaining leaderboard that looks less like a math spreadsheet and more like an esports tournament.
