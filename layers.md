---
title: Layers of Human-like-ness
---

<p>&nbsp;&nbsp;&nbsp;&nbsp;Across my research, I explore how specific layers of humanlike behaviour can be designed and evaluated in generative agents. By focusing on measurable and interpretable aspects of personality, I aim to explore the realism and utility of these systems without overstating their capabilities. This is the layered framework I'm using to guide my research: </p>

- *Biography*: The foundational input that shapes an agent’s knowledge, traits, and backstory.
- *Persona*: The outward-facing behaviours and language styles adapted to specific roles or contexts.
- *Personality*: The consistent traits expressed across interactions, informed by frameworks like HEXACO.
- *Character*: A reflection of ethical alignment and value-driven decisions, as framed by the agent’s biography and its experiences.
- *Humanlike Adaptability*: The aspirational goal of creating agents that navigate ambiguity and context with greater nuance.

<p align=center><img src="https://drsezzer.github.io/willowbrook2.png" /><br>
<small>DALLE-3 generated image of Willowbrook</small></p>

Major work packages, and their findings:

- <b>Willowbrook</b>: explored the feasibility of creating a simulated society of generative agents.
    - Plausible patterns of life / daily schedules. [tick] 
        - GPT-4: provided sufficient 'pseudo reasoning' to allow the agents to assume things like a residence contains a kitchen, and that the agents did not need to go to the cafe for a family breakfast.

    - Plausible conversation; flow, progression etc. [tick] 
        - GPT-3.5 +: provided reasonable conversations, tone could be specified to alter 'wordiness' and mood to some degree. however, most interactions suffered from overly generic conversational tones and helpfulness.

- <b>Agent Personas and Psychometrics</b>: explored the stability/reliability/consistency and depth of agent personas w.r.t. personality psychometric testing.

    - Demonstrated that agents could consistently "pass" Myers Briggs personality tests, with results aligning with their designed character profiles.
    
        - GPT-4: was able to maintain a persona across the PI survey such that the MBTI personality-type derived was the same across 5 attempts for all 8 agents tested.

    - Shifted to the HEXACO framework for a more rigorous assessment, recreating the original 2004 Ashton et al. experiment to evaluate population-level patterns in agents’ lexical analysis.

        - Structure of biographies are critical for persona consistency.
        - Agent populations exhibit patterns *almost* resembling humanlike behaviour but lack critical nuance.
        - Limitations emerged, especially around abstract or value-laden topics.

- <b>Unhappy Willowbrook</b>: exploring the ability of generative agents to retain and maintain information akin to their 'social awareness' and the degree to which this information can and should affect their actions and utterances, i.e. their social facility.  [ongoing, active research]

