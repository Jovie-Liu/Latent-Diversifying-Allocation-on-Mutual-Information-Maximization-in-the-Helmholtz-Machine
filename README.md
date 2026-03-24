# Latent-Diversifying-Allocation-on-Mutual-Information-Maximization-in-the-Helmholtz-Machine

One of the author’s significant contributions is to address the latent state collapse in the Helmholtz machine when training with the wake-sleep algorithm by interleaving a mutual-information diversifying sampling scheme that promotes inter-layer information gains and communication efficiency, thus largely improving the model performance. This training scheme works as an auxiliary function empowering the original wake-sleep algorithm, while keeping its merits such as simplicity, local efficacy, and biological plausibility.

This work was first introduced in Chapter 2 of my [Ph.D. qualification writing](https://drive.google.com/file/d/1CNLO2FjDNW5RT0Zfc70ynZeVdm-KQsTH/view?pli=1), 2024, as an answer to the qualifying exam question by Prof. Sanjoy Dasgupta. It was later improved and evaluated on additional datasets, detailed in Chapter 2 of my [Ph.D. dissertation](https://www.proquest.com/openview/581cd124d0c14930d566ba9010cecd67/1?pq-origsite=gscholar&cbl=18750&diss=y), 2025. Here is a [pre-print](https://drive.google.com/file/d/1lj9kcIfja8ivIgsRGjZWSTAlB15Z5i3V/view?usp=sharing) of the first stage of this work.

---

The Helmholtz machine [[Peter Dayan, Geoffrey E. Hinton., 1995](https://www.gatsby.ucl.ac.uk/~dayan/papers/hm95.pdf)] is a hierarchical generative model implemented as a fully connected feedback neural network composed of stochastic binary neurons. Its architecture alternates between bottom-up recognition and top-down generation pathways—parameterized by weights $\phi$ and $\theta$, respectively—forming a bidirectional structure that parallels the hierarchical organization of cortical processing in the brain [[Karl Friston, 2008](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000211)]. The recognition network infers latent representations from observed data, while the generative network reconstructs sensory inputs from those latent variables, establishing a self-supervised loop of *analysis-by-synthesis*.

<img src="helmholtz.png" style="width:660px">
<caption><center> Figure 1: The Helmholtz Machine.</center></caption>

<br>
<br>

<img src="Wake_Sleep.png" style="width:800px">
<caption><center> Figure 2: Latent State Collapse in the Helmholtz Machine Training with the Wake-Sleep Algorithm. </center></caption>

<br>
<br>

When improved with the mutual information maximization algorithm:

<img src="MI_Maximization.png" style="width:800px">
<caption><center> Figure 3: Training Result with the Interleaved Mutual Information Maximization (MIM) Scheme. </center></caption>

<br>
<br>

Unlike the sampled instances, here is a record of the training dynamics of three algorithms:

<img src="Summary.png" style="width:800px">
<caption><center> Figure 4: Model performance on the vanilla wake-sleep algorithm, the interleaved MIM scheme, and the interleaved random perturbation. </center></caption>
<br>
<br>
This algorithm was tested on several synthetic datasets and demonstrated effectiveness. The simplified version, with substantially reduced computational complexity, was subsequently tested on the MNIST dataset and showed a noticeable improvement in generation quality.
<img src="MNIST_Gen.png" style="width:800px">
<caption><center> Figure 5:  Generated handwritten digits with the wake-sleep algorithm. </center></caption>

<br>
<br>
<br>

<img src="MNIST_MI.png" style="width:800px">
<caption><center> Figure 6:  Generated handwritten digits with the interleaved mutual information maximization algorithm. </center></caption>
