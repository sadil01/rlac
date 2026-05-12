---
title: "Assignment 2"
categories:
  - Blog

---
__Comparing Stylo and TF-IDF in a Science Fiction Corpus__


## Introduction

Science fiction is often discussed through themes: alien worlds, technological anxiety, scientific experimentation, postwar paranoia, and visions of the future. However, computational text analysis approaches literature differently. Rather than beginning with plot or interpretation, distant reading methods attempt to identify patterns through measurable textual features such as word frequency, vocabulary distribution, and stylistic repetition. This project compares two computational approaches applied to a corpus of eighteen science fiction texts from Project Gutenberg: the Stylo package in R and TF-IDF PCA clustering. While Stylo primarily analyzes stylistic similarity through the distribution of frequent function words, TF-IDF emphasizes distinctive thematic vocabulary. Comparing the two methods reveals that they organize the same corpus in fundamentally different ways.

The corpus contains works by Leigh Brackett, Philip K. Dick, Henry Kuttner, Andre Norton, H.G. Wells, and Marion Zimmer Bradley. These texts span different subgenres of science fiction, including planetary romance, dystopian fiction, invasion narratives, survival adventure, and speculative futurism. Because many of the texts emerged during or shortly after World War II and the beginning of the Cold War, the corpus also reflects anxieties surrounding technology, war, civilization, and humanity’s future.

This essay argues that Stylo and TF-IDF reveal different kinds of relationships within the corpus. Stylo stabilizes into relatively coherent authorial clusters, suggesting that stylistic habits remain consistent across texts by the same writer. TF-IDF, however, organizes the corpus into thematic and conceptual regions that frequently cross authorial boundaries. The comparison between the two methods ultimately demonstrates that style and content are not entirely separable, especially in genre fiction where thematic conventions influence both vocabulary and prose style.


## Stylo and Authorial Clustering

Stylo produced the clearest and most interpretable results at 4000 Most Frequent Words (MFW). Lower settings such as 2 or 10 MFW generated unstable and less meaningful relationships, while the higher settings stabilized the authorial clusters more effectively. At 4000 MFW, most authors grouped closely with their own works, suggesting that Stylo successfully detected recurring stylistic habits across the corpus.

![Stylo Cluster Analysis at 4000 MFW]({{ site.baseurl }}/assets/images/4000_mfw_ca.png)

*Figure 1: Stylo Cluster Analysis at 4000 MFW*

One of the strongest examples of stylistic stability was Andre Norton. Across nearly every Stylo visualization, Norton’s texts remained tightly clustered together. *Plague Ship*, *Star Hunter*, and *Voodoo Planet* consistently formed a coherent group, suggesting that Norton possesses a particularly stable stylistic signature. One explanation is that all three works operate within a similar adventure-oriented science fiction mode characterized by direct prose, immersive world-building, and relatively straightforward narrative pacing. Unlike other authors in the corpus, Norton does not shift dramatically between rhetorical forms or conceptual registers. In this sense, Norton becomes the clearest example of Stylo successfully identifying authorial style.

Philip K. Dick also clustered strongly within Stylo. Despite differences in plot and subject matter between *Second Variety*, *The Defenders*, and *The Variable Man*, Stylo repeatedly grouped these works together. This suggests that Dick’s stylistic habits remain stable even when his thematic concerns shift. Stylo therefore appears capable of distinguishing between content and style by prioritizing recurring linguistic patterns over narrative subject matter.

H.G. Wells produced a more complicated result. While *The War of the Worlds* and *The Island of Doctor Moreau* remained relatively close, *The Salvaging of Civilization* frequently separated from the rest of Wells’ works. This separation is significant because *The Salvaging of Civilization* is nonfiction rather than speculative narrative fiction. Stylo therefore appears highly sensitive not only to authorship, but also to rhetorical form and discourse structure. The nonfiction text’s argumentative and expository language disrupts the stylistic coherence of Wells’ fictional works.

