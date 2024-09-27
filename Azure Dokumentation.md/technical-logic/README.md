---
description: The Technik that we used in ChatBot
---

# 🧑‍💻 Technical Logic

**RAG and LLM Architecture**

<figure><img src="../.gitbook/assets/ChristianDiagram RAG und LLM.png" alt=""><figcaption><p>RAG and LLM Dagramm</p></figcaption></figure>

The user asks a question (question...). This question is forwarded to a Large Language Model (LLM).&#x20;

**At the same time, the relevant documents are indexed:**

The documents are divided into smaller chunks. An embedding model creates a numerical representation (embeddings) for each chunk, for example in the form of a vector such as \[0.3, 0.1, 0.7]. The embeddings are then stored by a vector store. Based on the user's original question, a search for the relevant documents is carried out. The relevant documents are returned to the LLM, which prepares the answer.&#x20;

Finally, the user receives an answer based on the relevant documents.
