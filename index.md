---
title: Dr Sarah Mercer
---
<div class="sm_Parent">
    <div class="sm_child1">
      <img src="https://drsezzer.github.io/profile_pic.png" />
    </div>
    <div class="sm_child2">
      Hi! I'm Sarah, a Principal Researcher at The Alan Turing Institute, working at the intersection of agents and generative AI.
    </div>
</div>

<br>

<hr>
<p valign="center" align="center">
<big><i class="fa-brands fa-square-github"></i></big>&nbsp;&nbsp;<a href="https://github.com/drsezzer/">drsezzer</a> |
<big><i class="fa-brands fa-bluesky"></i></big>&nbsp;&nbsp;<a href="https://bsky.app/profile/drsezzer.bsky.social">@drsezzer.bsky.social</a> |
<big><i class="fa-brands fa-square-x-twitter"></i></big>&nbsp;&nbsp;<a href="https://twitter.com/fanofjavi">@FanOfJavi</a> | 
<big><i class="fa-brands fa-linkedin"></i></big>&nbsp;&nbsp;<a href="https://www.linkedin.com/in/sarah-mercer-033609273">Sarah Mercer</a>
<br>
<big><i class="fa-solid fa-envelope"></i></big>&nbsp;&nbsp;smercer[at]turing.ac.uk
</p>
<hr>

&nbsp;&nbsp;&nbsp;&nbsp; The propensity of LLMs to portray humanlike behaviour fascinates me.  Since the publication of the <a href="https://cetas.turing.ac.uk/publications/welcome-willowbrook">Willowbrook</a> report, I have continued to explore the capacity of generative agents to mimic human behaviour... exploring their ability to maintain believable and consistent personas, their capacity to make human-like mistakes, and their (in)ability to get angry!


<p align=center><img src="https://drsezzer.github.io/willowbrook1.png" /><br>
<small>DALLE-3 generated image of Willowbrook</small></p>

&nbsp;&nbsp;&nbsp;&nbsp; Inspired by the Stanford <a href="https://hai.stanford.edu/news/computational-agents-exhibit-believable-humanlike-behavior">Smallville paper</a>, a simulation comprising 12 characters and 10 locations - including a library, cafe, farm shop, village green and various residences - was developed to further explore the capacity of generative-agents to [portray human like behaviours](layers.md).


&nbsp;&nbsp;&nbsp;&nbsp; Unlike Smallville, the Willowbrook simulation does not maintain a shared representation of the agents' environment, meaning that the agents' reality is purely LLM generated (with the exception of the initial character and location descriptions).  This reality is held within each agent's memory of what they observed, did and heard. As such, any error in the way the LLM is directing the agents is magnified as the simulation progresses and the agents' memories of such inaccuracies are retained, or even acted upon.  This gives us a novel way to evaluate the influence different LLM models have on the lives of the Willowbrook residents.


&nbsp;&nbsp;&nbsp;&nbsp; A few people have asked me what a generative agent actually is, how they are implemented and the frameworks I use.  I don't use a framework, as I did not want an additional layer of abstraction between me and the LLM.  The key to designing a good persona-agent lies in it's initial biography and it's memory retention mechanism. I expand on this [here](agent_architecture.md).


&nbsp;&nbsp;&nbsp;&nbsp; Prior to working at the Turing, I was a researcher in Cyber Security.  The interest garnered by LLMs at the beginning of 2023 obviously had an impact on the cyber security community.  The paper below, was my attempt to bring some evidenced thinking to the fairly polarised (at the time) debate, given my familiarity of developing LLM based applications and intuition for their strengths and weaknesses.  <i>Note: Technical readers may prefer the unedited version of the paper, as linked below</i>.


## Research Publications

### Generative Agents:

