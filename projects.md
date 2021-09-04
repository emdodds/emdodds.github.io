---
layout: page
title: Projects
permalink: /projects/
---

## Machine Learning, Computer Vision (and Language)
At Yahoo I work primarily on machine learning research for vision and/or natural language applications. Some of this work leads to research publications, which are described here.

### Modality-Agnostic Attention Fusion for visual search with text feedback
<img src="../static/img/maaf.png" width="500px" height="auto" alt="Our text-image fusion mechanism uses Transformer attention to combine features from an image model and a text model." title="Our text-image fusion mechanism uses Transformer attention to combine features from an image model and a text model." align='left'>
[(paper)](https://arxiv.org/abs/2007.00145) <i> Eric Dodds, Jack Culpepper, Simao Herdade, Yang Zhang, Kofi Boakye </i> <br>
Visual search with text feedback provided an interesting (and potentially useful to Yahoo) testbed for combining signals from multiple modalities using dot-product attention. We found the technique effective once we got the details right, and we found some interesting and surprising phenomena in the text-image attention maps. We followed up this work with a study of pretraining and evaluation methods for this task, which is under review for publication (as of September 2021).


### Learning Embeddings for Product Visual Search with Triplet Loss and Online Sampling
<img src="../static/img/product_visual_search.png" width="300px" height="auto" alt="A model trained with triplet loss using an online sampling technique can retrieve relevant images from a large catalog. Five examples shown for each query, labeled correct retrievals boxed." title="A model trained with triplet loss using an online sampling technique can retrieve relevant images from a large catalog. Five examples shown for each query, labeled correct retrievals boxed" align='left'>
During my internship at Yahoo (then Verizon Media) I applied online sampling techniques for the triplet loss and found some other tricks to train state-of-the-art (at the time) models for visual search. Business applications have focused on matching products with content for commerce and advertisement. We also posted a [technical report](https://arxiv.org/abs/1810.04652) on the work to arXiv.

<br> <br>
## PhD: Theoretical Neuroscience / Physics
I completed my PhD in the physics department at UC Berkeley, but my thesis work under Mike DeWeese at the Redwood Center for Theoretical Neuroscience was only "physics" in the spirit of its quantitative methods. My PhD dissertation can be found [here](https://escholarship.org/content/qt1c05d34t/qt1c05d34t.pdf) and several major projects are described below.

### Spatial whitening in the retina may be necessary for V1 to learn a sparse representation of natural scenes
<img src="../static/img/natims_examples.png" width="300px" height="auto" alt="A V1 model with local learning recovers the sparse components of natural images, but only when the images are whitened in advance." title="A V1 model with local learning recovers the sparse components of natural images (top examples), but only when the images are whitened in advance." align='left'>
[(paper)](https://www.biorxiv.org/content/10.1101/776799v1.abstract) <i> Eric McVoy Dodds, Jesse Alexander Livezey, Michael Robert DeWeese (in preparation) </i> <br>
[Atick and Redlich](http://www.cnbc.cmu.edu/cns/papers/Atick-Redlich-NC92.pdf) showed that the receptive fields of retinal ganglion cells are consistent with these cells whitening their inputs from photoreceptors (while suppressing high-frequency noise). They suggested that such a representation might be a step towards a representation in terms of statistically independent atoms. We suggest that this particular step may be taken because it is a necessary prerequisite for learning in cortex, regardless of the other benefits of a representation without pairwise correlations.

A successful and well-studied [model](http://redwood.berkeley.edu/bruno/papers/nature-paper.pdf) of primary visual cortex (V1) simple cell function posits that V1 is optimized for sparse representations of natural scenes. Zylberberg and colleagues [showed](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002250) that this optimization could be (at least approximately) achieved using synaptically local learning mechanisms. That is, each synapse only needs access to its own current strength and the activity of the neurons that meet at that synapse to update its strength to improve the optimization. We show that these synaptically local mechanisms only drive the model to recover the sparse features of the data and form good sparse representations when the data is <i>whitened</i> before being input to the network.

Data is white in this sense if all directions have the same variance (the covariance matrix is proportional to the identity matrix); whitening is also known as sphering. Intuitively, a neuron that doesn't have access to other neurons' contributions to the network's representation will prefer the high-variance directions where its own contribution will be biggest. If the data is close enough to white, synaptically local mechanisms that decorrelate neurons' activities using lateral inhibition can deal with this problem. But raw natural images are too far from white for this to work.

### Sparse structure of natural sounds and natural images
<img src="../static/img/imsounds.png" width="300px" height="auto" alt="Sounds and images both have sparse linear features, but there are significant differences" title="An element of a sparse coding dictionary trained on speech spectrograms, and a log histogram of its linear projections onto the data. Similarly, an example for natural images." align='left'>
[(paper)](https://www.frontiersin.org/articles/10.3389/fncom.2019.00039/full) <i> Eric McVoy Dodds, Michael Robert DeWeese </i> <br>
We report on differences and similarities in the structure of sparse linear components of sets of natural sounds and natural images, and we show consequences of the differences for a neurally plausible model.

Since [Olshausen and Field showed](http://redwood.berkeley.edu/bruno/papers/nature-paper.pdf) that a network optimized to form sparse codes of natural image patches accounted for the receptive fields of simple cells in mammalian primary visual cortex, many studies have improved our understanding of sparse coding and the visual system. There has also been [some successful work](https://search.proquest.com/docview/204546620?pq-origsite=gscholar) [in the auditory domain](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002594), though the story there is less clear. It's interetesting that the principle of sparse coding seems to apply across multiple sensory modalities. My work with Mike is, as far as I know, the first to look at the sparse structure of data from two modalities side-by-side to better understand the universality of this principle and what differs between modalities. We also show that differences we observe in sparse coding of natural sounds have implications for [models with biological constraints](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002250).

My TensorFlow implementation of the ["locally competitve" sparse coding algorithm](http://www.mitpressjournals.org/doi/abs/10.1162/neco.2008.03-07-486) used in this work is [here](https://github.com/emdodds/DictLearner/tf_lca.py), and my python implementation of [Zylberberg's "Sparse and Independent Local network"](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002250) is [here](https://github.com/emdodds/SAILnet.).

We have submitted this work to a journal and hope to see it published soon!

### Causal efficient auditory coding
<i> Course project, Fall 2016 </i> <br>
<img src="../static/img/causalMPexample.PNG" width="150px" height="auto" title="Example of a synthesis filter for a causal efficient coding algorithm optimized for speech waveforms" align='left'>
As my course project for Bruno Olshausen's Neural Computation course, I extended the work of [Smith and Lewicki](https://search.proquest.com/docview/204546620?pq-origsite=gscholar) on efficient auditory coding by developing a version of their convolutional Matching Pursuit-based algorithm that respects causality when forming codes of input stimuli. That is, each coefficient is committed to the code using only the part of the signal prior to the time of that coefficient. This notion of causality is likely a constraint for the real auditory nerve.

My code for this project is [here](https://github.com/emdodds/causal-sparse-coding) and I implemented a (near) copy of Smith and Lewicki's method in TensorFlow [here](https://github.com/emdodds/matching-pursuit).


### Topographic sparse coding of speech
<img src="../static/img/topo.png" width="350px" height="auto" title="Topographic sparse coding dictionary trained on speech data" align='left'> A Berkeley undergrad named Teppei worked with me to apply [topographic ICA](http://www.mitpressjournals.org/doi/abs/10.1162/089976601750264992) to auditory data, an idea suggested by fellow Redwood student Jesse Livezey. I implemented a topographic version of the sparse coding network of [Olshausen and Field](http://www.sciencedirect.com/science/article/pii/S0042698997001697) in TensorFlow, which you can find [here](https://github.com/emdodds/DictLearner/blob/master/TopoSparsenet.py). We later discovered [something very similar](http://papers.nips.cc/paper/4703-the-topographic-unsupervised-learning-of-natural-sounds-in-the-auditory) had already been done, but our results look cool. We hoped this model could help us understand how cells in a region of the mammalian early auditory system are organized by the stimuli to which they respond, and maybe it will yet...



### Analysis of single-neuron recordings from rat auditory cortex
<img src="../static/img/favSTA.png" width="250px" height="auto" title="The spike-trigged average stimulus for one cell" align='left'>
When Vanessa, a student in the experimental side of the DeWeese lab, saw no structure in her hard-won single-neuron data, Mike brought his newest theory student (me) in to try some fancier analysis techniques. Sadly, this work yielded to other priorities when we convinced ourselves we weren't going to find anything. The image here shows a representative "spectro-temporal receptive field."

Along the way I did learn a lot about techniques for characterizing neural responses to stimuli. I also enjoyed coding a [python implementation](https://github.com/emdodds/MID) of [Sharpee, Rust, and Bialek's "Maximally Informative Dimensions"](http://www.mitpressjournals.org/doi/abs/10.1162/089976604322742010) algorithm for finding the linear subspace of the stimulus space with maximal mutual information with the neural spike train.
