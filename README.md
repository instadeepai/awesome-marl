# Awesome MARL: [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

There has been substantial growth in the field of Multi-Agent Reinforcemnt Learning (MARL) in recent years. MARL covers a wide variety of problem fields which are constantly in a state of flux.

This is a collection of review papers for MARL and evaluation methods for RL in general. We sort papers by publication date and survey subtopic. Any additions to this repo are welcome. Although our current focus is more on evaluation, this repository aims to include all relevant subtopics related to MARL.

## Overview
* [Survey Papers](https://github.com/instadeepai/awesome-marl/blob/main/README.md#survey-papers)
  * [Older Surveys](https://github.com/instadeepai/awesome-marl/blob/main/README.md#older-surveys)
* [Research Papers](https://github.com/instadeepai/awesome-marl/blob/main/README.md#research-papers)
  * [Value Factorisation](https://github.com/instadeepai/awesome-marl/blob/main/README.md#value-factorisation)
  * [Communication](https://github.com/instadeepai/awesome-marl/blob/main/README.md#communication) 
  * [Evaluation for RL](https://github.com/instadeepai/awesome-marl/blob/main/README.md#evaluation-for-rl)
  * [Evaluation for MARL](https://github.com/instadeepai/awesome-marl/blob/main/README.md#evaluation-for-marl)
  * [Implementation](https://github.com/instadeepai/awesome-marl/blob/main/README.md#implementation)
  * [Real-world challenges](https://github.com/instadeepai/awesome-marl/blob/main/README.md#real-world-challenges)
  * [Frameworks](https://github.com/instadeepai/awesome-marl/blob/main/README.md#frameworks)
  * [Benchmarks](https://github.com/instadeepai/awesome-marl/blob/main/README.md#benchmarks)
 
## Survey Papers
* [Multi‑agent deep reinforcement learning: a survey](https://link.springer.com/content/pdf/10.1007/s10462-021-09996-w.pdf) by Sven Gronauer and Klaus Diepold. Artifcial Intelligence Review 2021.
* [Multiagent Deep Reinforcement Learning: Challenges and Directions Towards Human-Like Approaches](https://www.researchgate.net/publication/353060371_Multiagent_Deep_Reinforcement_Learning_Challenges_and_Directions_Towards_Human-Like_Approaches) by Annie Wong, Thomas Bäck, Anna V. Kononova and Aske Plaat. arXiv 2021.
* [Deep Reinforcement Learning for Multi-Agent Systems: A Review of Challenges, Solutions and Applications](https://arxiv.org/pdf/1812.11794.pdf) by Thanh Thi Nguyen, Ngoc Duy Nguyen, and Saeid Nahavandi. arXiv 2019.
* [A Survey and Critique of Multiagent Deep Reinforcement Learning](https://arxiv.org/abs/1810.05587) by Pablo Hernandez-Leal, Bilal Kartal and Matthew E. Taylor. arXiv 2018.
* [Multi-Agent Reinforcement Learning: A Review of Challenges and Applications](https://www.mdpi.com/2076-3417/11/11/4948) by Lorenzo Canese, Gian C. Cardarilli, Luca Di Nunzio, Rocco Fazzolari, Daniele Giardino, Marco Re, and Sergio Spanò. MDPI 2021.
* [Multi-Agent Reinforcement Learning: A Selective Overview of Theories and Algorithms](https://arxiv.org/abs/1911.10635) by Kaiqing Zhang, Zhuoran Yang and Tamer Başar. arXiv 2019.
* [A Review of Cooperative Multi-Agent Deep Reinforcement Learning](https://arxiv.org/abs/1908.03963) by Afshin OroojlooyJadid and Davood Hajinezhad. arXiv 2019.
* [An Overview of Multi-Agent Reinforcement Learning from Game Theoretical Perspective](https://arxiv.org/abs/2011.00583) by Yaodong Yang and Jun Wang. arXiv 2020.
* [Evolutionary dynamics of multi-agent learning: A survey](https://jair.org/index.php/jair/article/view/10952) by Daan Bloembergen, Karl Tuyls, Daniel Hennes and Michael Kaisers. Journal of Artificial Intelligence Research 2015.
* [A survey of learning in multiagent environments: Dealing with non-stationarity](https://arxiv.org/abs/1707.09183) by Pablo Hernandez-Leal, Michael Kaisers, Tim Baarslag and Enrique Munoz de Cote. arXiv 2017.
* [A Survey on Transfer Learning for Multiagent Reinforcement Learning Systems](https://www.jair.org/index.php/jair/article/view/11396) by Felipe Leno Da Silva and Anna Helena Reali Costa. Journal of Artificial Intelligence Research 2019.
* [A Survey of Multi-Agent Reinforcement Learning with Communication](https://arxiv.org/abs/2203.08975) by Changxi Zhu, Mehdi Dastani and Shihan Wang. arXiv 2022.


### Older Surveys
* [Multiagent Learning: Basics, Challenges, and Prospects](http://www.weiss-gerhard.info/publications/AI_MAGAZINE_2012_TuylsWeiss.pdf) by Karl Tuyls and Gerhard Weiss. Ai Magazine 2012.
* [Independent reinforcement learners in cooperative markov games: a survey regarding coordination problems](https://perso.liris.cnrs.fr/laetitia.matignon/index/matignon2012KER.pdf) by Laetitia Matignon, Guillaume J. Laurent and Nadine Le Fort-Piat. Cambridge University Press 2012.
* [Multi-agent reinforcement learning:An overview](https://www.dcsc.tudelft.nl/~bdeschutter/pub/rep/10_003.pdf) by Lucian Buşoniu, Robert Babuška and Bart De Schutte. Springer 2010.
* [Multiagent systems: Algorithmic, game-theoretic, and logical foundations](https://www.masfoundations.org/download.html) by Yoav Shoham and Kevin Leyton-Brown. Cambridge University Press 2009.
* [An Introduction to MultiAgent Systems](https://www.cs.ox.ac.uk/people/michael.wooldridge/pubs/imas/IMAS2e.html) by Michael Wooldridge. John Wiley & Sons 2009.
* [If multi-agent learning is the answer, what is the question?](https://www.sciencedirect.com/science/article/pii/S0004370207000495) by Yoav Shoham, Rob Powers  and Trond Grenager. Elsevier 2007.
* [Multiagent learning is not the answer. It is the question](https://www.sciencedirect.com/science/article/pii/S0004370207000021) by Peter Stone. Elsevier 2007.
* [Cooperative Multi-Agent Learning: The State of the Art](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.307.6671) by  Liviu Panait and Sean Luke. JAAMAS 2005.
* [An overview of cooperative and competitive multiagent learning](https://cs.gmu.edu/~sean/papers/LAMAS05Overview.pdf) by Pieter Jan 't Hoen, Karl Tuyls, Liviu Panait, Sean Luke and J. A. La Poutré. AAMAS 2005.
* [Evolutionary game theory and multi-agent reinforcement learning](https://www.cambridge.org/core/journals/knowledge-engineering-review/article/abs/evolutionary-game-theory-and-multiagent-reinforcement-learning/CB038537B4DB36E74311984BC13AD742) by Karl Tuyls and Ann Nowe. Cambridge University Press 2005.
* [Multi-Agent Reinforcement Learning:a critical survey](https://www.cc.gatech.edu/classes/AY2009/cs7641_spring/handouts/MALearning_ACriticalSurvey_2003_0516.pdf) by  Yoav Shoham &  Rob Powers &  Trond Grenager. Stanford University 2003.
* [Multiagent Systems: A Modern Approach to Distributed Artificial Intelligence](https://ieeexplore.ieee.org/book/6267355) by Gerhard Weiss. MIT Press 2000.


## Research Papers

### Value Factorisation
* [VAST: Value Function Factorization with Variable Agent Sub-Teams](https://openreview.net/pdf?id=hyJKKIhfxxT) by Thomy Phan, Fabian Ritz, Lenz Belzner, Philipp Altmann, Thomas Gabor, Claudia Linnhoff-Popien. openreview 2021.
* [Qatten: A General Framework for Cooperative Multiagent Reinforcement Learning](https://arxiv.org/pdf/2002.03939.pdf) by Yaodong Yang, Jianye Hao, Ben Liao, Kun Shao, Guangyong Chen, Wulong Liu, Hongyao Tang. arXiv 2020.
* [QMIX: Monotonic Value Function Factorisation for Deep Multi-Agent Reinforcement Learning](https://arxiv.org/pdf/1803.11485.pdf) by Tabish Rashid, Mikayel Samvelyan, Christian Schroeder de Witt, Gregory Farquhar, Jakob Foerster, Shimon Whiteson. arXiv 2018.
* [Value-Decomposition Networks For Cooperative Multi-Agent Learning](https://arxiv.org/pdf/1706.05296.pdf) by Peter Sunehag, Guy Lever, Audrunas Gruslys, Wojciech Marian Czarnecki, Vinicius Zambaldi, Max Jaderberg, Marc Lanctot, Nicolas Sonnerat, Joel Z. Leibo, Karl Tuyls, Thore Graepel. arXiv 2017.
* [Multi-Agent Actor-Critic for Mixed Cooperative-Competitive Environments](https://arxiv.org/pdf/1706.02275.pdf) by Ryan Lowe, Yi Wu, Aviv Tamar, Jean Harb, Pieter Abbeel, Igor Mordatch. arXiv 2017.
* [Counterfactual Multi-Agent Policy Gradients](https://arxiv.org/pdf/1705.08926.pdf) by Jakob Foerster, Gregory Farquhar, Triantafyllos Afouras, Nantas Nardelli, Shimon Whiteson. arXiv 2017. 
* [Revisiting QMIX: Discriminative Credit Assignment by Gradient Entropy Regularization](https://arxiv.org/abs/2202.04427) by Jian Zhao, Yue Zhang, Xunhan Hu, Weixun Wang, Wengang Zhou, Jianye Hao, Jiangcheng Zhu and Houqiang Li. arXiv 2022.

### Communication
* [Multi-Agent Graph-Attention Communication and Teaming](https://www.ifaamas.org/Proceedings/aamas2021/pdfs/p964.pdf) by Yaru Niu, Rohan Paleja and Matthew Gombolay. ifaamas 2021.
* [Emergent Communication through Negotiation](https://arxiv.org/pdf/1804.03980) by Kris Cao, Angeliki Lazaridou, Marc Lanctot, Joel Z Leibo, Karl Tuyls, Stephen Clark. arXiv 2018.
* [Emergence of Linguistic Communication from Referential Games with Symbolic and Pixel Input](https://arxiv.org/pdf/1804.03984) by Angeliki Lazaridou, Karl Moritz Hermann, Karl Tuyls, Stephen Clark. arXiv 2018.
* [TarMAC: Targeted Multi-Agent Communication](https://arxiv.org/pdf/1810.11187.pdf)by Abhishek Das, Théophile Gervet, Joshua Romoff, Dhruv Batra, Devi Parikh, Michael Rabbat, Joelle Pineau. arXiv 2018.
* [Emergence of Language with Multi-agent Games: Learning to Communicate with Sequences of Symbols](https://arxiv.org/pdf/1705.11192) by Serhii Havrylov, Ivan Titov. arXiv 2017.
* [Learning to Communicate with Deep Multi-Agent Reinforcement Learning](https://arxiv.org/pdf/1605.06676.pdf) by Jakob N. Foerster, Yannis M. Assael, Nando de Freitas, Shimon Whiteson. arXiv 2016.
* [Learning Multiagent Communication with Backpropagation](https://arxiv.org/pdf/1605.07736.pdf) by Sainbayar Sukhbaatar, Arthur Szlam, Rob Fergus. arXiv 2016.
* [Disentangling Successor Features for Coordination in Multi-agent Reinforcement Learning](https://arxiv.org/abs/2202.07741) by Seung Hyun Kim, Neale Van Stralen, Girish Chowdhary and Huy T. Tran. arXiv 2022.
* [Multi-Agent MDP Homomorphic Networks](https://arxiv.org/abs/2110.04495) by Elise van der Pol, Herke van Hoof, Frans A. Oliehoek and Max Welling. arXiv 2021.

### Evaluation for RL
* [Protecting Against Evaluation Overfitting in Empirical Reinforcement Learning](https://www.cs.utexas.edu/~pstone/Papers/bib2html-links/ADPRL11-shimon.pdf) by Shimon Whiteson, Brian Tanner, Matthew E. Taylor, and Peter Stone. arXiv 2011.
* [How Many Random Seeds? Statistical Power Analysis in Deep Reinforcement Learning Experiments](https://arxiv.org/pdf/1806.08295.pdf) by Cedric Colas, Olivier Sigaud and Pierre-Yves Oudeyer.arXiv 2018.
* [Deep Reinforcement Learning that Matters](https://arxiv.org/pdf/1709.06560.pdf) by Peter Henderson, Riashat Islam, Philip Bachman, Joelle Pineau, Doina Precup and David Meger. AAAI 2018.
* [A Hitchhiker’s Guide to Statistical Comparisons of Reinforcement Learning Algorithms](https://arxiv.org/pdf/1904.06979.pdf) by Cédric Colas, Olivier Sigaud and Pierre-Yves Oudeyer. arXiv 2019.
* [Evaluating the Performance of Reinforcement Learning Algorithms](https://arxiv.org/pdf/2006.16958.pdf) by Scott M. Jordan, Yash Chandak, Daniel Cohen, Mengxue Zhang, Philip S. Thomas. ICML 2020.
* [Deep Reinforcement Learning at the Edge of the Statistical Precipice](https://arxiv.org/pdf/2108.13264.pdf) by Rishabh Agarwal, Max Schwarzer, Pablo Samuel Castro, Aaron Courville and  Marc G. Bellemare. NeurIPS 2021.
* [MEASURING THE RELIABILITY OF REINFORCEMENT LEARNING ALGORITHMS](https://arxiv.org/pdf/1912.05663.pdf) by Stephanie C.Y. Chan, Samuel Fishman, John Canny, Anoop Korattikara, and Sergio Guadarrama. ICRL 2020.



### Evaluation for MARL
* [Benchmarking Multi-Agent Deep Reinforcement Learning Algorithms in Cooperative Tasks](https://arxiv.org/pdf/2006.07869.pdf) by Georgios Papoudakis, Filippos Christianos,  Lukas Schäfer and Stefano V. Albrecht. NeurIPS 2021.
* [Scalable Evaluation of Multi-Agent Reinforcement Learning with Melting Pot](https://arxiv.org/pdf/2107.06857.pdf) by Joel Z. Leibo, Edgar Du ́e ̃nez-Guzm ́an, Alexander Sasha Vezhnevets, John P. Agapiou, Peter Sunehag, Raphael Koster ,Jayd Matyas, Charles Beattie, Igor Mordatch and Thore Graepel. PMLR 2021.

### Implementation
* [IMPLEMENTATION MATTERS IN DEEP POLICY GRADIENTS: A CASE STUDY ON PPO AND TRPO](https://arxiv.org/pdf/2005.12729.pdf) by Logan Engstrom, Andrew Ilyas, Shibani Santurkar, Dimitris Tsipras, Firdaus Janoos, Larry Rudolph, and Aleksander Madry. ICLR 2020.
* [The Surprising Effectiveness of PPO in Cooperative Multi-Agent Games](https://arxiv.org/pdf/2103.01955.pdf) by Chao Yu,Akash Velu, Eugene Vinitsky, Yu Wang, Alexandre Bayen. arXiv 2021.
* [RETHINKING THE IMPLEMENTATION TRICKS AND MONOTONICITY CONSTRAINT IN COOPERATIVE MULTI-AGENT REINFORCEMENT LEARNING](https://arxiv.org/pdf/2102.03479.pdf) by Jian Hu, Siyang Jiang, Seth Austin Harding, Haibin Wu and Shih-wei Liao. arXiv 2022.
* [API: Boosting Multi-Agent Reinforcement Learning via Agent-Permutation-Invariant Networks](https://arxiv.org/abs/2203.05285) by Xiaotian Hao, Weixun Wang, Hangyu Mao, Yaodong Yang, Dong Li, Yan Zheng, Zhen Wang and Jianye Hao. arXiv 2022.

### Real-world challenges
* [On Testing Machine Learning Programs](https://arxiv.org/pdf/1812.02257.pdf) by Houssem Ben Braieka, Foutse Khomh. Journal of Systems and Software 2018.
* [Challenges of Real-World Reinforcement Learning](https://arxiv.org/pdf/1904.12901.pdf) by Gabriel Dulac-Arnold, Daniel Mankowitz and Todd Hester. ICML 2019.
* [An Introduction to Multi-Agent Reinforcement Learning and Review of its Application to Autonomous Mobility](https://arxiv.org/abs/2203.07676) by Lukas M. Schmidt, Johanna Brosig, Axel Plinge, Bjoern M. Eskofier and Christopher Mutschler. arXiv 2022.
* [Evaluating the Safety of Deep Reinforcement Learning Models using Semi-Formal Verification](https://arxiv.org/pdf/2010.09387.pdf) by Davide Corsi, Enrico Marchesini and Alessandro Farinelli. arXiv 2020.
* [Evaluating the Robustness of Collaborative Agents](https://arxiv.org/pdf/2101.05507.pdf) by Paul Knott, Micah Carroll, Sam Devlin, Kamil Ciosek, Katja Hofmann and A. D. Dragan. arXiv 2021.
* [An empirical investigation of the challenges of real-world reinforcement learning](https://arxiv.org/pdf/2003.11881.pdf) by Gabriel Dulac-Arnold, Nir Levine, Daniel J. Mankowitz, Jerry Li, Cosmin Paduraru, Sven Gowal and Todd Heste. arXiv 2021.

### Frameworks
* [Mava: a research framework for distributed multi-agent reinforcement learning](https://arxiv.org/pdf/2107.01460.pdf) by Arnu Pretorius, Kale-ab Tessera, Andries P. Smit, Kevin Eloff, Claude Formanek, St John Grimbly, Siphelele Danisa, Lawrence Francis, Jonathan Shock, Herman Kamper, Willie Brink, Herman Engelbrecht, Alexandre Laterre and Karim Beguir. arXiv 2021.

### Benchmarks
* [Behaviour Suite for Reinforcement Learning](https://arxiv.org/pdf/1908.03568.pdf) by Ian Osband, Yotam Doron, Matteo Hessel, John Aslanides, Eren Sezener, Andre Saraiva, Katrina McKinney, Tor Lattimore, Csaba Szepesvari, Satinder Singh, Benjamin Van Roy, Richard Sutton, David Silver and Hado Van Hasselt. arXiv 2020.
* [The StarCraft Multi-Agent Challenge](https://arxiv.org/abs/1902.04043) by Mikayel Samvelyan, Tabish Rashid, Christian Schroeder de Witt, Gregory Farquhar, Nantas Nardelli, Tim G. J. Rudner, Chia-Man Hung, Philip H. S. Torr, Jakob Foerster, Shimon Whiteson. arXiv 2019.
* [Comparative Evaluation of Cooperative Multi-Agent Deep Reinforcement Learning Algorithms](https://ala2021.vub.ac.be/papers/ALA2021_paper_44.pdf) by Georgios Papoudakis, Filippos Christianos, Lukas Schäfer, Stefano V. Albrecht. ALA 2021.
