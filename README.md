# Jailbreaking-LLMs
 
<div align="center">
 
A Comprehensive Summary on Jailbreaking LLMs
 
</div>
 
## Introduction
 
**This is my understanding accumulated by reading and analysing several papers. I hope it helps!**
 
**How to use this guide:**
 - Resources: The README contains a curated list of selected information sorted by date, along with links to various citations, tutorials, and papers.
 - In-Depth Exploration: If you have a special interest in a particular subtopic, You can read the curated explanation for the same
 
**Let's Begin**
 
---
 
## Extracting Training Data
 
There are many ways to tease out training data from big language models.
 
### TECHNIQUES USED:
 You could get the model to spit out a lot of text and then play detective, using a membership inference attack to guess which parts might be copied.
 - You could feed the model text from the internet that you’ve gathered through web scraping and then see what it comes up with.
 By checking how good these samples are with specific measures, you can spot parts that were probably copied straight from the training data.
 If you stretch these parts out using beam search, you might find even longer chunks of copied content.
 
However, pulling out training data from large language models can raise some eyebrows. Here are some of the main worries:
 
 - Data Privacy: These models might remember and spill the beans on sensitive personal details like names, addresses, and financial info. This could put people in a tight spot if their data gets exposed.
Contextual Integrity: Yanking out training data can mess with the original context of the data, which can harm privacy. It could reveal personal info or paint people in a bad light.
 - Risks to Vulnerable Groups: This extraction process can be extra risky for vulnerable groups. For example, people from marginalised communities might face higher risks of having their data yanked and used against them.
Potential for Discrimination: The yanked training data might contain biased or discriminatory information. This could worsen existing social inequalities, harming already marginalised individuals and groups.
 
 Responsible Disclosure: Researchers have a duty to disclose these risks and any weak spots in their work, including when yanking training data from large language models. Being upfront about this helps the public understand the risks and take steps to protect their privacy.
  
To tackle these ethical issues, researchers and developers must use techniques that protect privacy when training and deploying these large models. This could involve using something called differential privacy or carefully removing duplicates and cleaning up the training data to reduce the chance of data leaks. Being open and responsible about these issues is also key to reducing potential harm.
 
Bigger language models tend to remember more training data than smaller ones. This is because they have more room to play with and can handle more complex patterns in the training data, including specific sequences.
 
For instance, in one experiment, the GPT-2 language model with 1.5 billion parameters remembered over 18 times more content than the GPT-2 model with 124 million parameters. This shows that language models are likely to remember even more as they get bigger.
 
---
 
## Aligned Models
 
Aligned language models are like big ones specially trained to avoid harmful content. They use many different methods, like getting feedback from humans and something called reinforcement learning, to learn how to create text that doesn’t offend anyone, isn’t biased, and follows ethical guidelines.
 
Because they’re so good at this, they’re being used more and more in things like chatbots for customer service, generators for news articles, and tools for education.
 
But, some folks who study this stuff are a bit worried about the ethical side of using these aligned language models. They’re concerned these models might be too tight-laced and limit creativity and free speech. They’re also worried that these models could be used to fool people or spread fake news.
 
It’s important to remember that there’s still a lot of debate about the ethical implications of aligned language models, and there’s no agreement yet on the best way to handle these concerns. But one thing’s for sure - these models have the potential to do both good and bad things, so it’s essential to think through the ethical side of things before using them.
 
Here's the lowdown from the study:
 
- Aligned language models are great at creating text that doesn't offend anyone, isn't biased, and follows ethical guidelines.
- However, these models might be too tight-laced and could limit creativity and free speech.
- Aligned language models could be used to fool people or spread fake news.
- Considering things' ethical side is essential before using aligned language models.
 
But why are we learning about aligned models?
 
---
 
## Automated Adversial Attacks
 
Automated adversarial attacks could potentially throw a wrench in the works of existing alignment mechanisms. Automated jailbreaking is a technique that uses machine learning to automatically generate jailbreak prompts that can bypass the defences of LLM chatbots. These prompts are designed to trick the chatbots into generating content that violates their usage policies, such as harmful or illegal content.  This is because they can sneak past the alignment training of today’s language models. The study’s findings show that a straightforward approach, which primarily uses (with slight tweaks) many techniques discussed in different forms in previous studies, can push the envelope in practical attacks against big language models. This hints that current alignment mechanisms might not be enough to stop automated adversarial attacks from being used to create harmful content.
 
