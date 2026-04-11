---
title: "Assignment 1"
date: 2026-03-03T15:34:30-04:00
categories:
  - blog
tags:
  - 
  -
---
__Psychological Interiority and Moral Ambiguity in Harry Potter Fanfiction__


## Introduction

Harry Potter fanfiction has long served as a creative space where readers reinterpret and expand the emotional and psychological dimensions of characters from J.K. Rowling’s original novels. Among the most frequently reimagined figures are Draco Malfoy and Severus Snape, two morally ambiguous characters whose motivations and inner lives remain partially obscured in the canonical series. While Rowling’s narrative centers primarily on Harry Potter’s perspective, fanfiction writers often redistribute narrative attention toward characters whose interior perspectives are only briefly glimpsed in the original texts.

This project investigates whether fanfiction provides greater psychological interiority to Draco Malfoy and Severus Snape than Rowling’s canonical works. Specifically, I examine whether fanfiction places cognitive and emotional language—words such as “felt” and “thought”-in close proximity to these characters’ names more frequently than the canon does. To explore this question, I analyze a small corpus consisting of three Rowling novels and three Harry Potter fanfiction texts. Using exploratory text analysis in Voyant Tools alongside custom analysis in RMarkdown notebooks, I measure the frequency of interiority markers appearing within five words of each character’s name.

The goal is not to replace interpretive reading but to use computational methods to detect patterns that might otherwise be difficult to observe across multiple texts. As Ted Underwood warns in The Risks of Distant Reading, quantitative methods can reveal broad tendencies but must be interpreted cautiously and contextualized within literary analysis. By combining Voyant’s exploratory visualizations with a normalized metric calculated in R, this analysis seeks to determine whether fanfiction systematically expands the narrative interiority of morally ambiguous characters.

## Corpus and Context

The corpus analyzed in this study includes six texts: three canonical novels by J.K. Rowling and three fanfiction works drawn from the Harry Potter fandom. The canonical texts include Harry Potter and the Prisoner of Azkaban, Harry Potter and the Half-Blood Prince, and Harry Potter and the Deathly Hallows. These novels represent different stages of the series in which Draco Malfoy and Severus Snape play increasingly complex roles in the narrative.

The fanfiction texts were selected from publicly available works written by members of the Harry Potter fandom community. Fanfiction surrounding Draco Malfoy and Severus Snape frequently explores redemption arcs, alternative motivations, or deeper emotional backstories for these characters. Unlike the original novels, which are largely focalized through Harry Potter’s perspective, many fanfiction stories adopt alternative narrative viewpoints or include more explicit depictions of characters’ internal thoughts and emotions.

This contrast between canonical narrative structure and fanfiction reinterpretation makes Draco and Severus particularly interesting subjects for computational comparison. In Rowling’s novels, Draco often appears as an antagonist whose motivations remain largely externalized, while Snape’s psychological complexity is revealed gradually and somewhat indirectly. In fanfiction, however, these characters frequently become central narrative figures whose emotional experiences are explored in greater detail.

Understanding the cultural and narrative contexts of these texts is essential before applying computational analysis. Without this background knowledge, patterns revealed through distant reading methods might be misinterpreted or stripped of their literary significance.

## Methods

To explore how psychological interiority is distributed across the corpus, I used two complementary computational approaches: exploratory analysis in Voyant Tools and custom analysis in RMarkdown.

Voyant Tools served as the primary environment for exploratory data analysis. Using Voyant’s Trends visualization, I examined the relative frequency of interiority markers appearing near character names across each document in the corpus. Queries such as "draco* felt"~5 and "severus* thought"~5 were used to identify instances where emotional or cognitive language appeared within five words of a character’s name. Voyant’s interactive interface allowed rapid comparison across multiple texts and helped identify preliminary patterns in how interior language was distributed.

However, Voyant’s exploratory visualizations do not automatically normalize results based on character mentions. To address this limitation, I used RMarkdown in Posit Cloud to compute a custom “interiority ratio.” This metric measures how frequently interior markers (“felt” and “thought”) appear within five words of a character’s name relative to the total number of times that character is mentioned. The ratio therefore captures the likelihood that a character mention is accompanied by interior language.

This normalization step is important because characters appear at different frequencies across texts. Without normalization, a character who simply appears more often might appear to have more interiority even if the proportion of interior language is low. The R analysis therefore provides a more comparable measure across texts.