The most theoretically interesting relationship in the Stylo analysis emerged between Leigh Brackett and Marion Zimmer Bradley. Although the corpus generally clustered by author, Brackett and Zimmer Bradley repeatedly appeared near one another, with occasional overlaps between their texts. This pattern suggests that Stylo is not detecting authorship alone. Instead, shared genre conventions associated with planetary romance and space opera may influence stylistic similarity. Their works share immersive narration, alien-world description, adventure pacing, and emotionally dramatic prose. The overlap between these writers therefore complicates the assumption that computational stylistics can cleanly separate individual authorial identity from generic convention.


## Bootcamp Consensus Tree

The Bootstrap Consensus Tree (BCT) did not introduce entirely new relationships, but it served as an important reliability check for the Stylo findings. Whereas the Cluster Analysis visualized one arrangement of the corpus, the consensus tree demonstrated which relationships remained stable across repeated sampling.

![Bootstrap Consensus Tree (3500–4000 MFW)]({{ site.baseurl }}/assets/images/BCT_3500-4000.png)

*Figure 2: Bootstrap Consensus Tree (3500–4000 MFW)*

The consensus tree confirmed several major patterns visible in the cluster analysis. Norton remained tightly grouped, reinforcing the claim that Norton possesses one of the most stable stylistic signatures in the corpus. Dick’s texts also remained relatively coherent, suggesting strong stylistic consistency despite thematic variation. Most importantly, Brackett and Zimmer Bradley continued to appear near one another. Because this overlap survives repeated sampling, it cannot easily be dismissed as an accidental feature of a single dendrogram. Instead, the consensus tree strengthens the argument that their similarities emerge from recurring genre conventions that influence both vocabulary and style.

Wells remained comparatively unstable within the consensus tree because *The Salvaging of Civilization* continued to diverge from Wells’ fictional works. Once again, Stylo appears sensitive to shifts in rhetorical mode, demonstrating that genre and discourse structure can partially override authorial clustering.


## TF-IDF and Thematic regions

Unlike Stylo, TF-IDF did not organize the corpus primarily by author. Instead, the TF-IDF PCA visualizations gradually stabilized into thematic and conceptual regions. As the number of MFW increased from 100 to 3000, the visualizations changed less dramatically, suggesting that the corpus’ semantic structure had stabilized.

![TF-IDF PCA Visualization at 100 MFW]({{ site.baseurl }}/assets/images/MFW100.png)

*Figure 3: TF-IDF PCA Visualization at 100 MFW*

At 100 MFW, the TF-IDF visualization appeared relatively loose and unstable. Authorial clusters were weak, particularly for Dick and Norton. However, certain thematic relationships already began to emerge. Wells’ *The Salvaging of Civilization* strongly separated from most of the corpus due to its nonfiction and political vocabulary. At the same time, Brackett and Zimmer Bradley already appeared relatively close, suggesting that their similarity extended beyond style alone.

![TF-IDF PCA Visualization at 3000 MFW]({{ site.baseurl }}/assets/images/MFW3000.png)

*Figure 4: TF-IDF PCA Visualization at 3000 MFW*

By 3000 MFW, the TF-IDF visualization stabilized into several distinct semantic neighborhoods. Wells’ works formed a coherent conceptual region despite the stylistic differences between fiction and nonfiction. This is one of the most important contrasts with Stylo. Whereas Stylo separated *The Salvaging of Civilization* because of its rhetorical form, TF-IDF reunited Wells’ texts because they shared scientific, futurist, and social vocabulary. TF-IDF therefore prioritizes conceptual similarity over stylistic structure.

Dick and Kuttner also formed a relatively coherent semantic region. Across multiple TF-IDF settings, their texts repeatedly occupied nearby conceptual space because they shared vocabulary associated with machines, technological danger, war, paranoia, and dystopian conflict. Stylo had largely separated these authors by stylistic habit, but TF-IDF reunited them through shared thematic concerns. This demonstrates that TF-IDF is far more willing to cross authorial boundaries when texts occupy similar conceptual worlds.

