# Awesome-LLM-Hallucination

1. **Why Does ChatGPT Fall Short in Providing Truthful Answers?** [link](https://arxiv.org/abs/2304.10513) `arXiv'23`

This paper attributes untruthful answers from LLMs into four types of errors: 1) **comprehension error** of user queries; 2) **specificity errors** - fail to provide answer in the an expected level of specificity; 3) **reasoning errors** - mistakes in logical reasoning; 4) **facutality errors** - mainly result from knowledge memorization and recall.

Among these, factuality errors are the most common and severe. The paper argues that we can use **simple synthetic tasks** to probe models' capabilities on knowledge memorization and recall. The paper also suggests we can use **external knowledge base** to improve knowledge memorization and **triggers or cues** to improve knowledge recall.

2. **Towards Fewer Hallucinations in Knowledge-Grounded Dialogue Generation via Augmentative and Contrastive Knowledge-Dialogue** [link](https://aclanthology.org/2023.acl-short.148/) `ACL'23`

This paper was motivated by an observation: current LLMs training often solely rely on golden samples, but in real life, the query given by users are often not accurate and noisy, therefore it's important for models to learn how to handle incorrect knowledge in user queries.

Therefore the authors propose to **train the model on examples with different levels of incorrect knowledge** (augmentatively altered (minor changes) and contrastively altered (major errors) knowledge samples). Alongside the incorrect knowledge, it designs responses that are **euphemistic or vaguely correct**.

3. **DoLa: Decoding by Contrasting Layers Improves Factuality in Large Language Models** [link](https://arxiv.org/abs/2309.03883) `arXiv'23`

This paper identifies that factul knowledge are distributioned unevenly across layers in LLMs, and the earlier layers are more likely to produce factual errors. Therefore, the authors contrast project of later layers against the earlier layers (on the vocab space) during predicting the next token.

4. **Attention Satisfies: A Constraint-Satisfaction Lens on Factual Errors of Language Models** [link](https://arxiv.org/abs/2309.15098) `arXiv'23`

This paper propose SAT Probe, a method probing attention patterns, that can predict factual errors.

5. **Fine-tuning Language Models for Factuality** [link](https://arxiv.org/abs/2311.08401) `arXiv'23`

This paper generate a factuality dataset automatically, by automated factuality judging systems (external knowledge base or model’s confidence scores). Then models are fine-tuned with DPO to improve factuality.

6. **Teaching Language Models to Hallucinate Less with Synthetic Tasks** [link](https://arxiv.org/abs/2310.06827) `arXiv'23`

This paper propose to train LLMs on simple synthetic tasks where huallucination are common and easy to detect, with prompt-tuning method. Then the tuned-prompt are be used directly in real-life tasks.

7. **GRATH: Gradual Self-Truthifying for Large Language Models** [link](https://arxiv.org/abs/2401.12292) `arXiv'24`

Again, another paper that generate correct-incorrect answer pairs, and fine-tune the model with DPO.

8. **Self-Contradictory Hallucinations of Large Language Models: Evaluation, Detection, and Mitigation** [link](https://arxiv.org/abs/2305.15852) `ICLR'24`

This paper propose methods to automatically detect and mitigate self-contradictions in LLMs outputs. It is training-free so is thus applicable to black-box models.
