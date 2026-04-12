# Arabic-Toxicity-Datasets

## Dataset 1 - Superset:

This dataset is a superset of posts annotated as hateful or not. It results from the **preprocessing and merge** of all available Arabic hate speech datasets in April 2024. These datasets were identified through a systematic survey of hate speech datasets conducted in early 2024. We only kept datasets that:

- are documented
- are publicly available or could be retrieved with the Twitter API
- focus on hate speech

Size: 449,078

Class Distribution:

- hateful/toxic: 3.7% (16,546)
- neutral: 96.3% (432,532)

Original shape:

- **text:** the annotated post
- **labels:** annotation of whether the post is hateful (== 1) or not (==0). As datasets have different annotation schemes, we systematically binarized the labels.
- **source:** origin of the data (e.g., Twitter)
- dataset: dataset the data is from (see "Datasets" part below)
- **nb_annotators:** number of annotators by post
- **tweet_id:** tweet ID where available
- **post_author_country_location:** post author country location, when it could be inferred.

Modified shape: (dropped redundant columns)

- **text:** the annotated post
- **labels:** annotation of whether the post is hateful (== 1) or not (==0). As datasets have different annotation schemes, we systematically binarized the labels.

## Dataset 2 - MAHED:

All content in the related datasets was sourced from public social media platforms, anonymized to protect user privacy, and **annotated by native Arabic speakers**.

The annotation process achieved a high inter-annotator agreement, with a **Cohen’s Kappa score exceeding 0.85**, indicating strong consistency among annotators.

### Task1:

Classifies Arabic text into one of three categories: “hate”, “hope”, and “not_applicable”

Size: 9,843 (6,890 training, 1,476 validation, 1,477 for testing)

Class Distribution:

- hate: 18.8% (1,848)
- hope: 27.7% (2,723)
- NA: 53.5% (5,271)

Original shape:

- **text**
- **label:** hope, hate, not_applicable

Modified shape: (mapped labels to 0 and 1)

- **text**
- **labels:** hateful (== 1) not hateful (==0)

### Task2:

Multitask Learning for Emotion (12 emotions), Offensive Content, and Hate Detection

Size: 8,515

Class Distribution:

- Offensive: 29.1% (2,477)
- Not Offensive: 70.9% (6,038)

Original shape:

- **text**
- **Emotion:** Neutral, Anger, Anticipation, Disgust, Fear, Joy, Love, Optimism, Pessimism, Sadness, Surprise, Confidence
- Offensive: yes, no
- Hate: hate, not_hate, NaN

Modified shape: (mapped "Offensive" label to 0 and 1, dropped redundant data)

- **text**
- **labels:** hateful (== 1) not hateful (==0)

### Task3:

Multimodal Hateful Meme Detection

Size: 3,562

Class Distribution:

- propaganda:
  - &nbsp; propaganda: 28.1% (2200)
  - &nbsp; not propaganda: 71.9% (861)
- **hate:**
  - &nbsp; hate: 13.0% (398)
  - &nbsp; not hate: 87% (2663)
- fine_grained hate:
  - &nbsp; sarcasm: 8% (242)
  - &nbsp; humor: 78.7% (2409)
  - &nbsp; inciting violence: 0.9 (27)
  - &nbsp; mocking: 6.6% (201)
  - &nbsp; other: 1% (31)
  - &nbsp; exclusion: 0.3% (9)
  - &nbsp; dehumanizing: 0.5% (16)
  - &nbsp; contempt: 2.3% (70)
  - &nbsp; inferiority: 0.6% (19)
  - &nbsp; slurs: 1.2% (37)

Original shape:

Modified shape: (mapped "Offensive" label to 0 and 1, dropped redundant data)

- **text**
- **labels:** hateful (== 1) not hateful (==0)

## Dataset 3 - Twitter Corpus:

This dataset we collected in April 2019. It contains 58K Arabic tweets tweets annotated in positive and negative labels. The dataset is balanced and collected using positive and negative **emojis lexicon**.

Size: 58,000 (47K training, 11K test)

Class Distribution:

- negative: 49.8% (28,282)
- positive: 50.2% (28,513)

Original shape:

two tables, one for negative posts and the other for positive posts:

- Column 0: pos/neg
- Column 1: text

Modified shape:

- **text**
- **labels:** hateful (== 1) not hateful (==0)