Norton formed a recognizable exploration and survival region centered around alien worlds, planetary travel, and frontier adventure. Although Norton was less tightly grouped in TF-IDF than in Stylo, the works still occupied a coherent semantic area because they shared recurring adventure-oriented vocabulary.

The most important recurring relationship remained the overlap between Brackett and Zimmer Bradley. Across both Stylo and TF-IDF, their texts repeatedly occupied nearby space. This persistence suggests that their similarity operates simultaneously at the level of thematic vocabulary and stylistic convention. Planetary romance and space opera shape not only what these texts discuss, but also how they narrate, describe, and structure their fictional worlds.

One especially striking outlier throughout the TF-IDF visualizations was Marion Zimmer Bradley’s *Jackie Sees a Star*. The text repeatedly separated from most of the corpus because its vocabulary differed from the dominant concerns of the other works. Whereas much of the corpus focused on war, conquest, machines, and planetary survival, *Jackie Sees a Star* emphasized childhood perspective, wonder, psychic communication, and emotional discovery. TF-IDF therefore proved highly sensitive to differences in semantic field and narrative focus.


## Comapring the Two Methods

The most important insight of this project emerges through the comparison between Stylo and TF-IDF. Stylo stabilizes into authorial clusters because it analyzes recurring stylistic habits through frequent words and syntactic tendencies. TF-IDF, however, stabilizes into semantic neighborhoods because it emphasizes distinctive vocabulary and conceptual similarity.

One of the clearest examples of this contrast is Wells. Stylo partially separated *The Salvaging of Civilization* because its nonfiction structure disrupted Wells’ stylistic profile. TF-IDF, however, reunited the text with Wells’ fiction because all three works share scientific and futurist conceptual vocabulary. The two methods therefore “read” literature differently.

Similarly, Dick remained highly stable within Stylo but more dispersed within TF-IDF. This suggests that Dick’s stylistic fingerprint remains relatively constant even when his thematic concerns vary significantly. TF-IDF instead prioritized the conceptual overlap between Dick and Kuttner because both writers repeatedly explored machines, technological anxiety, and dystopian conflict.

The recurring overlap between Brackett and Zimmer Bradley is perhaps the project’s most theoretically significant finding because it persists across both methods. Their similarity appears simultaneously thematic and stylistic. This challenges the assumption that style and content are fully separable categories. In genre fiction especially, thematic conventions shape vocabulary, pacing, narration, and descriptive habits simultaneously.

This observation connects closely to Ted Underwood’s discussion in *The Dangers of Distant Reading*. Underwood argues that computational methods always depend on what they choose to measure. Stylo and TF-IDF do not produce identical maps of the corpus because they prioritize different textual features. The methods therefore reveal different forms of literary similarity rather than objective truths about the texts themselves.


## Conclusion

This project demonstrates that computational methods can reveal meaningful relationships within a literary corpus, but those relationships depend heavily on methodology. Stylo proved highly effective at detecting recurring authorial habits, especially in the case of Norton and Dick, while TF-IDF mapped broader thematic and subgeneric structures across the corpus. Wells’ nonfiction text illustrated the tension between stylistic and conceptual similarity, while the recurring overlap between Brackett and Zimmer Bradley suggested that genre conventions influence both content and style simultaneously.

Ultimately, the comparison between Stylo and TF-IDF suggests that computational literary analysis does not replace interpretation; instead, it reframes interpretation around measurable textual patterns. Reading like a computer reveals that science fiction in this corpus is organized not only by authorship, but also by shared conceptual worlds: technological anxiety, futurist speculation, planetary exploration, and postwar visions of humanity’s future. The project therefore demonstrates both the power and the limitation of distant reading: what the computer sees depends on what the computer is taught to measure.


## Works Cited

Underwood, Ted. Distant Horizons: *Digital Evidence and Literary Change*. University of Chicago Press, 2019.

READY FOR GRADING