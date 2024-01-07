# What To Learn? A Survey On Pretext Tasks for Graph Self-Supervised Learning

This is a extensive and continuously updated compilation of graph SSL literature categorized by the knowledge-based taxonomy, proposed by our paper "[What To Learn? A Survey On Pretext Tasks for Graph Self-Supervised Learning]()". Here every pretext and the adapted downstream tasks of each paper are listed and briefly explained. You can find all the sub-tasks and their corresponding papers along with their PDF and source code links in the sections below, as well as additional pretexts and literature not detailed in our paper. The aim of this list is to assist in designing new self-supervised graph pretexts for better SSL performance on GNNs, graph transformers, LLM-based graph foundation models, and more graph learning frameworks.

# Contents

* [Relevant surveys](#relevant-surveys)
* Microscopic pretexts
  * [Node features](#node-features)
  * [Node properties](#node-properties)
  * [Links](#links)
  * [Context](#context)
* Macroscopic pretexts
  * [Long-range similarities](#long-range-similarities)
  * [Motifs](#motifs)
  * [Clusters](#clusters)
  * [Global structure](#global-structure)
  * [Manifolds](#manifolds)
* [Task adaptation strategies](#task-adaptation-strategies)

# Relevant surveys

| Paper                                                        | Venue      |
| ------------------------------------------------------------ | ---------- |
| [Self-supervised Learning on Graphs: Deep Insights and New Direction](https://arxiv.org/abs/2006.10141) | arXiv:2006 |
| [Self-supervised Learning on Graphs: Contrastive, Generative, or Predictive](https://arxiv.org/abs/2105.07342) | TKDE'21    |
| [An Empirical Study of Graph Contrastive Learning](https://arxiv.org/abs/2109.01116) | NeurIPS'21 |
| [Self-Supervised Learning of Graph Neural Networks: A Unified Review](https://arxiv.org/abs/2102.10757) | TPAMI'22   |
| [Graph Self-Supervised Learning: A Survey](https://arxiv.org/abs/2103.00111) | TKDE'22    |
| [A Survey of Pretraining on Graphs: Taxonomy, Methods, and Applications](https://arxiv.org/abs/2202.07893) | IJCAI'22   |
| [A Systematic Survey of Chemical Pre-trained Models](https://arxiv.org/abs/2210.16484) | IJCAI'23   |
| [Graph Prompt Learning: A Comprehensive Survey and Beyond](https://arxiv.org/abs/2311.16534) | arXiv:2311 |

# Node features

<details close>
    <summary>Node features</summary>

## Feature prediction

* Feature prediction: to predict the original node features by decoding low-dimensional representations
* Masked feature prediction: to predict the original features of masked nodes by representations of unmasked ones. It is "autoregressive" if the predicted nodes are generated one-by-one
* Feature recovery: to predict the original node features by the trivial synthetic features

| Paper                                                        | Venue                             | Pretext                                    | Downstream                                                   | Code                                                         |
| ------------------------------------------------------------ | --------------------------------- | ------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [MGAE: Marginalized Graph Autoencoder for Graph Clustering](https://dl.acm.org/doi/10.1145/3132847.3132967) | CIKM'17                           | Feature prediction                         | Graph partitioning                                           | [link](https://github.com/GRAND-Lab/MGAE)                    |
| [Symmetric Graph Convolutional Autoencoder for Unsupervised Graph Representation Learning](https://arxiv.org/abs/1908.02441) (GALA) | ICCV'19                           | Feature prediction                         | Node clustering; link prediction; image clustering           | [link](https://github.com/sseung0703/GALA_TF2.0)             |
| [Strategies for Pre-training Graph Neural Networks](https://arxiv.org/abs/1905.12265) (AttrMask) | ICLR'20                           | Masked feature prediction                  | Graph classification; biological function prediction         | [link](https://github.com/snap-stanford/pretrain-gnns/)      |
| [Graph-Bert: Only Attention is Needed for Learning Graph Representations](https://arxiv.org/abs/2001.05140) | arXiv:2001                        | Feature prediction                         | Node classification; node clustering                         | [link](https://github.com/jwzhanggy/Graph-Bert)              |
| [Graph Representation Learning via Graphical Mutual Information Maximization](https://arxiv.org/abs/2002.01169) (GMI) | WWW'20                            | Feature prediction (JS)                    | Node classification; link prediction                         | [link](https://github.com/zpeng27/GMI)                       |
| [When Does Self-Supervision Help Graph Convolutional Networks?](https://arxiv.org/abs/2006.09136) (GraphComp) | ICML'20                           | Masked feature prediction                  | Node classification                                          | [link](https://github.com/Shen-Lab/SS-GCNs)                  |
| [GPT-GNN: Generative Pre-Training of Graph Neural Networks](https://arxiv.org/abs/2006.15437) | KDD'20                            | Masked feature prediction (autoregressive) | Node classification; edge regression (recommendation score); meta-path prediction | [link](https://github.com/acbull/GPT-GNN)                    |
| [Self-supervised Learning on Graphs: Deep Insights and New Direction](https://arxiv.org/abs/2006.10141) (AttributeMask) | arXiv:2006                        | Masked feature prediction                  | Node classification                                          | [link](https://github.com/ChandlerBang/SelfTask-GNN)         |
| [SLAPS: Self-Supervision Improves Structure Learning for Graph Neural Networks](https://arxiv.org/abs/2102.05034) | NeurIPS'21                        | Masked feature prediction                  | Node classification; image classification                    | [link](https://github.com/BorealisAI/SLAPS-GNN)              |
| [Motif-based Graph Self-Supervised Learning for Molecular Property Prediction](https://arxiv.org/abs/2110.00987) (MGSSL) | NeurIPS'21                        | Masked feature prediction                  | Graph classification                                         | [link](https://github.com/zaixizhang/MGSSL.)                 |
| [Multi-Scale Variational Graph AutoEncoder for Link Prediction](https://dl.acm.org/doi/abs/10.1145/3488560.3498531) (MSVGAE) | WSDM'22                           | Feature prediction                         | Link prediction                                              | --                                                           |
| [Self-Supervised Representation Learning via Latent Graph Prediction](https://arxiv.org/abs/2202.08333) (LaGraph) | ICML'22                           | Masked feature prediction                  | Node classification; graph classification                    | [link](https://github.com/divelab/DIG/tree/dig/examples/sslgraph/LaGraph) |
| [Graph Masked Autoencoders with Transformers](https://arxiv.org/abs/2202.08391) (GMAE) | arXiv:2202                        | Masked feature prediction                  | Node classification; graph classification                    | [link](https://github.com/RinneSz/GMAE)                      |
| [GraphMAE: Self-Supervised Masked Graph Autoencoders](https://arxiv.org/abs/2205.10803) | KDD'22                            | Masked feature prediction                  | Node classification; graph classification                    | [link](https://github.com/THUDM/GraphMAE)                    |
| [Wiener Graph Deconvolutional Network Improves Graph Self-Supervised Learning](https://arxiv.org/abs/2206.12933) (WGDN) | AAAI'23                           | Feature prediction                         | Node classification; graph classification                    | [link](https://github.com/jcheng66/WGDN)                     |
| [Mole-BERT: Rethinking Pre-training Graph Neural Networks for Molecules](https://openreview.net/forum?id=jevY-DtiZTR) | ICLR'23                           | Masked feature prediction                  | Graph classification; graph regression                       | [link](https://github.com/junxia97/Mole-BERT)                |
| [GraphMAE2: A Decoding-Enhanced Masked Self-Supervised Graph Learner](https://arxiv.org/abs/2304.04779) | WWW'23                            | Masked feature prediction                  | Node classification                                          | [link](https://github.com/THUDM/GraphMAE2)                   |
| [Graph Neural Networks can Recover the Hidden Features Solely from the Graph Structure](https://arxiv.org/abs/2301.10956) (GNNRecover) | ICML'23                           | Feature recovery                           | Node classification                                          | [link](https://github.com/joisino/gnnrecover)                |
| [DiP-GNN: Discriminative Pre-Training of Graph Neural Networks](https://arxiv.org/abs/2209.07499) | NeurIPS Workshop (GLFrontiers)'23 | Masked feature prediction                  | Node classification; link prediction                         | --                                                           |
| [RARE: Robust Masked Graph Autoencoder](https://arxiv.org/abs/2304.01507) | TKDE'23                           | Masked feature prediction                  | Node classification; graph classification; image classification | [link](https://github.com/WxTu/RARE)                         |

## Discrimination (contrastive)

* Latent feature matching: to minimize the (Euclidean) distance between pairs of positive representation vectors
* Instance discrimination: to minimize/maximize the distance between pairs of positive/negative representation samples. Jenson-Shannon (JS), InfoNCE, Bootstrapping, and Triplet margin are all estimators of mutual information (MI) between nodes. BPR stands for Bayesian Personalized Ranking loss.
* Dimension discrimination: to minimize/maximize the mutual information (MI) between pairs of positive/negative representation dimensions. Could be either intra-sample or inter-sample
* Factor discrimination: to maximize the log-likelihood of the target instance given the corresponding instance conditioned on multiple disentangled latent factors

| Paper                                                        | Venue                      | Pretext                                                      | Downstream                                                   | Code                                                         |
| ------------------------------------------------------------ | -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Deep Graph Contrastive Representation Learning](https://arxiv.org/abs/2006.04131) (GRACE) | ICML Workshop (GRL+)'20    | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/CRIPAC-DIG/GRACE)                  |
| [Graph Attention Auto-Encoders](https://arxiv.org/abs/1905.10715) (GATE) | ICTAI'20                   | Feature prediction                                           | Node classification                                          | [link](https://github.com/amin-salehi/GATE)                  |
| [Graph Contrastive Learning with Augmentations](https://arxiv.org/abs/2010.13902) (GraphCL) | NeurIPS'20                 | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/Shen-Lab/GraphCL)                  |
| [Contrastive and Generative Graph Convolutional Networks for Graph-based Semi-Supervised Learning](https://arxiv.org/abs/2009.07111) (CG<sup>3</sup>) | AAAI'21                    | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/LEAP-WS/CG3)                       |
| [Contrastive Self-supervised Learning for Graph Classification](https://arxiv.org/abs/2009.05923) (CSSL) | AAAI'21                    | Instance discrimination (InfoNCE)                            | Graph classification                                         | --                                                           |
| [Self-supervised Graph Learning for Recommendation](https://arxiv.org/abs/2010.10783) (SGL) | SIGIR'21                   | Instance discrimination (InfoNCE)                            | Recommendation                                               | [link](https://github.com/wujcan/SGL-TensorFlow)             |
| [Multi-Scale Contrastive Siamese Networks for Self-Supervised Graph Representation Learning](https://arxiv.org/abs/2105.05682) (MERIT) | IJCAI'21                   | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/GRAND-Lab/MERIT)                   |
| [Graph Contrastive Learning Automated](https://arxiv.org/abs/2106.07594) (JOAO) | ICML'21                    | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/Shen-Lab/GraphCL_Automated)        |
| [Adversarial Graph Augmentation to Improve Graph Contrastive Learning](https://arxiv.org/abs/2106.05819) (AD-GCL) | NeurIPS'21                 | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/susheels/adgcl)                    |
| [InfoGCL: Information-Aware Graph Contrastive Learning](https://arxiv.org/abs/2110.15438) | NeurIPS'21                 | Instance discrimination (Bootstrapping)                      | Node classification; graph classification                    | --                                                           |
| [Graph Adversarial Self-Supervised Learning](https://proceedings.neurips.cc/paper/2021/hash/7d3010c11d08cf990b7614d2c2ca9098-Abstract.html) (GASSL) | NeurIPS'21                 | Instance discrimination (Bootstrapping)                      | Graph classification                                         | [link](https://github.com/LuckyZebra/GASSL) (Unavailable)    |
| [From Canonical Correlation Analysis to Self-supervised Graph Neural Networks](https://arxiv.org/abs/2106.12484) (CCA-SSG) | NeurIPS'21                 | Latent feature matching; dimension discrimination            | Node classification                                          | [link](https://github.com/hengruizhang98/CCA-SSG)            |
| [Disentangled Contrastive Learning on Graphs](https://proceedings.neurips.cc/paper/2021/hash/b6cda17abb967ed28ec9610137aa45f7-Abstract.html) (DGCL) | NeurIPS'21                 | Factor discrimination                                        | Graph classification                                         | [link](https://haoyang.li/assets/code/DGCL.zip)              |
| [Bringing Your Own View: Graph Contrastive Learning without Prefabricated Data Augmentations](https://arxiv.org/abs/2201.01702) (GraphCL-LP) | WSDM'22                    | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/Shen-Lab/GraphCL_Automated)        |
| [Simple Unsupervised Graph Representation Learning](https://ojs.aaai.org/index.php/AAAI/article/view/20748) (SUGRL) | AAAI'22                    | Instance discrimination (Triplet margin)                     | Node classification                                          | [link](https://github.com/YujieMo/SUGRL)                     |
| [AutoGCL: Automated Graph Contrastive Learning via Learnable View Generators](https://arxiv.org/abs/2109.10259) | AAAI'22                    | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/Somedaywilldo/AutoGCL)             |
| [Large-Scale Representation Learning on Graphs via Bootstrapping](https://arxiv.org/abs/2102.06514) (BGRL) | ICLR'22                    | Instance discrimination (Bootstrapping)                      | Node classification                                          | [link](https://github.com/nerdslab/bgrl)                     |
| [VICReg: Variance-Invariance-Covariance Regularization for Self-Supervised Learning](https://arxiv.org/abs/2105.04906) (VICReg) | ICLR'22                    | Dimension discrimination; latent feature matching            | Node classification                                          | [link](https://github.com/PyGCL/PyGCL/blob/main/GCL/losses/vicreg.py) |
| [Graph Barlow Twins: A Self-supervised Representation Learning Framework for Graphs](https://arxiv.org/abs/2106.02466) (G-BT) | Knowledge-Based Systems'22 | Dimension discrimination                                     | Node classification                                          | [link](https://github.com/pbielak/graph-barlow-twins)        |
| [SimGRACE: A Simple Framework for Graph Contrastive Learning without Data Augmentation](https://arxiv.org/abs/2202.03104) | WWW'22                     | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/junxia97/SimGRACE)                 |
| [Adversarial Graph Contrastive Learning with Information Regularization](https://arxiv.org/abs/2208.06956) (ARIEL) | WWW'22                     | Instance discrimination (InfoNCE)                            | Node classification; graph classification                    | [link](https://github.com/Shengyu-Feng/ARIEL)                |
| [Self-Supervised Representation Learning via Latent Graph Prediction](https://arxiv.org/abs/2202.08333) (LaGraph) | ICML'22                    | Latent feature matching                                      | Node classification; graph classification                    | [link](https://github.com/divelab/DIG/tree/dig/examples/sslgraph/LaGraph) |
| [ProGCL: Rethinking Hard Negative Mining in Graph Contrastive Learning](https://arxiv.org/abs/2110.02027) | ICML'22                    | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/junxia97/ProGCL)                   |
| [COSTA: Covariance-Preserving Feature Augmentation for Graph Contrastive Learning](https://arxiv.org/abs/2206.04726) | KDD'22                     | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/yifeiacc/COSTA)                    |
| [M-Mix: Generating Hard Negatives via Multi-sample Mixing for Contrastive Learning](https://dl.acm.org/doi/10.1145/3534678.3539248) | KDD'22                     | Instance discrimination (InfoNCE)                            | Node classification; node clustering; graph classification; graph edit distance prediction | [link](https://github.com/Sherrylone/m-mix)                  |
| [Revisiting Graph Contrastive Learning from the Perspective of Graph Spectrum](https://arxiv.org/abs/2210.02330) (SpCo) | NeurIPS'22                 | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/liun-online/SpCo)                  |
| [Contrastive Graph Structure Learning via Information Bottleneck for Recommendation](https://proceedings.neurips.cc/paper_files/paper/2022/hash/803b9c4a8e4784072fdd791c54d614e2-Abstract-Conference.html) (CGI) | NeurIPS'22                 | Instance discrimination (InfoNCE)                            | Recommendation                                               | [link](https://github.com/weicy15/CGI)                       |
| [Uncovering the Structural Fairness in Graph Contrastive Learning](https://arxiv.org/abs/2210.03011) (GRADE) | NeurIPS'22                 | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/BUPT-GAMMA/Uncovering-the-Structural-Fairness-in-Graph-Contrastive-Learning) |
| [Co-Modality Graph Contrastive Learning for Imbalanced Node Classification](https://papers.nips.cc/paper_files/paper/2022/hash/65cbe3e21ac62553111d9ecf7d60c18e-Abstract-Conference.html) (CM-GCL) | NeurIPS'22                 | Instance discrimination (InfoNCE)                            | Node classification (imbalanced)                             | [link](https://github.com/graphprojects/CM-GCL)              |
| [MA-GCL: Model Augmentation Tricks for Graph Contrastive Learning](https://arxiv.org/abs/2212.07035) | AAAI'23                    | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/GXM1141/MA-GCL)                    |
| [Link Prediction with Non-Contrastive Learning](https://arxiv.org/abs/2211.14394) (T-BGRL) | ICLR'23                    | Instance discrimination (Bootstrapping)                      | Link prediction                                              | [link](https://github.com/snap-research/non-contrastive-link-prediction) |
| [Spectral Augmentation for Self-Supervised Learning on Graphs](https://arxiv.org/abs/2210.00643) (SPAN) | ICLR'23                    | Instance discrimination (InfoNCE)                            | Node classification; graph classification; graph regression  | [link](https://github.com/Louise-LuLin/GCL-SPAN)             |
| [LightGCL: Simple Yet Effective Graph Contrastive Learning for Recommendation](https://arxiv.org/abs/2302.08191) | ICLR'23                    | Instance discrimination (InfoNCE)                            | Recommendation                                               | [link](https://github.com/HKUDS/LightGCL)                    |
| [GraphMAE2: A Decoding-Enhanced Masked Self-Supervised Graph Learner](https://arxiv.org/abs/2304.04779) | WWW'23                     | Latent feature matching                                      | Node classification                                          | [link](https://github.com/THUDM/GraphMAE2)                   |
| [Generating Counterfactual Hard Negative Samples for Graph Contrastive Learning](https://arxiv.org/abs/2207.00148) (CGC) | WWW'23                     | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://www.dropbox.com/sh/kyf8p9unkhn0r99/AABd33jFBfjGYIkvIqWpuNwYa?dl=0) (Unavailable) |
| [Boosting Graph Contrastive Learning via Graph Contrastive Saliency](https://proceedings.mlr.press/v202/wei23c.html) (GCS) | ICML'23                    | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/weicy15/GCS)                       |
| [SEGA: Structural Entropy Guided Anchor View for Graph Contrastive Learning](https://arxiv.org/abs/2305.04501) | ICML'23                    | Instance discrimination (InfoNCE)                            | Graph classification                                         | [link](https://github.com/Wu-Junran/SEGA)                    |
| [Graph Contrastive Learning with Generative Adversarial Network](https://arxiv.org/abs/2308.00535) (GACN) | KDD'23                     | Instance discrimination (InfoNCE, BPR)                       | Node classification; link prediction                         | --                                                           |
| [GiGaMAE: Generalizable Graph Masked Autoencoder via Collaborative Latent Space Reconstruction](https://arxiv.org/abs/2308.09663) | CIKM'23                    | Instance discrimination (InfoNCE)                            | Node classification; node clustering; link prediction        | [link](https://github.com/sycny/GiGaMAE)                     |
| [Graph Self-Contrast Representation Learning](https://arxiv.org/abs/2309.02304) (GraphSC) | ICDM'23                    | Instance discrimination (Triplet margin); dimension discrimination | Graph classification                                         | --                                                           |
| [Provable Training for Graph Contrastive Learning](https://arxiv.org/abs/2309.13944) (POT) | NeurIPS'23                 | Instance discrimination (InfoNCE)                            | Node classification                                          | [link](https://github.com/VoidHaruhi/POT-GCL)                |
| [Better with Less: A Data-Active Perspective on Pre-Training Graph Neural Networks](https://arxiv.org/abs/2311.01038) (APT) | NeurIPS'23                 | Instance discrimination (InfoNCE)                            | Node classification; graph classification                    | [link](https://github.com/galina0217/APT)                    |
| [Graph Contrastive Learning with Stable and Scalable Spectral Encoding](https://openreview.net/forum?id=0kz5RmHxmE) (Sp<sup>2</sup>GCL) | NeurIPS'23                 | Instance discrimination (InfoNCE)                            | Node classification; graph classification; graph regression  | [link](https://github.com/bdy9527/Sp2GCL)                    |
| [RARE: Robust Masked Graph Autoencoder](https://arxiv.org/abs/2304.01507) | TKDE'23                    | Latent feature matching                                      | Node classification; graph classification; image classification | [link](https://github.com/WxTu/RARE)                         |
| [Rethinking and Simplifying Bootstrapped Graph Latents](https://arxiv.org/abs/2312.02619) (SGCL) | WSDM'24                    | Instance discrimination (Bootstrapping)                      | Node classification                                          | [link](https://github.com/ZsZsZs25/SGCL)                     |
| [Neural Eigenfunctions Are Structured Representation Learners](https://arxiv.org/abs/2210.12637) (NeuralEF) | arXiv:2210 (ICLR'24?)      | Dimension discrimination                                     | Node classification; image retrieval; object detection; instance segmentation | [link](https://openreview.net/attachment?id=OTMPdMH9JL&name=supplementary_material) |

</details>

# Node properties

<details close>
    <summary>Node properties</summary>

* Property prediction: a regression task to predict the property of a node (e.g. degree)
* Centrality score ranking: to estimate whether the centrality score of a node is greater/lower than that of another node
* Node order matching: to match the output node order with the input order 

| Paper                                                        | Venue                   | Pretext                                                   | Downstream                                          | Code                                                 |
| ------------------------------------------------------------ | ----------------------- | --------------------------------------------------------- | --------------------------------------------------- | ---------------------------------------------------- |
| [Unsupervised Pre-training of Graph Convolutional Networks](https://arxiv.org/abs/1905.13728) (ScoreRank) | ICLR Workshop (RLGM)'19 | Centrality score ranking                                  | Node classification                                 | --                                                   |
| [Self-supervised Learning on Graphs: Deep Insights and New Direction](https://arxiv.org/abs/2006.10141) (NodeProperty) | arXiv:2006              | Property prediction (degree, clustering coefficient, etc) | Node classification                                 | [link](https://github.com/ChandlerBang/SelfTask-GNN) |
| [Permutation-Invariant Variational Autoencoder for Graph-Level Representation Learning](https://arxiv.org/abs/2104.09856) (PIGAE) | NeurIPS'21              | Node order matching                                       | Graph classification                                | [link](https://github.com/jrwnter/pigvae)            |
| [Graph Auto-Encoder Via Neighborhood Wasserstein Reconstruction](https://arxiv.org/abs/2202.09025) (NWR-GAE) | ICLR'22                 | Property prediction (degree)                              | Node classification; structural role identification | [link](https://github.com/mtang724/NWR-GAE)          |
| [What's Behind the Mask: Understanding Masked Graph Modeling for Graph Autoencoders](https://arxiv.org/abs/2205.10053) (MaskGAE) | KDD'23                  | Property prediction (degree)                              | Node classification; link prediction                | [link](https://github.com/EdisonLeeeee/MaskGAE)      |

</details>

# Links

<details close>
    <summary>Links</summary>

* Link prediction: a generally binary classification task that predicts if two nodes are connected by a link
* Masked link prediction: to predict the masked links by node representations propagated on the unmasked graph. It is "autoregressive" if the predicted links are generated one-by-one
* Meta-path prediction: link prediction on heterogeneous graphs, to predict if two nodes are connected by a meta-path
* (Masked) edge feature prediction: to predict the original (masked) edge features by node representations

| Paper                                                        | Venue                             | Pretext                                  | Downstream                                                   | Code                                                         |
| ------------------------------------------------------------ | --------------------------------- | ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Variational Graph Auto-Encoders](https://arxiv.org/abs/1611.07308) (GAE, VGAE) | NIPS Workshop (BDL)'16            | Link prediction                          | Link prediction                                              | [link](https://github.com/tkipf/gae)                         |
| [Adversarially Regularized Graph Autoencoder for Graph Embedding](https://arxiv.org/abs/1802.04407) (ARGA, ARVGA) | IJCAI'18                          | Link prediction                          | Link prediction; node clustering                             | [link](https://github.com/GRAND-Lab/ARGA)                    |
| [Unsupervised Pre-training of Graph Convolutional Networks](https://arxiv.org/abs/1905.13728) (DenoisingRecon) | ICLR Workshop (RLGM)'19           | Masked link prediction                   | Node classification                                          | --                                                           |
| [Graphite: Iterative Generative Modeling of Graphs](https://arxiv.org/abs/1803.10459) | ICML'19                           | Link prediction                          | Node classification; link prediction                         | [link](https://github.com/ermongroup/graphite)               |
| [Semi-Implicit Graph Variational Auto-Encoders](https://arxiv.org/abs/1908.07078) (SIG-VAE) | NeurIPS'19                        | Link prediction                          | Node classification; link prediction; node clustering; graph generation | [link](https://github.com/sigvae/SIGraphVAE)                 |
| [Strategies for Pre-training Graph Neural Networks](https://arxiv.org/abs/1905.12265) (AttrMask) | ICLR'20                           | Masked edge feature prediction           | Graph classification; biological function prediction         | [link](https://github.com/snap-stanford/pretrain-gnns/)      |
| [Self-supervised Learning on Graphs: Deep Insights and New Direction](https://arxiv.org/abs/2006.10141) (EdgeMask) | arXiv:2006                        | Masked link prediction                   | Node classification                                          | [link](https://github.com/ChandlerBang/SelfTask-GNN)         |
| [GPT-GNN: Generative Pre-Training of Graph Neural Networks](https://arxiv.org/abs/2006.15437) | KDD'20                            | Masked link prediction (autoregressive)  | Node classification; edge classification; meta-path prediction | [link](https://github.com/acbull/GPT-GNN)                    |
| [Self-supervised Auxiliary Learning with Meta-paths for Heterogeneous Graphs](https://arxiv.org/abs/2007.08294) (SELAR) | NeurIPS'20                        | Meta-path prediction                     | Node classification; link prediction                         | [link](https://github.com/mlvlab/SELAR)                      |
| [Contrastive and Generative Graph Convolutional Networks for Graph-based Semi-Supervised Learning](https://arxiv.org/abs/2009.07111) (CG<sup>3</sup>) | AAAI'21                           | Link prediction                          | Node classification                                          | [link](https://github.com/LEAP-WS/CG3)                       |
| [How to Find Your Friendly Neighborhood: Graph Attention Design with Self-Supervision](https://arxiv.org/abs/2204.04879) (SuperGAT) | ICLR'21                           | Link prediction                          | Node classification; link prediction                         | [link](https://github.com/dongkwan-kim/SuperGAT)             |
| [Permutation-Invariant Variational Autoencoder for Graph-Level Representation Learning](https://arxiv.org/abs/2104.09856) (PIGAE) | NeurIPS'21                        | Link prediction; edge feature prediction | Graph classification                                         | [link](https://github.com/jrwnter/pigvae)                    |
| [Motif-based Graph Self-Supervised Learning for Molecular Property Prediction](https://arxiv.org/abs/2110.00987) (MGSSL) | NeurIPS'21                        | Masked edge feature prediction           | Graph classification                                | [link](https://github.com/zaixizhang/MGSSL.)                 |
| [Directed Graph Auto-Encoders](https://arxiv.org/abs/2202.12449) (DiGAE) | AAAI'22                           | Link prediction                          | (Directed) link prediction                                   | [link](https://github.com/gidiko/DiGAE)                      |
| [MGAE: Masked Autoencoders for Self-Supervised Learning on Graphs](https://arxiv.org/abs/2201.02534); [S2GAE: Self-Supervised Graph Autoencoders are Generalizable Learners with Graph Masking](https://dl.acm.org/doi/abs/10.1145/3539597.3570404) | WSDM'23                           | Masked link prediction                   | Node classification; graph classification; link prediction   | [link](https://github.com/qiaoyu-tan/S2GAE)                  |
| [Dual Low-Rank Graph Autoencoder for Semantic and Topological Networks](https://ojs.aaai.org/index.php/AAAI/article/view/25536) (DLR-GAE) | AAAI'23                           | Link prediction                          | Node classification                                          | [link](https://github.com/chenzl23/DLRGAE)                   |
| [Multi-head Variational Graph Autoencoder Constrained by Sum-product Networks](https://dl.acm.org/doi/abs/10.1145/3543507.3583517) (SPN-MVGAE) | WWW'23                            | Link prediction                          | Node classification; link prediction                         | [link](https://github.com/godlovexiari/MVGAE-SPN) (Unavailable) |
| [SeeGera: Self-supervised Semi-implicit Graph Variational Auto-encoders with Masking](https://arxiv.org/abs/2301.12458) | WWW'23                            | Masked link prediction                   | Node classification; link prediction; attribute prediction   | [link](https://github.com/SeeGera/SeeGera)                   |
| [DiP-GNN: Discriminative Pre-Training of Graph Neural Networks](https://arxiv.org/abs/2209.07499) | NeurIPS Workshop (GLFrontiers)'23 | Masked link prediction                   | Node classification; link prediction                         | --                                                           |

</details>

# Context

<details close>
    <summary>Context</summary>

* Context discrimination: to distinguish between contextual nodes and non-contextual nodes (LE stands for Laplacian Eigenmaps objective)
* Factorized context discrimination: to maximize the log-likelihood of context representations given the corresponding central node conditioned on multiple disentangled latent factors
* Contextual subgraph discrimination: to distinguish between representations aggregated from different contextual subgraphs (maybe from different receptive fields)
* Neighbor feature prediction: node feature prediction but to reconstruct the features of k-hop neighbors instead (BPR stands for Bayesian Personalized Ranking loss)
* Contextual property prediction: to predict the properties of contextual subgraphs

| Paper                                                        | Venue      | Pretext                                                      | Downstream                                                   | Code                                                         |
| ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Inductive Representation Learning on Large Graphs](https://arxiv.org/abs/1706.02216) (GraphSAGE) | NIPS'17    | Context discrimination (JS)                                  | Node classification                                          | [link](https://github.com/williamleif/GraphSAGE)             |
| [Strategies for Pre-training Graph Neural Networks](https://arxiv.org/abs/1905.12265) (ContextPred) | ICLR'20    | Contextual subgraph discrimination (CE)                      | Graph classification; biological function prediction | [link](https://github.com/snap-stanford/pretrain-gnns/)      |
| [GCC: Graph Contrastive Coding for Graph Neural Network Pre-Training](https://arxiv.org/abs/2006.09963) | KDD'20     | Contextual subgraph discrimination (InfoNCE)                 | Node classification; graph classification; similarity search | [link](https://github.com/THUDM/GCC)                         |
| [Graph Attention Auto-Encoders](https://arxiv.org/abs/1905.10715) (GATE) | ICTAI'20   | Context discrimination (JS)                                  | Node classification                                          | [link](https://github.com/amin-salehi/GATE)                  |
| [Sub-Graph Contrast for Scalable Self-Supervised Graph Representation Learning](https://arxiv.org/abs/2009.10273) (Subg-Con) | ICDM'20    | Context discrimination (Triplet margin)                      | Node classification                                          | [link](https://github.com/yzjiao/Subg-Con)                   |
| [Self-Supervised Graph Transformer on Large-Scale Molecular Data](https://arxiv.org/abs/2007.02835) (GROVER) | NeurIPS'20 | Contextual property prediction                               | Graph classification; graph regression                       | [link](https://github.com/tencent-ailab/grover)              |
| [Graph-MLP: Node Classification without Message Passing in Graph](https://arxiv.org/abs/2106.04051) | arXiv:2106 | Context discrimination (InfoNCE)                             | Node classification                                          | [link](https://github.com/yanghu819/Graph-MLP)               |
| [Transfer Learning of Graph Neural Networks with Ego-graph Information Maximization](https://arxiv.org/abs/2009.05204) (EGI) | NeurIPS'21 | Context discrimination (JS)                                  | Role identification; relation prediction                     | [link](https://github.com/GentleZhu/EGI)                     |
| [Contrastive Laplacian Eigenmaps](https://arxiv.org/abs/2201.05493) (COLES) | NeurIPS'21 | Context discrimination (LE)                                  | Node classification; node clustering                         | [link](https://github.com/allenhaozhu/COLES)                 |
| [Augmentation-Free Self-Supervised Learning on Graphs](https://arxiv.org/abs/2112.02472) (AFGRL) | AAAI'22    | Context discrimination (Bootstrapping)                       | Node classification; node clustering; similarity search      | [link](https://github.com/Namkyeong/AFGRL)                   |
| [Simple Unsupervised Graph Representation Learning](https://ojs.aaai.org/index.php/AAAI/article/view/20748) (SUGRL) | AAAI'22    | Context discrimination (Triplet margin)                      | Node classification                                          | [link](https://github.com/YujieMo/SUGRL)                     |
| [SAIL: Self-Augmented Graph Contrastive Learning](https://arxiv.org/abs/2009.00934) | AAAI'22    | Neighbor feature prediction (BPR)                            | Node classification; node clustering; link prediction        | --                                                           |
| [Node Representation Learning in Graph via Node-to-Neighbourhood Mutual Information Maximization](https://arxiv.org/abs/2203.12265) (N2N) | CVPR'22    | Context discrimination (InfoNCE)                             | Node classification                                          | [link](https://github.com/dongwei156/n2n)                    |
| [RoSA: A Robust Self-Aligned Framework for Node-Node Graph Contrastive Learning](https://arxiv.org/abs/2204.13846) | IJCAI'22   | Contextual subgraph discrimination (InfoNCE)                 | Node classification                                          | [link](https://github.com/ZhuYun97/RoSA)                     |
| [Towards Self-supervised Learning on Graphs with Heterophily](https://dl.acm.org/doi/abs/10.1145/3511808.3557478) (HGRL) | CIKM'22    | Context discrimination (InfoNCE)                             | Node classification; node clustering                         | [link](https://github.com/yifanQi98/HGRL)                    |
| [Generalized Laplacian Eigenmaps](https://proceedings.neurips.cc/paper_files/paper/2022/hash/c6b71f8d79d0b2d7bdac66ff3a3ba243-Abstract-Conference.html) (GLEN) | NeurIPS'22 | Context discrimination (LE)                                  | Node classification; node clustering                         | [link](https://github.com/allenhaozhu/GLEN)                  |
| [Decoupled Self-supervised Learning for Graphs](https://arxiv.org/abs/2206.03601) (DSSL) | NeurIPS'22 | Factorized context discrimination                            | Node classification                                          | [link](https://openreview.net/attachment?id=Bwh6XmDEDe&name=supplementary_material) |
| [Graph Auto-Encoder Via Neighborhood Wasserstein Reconstruction](https://arxiv.org/abs/2202.09025) (NWR-GAE) | ICLR'22    | Neighbor feature prediction (Wasserstein distance)           | Node classification; structural role identification          | [link](https://github.com/mtang724/NWR-GAE)                  |
| [Localized Graph Contrastive Learning](https://arxiv.org/abs/2212.04604) (Local-GCL) | arXiv:2212 | Context discrimination (InfoNCE)                             | Node classification                                          | [link](https://openreview.net/attachment?id=dSYkYNNZkV&name=supplementary_material) |
| [Deep Graph Structural Infomax](https://ojs.aaai.org/index.php/AAAI/article/view/25618) (DGSI) | AAAI'23    | Context discrimination (JS)                                  | Node classification                                          | [link](https://github.com/wtzhao1631/dgsi)                   |
| [Eliciting Structural and Semantic Global Knowledge in Unsupervised Graph Contrastive Learning](https://arxiv.org/abs/2202.08480) (S<sup>3</sup>-CL) | AAAI'23    | Contextual subgraph discrimination (InfoNCE)                 | Node classification; node clustering                         | [link](https://github.com/kaize0409/S-3-CL)                  |
| [Contrastive Learning Meets Homophily: Two Birds with One Stone](https://proceedings.mlr.press/v202/he23c.html) (NeCo) | ICML'23    | Context discrimination (InfoNCE)                             | Node classification                                          | --                                                           |
| [Contrastive Cross-scale Graph Knowledge Synergy](https://dl.acm.org/doi/abs/10.1145/3580305.3599286) (CGKS) | KDD'23     | Context discrimination (LE); contextual subgraph discrimination (InfoNCE) | Node classification; graph classification                    | --                                                           |
| [Simple and Asymmetric Graph Contrastive Learning without Augmentations](https://arxiv.org/abs/2310.18884) (GraphACL) | NeurIPS'23 | Context discrimination (InfoNCE)                             | Node classification                                          | [link](https://github.com/tengxiao1/GraphACL)                |

</details>

# Long-range similarities

<details close>
    <summary>Long-range similarities</summary>

* Similarity prediction: to predict a similarity matrix between nodes. The pairwise similarity can be defined by shortest path distance, PageRank, Katz index, Jaccard coefficient, cosine similarity between output representations, cosine similarity between input and output, etc
* Masked path prediction: similar to masked link prediction, but the link are masked in paths
* Similarity-based discrimination: instance discrimination that is node similarity-aware
* Feature graph alignment: to construct a feature graph based on pairwise similarities of node features and minimize the distance of representation distributions between the original graph and the feature graph

| Paper                                                        | Venue                   | Pretext                                                      | Downstream                                            | Code                                                 |
| ------------------------------------------------------------ | ----------------------- | ------------------------------------------------------------ | ----------------------------------------------------- | ---------------------------------------------------- |
| [Graph-Bert: Only Attention is Needed for Learning Graph Representations](https://arxiv.org/abs/2001.05140) | arXiv:2001              | Similarity prediction (PageRank, etc)                        | Node classification; node clustering                  | [link](https://github.com/jwzhanggy/Graph-Bert)      |
| [Self-supervised Learning on Graphs: Deep Insights and New Direction](https://arxiv.org/abs/2006.10141) (PairwiseDistance, PairwiseAttrSim) | arXiv:2006              | Similarity prediction (shortest path distance; cosine similarity) | Node classification                                   | [link](https://github.com/ChandlerBang/SelfTask-GNN) |
| [Adaptive Graph Encoder for Attributed Graph Embedding](https://arxiv.org/abs/2007.01594) (AGE) | KDD'20                  | Similarity prediction (cosine similarity)                    | Node clustering; link prediction                      | [link](https://github.com/thunlp/AGE)                |
| [AM-GCN: Adaptive Multi-channel Graph Convolutional Networks](https://arxiv.org/abs/2007.02265) | KDD'20                  | Feature graph alignment                                      | Node classification                                   | [link](https://github.com/zhumeiqiBUPT/AM-GCN)       |
| [SAIL: Self-Augmented Graph Contrastive Learning](https://arxiv.org/abs/2009.00934) | AAAI'22                 | Similarity prediction (cosine similarity)                    | Node classification; node clustering; link prediction | --                                                   |
| [Self-Supervised Graph Representation Learning via Global Context Prediction](https://arxiv.org/abs/2003.01604); [A New Self-supervised Task on Graphs: Geodesic Distance Prediction](https://www.sciencedirect.com/science/article/abs/pii/S0020025522006375) (S<sup>2</sup>GRL) | Information Sciences'22 | Similarity prediction (shortest path distance)               | Node classification; node clustering; link prediction | --                                                   |
| [Dual Low-Rank Graph Autoencoder for Semantic and Topological Networks](https://ojs.aaai.org/index.php/AAAI/article/view/25536) (DLR-GAE) | AAAI'23                 | Feature graph alignment                                      | Node classification                                   | [link](https://github.com/chenzl23/DLRGAE)           |
| [Self-Supervised Teaching and Learning of Representations on Graphs](https://dl.acm.org/doi/abs/10.1145/3543507.3583441) (GraphTL) | WWW'23                  | Similarity-based discrimination (InfoNCE)                    | Node classification                                   | --                                                   |
| [What's Behind the Mask: Understanding Masked Graph Modeling for Graph Autoencoders](https://arxiv.org/abs/2205.10053) (MaskGAE) | KDD'23                  | Masked path prediction                                       | Node classification; link prediction                  | [link](https://github.com/EdisonLeeeee/MaskGAE)      |

</details>

# Motifs

<details close>
    <summary>Motifs</summary>

* Motif prediction: to assign each node (or supernode in the fragment graph) a motif pseudo-label given by unsupervised motif discovery algorithms (e.g. RDKit) and learn to predict them. It is "autoregressive" if the predicted supernodes are generated one-by-one
* Motif-based masked feature prediction: similar to masked feature prediction, but the features are masked in motifs
* Motif-based discrimination: to perform contrast between the original graph view and the fragment graph view
* Motif adversarial generation: to generate motifs with an adversarial min-max optimizer

| Papers                                                       | Venue                             | Pretext                                                | Downstream                             | Code                                                         |
| ------------------------------------------------------------ | --------------------------------- | ------------------------------------------------------ | -------------------------------------- | ------------------------------------------------------------ |
| [Self-Supervised Graph Transformer on Large-Scale Molecular Data](https://arxiv.org/abs/2007.02835) (GROVER) | NeurIPS'20                        | Contextual property prediction                         | Graph classification; graph regression | [link](https://github.com/tencent-ailab/grover)              |
| [Motif-Driven Contrastive Learning of Graph Representations](https://arxiv.org/abs/2012.12533) (MICRO-Graph) | WWW Workshop (SSL)'21             | Motif-based discrimination (InfoNCE)                   | Graph classification          | [link](https://drive.google.com/file/d/1b751rpnV-SDmUJvKZZI-AvpfEa9eHxo9) |
| [Motif-based Graph Self-Supervised Learning for Molecular Property Prediction](https://arxiv.org/abs/2110.00987) (MGSSL) | NeurIPS'21                        | Motif prediction (autoregressive)                      | Graph classification          | [link](https://github.com/zaixizhang/MGSSL)                  |
| [Fragment-based Pretraining and Finetuning on Molecular Graphs](https://arxiv.org/abs/2310.03274) (GraphFP) | NeurIPS'23                        | Motif prediction; motif-based discrimination (InfoNCE) | Graph classification; graph regression | [link](https://github.com/lvkd84/GraphFP)                    |
| [Motif-aware Attribute Masking for Molecular Graph Pre-training](https://arxiv.org/abs/2309.04589) (MoAMa) | NeurIPS Workshop (GLFrontiers)'23 | Motif-based masked feature prediction                  | Graph classification          | [link](https://github.com/einae-nd/MoAMa-dev)                |
| [Motif-aware Riemannian Graph Neural Network with Generative-Contrastive Learning](https://arxiv.org/abs/2401.01232) (MotifRGC) | AAAI'24                           | Motif adversarial generation                           | Node classification; link prediction   | [link](https://github.com/RiemannGraph/MotifRGC)             |

</details>

# Clusters

<details close>
    <summary>Clusters</summary>

* Synthetic graph discrimination: binary classification between two synthetic graphs with different synthesizers (Erdős-Rényi generator / SBM generator)
* Node clustering: to assign each node a cluster centroid (prototype) and - i) minimize the distance between nodes and their corresponding centroids in the latent space; or ii) minimize the distance between the learned centroids and the ground-truth centroids given by unsupervised feature clustering algorithms (e.g. K-means, DeepCluster)
* Graph partitioning: to assign each node a cluster centroid (prototype) and - i) predict the quality of the learned partitions evaluated by some metrics, e.g. maximizing modularity or minimizing the normalized edge weights of a graph cut (spectral clustering); or ii) predict the cluster membership of each node given by unsupervised graph partitioning algorithms (structure-based, e.g. METIS, Louvain)
* Cluster/partition-based instance discrimination: instance discrimination that is aware of graph clustering/partitioning memberships
* Cluster/partition-conditioned link prediction: to maximize the log-likelihood of existing links, but conditioned by the graph cluster/partition distributions
* Partition-conditioned masked link prediction: similar to masked link prediction, but the links are masked in clusters

| Paper                                                        | Venue                   | Pretext                                                      | Downstream                                                   | Code                                                         |
| ------------------------------------------------------------ | ----------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [SGR: Self-Supervised Spectral Graph Representation Learning](https://arxiv.org/abs/1811.06237) | KDD Workshop (DLD)'18   | Synthetic graph discrimination                               | Graph classification                                         | --                                                           |
| [Unsupervised Pre-training of Graph Convolutional Networks](https://arxiv.org/abs/1905.13728) (ClusterDetect) | ICLR Workshop (RLGM)'19 | Graph partitioning                                           | Node classification                                          | --                                                           |
| [Multi-Stage Self-Supervised Learning for Graph Convolutional Networks on Graphs with Few Labeled Nodes](https://arxiv.org/abs/1902.11038) (M3S) | AAAI'20                 | Node clustering                                              | Node classification                                          | [link](https://github.com/datake/M3S)                        |
| [Collaborative Graph Convolutional Networks: Unsupervised Learning Meets Semi-Supervised Learning](https://ojs.aaai.org/index.php/AAAI/article/view/5843) (CGCN) | AAAI'20                 | Partition-conditioned link prediction                        | Node classification; node clustering                         | [link](https://github.com/AISKYEYE-TJU/CGCN-AAAI2020) (Deleted) |
| [When Does Self-Supervision Help Graph Convolutional Networks?](https://arxiv.org/abs/2006.09136) (NodeCluster, GraphPar) | ICML'20                 | Node clustering; graph partitioning                          | Node classification                                          | [link](https://github.com/Shen-Lab/SS-GCNs)                  |
| [Self-supervised Learning on Graphs: Deep Insights and New Direction](https://arxiv.org/abs/2006.10141) (Distance2Clusters) | arXiv:2006              | Graph partitioning                                           | Node classification                                          | [link](https://github.com/ChandlerBang/SelfTask-GNN)         |
| [CommDGI: Community Detection Oriented Deep Graph Infomax](https://dl.acm.org/doi/10.1145/3340531.3412042) | CIKM'20                 | Cluster-based instance discrimination (JS); graph partitioning | Node clustering                                              | [link](https://github.com/FDUDSDE/CommDGI)                   |
| [Dirichlet Graph Variational Autoencoder](https://arxiv.org/abs/2010.04408) (DGVAE) | NeurIPS'20              | Partition-conditioned link prediction                        | Graph generation; node clustering                            | [link](https://github.com/xiyou3368/DGVAE)                   |
| [Mask-GVAE: Blind Denoising Graphs via Partition](https://arxiv.org/abs/2102.04228) | WWW'21                  | Graph partitioning; partition-conditioned masked link prediction | Node clustering; graph denoising                             | [link](https://github.com/halimiqi/www21)                    |
| [Motif-Driven Contrastive Learning of Graph Representations](https://arxiv.org/abs/2012.12533) (MICRO-Graph) | WWW Workshop (SSL)'21   | Graph partitioning                                           | Graph classification                                | [link](https://drive.google.com/file/d/1b751rpnV-SDmUJvKZZI-AvpfEa9eHxo9) |
| [Self-supervised Graph-level Representation Learning with Local and Global Structure](https://arxiv.org/abs/2106.04113) (GraphLoG) | ICML'21                 | Node clustering                                              | Graph classification; biological function prediction | [link](https://github.com/DeepGraphLearning/GraphLoG)        |
| [Graph Communal Contrastive Learning](https://arxiv.org/abs/2110.14863) (gCooL) | WWW'22                  | Partition-based instance discrimination (InfoNCE)            | Node classification; node clustering                         | [link](https://github.com/lblaoke/gCooL)                     |
| [Self-supervised Heterogeneous Graph Pre-training Based on Structural Clustering](https://arxiv.org/abs/2210.10462) (SHGP) | NeurIPS'22              | Graph partitioning                                           | (Heterogeneous) node classification; node clustering         | [link](https://github.com/kepsail/SHGP)                      |
| [Eliciting Structural and Semantic Global Knowledge in Unsupervised Graph Contrastive Learning](https://arxiv.org/abs/2202.08480) (S<sup>3</sup>-CL) | AAAI'23                 | Cluster-based instance discrimination (InfoNCE)              | Node classification; node clustering                         | [link](https://github.com/kaize0409/S-3-CL)                  |
| [CSGCL: Community-Strength-Enhanced Graph Contrastive Learning](https://arxiv.org/abs/2305.04658) | IJCAI'23                | Partition-based instance discrimination (InfoNCE)            | Node classification; node clustering; link prediction        | [link](https://github.com/HanChen-HUST/CSGCL)                |
| [HomoGCL: Rethinking Homophily in Graph Contrastive Learning](https://arxiv.org/abs/2306.09614) | KDD'23                  | Node clustering; cluster-based instance discrimination (InfoNCE) | Node classification; node clustering                         | [link](https://github.com/wenzhilics/HomoGCL)                |
| [CARL-G: Clustering-Accelerated Representation Learning on Graphs](https://arxiv.org/abs/2306.06936) | KDD'23                  | Node clustering                                              | Node classification; node clustering; similarity search      | [link](https://github.com/willshiao/carl-g)                  |

</details>

# Global structure

<details close>
    <summary>Global structure</summary>

* Global-local instance discrimination: instance discrimination between the representation of each node and a global representation vector, usually aggregated from the whole graph by a readout function
* Group discrimination: a simplified global-local instance discrimination that binarily classifies if a node belongs to the original or the perturbed graph
* Global instance discrimination: to discriminate between global representations of different graph views (small-scale only)
* Graph kernel prediction: to predict various kinds of kernels between pairs of graphs: graphlet kernel, random walk kernel, graph edit distance kernel, etc
* Half-graph matching: to divide each graph into two halves and predict if two halves are from the same original graph

| Paper                                                        | Venue                                    | Pretext                                                      | Downstream                                                 | Code                                                         |
| ------------------------------------------------------------ | ---------------------------------------- | ------------------------------------------------------------ | ---------------------------------------------------------- | ------------------------------------------------------------ |
| [Pre-training Graph Neural Networks with Kernels](https://arxiv.org/abs/1811.06930) (KernelPred) | arXiv:1811                               | Graph kernel prediction                                      | Graph classification                                       | --                                                           |
| [Deep Graph InfoMax](https://arxiv.org/abs/1809.10341) (DGI) | ICLR'19                                  | Global-local instance discrimination (JS)                    | Node classification                                        | [link](https://github.com/PetarV-/DGI)                       |
| [InfoGraph: Unsupervised and Semi-supervised Graph-Level Representation Learning via Mutual Information Maximization](https://arxiv.org/abs/1908.01000) | ICLR'20                                  | Global-local instance discrimination (JS)                    | Graph classification                                       | [link](https://github.com/fanyun-sun/InfoGraph)              |
| [Contrastive Multi-View Representation Learning on Graphs](https://arxiv.org/abs/2006.05582) (MVGRL) | ICML'20                                  | Global-local instance discrimination (JS)                    | Node classification; graph classification                  | [link](https://github.com/kavehhassani/mvgrl)                |
| [Pairwise Half-graph Discrimination: A Simple Graph-level Self-supervised Strategy for Pre-training Graph Neural Networks](https://arxiv.org/abs/2110.13567) (PHD); [An Effective Self-Supervised Framework for Learning Expressive Molecular Global Representations to Drug Discovery](https://academic.oup.com/bib/article/22/6/bbab109/6262238?login=false) (MPG) | IJCAI'21; Briefings in Bioinformatics'21 | Half-graph matching                                          | Graph classification                                       | [link](https://github.com/pyli0628/MPG)                      |
| [Self-Supervised Graph Neural Networks via Diverse and Interactive Message Passing](https://ojs.aaai.org/index.php/AAAI/article/view/20353) (DIMP) | AAAI'22                                  | Global-local instance discrimination (JS)                    | Node classification; node clustering; graph classification | [link](https://github.com/chensnail/DIMP)                    |
| [Let Invariant Rationale Discovery Inspire Graph Contrastive Learning](https://arxiv.org/abs/2206.07869) (RGCL) | ICML'22                                  | Global instance discrimination (InfoNCE)                     | Graph classification                                       | [link](https://github.com/lsh0520/RGCL)                      |
| [Rethinking and Scaling Up Graph Contrastive Learning: An Extremely Efficient Approach with Group Discrimination](https://arxiv.org/abs/2206.01535) (GGD) | NeurIPS'22                               | Group discrimination                                         | Node classification                                        | [link](https://github.com/zyzisastudyreallyhardguy/Graph-Group-Discrimination) |
| [Graph Self-supervised Learning with Accurate Discrepancy Learning](https://arxiv.org/abs/2202.02989) (D-SLA) | NeurIPS'22                               | Group discrimination; graph kernel prediction                | Graph classification; link prediction                      | [link](https://github.com/DongkiKim95/D-SLA)                 |
| [Deep Graph Structural Infomax](https://ojs.aaai.org/index.php/AAAI/article/view/25618) (DGSI) | AAAI'23                                  | Global-local instance discrimination (JS)                    | Node classification                                        | [link](https://github.com/wtzhao1631/dgsi)                   |
| [Mole-BERT: Rethinking Pre-training Graph Neural Networks for Molecules](https://openreview.net/forum?id=jevY-DtiZTR) | ICLR'23                                  | Global instance discrimination (InfoNCE; Triplet margin)     | Graph classification; graph regression                     | [link](https://github.com/junxia97/Mole-BERT)                |
| [Multi-Scale Subgraph Contrastive Learning](https://www.ijcai.org/proceedings/2023/246) (MSSGCL) | IJCAI'23                                 | Global-local instance discrimination (InfoNCE); global instance discrimination (InfoNCE) | Graph classification                                       | [link](https://github.com/ZhaoYuTJPU/MSSGCL)                 |

</details>

# Manifolds

<details close>
    <summary>Manifolds</summary>

* Cross-manifold discrimination: to perform instance discrimination between different manifolds (e.g. Euclidean vs. Hyperbolic)
* Ricci curvature prediction: to predict the aggregated Ricci curvature of each node's neighborhood
* Curvature-based node clustering: to assign each node a cluster centroid and maximize/minimize the curvature-based density within/across clusters
* Hyperbolic angle prediction: to pool representations to 2-dimensional angle vectors in a unit hyperbola. These vectors serve as pseudo-labels for regression

| Paper                                                        | Venue      | Pretext                                                      | Downstream                             | Code                                                         |
| ------------------------------------------------------------ | ---------- | ------------------------------------------------------------ | -------------------------------------- | ------------------------------------------------------------ |
| [A Self-supervised Mixed-curvature Graph Neural Network](https://arxiv.org/abs/2112.05393) (SelfMGNN) | AAAI'22    | Cross-manifold discrimination (InfoNCE)                      | Node classification                    | --                                                           |
| [Dual Space Graph Contrastive Learning](https://arxiv.org/abs/2201.07409) (DSGC) | WWW'22     | Cross-manifold discrimination (InfoNCE)                      | Graph classification                   | [link](https://www.dropbox.com/sh/qyfq8j7v8lmbmap/AADgjR1-l5SrTyrWEfs1Jvdha) (Unavailable) |
| [CONGREGATE: Contrastive Graph Clustering in Curvature Spaces](https://arxiv.org/abs/2305.03555) | IJCAI'23   | Ricci curvature prediction; cross-manifold discrimination (InfoNCE); curvature-based node clustering | Node clustering                        | [link](https://github.com/CurvCluster/Congregate)            |
| [Graph-level Representation Learning with Joint-Embedding Predictive Architectures](https://arxiv.org/abs/2309.16014) (GraphJEPA) | arXiv:2309 | Hyperbolic angle prediction                                  | Graph classification; graph regression | [link](https://github.com/geriskenderi/graph-jepa)           |
| [Motif-aware Riemannian Graph Neural Network with Generative-Contrastive Learning](https://arxiv.org/abs/2401.01232) (MotifRGC) | AAAI'24    | Cross-manifold discrimination (InfoNCE)                      | Node classification; link prediction   | [link](https://github.com/RiemannGraph/MotifRGC)             |

</details>

# Task adaptation strategies

<details close>
    <summary>Task adaptation strategies</summary>

* Multi-task learning: to combine different pretexts and jointly learn them for task generalizable performance
* Fine-tuning: to jointly learn the downstream branches as well as the original pre-trained model
* Probing: to freeze the parameters of the pre-trained model during downstream task adaptation
* Prompting: to encode downstream data and the corresponding task information as tokens to instruct the behavior of pre-trained models for downstream adaptation (more information [here](https://github.com/WxxShirley/Awesome-Graph-Prompt))

| Paper                                                        | Venue      | Strategy            | Downstream                                                   | Code                                              |
| ------------------------------------------------------------ | ---------- | ------------------- | ------------------------------------------------------------ | ------------------------------------------------- |
| [Learning to Pre-train Graph Neural Networks]() (L2P-GNN)    | AAAI'21    | Fine-tuning         | Graph classification; biological function prediction         | [link](https://github.com/rootlu/L2P-GNN)         |
| [Adaptive Transfer Learning on Graph Neural Networks](https://arxiv.org/abs/2107.08765) (AUX-TS) | KDD'21     | Fine-tuning         | Node classification; link prediction                         | [link](https://github.com/Sean-Huang65/AUX-TS)    |
| [Automated Self-Supervised Learning for Graphs](https://arxiv.org/abs/2106.05470) (AutoSSL) | ICLR'22    | Multi-task learning | Node classification; node clustering                         | [link](https://github.com/ChandlerBang/AutoSSL)   |
| [GPPT: Graph Pre-training and Prompt Tuning to Generalize Graph Neural Networks](https://dl.acm.org/doi/10.1145/3534678.3539249) | KDD'22     | Prompting           | Node classification                                          | [link](https://github.com/MingChen-Sun/GPPT)      |
| [Multi-task Self-supervised Graph Neural Networks Enable Stronger Task Generalization](https://arxiv.org/abs/2210.02016) (ParetoGNN) | ICLR'23    | Multi-task learning | Node classification; node clustering; graph partition; link prediction | [link](https://github.com/jumxglhf/ParetoGNN)     |
| [GraphPrompt: Unifying Pre-Training and Downstream Tasks for Graph Neural Networks](https://arxiv.org/abs/2302.08043) | WWW'23     | Prompting           | Node classification; graph classification                    | [link](https://github.com/Starlien95/GraphPrompt) |
| [All in One: Multi-task Prompting for Graph Neural Networks](https://arxiv.org/abs/2307.01504) | KDD'23     | Prompting           | Node classification (multi-class); graph classification; link prediction; edge regression; graph regression | [link](https://github.com/sheldonresearch/ProG)   |
| [When to Pre-Train Graph Neural Networks? From Data Generation Perspective!](https://arxiv.org/abs/2303.16458) (W2PGNN) | KDD'23     | Fine-tuning         | Node classification; graph classification                    | [link](https://github.com/caoyxuan/W2PGNN)        |
| [Chain of Propagation Prompting for Node Classification](https://dl.acm.org/doi/10.1145/3581783.3612431) (CPP) | MM'23      | Prompting           | Node classification                                          | --                                                |
| [Universal Prompt Tuning for Graph Neural Networks](https://arxiv.org/abs/2209.15240) (GPF) | NeurIPS'23 | Prompting           | Graph classification; biological function prediction         | [link](https://github.com/zjunet/GPF)             |
| [PRODIGY: Enabling In-context Learning Over Graphs](https://arxiv.org/abs/2305.12600) | NeurIPS'23 | Prompting           | Node classification; link prediction                         | [link](https://github.com/snap-stanford/prodigy)  |
| [An Empirical Study Towards Prompt-Tuning for Graph Contrastive Pre-Training in Recommendations]() (CPTPP) | NeurIPS'23 | Prompting           | Recommendation                                               | [link](https://github.com/Haoran-Young/CPTPP)     |
| [Fine-tuning Graph Neural Networks by Preserving Graph Generative Patterns](https://arxiv.org/abs/2312.13583) (G-Tuning) | AAAI'24    | Fine-tuning         | Graph classification                                         | [link](https://github.com/zjunet/G-Tuning)        |

</details>

# What's next?

:heart: Contributions by issues and pull requests to this source list are always welcome! Feel free to initiate a discussion with me, or give me a reminder if there are oversights of representative papers or categorical mistakes. 

