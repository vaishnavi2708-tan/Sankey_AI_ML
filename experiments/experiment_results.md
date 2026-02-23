Experiment Results – AI Study Assistant (Computer Networks)

1. Experiments

Baseline (Fixed-Size Chunks):
PDFs were split every 500 characters. Embeddings stored in ChromaDB; top 5 chunks retrieved for Mistral to answer. Worked well for simple factual questions, but conceptual answers were often incomplete or verbose. Sentence breaks were sometimes awkward, and OCR errors caused clarity issues.

Improved (Sentence-Based Chunks):
Text split by complete sentences (min 40 characters). Structured prompts used. Produced concise, focused answers, preserved meaning, and handled OCR artifacts better. Slightly longer chunking time, but overall retrieval was faster and more precise.

2. Comparison

| Aspect              | Fixed-Size | Sentence-Based |
| ------------------- | ---------- | -------------- |
| Chunks              | ~2,000     | ~1,500         |
| Semantic Integrity  | Broken     | Preserved      |
| Conceptual Accuracy | Partial    | Complete       |
| Answer Clarity      | Medium     | High           |
| Processing Time     | ~45.5s     | ~41.3s         |

3. Key Findings & Recommendations

* Sentence-based chunking improves answer quality, clarity, and semantic consistency.
* Smaller, semantically complete chunks outperform fixed-size chunks.
* Open-source tools (Mistral + Sentence-Transformers + ChromaDB) provide a cost-effective, local solution.
* Use structured prompts and filter out very short chunks (<40 chars).

Future Improvements: semantic chunking, query expansion, re-ranking, user interface.

4. Decision-Making Rationale

* Sentence-based chunks preserve meaning, improve retrieval, and produce concise answers.
* Open-source stack is reproducible, local, and cost-free.
* Mistral + Sentence-Transformers balance performance, speed, and usability.


