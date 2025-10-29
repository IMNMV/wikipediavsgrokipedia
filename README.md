# Grokipedia vs Wikipedia, a Content Divergence Analysis

## Why

I was curious to see how similar or dissimilar Grokipedia is from Wikipedia. These results do not make claims about the content being better or worse between either platform—simply, how different are they?

## Methodology

### Data Collection

Full article text scraped from both platforms for 211 topics. Claude Sonnet 4.5 performed initial web scraping on controversial and newsworthy sources. I manually added additional topics that were missing from its initial list.

### Embeddings

Each article was encoded using the **all-MiniLM-L6-v2** sentence transformer, which creates 384-dimensional vectors. I selected this model based on prior work with BERTopic, where it demonstrated strong performance. Given my need for good contextual awareness, I opted for a transformer-based approach rather than simpler methods like word2vec.

### Similarity Measurement

Pairwise cosine similarity was computed between Grokipedia and Wikipedia embeddings for each topic.

- **Range:** 0 (completely different) to 1 (identical)
- **Interpretation:** Higher values indicate greater semantic alignment

### Visualization

UMAP dimensionality reduction projects the 384-dimensional embeddings into 2D space for visualization.

**Parameters:**
- `n_neighbors = 15`
- `min_dist = 0.1`
- `metric = "cosine"`

Points are colored by similarity score (red = divergent, green = similar).

Visual distance reflects thematic clustering; color indicates content similarity. A topic pair can be spatially close (similar theme) but different in color (different coverage).

---