* [Welcome to Willowbrook](https://cetas.turing.ac.uk/publications/welcome-willowbrook), The simulated society built by generative agents, December 2023. 

### Cyber Security / Protective Security:

* Insider risk: 
  * [We Need to Talk About the Insider Risk from AI - short article](https://rusi.org/explore-our-research/publications/commentary/we-need-talk-about-insider-risk-ai), 'Emerging threat: organisations face growing risks from artificial insiders as well as human ones.', 8th January 2025, RUSI. 
  * :new: &nbsp;&nbsp; ['I'm Sorry Dave: How the old world of personnel security can inform the new world of AI insider risk' (preprint-v1) on arXiv](https://arxiv.org/abs/2504.00012), 26th March 2025.

* [Generative AI in Cyber Security](https://cetas.turing.ac.uk/publications/generative-ai-cybersecurity), Assessing impact on current and future malicious software, June 2024. <br> 
<i class="fa-solid fa-file-pdf"></i>&nbsp;&nbsp;[Formal PDF](docs/cetas_briefing_paper_-_evaluating_malicious_generative_ai_capabilities.pdf) | <i class="fa-solid fa-pen-ruler"></i>&nbsp;&nbsp;[Final (unedited) Draft](raw_malicious_genai.md)

### Other bits:

* [A Breif Analysis of DeepSeek-R1 and its implications for Generative AI - arXiv](https://arxiv.org/abs/2502.02523) a quick turn-around report covering the release of DeepSeek's R1 model and the implications on the wider eco-system, 3rd February 2025.

  * Just for the giggles: I asked ChatGPT-o1 Deep research to generate a similar report, here's its [paper](DeepResearch-DeepSeekR1_and_DeepSeekV3.pdf).

* [My thoughts on Coding Assistants](my_thoughts_coding_assistants.md) - a short piece on my first experience with Cursor, and how such tools are starting to impact (benefit) experienced coders.

<p></p>
<p>Alongside my own research looking at the human like capacity of generative agents, I also provide technical expertise to the CETaS team, specifically Generative AI.</p>

### CETaS papers:

* [Securing the UK's Research Eco-system](https://cetas.turing.ac.uk/publications/securing-uks-ai-research-ecosystem), my contribution focused on how AI is different; what specific issues do UK academics need to think about to ensure their research is less vulnerable to those with hostile intent.   <i class="fa-solid fa-pen-ruler"></i>&nbsp;&nbsp;Unedited/draft of[ why AI is different](raw_how_is_ai_different.md) (before word limits hit!).
* [Evaluating Malicious Generative AI Capabilities](https://cetas.turing.ac.uk/publications/evaluating-malicious-generative-ai-capabilities), Understanding inflection points in risk, July 2024.
* [The Rapid Rise of Generative AI](https://cetas.turing.ac.uk/publications/rapid-rise-generative-ai), Assessing risks to safety and security, December 2023.

## Current Projects:

* Psychometric testing for generative agents.  Is it a good idea to use generative agents as replacement humans in social science? [HEXACO-Rep (public repo)](https://github.com/alan-turing-institute/hexaco-rep-public), [draft paper](https://github.com/alan-turing-institute/hexaco-rep-public/blob/main/Hexaco-25-04-04.pdf)

* Willowbrook baseline configuration; as an evaluation mechanism for new LLM models.
* Unhappy Willowbrook :cry: :rage: - Can generative agents act upon their emotions?  [Research Proposal](rp_unhappy_willowbrook.md)

<hr>

<div align="center">
<small>All rights are reserved for the contents on this site (drsezzer.github.io), same for uploaded PDFs unless otherwise stated within the document itself. 

<br> (c) 2025 Sarah Mercer.

<br><br>Web site generated using <a href="https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages">GitHub Pages</a> with <a href="https://jekyllrb.com/">Jekyll</a> Theme <a href="https://github.com/pages-themes/midnight">Midnight</a> and using the <a href="https://github.com/jekyll/jemoji">jemoji</a> plugin (<a href="https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md">emoji cheat sheet</a>).

<br><br>
</small>
</div>

