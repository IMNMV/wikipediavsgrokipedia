Grokipedia vs Wikipedia

Simply, I was curious to see how similar/disimilar Grokipedia is from Wikipedia. 

These results do not make claims about the content being better or worse between either platform - simply, how different are they?

Methodology

Data: Full article text scraped from both platforms for 211 topics (Claude Sonnet 4.5 did webscrape on large amounts of controversial/news worthy sources. I added some additional topics I thought were missing from its initial list.

Embeddings: Each article encoded using all-MiniLM-L6-v2 sentence transformer (this creates 384-dimensional vectors). I've had decent work done with BERTopic model using this embedding model, and given my desire for good contextual awareness, I went with a transformer based approach rather
than a simpler approach such as word2vec.

Similarity: Pairwise cosine similarity computed between Grokipedia and Wikipedia embeddings for each topic. Range: 0 (completely different) to 1 (identical).

Visualization: UMAP dimensionality reduction projects 384D embeddings to 2D (n_neighbors=15, min_dist=0.1, cosine metric). Points are colored by similarity score (red=divergent, green=similar).

Note: Visual distance reflects thematic clustering; color indicates content similarity. A topic pair can be spatially close (similar theme) but different in color (different coverage).

Data available upon request.
