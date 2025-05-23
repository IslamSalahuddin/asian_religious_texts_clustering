# Religious Texts Clustering Analysis

This project analyzes Asian religious texts and Biblical literature using unsupervised learning techniques to uncover thematic patterns and relationships between different religious and philosophical traditions.

## Dataset

The analysis uses the [Asian Religious and Biblical Texts dataset](https://archive.ics.uci.edu/dataset/512/a+study+of+asian+religious+and+biblical+texts) from the UCI Machine Learning Repository. The dataset contains:

- 590 chapters from 8 different religious texts
- Each chapter is represented as a document-term matrix
- Original dimensionality: 8,267 terms per document
- Texts include both Asian philosophical works and Biblical wisdom literature

## Techniques Used

### Data Preparation
1. **Text Preprocessing**:
   - Lemmatization using WordNetLemmatizer for all word forms (nouns, verbs, adjectives, adverbs)
   - Stop words removal using NLTK's English stop words

2. **Dimensionality Reduction**:
   - Standardization using StandardScaler
   - Principal Component Analysis (PCA)
   - Optimal components selected to retain 95% variance

### Clustering Methods
Three different clustering approaches were evaluated:

1. **K-means**:
   - Evaluated using elbow method and silhouette scores
   - Range of clusters: 2-8
   - Showed less clear results due to overlapping boundaries

2. **Gaussian Mixture Model (GMM)**:
   - Evaluated using BIC scores and silhouette scores
   - Better suited for overlapping clusters
   - Clearly identified 2 optimal clusters

3. **Hierarchical Clustering**:
   - Used Ward's method with optimal ordering
   - Dendrogram visualization
   - Selected as final method due to clear cluster visualization
   - Cut threshold selected at distance=280

## Key Findings

### 1. Optimal Clustering
- Two distinct clusters identified consistently across methods
- High cluster purity:
  - Asian Philosophy cluster: 99% purity
  - Biblical Literature cluster: 98% purity
- Cluster size ratio: Asian Philosophy cluster is 4.4 times larger

### 2. Thematic Distinctions

**Asian Philosophy Cluster**
- Focus on inner journey and self-realization
- Key themes: mind, consciousness, nature, perception
- Emphasis on meditative and introspective approach

**Biblical Literature Cluster**
- Focus on divine authority and moral law
- Key themes: God, Lord, justice, righteousness
- Emphasis on practical moral guidance

### 3. Universal Themes
Both traditions share fundamental concerns:
- Human existence and mortality
- Nature of wisdom and knowledge
- Importance of moral action
- Concept of soul/spirit
- Path to enlightenment/righteousness

### 4. Cross-Border Cases
Interesting findings of thematic overlap:
- 5 Biblical chapters showing Asian philosophical characteristics
- 2 Asian texts showing Biblical literature characteristics
- These cases demonstrate the universality of certain spiritual themes

## Technologies Used
- Python 3.x
- Key libraries:
  - pandas & numpy for data manipulation
  - scikit-learn for machine learning
  - NLTK for text processing
  - matplotlib & seaborn for visualization
  - WordCloud for word frequency visualization

## Installation and Usage

1. Clone the repository
2. Install the required packages:
```bash
pip install -r requirements.txt
```
3. Run the Jupyter notebook:
```bash
jupyter notebook notebook.ipynb
```

## Requirements

The project requires Python 3.x and the following packages:
- numpy>=1.21.0
- pandas>=1.3.0
- matplotlib>=3.4.0
- seaborn>=0.11.0
- scikit-learn>=1.0.0
- nltk>=3.6.0
- wordcloud>=1.8.0

For detailed version requirements, see `requirements.txt`.

## Conclusion

The analysis demonstrates how modern data science techniques can provide quantitative insights into comparative religious studies. While Eastern and Western traditions show distinct approaches to wisdom and spirituality, they share fundamental human concerns and occasionally bridge their characteristic differences.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