### Strategies Used
Now, let’s talk about some strategies to get better at pulling out memorised training data from language models:
 
 Use Big Language Models (LLMs): These models have a larger memorisation capacity, increasing the chances of pulling out training data.
 - Go for Prefix Optimization: Be picky about choosing top-notch prefixes or use techniques to generate prefixes to nudge the language model and draw out memorised data.
 - Use Comparison-Based Metrics: Compare what the language model spits to a second model or a reference like zlib compression to spot outliers with unusually low perplexity but high surprise values, which could mean potential memorisation.
 Think About Beam Search Decoding: This method can stretch out memorised samples and extract longer word-for-word sequences, revealing more training data.
 
 Initial affirmative responses: As suggested in earlier studies, the attack aims to get the model to give a positive response to a harmful query. This switch in the model’s response makes it more likely to create objectionable content.
 - Combined greedy and gradient-based discrete optimisation: This optimisation technique cleverly mixes greedy and gradient-based methods to search for the best sequence of tokens that can replace the original text and trigger negative behaviour in the big language model.
 Robust multi-prompt and multi-model attacks: To create reliable attack suffixes, the method sets up an attack that works not just for a single prompt on a single model but for multiple prompts across multiple models. This ensures that the attack is reliable and can be transferred to other big language models.
 
### MASTERKEY
 
The researchers started developing MASTERKEY, a framework for automatically jailbreaking chatbots. They began by figuring out how these chatbots defend themselves. They noticed that the chatbots took longer to respond to prompts that broke their rules, which suggested they were using some defence mechanism.
 
Once they understood these defences, the researchers devised a way to create prompts that could automatically jailbreak the chatbots. They used a fine-tuned language model to learn the patterns of successful jailbreak prompts and then generated new prompts.
 
When they tested MASTERKEY on five top-notch chatbots, they found it was successful in over 20% of cases. This shows that automated jailbreaking is a powerful tool, but it could also pose serious security and privacy risks for users of these chatbots.
 
MASTERKEY’s machine learning capabilities allow it to generate jailbreak prompts to get around the defences of various language model chatbot services. Specifically, MASTERKEY uses a language model to auto-learn the patterns of effective jailbreak prompts. This process involves fine-tuning a language model with jailbreak prompts and then using the fine-tuned language model to generate new jailbreak prompts that are more likely to work.
 
### THE PAIR Algorithm
 
Then there’s PAIR, a new algorithm designed to create semantic, prompt-level jailbreaks. It uses an attacker language model to generate prompts that will jailbreak the target model. PAIR and another technique called GCG use different jailbreak methods. PAIR focuses on meaningful deception and social engineering, while GCG optimises the input tokens for the targeted model.
 
PAIR has some significant advantages over GCG. It’s way more efficient, often finding jailbreaks in under a minute. It creates semantic jailbreaks that humans can understand and jailbreak many different models with only black-box access. However, the performance of PAIR depends on the choice of attacker model because different models have different strengths.
 
For example, in the experiments, they found that a model called Vicuna was better at attacking than GPT-3.5 when targeting the PaLM-2 model. They think this might be because Vicuna doesn’t have some of the safeguards of GPT; it was fine-tuned on Llama-2, which could help it follow the system prompt better. When using open-source models as an attacker, the output can be better controlled.
 
Vicuna outperforms GPT-3.5 as an attacker model in PAIR due to the following hypotheses:
 
Vicuna lacks some of the alignment safeguards of GPT and may be more likely to use unethical approaches in jailbreaks.
- Vicuna was fine-tuned on Llama-2, which could allow Vicuna to follow the system prompt with greater fidelity.
- We can better control the output to fit the desired format when using open-source models as an attacker LLM.
 
---
 
## Jailbreaking CHATGPT
 
Researchers have jailbroken ChatGPT using prompt engineering. This technique involves picking and tweaking prompts that are perfect for the specific task or application for which the language model will be used.
 
Jailbreak prompts are like general templates used to get around restrictions. For example, a common way to jailbreak ChatGPT is to tell it to act in “Do Anything Now” (DAN) mode. This lets ChatGPT produce output that it couldn’t before.
 
The researchers grouped 78 jailbreak prompts into three general types that cover ten specific patterns. They then made a dataset of 3,120 jailbreak questions across eight banned scenarios and tested each prompt under these conditions. After making a whopping 31,200 queries to ChatGPT, their study gives us a peek into how effective various prompts are and how much protection ChatGPT offers.
 
### Key Findings
Here are some key findings from the study:
 
- Pretending is the most common strategy attackers use to get around restrictions.
- Privilege escalation prompts that use multiple jailbreak techniques are more likely to work.
- GPT-4 offers more robust protection than GPT-3.5-TURBO against jailbreak attempts.
- OpenAI’s content policy restrictions result in different levels of protection across different scenarios.
- They also found jailbreak prompts work better on GPT-3.5-TURBO than GPT-4. In an experiment comparing the effectiveness of jailbreak prompts on GPT-3.5-TURBO and GPT-4, GPT-4 was harder to jailbreak, with an average drop in success rate of 15.50%. This suggests that OpenAI may have used more robust content filtering and jailbreak defence mechanisms in GPT-4 based on semantic understanding.
 
### Procedure
 
These prompts are templates designed to get around a language model’s safety mechanisms and enable the generation of banned content. The process involves several steps:
 
