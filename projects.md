---
layout: page
title: Projects
permalink: /projects/
---

### Spatial whitening in the retina may be necessary for V1 to learn a sparse representation of
natural scenes
<img src="../static/img/imgsounds.png" width="300px" height="auto" alt="A V1 model with local learning recovers the sparse components of natural images, but only when the images are whitened in advance." title="A V1 model with local learning recovers the sparse components of natural images (top examples), but only when the images are whitened in advance.">
<i> Eric McVoy Dodds, Jesse Alexander Livezey, Michael Robert DeWeese (submitted to Cosyne 2018) </i> <br>
[Atick and Redlich](http://www.cnbc.cmu.edu/cns/papers/Atick-Redlich-NC92.pdf) showed that the receptive fields of retinal ganglion cells are consistent with these cells whitening their inputs from photoreceptors (while suppressing high-frequency noise). They suggested that such a representation might be a step towards a representation in terms of statistically independent atoms. We suggest that this particular step may be taken because it is a necessary prerequisite for learning in cortex, regardless of the other benefits of a representation without pairwise correlations.

A successful and well-studied [model](http://redwood.berkeley.edu/bruno/papers/nature-paper.pdf) of primary visual cortex (V1) simple cell function posits that V1 is optimized for sparse representations of natural scenes. Zylberberg and colleagues [showed](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002250) that this optimization could be (at least approximately) achieved using synaptically local learning mechanisms. That is, each synapse only needs access to its own current strength and the activity of the neurons that meet at that synapse to update its strength to improve the optimization. We show that these synaptically local mechanisms only drive the model to recover the sparse features of the data and form good sparse representations when the data is <i>whitened</i> before being input to the network. 

Data is white in this sense if all directions have the same variance (the covariance matrix is proportional to the identity matrix); whitening is also known as sphering. Intuitively, a neuron that doesn't have access to other neurons' contributions to the network's representation will prefer the high-variance directions where its own contribution will be biggest. If the data is close enough to white, synaptically local mechanisms that decorrelate neurons' activities using lateral inhibition can deal with this problem. But raw natural images are too far from white for this to work. 

### Sparse structure of natural sounds and natural images
<img src="../static/img/imsounds.png" width="300px" height="auto" alt="Sounds and images both have sparse linear features, but there are significant differences" title="An element of a sparse coding dictionary trained on speech spectrograms, and a log histogram of its linear projections onto the data. Similarly, an example for natural images." align='left'>
<i> Eric McVoy Dodds, Michael Robert DeWeese (article in preparation) </i> <br>
We report on differences and similarities in the structure of sparse linear components of sets of natural sounds and natural images, and we show consequences of the differences for a neurally plausible model. 

Since [Olshausen and Field showed](http://redwood.berkeley.edu/bruno/papers/nature-paper.pdf) that a network optimized to form sparse codes of natural image patches accounted for the receptive fields of simple cells in mammalian primary visual cortex, many studies have improved our understanding of sparse coding and the visual system. There has also been [some successful work](https://search.proquest.com/docview/204546620?pq-origsite=gscholar) [in the auditory domain](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002594), though the story there is less clear. It's interetesting that the principle of sparse coding seems to apply across multiple sensory modalities. My work with Mike is, as far as I know, the first to look at the sparse structure of data from two modalities side-by-side to better understand the universality of this principle and what differs between modalities. We also show that differences we observe in sparse coding of natural sounds have implications for [models with biological constraints](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002250).

My TensorFlow implementation of the ["locally competitve" sparse coding algorithm](http://www.mitpressjournals.org/doi/abs/10.1162/neco.2008.03-07-486) used in this work is [here](https://github.com/emdodds/DictLearner/tf_lca.py), and my python implementation of [Zylberberg's "Sparse and Independent Local network"](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1002250) is [here](https://github.com/emdodds/SAILnet.).

We hope to submit a paper on this work very soon!

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

