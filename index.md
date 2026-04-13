---
title: Dr Sarah Mercer
---
<div class="sm_Parent">
    <div class="sm_child1">
      <img src="https://drsezzer.github.io/profile_pic.png" />
    </div>
    <div class="sm_child2">
      Hi! I'm Sarah, a Software Engineer (formerly Principal Researcher at The Alan Turing Institute) working at the intersection of generative AI and agent-based systems. 
    </div>
</div>

<br>

<hr>
<p valign="center" align="center">
<big><i class="fa-brands fa-square-github"></i></big>&nbsp;&nbsp;<a href="https://github.com/drsezzer/">drsezzer</a> |
<big><i class="fa-brands fa-linkedin"></i></big>&nbsp;&nbsp;<a href="https://www.linkedin.com/in/sarah-mercer-033609273">Sarah Mercer</a>
</p>
<hr>

&nbsp;&nbsp;&nbsp;&nbsp; The propensity of LLMs to portray human-like behaviour fascinates me.  Since the publication of the <a href="https://cetas.turing.ac.uk/publications/welcome-willowbrook">Willowbrook</a> report, I have continued to explore the capacity of generative agents to mimic human behaviour... exploring their ability to maintain believable and consistent personas, their capacity to make human-like mistakes, and their (in)ability to get angry!


<p align=center><img src="https://drsezzer.github.io/willowbrook1.png" /><br>
<small>DALLE-3 generated image of Willowbrook</small></p>

&nbsp;&nbsp;&nbsp;&nbsp; Inspired by the Stanford <a href="https://hai.stanford.edu/news/computational-agents-exhibit-believable-humanlike-behavior">Smallville paper</a>, a simulation comprising 12 characters and 10 locations - including a library, cafe, farm shop, village green and various residences - was developed to further explore the capacity of generative agents to [portray human-like behaviours](layers.md).


&nbsp;&nbsp;&nbsp;&nbsp; Unlike Smallville, the Willowbrook simulation does not maintain a shared representation of the agents' environment, meaning that the agents' reality is purely LLM generated (with the exception of the initial character and location descriptions).  This reality is held within each agent's memory of what they observed, did and heard. As such, any error in the way the LLM is directing the agents is magnified as the simulation progresses and the agents' memories of such inaccuracies are retained, or even acted upon.  This provides a novel way to evaluate how different LLMs influence the lives of the Willowbrook residents.


&nbsp;&nbsp;&nbsp;&nbsp; A common question is how generative agents are implemented and what frameworks are used.  I don't use a framework, as I wanted to avoid introducing an additional layer of abstraction between the system and the underlying model.  The key to designing a good persona-agent lies in its initial biography and its memory retention mechanism. 


## Research Publications

### Generative Agents / Simulated Societies:

