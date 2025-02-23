# Natural-Language-Processing---Word-Embeddings-Analysis

Project Overview
This project explores various distributional semantics techniques to analyze word representations using statistical methods such as co-occurrence counting, TF-IDF, and Pointwise Mutual Information (PMI). The evaluations are performed on well-known similarity datasets, including MEN and SimLex-999, to assess how well different word vector representations capture semantic relationships.

Key Components
1. Distributional Counting
Implemented a word co-occurrence counting approach using a context window of varying sizes (w = 3 and w = 6).
Analyzed the impact of window size on word pair co-occurrences.
Example:
"Chicken" and "the" → Count: 52 (w=3), 103 (w=6)
"Coffee" and "the" → Count: 95 (w=3), 201 (w=6)
Larger window sizes capture more context, leading to higher co-occurrence counts.
2. TF-IDF-Based Word Vectors
Utilized Inverse Document Frequency (IDF) to enhance semantic representation.
Evaluated performance using the Spearman correlation on similarity datasets:
MEN dataset: Correlation improved from 0.2251 to 0.2494.
SimLex-999 dataset: Correlation improved from 0.0588 to 0.0729.
IDF weighting enhances word association accuracy by reducing the influence of common words.
3. PMI-Based Word Representations
Computed Pointwise Mutual Information (PMI) to measure word association strength.
Example: PMI values for "coffee" show strong association with "tea" but weak association with function words like "he".
PMI-based vectors demonstrated better performance than count-based and IDF-based vectors:
MEN dataset: Outperformed both methods.
SimLex-999 dataset: Provided better correlation but remained low across all approaches.
4. Quantitative Analysis
Compared three methods (Count-based, IDF-based, and PMI-based) under different window sizes and vocabulary constraints.
Findings:
PMI performed best for MEN.
Larger window sizes improved MEN performance but decreased SimLex-999 correlation.
IDF method showed better MEN results with larger vocabularies.
5. Qualitative Analysis - Nearest Neighbor Evaluation
Evaluated nearest neighbors for different query words and window sizes:
Judges (w = 1, w = 6) → Neighbors remained semantically close.
Effect of Part-of-Speech:
Nouns: (e.g., "coffee") - Broader connections in larger windows.
Verbs: (e.g., "transported") - Larger windows introduced related nouns.
Adjectives: (e.g., "large") - Shifted from synonyms to contextual words.
Prepositions: (e.g., "under") - Larger windows led to noun-based neighbors.
6. Multisense Word Analysis
Investigated the effect of window size on words with multiple senses (e.g., bank, apple, cell).
Bank:
w=1 → "side", "coast" (riverbank)
w=6 → "capital", "corporation" (finance)
Apple:
w=1 → "pine", "cherry" (fruit)
w=6 → "Microsoft", "computers" (technology)
Larger window sizes shift the meaning based on broader context.
Conclusions
PMI is the most effective method for capturing semantic relationships, especially in MEN.
TF-IDF weighting improves word associations but has limitations.
Window size influences results, with larger windows benefiting general associations but reducing precision for fine-grained semantic datasets.
Word meaning shifts with different context sizes, highlighting the importance of multi-sense representation.
Repository Details
Dataset: Wiki-1Percent, MEN dataset, SimLex-999
Techniques Used: Co-occurrence counting, TF-IDF, PMI
Languages & Tools: Python (NumPy, Pandas), Natural Language Processing (NLP)
