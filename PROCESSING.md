# Architecture & Trade-offs

## Processing Pipeline

```
Original text  →  Interlingua (AIL)  →  Core LLM Processing  →  Diffusion-based Decoder →  Human-readable output
```
* Original text — user input in any supported language.

* AIL (Artificial Interlingua Language) — compact, normalized representation used for all reasoning and parameter sharing.

* Core LLM Processing — the main language model trained only on AIL, reducing redundancy across multiple languages.

* Diffusion-based Decoder — reconstructs rich, natural human language from the compressed AIL representation.

* Human-readable output — final response, indistinguishable (in theory) from a multilingual native LLM.

## Advantages

* Model size reduction: one shared representation instead of many duplicated embeddings.

* Efficiency: faster inference, fewer parameters.

* Consistency: reasoning and factual grounding unified across languages.

## Risks & Limitations

* Loss of flexibility: the core model becomes specialized in AIL only, not directly multilingual.

* Dependency on translators: both input → AIL and AIL → output must be maintained and constantly improved.

* Post-processing challenges: reconstructing nuanced, stylistically rich answers requires advanced decoding.

* Diffusion cost: using diffusion models for decoding can reintroduce computational heaviness.