* Welcome to Willowbrook, The simulated society built by generative agents, December 2023. <br> 
[Online](https://cetas.turing.ac.uk/publications/welcome-willowbrook) | 
[PDF](cetas_expert_analysis_-_welcome_to_willowbrook.pdf)

* Applying Psychometrics to Large Language Model Simulated Populations: Recreating the HEXACO Personality Inventory Experiment with Generative Agents, August 2025, psychometric testing for generative agents.  Is it a good idea to use generative agents as replacement humans in social science? <br>
[arXiv](https://arxiv.org/abs/2508.00742) | [PDF??]()

   * Patterns, Not People: Personality Structures in LLM-powered Persona Agents, October 2025. <br>
   [Online](https://cetas.turing.ac.uk/publications/patterns-not-people-personality-structures-llm-powered-persona-agents)

* Return to Willowbrook: Inside the Minds of Generative Agents, October 2025, can generative agents move beyond polite imitation and become psychologically rich? <br>
[Online](https://cetas.turing.ac.uk/publications/return-willowbrook-inside-minds-generative-agents) | 
[Final draft](willowbrook2.md) | 
[Original research proposal](rp_unhappy_willowbrook.md).


### Cyber Security / Protective Security:

Prior to working at the Turing, I was a researcher in Cyber Security.  The interest garnered by LLMs at the beginning of 2023 obviously had an impact on the cyber security community.  The paper below, was my attempt to bring some evidenced thinking to the fairly polarised (at the time) debate, given my familiarity of developing LLM based applications and intuition for their strengths and weaknesses.  <i>Note: Technical readers may prefer the unedited version of the paper, as linked below</i>.

* Generative AI in Cyber Security, Assessing impact on current and future malicious software, June 2024. <br>
<i class="fa-solid fa-link"></i>&nbsp;&nbsp;[CETaS article](https://cetas.turing.ac.uk/publications/generative-ai-cybersecurity) | 
<i class="fa-solid fa-file-pdf"></i>&nbsp;&nbsp;[PDF](cetas_briefing_paper_-_generative_ai_in_cybersecurity.pdf) | 
<i class="fa-solid fa-pen-ruler"></i>&nbsp;&nbsp;[Final (unedited) Draft](raw_malicious_genai.md)


* Insider risk: 
  * 'We Need to Talk About the Insider Risk from AI' short article, January 2025, RUSI. <br> 
  [Online](https://rusi.org/explore-our-research/publications/commentary/we-need-talk-about-insider-risk-ai).
  * 'I'm Sorry Dave: How the old world of personnel security can inform the new world of AI insider risk', updated April 2025. <br>
  [arXiv](https://arxiv.org/abs/2504.00012)
  * How Personnel Security can Inform the New World of AI Insider Risk, RUSI Journal article, October 2025. <br>
  [Online](https://doi.org/10.1080/03071847.2025.2550122) | [PDF](AI_Insider_Risk.pdf)


### Other Topics:

* A Brief Analysis of DeepSeek-R1 and its implications for Generative AI - a quick turnaround report covering the release of DeepSeek's R1 model and the implications on the wider ecosystem, February 2025. <br> [arXiv](https://arxiv.org/abs/2502.02523)

  * China’s AI Evolution: DeepSeek and National Security - CETaS Expert Analysis, February 2025. <br>
  [Online](https://cetas.turing.ac.uk/publications/chinas-ai-evolution-deepseek-and-national-security) | [Final Draft (no spin)]()

* [My thoughts on Coding Assistants](my_thoughts_coding_assistants.md) - a short piece on my first experience with Cursor, and my thoughts on how such tools are starting to impact (benefit) experienced software developers.

### CETaS papers:

<p>Alongside my own research looking at the human like capacity of generative agents, I also provided technical expertise to the CETaS team, specifically Generative AI.</p>

* [Securing the UK's Research Ecosystem](https://cetas.turing.ac.uk/publications/securing-uks-ai-research-ecosystem), my contribution focused on how AI is different; what specific issues do UK academics need to think about to ensure their research is less vulnerable to those with hostile intent.   <i class="fa-solid fa-pen-ruler"></i>&nbsp;&nbsp;Unedited/draft of [why AI is different](raw_how_is_ai_different.md) (before word limits hit!).
* [Evaluating Malicious Generative AI Capabilities](https://cetas.turing.ac.uk/publications/evaluating-malicious-generative-ai-capabilities), Understanding inflection points in risk, July 2024.
* [The Rapid Rise of Generative AI](https://cetas.turing.ac.uk/publications/rapid-rise-generative-ai), Assessing risks to safety and security, December 2023.

<hr>

<div align="center">
<small>All rights are reserved for the contents on this site (drsezzer.github.io), same for uploaded PDFs unless otherwise stated within the document itself. 

<br> (c) 2026 Sarah Mercer.

<br><br>Web site generated using <a href="https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages">GitHub Pages</a> with <a href="https://jekyllrb.com/">Jekyll</a> Theme <a href="https://github.com/pages-themes/midnight">Midnight</a> and using the <a href="https://github.com/jekyll/jemoji">jemoji</a> plugin (<a href="https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md">emoji cheat sheet</a>).

<br><br>
</small>
</div>

