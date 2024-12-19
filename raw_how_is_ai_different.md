---
title: Threats and Mitigations - How is AI Different?
---

### [Dr Sarah Mercer](index.md), full report to be published Feb 2025.

> <i>This is the unedited (final draft) version of the 2nd Chapter/Section of an upcoming paper, written with additional technical detail.  The formally published version of the paper will be found [here](https://cetas.turing.ac.uk/).</i>

## Chapter 2. The Developing Threat and Mitigations

### 2.1 How is AI Different?

<b><i>Why would AI/ML and Data be targeted?</i></b>

AI and machine learning technologies could deliver advanced capabilities in intelligence analysis, autonomous operations and cybersecurity, for national security and defence.  However, these systems and associated datasets are also high-value targets for hostile states seeking to replicate or undermine a nation’s defence. The theft of AI models allows adversaries to gain technology on the cheap.  By reverse-engineering these models, adversaries can reproduce or improve upon proprietary systems, potentially neutralising an edge in military technology or surveillance capabilities.  Access to these models also enables attackers to exploit AI-driven systems, evading detection or bypassing defences with tailored cyber-attacks.

The dual-use nature of AI/ML presents unique challenges, if the technologies are compromised or reverse engineered, they could enable adversaries to predict or evade surveillance tactics, disrupt defence mechanisms, or even manipulate systems in ways that pose significant risks.  Sensitive datasets often used to train AI models, such as biometric data, satellite imagery and public behaviour data, are especially valuable to attackers, as they could provide strategic insights that impact defence planning and intelligence efforts.  

Additionally, as tools are developed to counter advances in (generative) AI systems, such as those developed to uphold democracy through the detection of synthetic media and mis/dis information, there is a risk that these efforts themselves could be reversed-engineered or subverted, allowing adversaries to evade detection and manipulate digital media more effectively.  
Another major consideration is the value to an hostile state actor / adversary of the data itself.  The ever-growing risk of identity theft and data breaches have somewhat hardened us to the idea that our digital identities are at risk.  Good cyber security hygiene (link to NCSC advice?) can mitigate the impact, as can building awareness of how such data enables scammers and fraudsters.  But it’s not just about names, dates of birth and bank details.

Many forms of data can be used to cause harm.  The recent data breach and financial woes of 23andMe (the DNA testing company), the ransomware attack on the NHS sub-contractor Synnovis[1] and the breach and subsequent publication of photographs from a breast cancer clinic in the US[2], and recently the breach of an AI Girlfriend service[3], show how data, once collected, is always a potential vector for harm[4].  

Even less obviously personal data can be used to invade privacy and identify people when data are aggregated.  Smart cities are a particularly interesting example, in many cases the intent is to improve public services, save tax-payers’ money, and enable innovation.  But from a data aggregation point of view, they raise non-trivial privacy concerns[5, 6, 7].

Of course, data are essential for machine learning, but a key blocker is data availability, existing privacy concerns means new data sets are hard to acquire.  Published, open sourced, data sets can be used and can be big (petabytes), but in addition to size they can also vary in exhaustivity (capturing an entire population), relationality (features allowing for integration with other datasets), and velocity (the speed of collection and use).  

In addition, there are challenges due to the nature of larger datasets and how they were obtained/collected.  Consider the domain of social media information, the data may not be generalisable, meaning usage across the different social media platforms will be different as each platform attract a different population, and there may be issues related to authenticity (e.g. is the data point human or bot generated)[8].  Fundamentally there are no standards or quality assurance in place for open-source data, and without fully understanding the data collection process, the researcher is not fully informed of any biases which may reside within the data set.

In addition, opensource datasets can also be the target of malicious attack, or poisoning.  Interesting recent research[9] from Deepmind and NVIDIA have shown that ‘frontrunning poisoning’ attacks targets web-scale datasets that periodically snapshot crowd sourced content (such as Wikipedia), where they can ‘sneak’ in malicious content just before the harvest/scrape is conducted and clean up after.  Exploiting the predictability of snapshots and the lag in content moderation.

In the absence of good and/or trustworthy training data, many researchers are turning to synthetic data, data generated by Generative AI (GenAI) to top-up or fine tune existing models, but it can only ever be an approximation of the problem domain.  Over-reliance risks overfitting to the characteristics in the synth-data generation process.  LLMs can also be used as labellers[10], reportedly labelling text datasets to the same or higher standard, and in a fraction of the time, than human annotators.  Although they are able to annotate without fatigue setting in, bias within the model will still be a concern, as would hallucinations.

> To address these risks, existing data protection practices provide a good starting point, but researchers must explore such considerations for all aspects of the data lifecycle, from acquisition to disposal.  Adopting strict revision control mechanisms and engaging with a security expert may help to embed good practice within the research project from the start.

<i><b>... above and beyond traditional cybersecurity and IP related concerns:</i></b>

There are several ways in which the risks related to AI/ML systems should be considered different to the traditional software development and deployment environments:

1.	Attacking the model itself; the complex data dependencies and adaptive nature of ML algorithms mean that even subtle attacks – like data poisoning or adversarial manipulation – can lead to significant, often undetected impacts on model performance and reliability. 

2.	AI workflows often rely on specialised libraries, less-mature compilers and high-performance hardware (e.g. GPUs, TPUs) which may lack the stability and (security) maturity of standard software environments.  In addition, AI pipelines require custom data handling and storage solutions for managing very large datasets.

3.	The datasets used in AI/ML systems hold intrinsic value not only for model training but also as targets for adversaries seeking strategic, economic, or even competitive advantages.  These datasets often contain sensitive / personal information, or proprietary knowledge, making them high-value assets.

4.	The dynamic nature of AI models introduces risks like model drift, edge cases, and safety issues, all of which complicate the processes of verification and validation compared to traditional software systems.

There are a number of vulnerabilities that are specific to AI/ML.  Here, we give a high-level overview of some, for more information please see the MITRE Atlas framework[link] and OWASP guidance for machine learning security [link] and LLM applications [link].

* Data poisoning attacks: where adversaries may manipulate or introduce false data into the training datasets, thus causing them to behave incorrectly.  Either to erode accuracy, confidence or even to introduce a bias or weakness that can later be exploited.

* Model Inference attacks: these aim to extract information about the model and/or its training data, adversaries reverse-engineer the model to recover private/sensitive data or to understand it’s decision-making processes.  If released via an API, model extraction could also be used to repeatedly query the model, the answers of which would allow an adversary to label a dataset and subsequently train their own copy of the model.

* Adversarial attacks (on input): small, carefully created changes to inputs could be used to confuse the model, making it misclassify or mis-interpret the input.  In the D&NS arena, this could include deceiving an AI system to misidentify a threat.  Unlike data-poisoning, this would not need the training data to be manipulated, but knowledge of how the model works, would be required.
<br><br>
As with many security related tasks, there is inherent dual-use; the detection of weaknesses can expose weaknesses.  An example is the publicly available CleverHans (https://cleverhans-lab.github.io) which looks to uncover how a model is vulnerable to adversarial attacks.
<br><br>
In conventional software, responsible disclosure, and response teams aim to ensure any weaknesses are patched, before details of the weakness are released to the public, and therefore before those with dubious intent are made aware of it.  <font color="orange">This is not yet an established thing for ML models!</font>

* Model theft: models could be analysed, replicated or modified to neutralise any advantage of the developer(commissioning?) organisation.  Additionally, models could be reversed-engineered in slow time, to recover sensitive, or personal data or to gain strategic insights into its behaviours.  Insider threat or remote attack could mean an adversary could steal the training data or compiled model, although it is likely the model itself as it is smaller [link to compression papers] and therefore easier to exfiltrate.

> There is a substantial amount of research being conducted on AI security.  To address the risks, we would advise researchers to gain familiarity with the techniques described within the MITRE/OWASP frameworks and experiment with adversarial robustness techniques, to consider how a model will behave under malicious conditions or unusual inputs.

<br>

The rapid advancement of AI technology means that tools, frameworks and best practices are constantly evolving, often faster than standard engineering fields.  This can lead to gaps in reliability and robustness because, unlike traditional engineering where mature options allow for informed trade-offs, AI practitioners are sometimes limited to using the latest or only available tool, which many not yet be fully vetted/tested.

The AI field’s evolving nature also means that engineering practices and standards are still catching up.  This lack of standardisation can result in inconsistent outcomes, making it challenging to ensure reliability, especially in high-stakes applications.

The risks of working with less mature components[11], include a lack of built in security measures[12], inconsistent (or incompatible) logging and monitoring subsystems, and variable responses to discovered vulnerabilities, i.e. delayed patch management/security updates.  All of which will weaken the security robustness of a system.  Additionally, ML frameworks often have extensive dependencies, many of which may be immature or lack thorough security vetting, opening themselves up to attack from adversaries, looking for a way-in to attack or modify the ML model.  Sometimes, regardless of its overall vulnerability, a sub-component’s popularity[13] may increase the chance of it being targeted by adversaries in the AI/ML equivalent[14] of an Advanced persistent threat (APT), where weaknesses are surreptitious embedded within ‘trusted’ subcomponents, such that the weakness can be exploited later on (sometimes years later[15]) for maximum operational effect.

> To address the risks associated with immature ML frameworks and protect against APTs, the implementation of proactive security measures is essential.  Strong access controls and data encryption should be considered at every stage of research and development.  Rigorous logging and monitoring systems should be established to detect anomalies and unauthorised access early.  Judgements about the security and reliability of sub-components (and their vendors) should be considered when setting up the research environment.  Collaboration with security experts during the early phases of research will help embed security best practice into the ML lifecycle. 

Additionally, the rapid progression of AI research, development and deployment, also encourages researchers to share more and share earlier.  The well-meaning requirement to ensure replicability and reproducibility of findings within academic papers, mean that models are more readily dropped into the public sphere, potentially before their dual use considerations have been considered.

<i><b>Quality Assurance as a backstop?</i></b>

There are several factors that make testing (verification and validation) of machine learning models more challenging than traditional software development.  The most pertinent of which is the fact that ML systems are often designed for situations where the definition of correct is elusive, meaning that it is difficult to determine a fixed “expected” outcome for every input.

Probabilistic behaviour, often present in ML models, means a model can generate different outputs for the same input, depending on the models training, the underlying data distribution, and even random initialisation factors.  Meaning the testing becomes more about assessing the reliability of the model’s behaviour under diverse conditions and less about verifying specific rules.  Approaches such as structured user testing, simulation-based evaluations, and specific tests such as semantic similarity can help mitigate this risk.

Since ML models are trained on historical data, their performance and behaviour are highly dependent on the quality, completeness and relevance of that data.  Testing an ML model requires an additional activity of validating the data, its representativeness of real-word conditions, and its sensitivity to changes.  To pre-empt post-deployment issues of susceptibility to edge cases and bias.

Many powerful ML models, especially deep learning models, operate as black boxes, where the internal logic of how specific decisions are made isn’t easily interpretable.  This opacity makes it difficult to trace why a model produced a particular result, complicating debugging and validation.

All of these factors make it more challenging to ensure model reliability and safety, especially in critical applications.  Which in turn makes it trickier to detect if a model or the datasets it depends on have been tampered with.

> To address these challenges, a range of specialised approaches are essential.  Stress testing expose models to edge cases, ensuring resilience under atypical conditions, Fairness assessments detect and mitigate bias by analysing model outputs across demographic groups.  Explainability tools like SHAP and LIME may help provide transparency into model decisions and continuous monitoring can help to detect model drift.  Although further research is needed to developing ways to quantify or detect whether an ML model has been tampered with.

Given these complexities, autonomous AI introduces an additional layer of risk, particularly when it comes to predictability and oversight.  The probabilistic nature of ML models, combined with the difficulty of thorough testing, makes it challenging to ensure that autonomous systems will behave reliably in all circumstances.  Integrating a “human-in-the-loop” mechanism to ensure autonomous decisions are reviewed and adjusted as needed, is strongly recommended for critical applications.  It therefore follows that an inherent dual use risk of autonomous AI is the removal of human oversight.  Allowing autonomous AI to make high-stakes decisions without any real-time human intervention or feedback, thus amplifying the risks of unintended actions or system exploitation.  

<br>

In summary, we have highlighted the importance of AI/ML researchers remaining mindful of the often-overlooked national security implications inherent in their work.  While national security may not be a primary concern for most researchers, AI/ML models are increasingly embedded in systems and infrastructure with potential security ramifications.  This ‘melting pot’ moment – where AI/ML R&D are progressing rapidly amid significant interest/hype – requires a cautious security-aware approach.

Additionally, how a piece of research may be used if acquired by adversaries, is not easily defined.  And as such the dual-use-ness of a project may not even be considered by researchers in the early stages.  To address this, it is important to building a culture of awareness within institutions, where discussions of dual-use potential and possible applications are facilitated within research teams, and interdisciplinary dialogue is encouraged with policymakers, ethicists, and threat modelling / cyber security experts.

<br>

References:

<font size="1pt">

1. ‘NHS confirms patient data stolen in cyber attack’ https://www.bbc.co.uk/news/articles/c9777v4m8zdo

2. https://www.cio.inc/breast-cancer-patients-sue-over-breached-exam-photos-data-a-21431 
3. https://www.malwarebytes.com/blog/news/2024/10/ai-girlfriend-site-breached-user-fantasies-stolen 
4. https://www.theguardian.com/technology/2024/feb/17/23andme-dna-data-security-finance 
5. https://itif.org/publications/2023/03/06/balancing-privacy-and-innovation-in-smart-cities-and-communities/ 
6. https://www.rand.org/pubs/commentary/2024/08/addressing-the-national-security-risks-of-bulk-data.html
7. https://arxiv.org/abs/cs/0610105 
8. https://www.cl.cam.ac.uk/~ah793/papers/2021_too_much_data.pdf 
9. https://arxiv.org/pdf/2302.10149 
10. https://www.refuel.ai/blog-posts/llm-labeling-technical-report 

11. Ministry of Defence, 13 November 2024, ’JSP 936: Dependable Artificial Intelligence (AI) in defence (part 1: directive)’, https://www.gov.uk/government/publications/jsp-936-dependable-artificial-intelligence-ai-in-defence-part-1-directive 
12. Google Security Blog, 24th September 2024, ‘Google & Arm – Raising The Bar on GPU Security’, https://security.googleblog.com/2024/09/google-arm-raising-bar-on-gpu-security.html
13. https://linuxfoundation.eu/newsroom/the-rising-threat-of-software-supply-chain-attacks-managing-dependencies-of-open-source-projects 
14. Trendmirco, 23rd May 2024, ‘Navigating the Threat Landscape of Cloud-Based GPUs’, https://www.trendmicro.com/vinfo/us/security/news/threat-landscape/navigating-the-threat-landscape-for-cloud-based-gpus
15. https://www.wired.com/story/xz-backdoor-everything-you-need-to-know/ 

