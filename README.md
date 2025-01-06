# Topic-Modelling-on-Neurology-with-LLM
This project explores a novel approach to analyzing neurological research documents, combining chain-of-thought reasoning with multi-label categorization.  It leverages the power of Sentence Transformers and BERT for semantic understanding and similarity calculation. Unlike traditional topic modeling, which often relies on statistical distributions of words to identify topics, this method focuses on the semantic meaning of text. This approach allows for a more nuanced understanding of the relationships between research questions and document content.

Traditional topic modeling techniques often struggle with identifying subtle relationships or specialized terminology within specific domains.  This project addresses this limitation by using sentence embeddings, capturing the semantic meaning of sentences rather than individual words.  This facilitates more accurate retrieval of relevant documents and enables a more refined analysis of complex research questions.

The project defines research prompts across categories (Disease, Type, Treatment, Prevention, Technology, Policy, and Other) based on specific keywords, and provides a function that calculates semantic similarity between a given query and document excerpts. These similarities are then used to rank and summarize the most relevant documents for a specific research query.

The project also explores using BERT embeddings for semantic analysis to calculate cosine similarity between the query and documents, offering an alternative method for comparison.

**Code Functionality:**

1. **Research Prompt Generation:**  The code defines a function `generate_research_prompts` that creates research questions based on a specified category (e.g., "Disease," "Treatment," "Technology") and a list of keywords. This is a crucial step for guiding research and analysis.

2. **Semantic Similarity and Chain-of-Thought Reasoning:**  The code uses Sentence Transformers (`paraphrase-MiniLM-L6-v2`) to calculate semantic similarity between a given question and a set of documents. This helps identify the most relevant documents for answering the question. The `chain_of_thought_answer` function then ranks documents based on their similarity to the question and constructs a summary of relevant excerpts, imitating a human-like reasoning process.

3. **BERT-based Cosine Similarity:** In addition to Sentence Transformers, the code leverages BERT (`bert-base-uncased`) to calculate cosine similarity between the question and documents. This provides another measure of semantic similarity. The code uses BERT's contextualized word representations for more refined comparisons.


**Comparison to Traditional Topic Modeling:**

Traditional topic modeling techniques (like Latent Dirichlet Allocation - LDA) aim to discover underlying topics within a collection of documents. They represent documents as mixtures of topics, and topics as distributions of words.  The core difference lies in their purpose and approach:

* **Purpose:** Traditional topic modeling is primarily *unsupervised*. It's about discovering hidden themes or subjects within a corpus *without* specific queries or questions in mind. The provided code, on the other hand, is more *query-driven*.  It focuses on answering specific questions by finding relevant information within a document set.

* **Approach:** Topic modeling identifies topics based on word co-occurrence patterns. The code uses pre-trained language models (Sentence Transformers and BERT) to understand the *meaning* and *semantic relationship* between words and sentences, making it more nuanced than simple word counts. The concept of "chain-of-thought" adds another layer by mimicking a reasoning process to prioritize the most pertinent parts of documents in answering a specific question. Topic models don't typically provide ranked documents or chain-of-thought summaries in response to a question.

* **Output:** Topic modeling outputs a set of topics and their associated words, along with topic distributions for each document.  The provided code's output is a targeted answer to a specific question, summarizing the relevant parts of documents based on semantic similarity.

**In Summary:**

The code offers a more targeted and question-answering oriented approach to text analysis compared to the broader topic discovery provided by traditional topic modeling techniques. The use of powerful sentence embeddings and the "chain-of-thought" concept allows the code to provide more contextually relevant answers based on specific research prompts or queries.
