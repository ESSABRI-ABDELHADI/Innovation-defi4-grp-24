
# Character Network Extraction in Isaac Asimov's Foundation Series

This project explores automatic extraction of character networks from texts in Isaac Asimov's *Foundation* series. It leverages Natural Language Processing (NLP) techniques to detect named entities and interactions between characters across chapters, visualizing these relationships in a graph structure.

## Project Overview
This project uses multiple NLP models, including **SpaCy**, **Camembert-NER**, and **Flair**, to identify named entities (characters) and build network graphs representing their interactions. By analyzing co-occurrences of character mentions within specified textual ranges, we construct a network of relationships and visualize them for each chapter.

## Requirements
- Python 3.x
- Jupyter Notebook
- NLP libraries: SpaCy, Flair, and Camembert (Hugging Face Transformers)
- NetworkX for graph construction and manipulation
- Pandas and Numpy for data processing
- Matplotlib/Seaborn for visualization (optional)

Install the dependencies using:
```bash
pip install -r requirements.txt
```

## Usage
### Data Preparation
The dataset consists of chapters from *Foundation* novels, preprocessed to remove unwanted formatting. Organize the text files within the `data` folder.

### Running Notebooks
1. **NER_with_Spacy.ipynb**: Detects named entities using the SpaCy model.
2. **Ner_with_Flair.ipynb**: Alternative NER approach using the Flair model for entity detection.
3. **Network_withoutAlias_Camembert.ipynb**: Constructs the character network based on initial detected entities without alias resolution.
4. **PersoNetwork_Camembert.ipynb**: Finalizes character networks with alias resolution and relationship weights.

### Output
Results include CSV files and visual graphs stored in the `fig` directory. The graphs are exported as `.gexf` files compatible with Gephi for detailed analysis.

## Methodology
### Entity Recognition
We utilize SpaCy, Camembert-NER, and Flair for Named Entity Recognition (NER) to identify characters. Each model's output is compared to enhance entity detection accuracy.

### Network Construction
Character interactions are defined by their co-occurrence within a specified range in the text. Each chapter's interactions are visualized as nodes (characters) and edges (relationships) in a graph, where edge weights indicate interaction frequency. NetworkX is used for graph construction.

## Results
Character network graphs reveal the relationships and central figures in each chapter, visualizing the dynamics between key characters in the *Foundation* series. Alias resolution consolidates character names for more accurate network representation.

## References
- [SpaCy Documentation](https://spacy.io/)
- [Hugging Face Transformers for Camembert](https://huggingface.co/transformers/model_doc/camembert.html)
- [Flair for NLP](https://github.com/flairNLP/flair)
- Asimov, I. *Foundation* series texts used for analysis.