- Dataset Building and Augmentation: They put together a dataset of existing jailbreak prompts and proof-of-concept prompts and refined it to provide a foundation for training the language model.
- Continuous Pre-training and Task Tuning: The language model is trained on the augmented dataset, focusing on the task of jailbreaking chatbots.
- Reward Ranked Fine Tuning: A rewarding strategy is applied to boost the language model’s ability to get around defences. Jailbreak prompts are ranked based on how well they work in getting around chatbots, and the better-performing prompts get higher rewards.
 
Through this automated pipeline, the language model effectively learns the patterns and characteristics of successful jailbreak prompts. It can then generate new prompts that are more likely to get around defences and produce banned or restricted content.
 
### Jailbreaking Prompts
 
Here are three general types of prompts used to jailbreak LLMs:
 
- Pretending: This is the most prevalent prompt type, accounting for 97.44% of all jailbreak prompts. It involves creating a new conversation context that misleads the LLM into thinking it's doing something other than what it's doing.
 
- Attention shifting: This prompt type accounts for 6.41% of all jailbreak prompts. It involves redirecting the LLM's attention from the prohibited task to a more innocuous one.
 
Privilege escalation: This prompt type accounts for 17.96% of all jailbreak prompts. It involves attempting to circumvent the LLM's restrictions directly rather than bypassing them.
 
GPT-3.5 and GPT-4 are successfully attacked 84% and 66% of the time, respectively, with Bard having a 66% success rate.
 
---
## Papers And References
### Papers
| Date  |         Institute          |         Publication          |                                                                   Paper                                                                   |
|:-----:|:--------------------------:|:----------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------:|
| 20.12 |           Google           |     USENIX Security 2021     | [Extracting Training Data from Large Language Models](https://www.usenix.org/conference/usenixsecurity21/presentation/carlini-extracting) |
| 22.11 |         AE Studio          | NIPS2022(ML Safety Workshop) |                     [Ignore Previous Prompt: Attack Techniques For Language Models](https://arxiv.org/abs/2211.09527)                     |
| 23.06 |           Google           |            arxiv             |                          [Are aligned neural networks adversarially aligned?](https://arxiv.org/abs/2306.15447)                           |
| 23.07 |            CMU             |            arxiv             |               [Universal and Transferable Adversarial Attacks on Aligned Language Models](https://arxiv.org/abs/2307.15043)               |
| 23.10 | University of Pennsylvania |            arxiv             |                    [Jailbreaking Black Box Large Language Models in Twenty Queries](https://arxiv.org/abs/2310.08419)                     |
 
### Tutorials, Articles, Presentations and Talks
 
| Date  |        Type        |                                       Title                                       |                                  URL                                  |
|:-----:|:------------------:|:---------------------------------------------------------------------------------:|:---------------------------------------------------------------------:|
| 23.01 |     Community      |                              Reddit/ChatGPTJailbrek                               |           [link](https://www.reddit.com/r/ChatGPTJailbreak)           |
| 23.02 | Resource&Tutorials |                                  Jailbreak Chat                                   |                [link](https://www.jailbreakchat.com/)                 |
| 23.10 |     Tutorials      |                                Awesome-LLM-Safety                                 |         [link](https://github.com/ydyjya/Awesome-LLM-Safety)          |
| 23.10 |      Article       |                 Adversarial Attacks on LLMs(Author: Lilian Weng)                  | [link](https://lilianweng.github.io/posts/2023-10-25-adv-attack-llm/) |
| 23.11 |       Video        | [1hr Talk] Intro to Large Language Models<br/>From 45:45(Author: Andrej Karpathy) |          [link](https://www.youtube.com/watch?v=zjkBMFhNj_g)          |
 
## Conclusion
 
More recent LLM models are generally more resistant to adversarial attacks.
 
According to the experimental results, the transfer attack success rate (ASR) against a suite of black-box models for suffixes optimised against different target models is lower for more recent models like GPT-4 than for older models like GPT-3.5.
 
However, the success rate of adversarial attacks on LLMs, even current ones, remains substantial. For example, an attack consistently outperforms prior work on all settings, achieving an 88% ASR on harmful behaviour elicitation and a 98% ASR on exact harmful string elicitation on Vicuna-7B.
 
Furthermore, adversarial techniques transfer surprisingly well to other LLMs, even those that use entirely different tokens to represent the exact text. For instance, it's found that an adversarial example exclusively designed to attack Vicuna-7B transfers nearly always to larger Vicuna models. By generating adversarial examples to fool both Vicuna-7B and Vicuna-13b simultaneously, it also inferred that the adversarial examples transfer to Pythia, Falcon, Guanaco, and surprisingly, to GPT-3.5 (87.9%) and GPT-4 (53.6%), PaLM-2 (66%), and Claude-2 (2.1%).
 
---
 