Together, Voyant Tools and RMarkdown provided complementary perspectives. Voyant enabled exploratory discovery and interactive visualization, while R allowed more controlled computational analysis and the creation of customized visualizations that summarized patterns across the corpus.

## Findings

The computational analysis reveals clear differences in how psychological interiority is distributed between the canonical novels and fanfiction texts. In particular, fanfiction appears to provide more space for morally ambiguous characters such as Draco Malfoy and Severus Snape to express internal thoughts and emotions.

One way this pattern emerges is through the frequency of interiority markers such as *“felt.”* When examining how often “felt” appears near Draco and Severus across texts, fanfiction consistently shows higher relative frequencies than the canonical novels. This suggests that fanfiction authors more frequently situate these characters within emotional or introspective contexts.

![Felt Near Draco and Severus Across Texts](/assets/images/felt_graph.png)


A similar trend appears when analyzing *“thought”* as an interiority marker. Again, Draco and Severus are more often associated with cognitive language in fanfiction than in canonical texts. While canonical texts do include moments of introspection, these are less frequent and less consistently distributed across texts.

![Thought Near Draco and Severus Across Texts](/assets/images/thought_graph.png)

Together, these exploratory visualizations suggest a broader pattern: fanfiction tends to amplify the psychological interiority of characters who are more narratively restrained in the original novels. However, these trends alone do not fully account for differences in character frequency or text length, which can influence raw counts.

To allow for a more interactive exploration of these patterns, the visualization below provides a dynamic view of how these terms are distributed across the corpus:

<iframe style='width: 800px; height: 500px;' src='https://voyant-tools.org/?corpus=714378798e2d2648b797b5115c813fa2&query=%22draco*%20felt%22~5&query=%22severus*%20felt%22~5&view=Trends'></iframe>

While Voyant Tools highlights general trends, a more controlled computational analysis using RMarkdown provides a clearer comparison by normalizing interiority markers relative to character mentions. This approach ensures that differences are not simply due to how often a character appears, but rather how they are portrayed when they do appear.

![Psychological Interiority of Draco and Severus](/assets/images/r_bar_chart.png)

The normalized results confirm the earlier observations: both Draco and Severus exhibit higher levels of psychological interiority in fanfiction than in canonical texts. Draco, in particular, shows a noticeable increase, indicating that fanfiction significantly expands his emotional and cognitive representation. Severus also demonstrates increased interiority, though the difference is more moderate.

Importantly, this does not suggest that these characters lack depth in the canonical texts. Rather, it indicates that fanfiction redistributes narrative attention, allowing secondary or morally complex characters greater access to introspection and emotional expression. In this sense, fanfiction functions as a space for reinterpreting and deepening character psychology beyond the constraints of the original narrative.

## Discussion and Methodological Reflection

This analysis demonstrates how computational tools can reveal patterns in character representation that are difficult to observe through close reading alone. While Voyant Tools was effective for identifying general trends—such as increased proximity between interiority markers and character names in fanfiction—it remained limited in its ability to account for differences in character frequency and text length. By contrast, the RMarkdown analysis provided a normalized measure of interiority, allowing for more reliable comparison across texts. This distinction was crucial, as it ensured that differences reflected changes in representation rather than simple differences in how often characters appeared.

The results suggest that fanfiction redistributes psychological interiority toward morally ambiguous characters. Both Draco and Severus exhibit higher interiority ratios in fanfiction, indicating that these texts more frequently situate them within emotional and cognitive frameworks. This supports the idea that fanfiction expands narrative attention beyond the constraints of the original novels.

At the same time, this method has important limitations. As Ted Underwood argues, distant reading risks oversimplifying complex literary phenomena by reducing them to quantifiable patterns (Underwood 143). In this case, using words like “felt” and “thought” as proxies for interiority captures only a narrow dimension of character depth. Additionally, proximity-based queries do not guarantee meaningful relationships, meaning that results should be interpreted as patterns rather than definitive claims.

## Conclusion

Overall, this analysis shows that fanfiction functions as a space for reinterpreting and expanding the psychological depth of characters such as Draco Malfoy and Severus Snape. By combining exploratory and computational methods, this project highlights both the potential and the limitations of distant reading, demonstrating how digital tools can complement—but not replace—literary interpretation.

## Works Cited

Underwood, Ted. *Distant Horizons: Digital Evidence and Literary Change*. University of Chicago Press, 2019.


Ready for grading!



