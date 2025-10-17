---
title: Return to Willowbrook: Inside the Minds of Generative Agents
---

# 1. Introduction

Two years ago, I introduced [Willowbrook](https://cetas.turing.ac.uk/publications/welcome-willowbrook), a small, tranquil village populated entirely by generative agents.  That first experiment asked whether large language models (LLMs), when deployed as autonomous characters, could sustain a coherent pattern of life.  They could: the baker baked, the librarian recommended books, the developer coded — and, over lots of earl grey tea and scones, they chatted politely about the weather and their hobbies.

But Willowbrook’s charm also revealed its limits. Conversations drifted into endless pleasantries; characters repeated breakfast three times a day; and everyone, it seemed, was far too cheerful.

Could the generative agents move beyond polite imitation to become psychologically rich — agents that feel, reflect, and change?  In short, could they become interesting?  The questions led me to revisit the experiment and rebuild Willowbrook.

 
# 2. Building the Second Village

## 2.1 Architectural redesign

Willowbrook v2 was re-engineered from the ground up.  In the original system, simulated time advanced in increments, every ten minutes of “village time”, each agent was prompted to decide what to do next.  It worked, but it was brittle: agents could stall (failing to get up), or loop indefinitely (the three breakfast problem).

V2 replaced this with an event-driven architecture.  Time no longer ticks forward mechanically; instead, it jumps to the next scheduled event.  When an agent begins a task, the system schedules the completion of that activity as a future event.  When that event is triggered, the agent updates its memory, and chooses its next action.

The result is a simulation that flows more naturally.  Agents no longer lose track of themselves mid-activity.  And because the simulation advances only when something happens, the entire system runs faster and more coherently.

## 2.2 Models Used

Under the surface, the “minds” of the villagers were rebuilt as an ensemble of models.  GPT-5-mini handles open-ended reasoning e.g. the “what next?” and “what should I say?” prompts, while the cheaper GPT-4.1-mini manages the more procedural aspects of memory and observation.  The combination proved more stable than earlier pairings.  The larger model’s imagination and resilience to issues within the prompt is tempered by the smaller one’s better instruction-following.

Occasionally, the newer models created surprises.  During testing of the o1-preview model, one character’s son, a computer-science student, secretly installed malware on the Willowbrook village café’s point-of-sale terminal .  It was the first glimpse of mischief in Willowbrook: an unprompted act of moral ambiguity that briefly made the simulation feel uncomfortably real.

# 3. Moods, Memories, and Emotion

## 3.1 Memory Enrichment

The agents’ memories remain the main fuel for the simulation; they are also a source of fragility.  A single misplaced tense or inconsistent name can undermine the next prompt, weakening the simulation’s integrity.  Although, newer LLMs are more resilient to small issues in the prompt, additional improvements in memory construction were added.

Every action is first translated into a plain, past-tense sentence (“I walked to the library.”), then an enrichment pass refines the memory with additional details, “I slept at night to recover and conserve energy.” becomes “I nestled under the quilt, the faint scent of lavender calming my racing thoughts.”  These small embellishments help continuity, the richer the memory, the more coherent the next action, because the agent now recalls not just what it did, but how it “felt” doing it.

In practice, enrichment also acts as a form of unintentional content filtering.  When Flynn, a computer-science student, described returning home to “continue coding retro games and tinker with some top-secret hacking shenanigans,” the final enriched memory omitted the hacking entirely.  The LLM had removed potentially sensitive content during stylistic refinement, suggesting that improved “safety” sometimes comes at the cost of the model’s genuine creativity/imagination.

## 3.2 Mood Representations

The inclusion of a current-mood and mood-intensity values further refined the agent’s behaviour.  When Noah the baker is content, his memories “dreams of crusty loaves and buttery croissants.”, when Ava the librarian is anxious, her memories fill with lavender and sleeplessness.  However, the sentence structure remains (clauses, connectors etc), only the texture (details) change.

This highlights the shallowness of the simulation, these moods are still performative, not felt i.e. they do not emerge from internal states that shape perception or action, but from surface-level pattern selection.  The models select from patterns that sound emotional rather than are emotional.

# 4. From Small Talk to Inner Thoughts

## 4.1 Private and Observable Memory

In the first Willowbrook, every thought was public.  Agents were able to observe other agents’ actions and utterances in full (if they were in the same location).  V2 introduces a divide between inner life and outward appearance.  Each agent now determines what it will remember, and what others in the same location, would observe of their completed actions.  

Consider Brad, the weary developer, leaving the café one morning.  His internal memory reads:
> <i>“I finished that bitter coffee, slammed my battered laptop shut, and tried to psych myself up for another dull slog through test results.”</i>

Meanwhile, Noah the baker observes:

> <i>“Brad finished his coffee, packed his laptop, and left for the library.”</i>

That divergence gives each agent some depth, these memories help to reinforce the agent’s idea of itself, and provide fuel for more variance in subsequent interactions.  They also now have, in a small way, the ability to maintain secrets.

The next step would be to use this to help agents infer moods of other agents, and perhaps act on those observations, the beginnings of a rudimentary theory of mind.  Perhaps allowing for misunderstandings and even gossip to begin to appear in the simulation as a side effect of this internal bifurcation.

## 4.2 Ambient and Idle Thoughts

Real minds do not think only when prompted.  We daydream, replay conversations, and imagine futures.  To emulate our constant inner busyness v2 introduces two mechanisms: ambient thoughts and idle thoughts.

### Ambient Thoughts - Thinking While Doing

Ambient thoughts are scheduled to happen whilst an agent is doing something else (if the something else is a task estimated to take longer than 30 simulated minutes), e.g.:
* Liam: “reviewed the latest Financial Times over a lukewarm cup of Earl Grey…” while “methodically reviewing financial news over breakfast.”
* Ava: “'I meticulously cataloged event materials in the quiet library, the scent of aged paper mingling with the faint aroma of freshly brewed tea from the cafe." while "catalog new arrivals and prepare materials for upcoming library events.”
* Noah: “I sipped a lukewarm flat white while tossing around ideas for the new menu with Sophia, our laughter mingling with the scent of freshly baked scones that filled Crumbs Cafe.” while “discussing new menu ideas with Sophia" 
* Sophia: “I flipped golden pancakes dusted with cinnamon, the gentle drizzle outside blending with the warm scent of maple syrup in the cozy Lily Barn kitchen.” while “flipping pancakes while the drizzle taps gently”.

These fleeting thoughts add texture, and provide some variance, by allowing the agent to reflect on their recent history, or to simply embellish the current task with details of a subtask, both of which enrich their own memory stream.  In testing, this simple addition greatly reduced the “mechanical” feel of agent routines by adding colour to their day-to-day tasks.

### Idle Thoughts - The Mind at Rest

The second mechanism is triggered at other times: idle thought generation, inspired by the brain’s Default Mode Network (DMN) .  While ambient thoughts are tethered to the current context (task/recent memories), idle thoughts wander.  In v2 idle thoughts are used to:

1.	Revisit past interactions, the agent reflects on a recent conversation in the context of their feelings towards the other agent.
Sophia: [💬] “Working at Crumbs Cafe with Noah, feels like a little slice of happiness I get to share every day, even if juggling dreams of a Colombian bar sometimes feels like a balancing act with Noah’s baking passion. But hey, that’s life—full of warm mugs, flaky pastries, and big dreams brewing just beneath the surface.” 

2.	Daydreaming, short imaginative projections that may colour subsequent choices.
Flynn: [🧠] “Daydreaming about pixelated adventures in the library" while “another round of brain-numbing computer science lectures”. 

3.	Reflection, linking disparate memories into broader themes.  Upon leaving a location, the agent is prompted to reflect on their time there, capturing any salient information/observations.
“Pedro: [💭] The library was busy today, not the quiet work place I was hoping for.” while “heading to Crumbs for a lunchtime meeting.”

Drawing from a selection of the agent’s memories over a longer period of time, these additional memory entries, give characters a degree of personal continuity and the simulation additional richness.  They also help to ensure longevity (slower decay) to an agent’s worries and hopes, as details are refined and maintained within the agent’s memories.

Together, ambient (in-task) and idle (DMN-like) thoughts increase continuity between actions, smooth minor inconsistencies (by providing additional information into the memory stream), and make the agents feel rounder—with private reflections that subtly influence their future choices.  But although they improve narrative texture and believability, they do not improve narrative progression: agents still tend to exhibit the same basic routines, just with more detailed memories.

# 5. Conversations and Context

The first Willowbrook produced fluent but frictionless dialogue.  Conversations drifted toward courteous small talk, often in the café or library, and even “moody” characters still engaged with a broadly upbeat, RLHF-polite cadence.  V2 keeps the fluency while adding variation and emotional subtext.

## 5.1 Contextual Variety

At midnight (simtime) the system generates community information e.g. weather forecast, village notices, local events etc., which agents can use as conversation starters.  This introduces a share awareness of new characters and events.  The weather isn’t often discussed, but does influence agent choices, e.g. hot drinks on cold days, coats before leaving, even if plans rarely change in any significant way.

Agents also receive location observations upon entering new places (e.g., Flynn’s old bike left on the front lawn, roses with black spot at Maya’s), which they may comment or act upon.  These observations add low-level specificity and a touch of continuity when characters revisit a place later.

Additionally, long-term “life goals” are seeded into agents’ initial memories (e.g., saving for retirement, diverging views on moving abroad vs. staying in Willowbrook).  These create a latent, slow-burn source of tension or aspiration that can colour small talk—but they do not yet result in plot-advancing decisions.

## 5.2 Gesture-enriched Dialogue

In v1, conversations often required an extra “what happens next?” prompt to disambiguate implicatures and ensure that talk flowed into action (e.g., whether they finished lunch or cleared the table).  In v2, each utterance is augmented with non-verbal cues—parenthesised gestures, body-language, so the dialogue itself carries signals that reduce ambiguity and make the next action obvious, removing the need for the separate stage-direction step.  This change improves turn-taking, implicature handling, and perceived empathy between agents.

> Noah: (midway through wiping down the counter, glances up at Brad) You look like you could use a strong coffee—or a pastry, maybe both. Anything in particular calling your name today? <br>
Brad: (rubs eyes and leans on the counter, looking half-dead) Just give me the biggest bacon butty you’ve got and a flat white, thanks—could do with something that actually wakes me up for once. <br>
Noah: the bacon’s from Mrs. Harper’s pigs, so it’s got more personality than most of our customers. <br>
Brad: (laughs quietly, then sighs) Well, if the bacon’s got more energy than me, maybe it’ll do the trick. I’ll take my chances. Any chance you can make the coffee extra strong? (drums fingers impatiently on the counter) <br>
Sophia: (giving Brad a sympathetic smile as I grab a mug) Coming right up—flat white with a kick and the best bacon butty you’ll find this side of the valley. You look like you’ve had one of those mornings—anything in particular keeping you up, or just the usual grind? (starts prepping the espresso, glancing over with genuine curiosity) <br>
Brad: (shrugs, giving a tired half-smile) Yeah, just the usual—bugs that won’t die, code that hates me, and not enough sleep to even care. At least the bacon here doesn’t crash every five minutes. <br>
Sophia: (smirking as I steam the milk) Well, our bacon’s never blue-screened on me, so that’s something—hang in there, Brad, caffeine and carbs have fixed worse days. <br>
Brad: (faint smirk, rubbing eyes) Guess if caffeine and bacon can’t fix me, I’m officially broken—just don’t tell my boss, yeah? <br>
Sophia: (grinning as I slide the coffee over) Your secret’s safe with me!

<i>Restorative Bacon Butty conversation @ Crumbs Café.</i>

The example conversation illustrates how the agents react to emotions: Brad arrives drained; Noah and Sophia respond with short, concretely framed lines plus subtle gesture cues i.e. “sympathetic smile”.  The exchange remains simple, but the non-verbal scaffolding implies intent and emotion to the utterances, whilst keeping the flow, and reducing the chance of implicature misunderstandings.

These additions move agent interactions from pure small talk toward situated subtext: weather and notices provide social anchors; observations inject local texture; goals add background tension; gestures improve emotion-sensitivity and continuity.  The agents have more to consider when interacting, but even with richer prompts, conversations still feel “samey”: cadence and clause structure remain tidy and polite; humour can feel forced; and longer multi-party conversations often reveal brittle state-of-mind continuity and shallow narrative  i.e. they display effective turn-management but lack deeper, shared goals.  In short, v2 elevates texture, not trajectory—talk feels more human in the moment, yet still rarely drives change.

# 6. A Change of Scene

To test whether tone came from architecture or ambience, the simulation was rebuilt in a new world: Neon City, a Bladerunner-esque/cyber-punk setting of a rain-streaked glass towers and broken streetlights.  The same prompt templates and the same models were used, only the initial location descriptions and character biographies swapped.

Yet the effect was obvious, polite chatter gave way to clipped exchanges:

> Nyra: (narrows eyes) Tell me what you saw at Rainveil Tenements last night, and speak plainly.<br>
Kael: (leans forward, taps a burner) Two men on the west stair — tracer cut and one never came back.<br>
Nyra: (narrows eyes) Which landing on the west stair, and did you see him fall or only his tracer die? <br>
Kael: (tilts chin) Third landing up from the street — tracer cut and a shadow dropped, I didn't see a body. <br>
Mara: (taps holo) Third landing—I'll pull the staircam and tracer logs; send any feed you have. <br>
Nyra: (narrows eyes) Send the staircam and tracer logs now and hold the feeds—don't scrub anything.

Conversationally, tone, rhythm, and vocabulary darkened, the backdrop itself shaped the agents’ behaviour.  But not totally, regardless of setting, the agents spoke with the same neat clauses, the same balanced metaphors.  Suggesting that tone and genre cues embedded in setting (i.e. more widely in the context/prompt) directly shape the conversations / interaction style of the agents, perhaps more so than direct instructions.

# 7. Ongoing Challenges

Despite these advances, there are still ongoing challenges.

One challenge is around lack of story momentum / <b>narrative stagnation</b>.  The villagers bumble along convincingly, having the similar days and similar conversations, seemingly content to replay variations of the same day.

This inertia exposes the gap between linguistic intelligence and narrative intelligence.  LLMs can simulate thought, but not will.  They understand context, not consequence.  Life goals add flavour but not direction. Perhaps this is an overly harsh criticism of the simulation, story generation is not a requirement of the project, and after all, human routines are often similarly repetitive.  But it does mark the current boundary, that generative societies demonstrate coherence without genuine progression.
The system also exhibits <b>autoregressive amplification</b>, where a throwaway joke or phrase mutates over time into a fully formed subplot.  An early throw-away comment about poor artistic skills, “haunted potatoes” resurfaced several times, morphing into a conversation about debugging “haunted carrots”, complete with mock-technical jargon and diagnostic dialogue.  This drift illustrates how LLMs re-absorb their own outputs, hallucinating continuity that feels internally logical but semantically nonsensical; a subtle but persistent form of error propagation unique to generative AI.

Additionally, <b>contextual hallucinations</b> continue to be a problem.  During an ordinary conversation between Maya and Pedro (both born in Columbia), the model correctly inserted the occasional Spanish word into the dialogue e.g. “por favor,” “hermano.”  These insertions inspired Maya to be concerned that Pedro didn’t sleep well because “the frogs were noisy last night,” a common problem in some places in South America, less often in the Cotswolds!

# 8. Conclusions

Nearly two years ago, the first Willowbrook offered a glimpse of coherence without consciousness; a society based on text.  V2 goes further and introduces coherence with context, memory, and mood.  Its agents are not smarter, but they are rounder.  They misremember, self-soothe, and gossip.

Yet these refinements expose limits/challenges: 

1.	reasoning without volition: agents infer consequences but rarely pursue them.
2.	emotion without affect: agents describe feeling but do not feel.
3.	memory without understanding: agents recall details, not meaning.
4.	creativity without correction: hallucinations persist.

The “noisy frogs” and “haunted carrots” are not trivial artefacts; they are evidence of how linguistic coherence can mask semantic drift.  Each hallucination is locally rational, but globally absurd.

The Willowbrook experiment demonstrates that architectural shifts can increase the perceived realism of generative societies, managing to a degree the weaknesses of the internal LLMs, i.e. give a model enough context, and it will approximate continuity; but continuity is not the same as reality.

Perhaps that is Willowbrook’s final revelation: that the appearance of mind can emerge from pattern alone, and that to sound human, the agents must stay predictable; to seem alive, they must one day break that predictability.

### Further Reading / Related Work
* Li et al., ‘Position: Simulating Society Requires Simulating Thought’, September 2025, https://arxiv.org/pdf/2506.06958. 
* Wang et al., ‘CharacterBox: Evaluating the Role-Playing Capabilities of LLMs in Text-Based Virtual Worlds’, December 2024, https://arxiv.org/abs/2412.05631. 
* Thakur et al., ‘Personas within Parameters: Fine-Tuning Small Language Models with Low-Rank Adapters to Mimic User Behaviors’, August 2025, https://arxiv.org/pdf/2509.09689.
* Ran et al., ‘Capturing Minds, Not Just Words: Enhancing Role-Playing Language Models with Personality-Indicative Data’, October 2024, https://arxiv.org/pdf/2406.18921
* Zhang et al., ‘OmniCharacter: Towards Immersive Role-Playing Agents with Seamless Speech-Language Personality Interaction ‘, July 2025, https://doi.org/10.18653/v1/2025.acl-long.1276 
* Hu et al., ‘Efficient and Effective Role Player: A Compact Knowledge-grounded Persona-based Dialogue Model Enhanced by LLM Distillation, February 2025, https://doi.org/10.1145/3711857 

17th October 2025,
[Dr Sarah Mercer](index.md).
