# interlingua-llm
Exploring artificial compressed languages to improve efficiency, context usage, and cross-lingual unification in LLMs

# Artificial Languages for Efficient Training of Large Language Models

## Abstract
Large Language Models (LLMs) are typically trained on heterogeneous natural language corpora. This introduces redundancy, noise, and the necessity to allocate parameters for handling multiple linguistic structures. We propose the idea of using artificial intermediate languages (AILs) as a compressed, noise-free representation for training. Instead of mapping raw natural language directly into embeddings, a preprocessing stage could translate natural text into a canonical artificial language. This may reduce entropy, improve generalization, and lead to more efficient parameter utilization.

## Motivation

Training multilingual models incurs substantial computational overhead. Each natural language brings idiosyncratic grammar, orthography, and irregularities. LLMs must allocate capacity to disambiguate and represent these differences. An artificial language could provide:

* Compression: Removing redundant morphology and syntax.

* Normalization: Standardizing meaning representation across languages.

* Noise Reduction: Excluding low-quality or inconsistent samples.


## Method (Proposed)

* Artificial Language Design: Create a symbolic or token-based canonical language optimized for LLM consumption.

* Preprocessing Pipeline: Translate input natural languages into AIL before feeding them into the model.

* Model Training: Train on AIL directly, possibly with fewer layers or smaller embedding sizes.

Postprocessing/Decoding: Map model outputs back into natural languages for human interpretability.

## Discussion

* AIL could function analogously to Intermediate Representations (IRs) in compilers.

* This approach may decouple representation learning from communication in natural languages.

* Forward pass efficiency would not reduce the number of layers but could reduce hidden size requirements due to the lower entropy of input data.

* Potential drawbacks include the complexity of building robust bidirectional AIL-to-natural language mappers.

# Conclusion
Artificial languages could serve as a powerful abstraction for LLM training. While forward-pass depth (number of layers) remains constant, hidden dimension requirements and noise-related redundancy could decrease. This may yield significant GPU efficiency gains, enabling smaller, faster, and more interpretable models.