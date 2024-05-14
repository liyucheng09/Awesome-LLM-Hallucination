# Awesome-LLM-Hallucination

My personal paper selection for LLM Hallucination.

---

### 1. Analysis

* [Analysis] **Why Does ChatGPT Fall Short in Providing Truthful Answers?** [link](https://arxiv.org/abs/2304.10513) `arXiv'23`

This paper attributes untruthful answers from LLMs into four types of errors: 1) **comprehension error** of user queries; 2) **specificity errors** - fail to provide answer in the an expected level of specificity; 3) **reasoning errors** - mistakes in logical reasoning; 4) **facutality errors** - mainly result from knowledge memorization and recall.

* [Analysis] **Attention Satisfies: A Constraint-Satisfaction Lens on Factual Errors of Language Models** [link](https://arxiv.org/abs/2309.15098) `arXiv'23`

This paper propose SAT Probe, a method probing attention patterns, that can predict factual errors.

* [Analysis] **Do Large Language Models Know What They Don’t Know?** [link](https://arxiv.org/pdf/2305.18153) `ACL'23-findings`

Would LLMs have the self-awareness of admiting their own limitations? Such as, identiying their unknowable questions? This paper developed a new dataset contains five types of unanswerable questions and their answerable counterparts.


### 2. Fine-tuning

* [Fine-tuning] **Towards Fewer Hallucinations in Knowledge-Grounded Dialogue Generation via Augmentative and Contrastive Knowledge-Dialogue** [link](https://aclanthology.org/2023.acl-short.148/) `ACL'23`

This paper was motivated by an observation: current LLMs training often solely rely on golden samples, but in real life, the query given by users are often not accurate and noisy, therefore it's important for models to learn how to handle incorrect knowledge in user queries.

Therefore the authors propose to **train the model on examples with different levels of incorrect knowledge** (augmentatively altered (minor changes) and contrastively altered (major errors) knowledge samples). Alongside the incorrect knowledge, it designs responses that are **euphemistic or vaguely correct**.

* [Fine-tuning] **Fine-tuning Language Models for Factuality** [link](https://arxiv.org/abs/2311.08401) `arXiv'23`

This paper generate a factuality dataset automatically, by automated factuality judging systems (external knowledge base or model’s confidence scores). Then models are fine-tuned with DPO to improve factuality.

* [Fine-tuning] **Teaching Language Models to Hallucinate Less with Synthetic Tasks** [link](https://arxiv.org/abs/2310.06827) `arXiv'23`

This paper propose to train LLMs on simple synthetic tasks where huallucination are common and easy to detect, with prompt-tuning method. Then the tuned-prompt are be used directly in real-life tasks.

* [Fine-tuning] **GRATH: Gradual Self-Truthifying for Large Language Models** [link](https://arxiv.org/abs/2401.12292) `arXiv'24`

Again, another paper that generate correct-incorrect answer pairs, and fine-tune the model with DPO.

### 3. Decoding

* [Decoding] **Faithfulness-Aware Decoding Strategies for Abstractive Summarization** [link](https://aclanthology.org/2023.eacl-main.210/) `EACL'23`

This paper propose two new decoding methods: 1) rank beams based on faithfulness score; 2) lookahead heuristics: predict unfinished beams' faithfulness score to find the more faithful continuation.

Among these, factuality errors are the most common and severe. The paper argues that we can use **simple synthetic tasks** to probe models' capabilities on knowledge memorization and recall. The paper also suggests we can use **external knowledge base** to improve knowledge memorization and **triggers or cues** to improve knowledge recall.

* [Decoding] **DoLa: Decoding by Contrasting Layers Improves Factuality in Large Language Models** [link](https://arxiv.org/abs/2309.03883) `arXiv'23`

This paper identifies that factul knowledge are distributioned unevenly across layers in LLMs, and the earlier layers are more likely to produce factual errors. Therefore, the authors contrast project of later layers against the earlier layers (on the vocab space) during predicting the next token.

* [Decoding] **KCTS: Knowledge-Constrained Tree Search Decoding with Token-Level Hallucination Detection** [link](https://arxiv.org/abs/2310.09044) `arXiv'23.10`

This paper propose to use a knowledge classifier score and Monte Carlo Tree Search to guide the decoding process.

### 4. Post processing

* [Post-processing] **Self-Contradictory Hallucinations of Large Language Models: Evaluation, Detection, and Mitigation** [link](https://arxiv.org/abs/2305.15852) `ICLR'24`

This paper propose methods to automatically detect and mitigate self-contradictions in LLMs outputs. It is training-free so is thus applicable to black-box models.
