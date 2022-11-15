## Research Papers

This is a collection of papers for Deep MARL. We sort papers by publication date and survey subtopic. Any additions to this repo are welcome.

### Value Factorisation

<details> <summary> <a href="https://proceedings.neurips.cc/paper/2021/file/c97e7a5153badb6576d8939469f58336-Paper.pdf"> VAST: Value Function Factorization with Variable Agent Sub-Teams </a>by Thomy Phan, Fabian Ritz, Lenz Belzner, Philipp Altmann, Thomas Gabor, Claudia Linnhoff-Popien. NeurIPS 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://openreview.net/pdf?id=Rcmk0xxIQV"> QPLEX: Duplex Dueling Multi-Agent Q-Learning </a>by Jianhao Wang, Zhizhou Ren, Terry Liu, Yang Yu, Chongjie Zhang. ICLR 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  We explore value-based multi-agent  reinforcement learning (MARL) in the popular paradigm of centralized training with decentralized execution (CTDE). CTDE has an important concept, Individual-Global-Max (IGM) principle, which requires the consistency between joint and local action selections to support efficient local decision-making. However, in order to achieve scalability, existing MARL methods either limit representation expressiveness of their value function classes or relax the IGM consistency, which may suffer from instability risk or may not perform well in complex domains. This paper presents a novel MARL approach, called duPLEX dueling multi-agent Q-learning (QPLEX), which takes a duplex dueling network architecture to factorize the joint value function. This duplex dueling structure encodes the IGM principle into the neural network architecture and thus enables efficient value function learning. Theoretical analysis shows that QPLEX achieves a complete IGM function class. Empirical experiments on StarCraft II micromanagement tasks demonstrate that QPLEX significantly outperforms stateof-the-art baselines in both online and offline data collection settings, and also reveal that QPLEX achieves high sample efficiency and can benefit from offline datasets without additional online exploration. <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2002.03939.pdf"> Qatten: A General Framework for Cooperative Multiagent Reinforcement Learning </a>by Yaodong Yang, Jianye Hao, Ben Liao, Kun Shao, Guangyong Chen, Wulong Liu, Hongyao Tang. arXiv 2020 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="http://proceedings.mlr.press/v97/son19a/son19a.pdf"> QTRAN: Learning to Factorize with Transformation for Cooperative Multi-Agent Reinforcement learning </a>by Kyunghwan Son, Daewoo Kim, Wan Ju Kang, David Hostallero, Yung Yi. ICML 2019 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary> We explore value-based solutions for multi-agent reinforcement learning (MARL) tasks in the centralized training with decentralized execution (CTDE) regime popularized recently. However, VDN and QMIX are representative examples that use the idea of factorization of the joint actionvalue function into individual ones for decentralized execution. VDN and QMIX address only a fraction of factorizable MARL tasks due to their structural constraint in factorization such as additivity and monotonicity. In this paper, we propose a new factorization method for MARL, QTRAN, which is free from such structural constraints and takes on a new approach to transforming the original joint action-value function into an easily factorizable one, with the same optimal actions. QTRAN guarantees more general factorization than VDN or QMIX, thus covering a much wider class of MARL tasks than does previous methods. Our experiments for the tasks of multi-domain Gaussian-squeeze and modified predator-prey demonstrate QTRAN’s superior performance with especially larger margins in games whose payoffs penalize non-cooperative behavior more aggressively. <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1803.11485.pdf"> QMIX: Monotonic Value Function Factorisation for Deep Multi-Agent Reinforcement Learning </a>by Tabish Rashid, Mikayel Samvelyan, Christian Schroeder de Witt, Gregory Farquhar, Jakob Foerster, Shimon Whiteson. arXiv 2018 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1706.05296.pdf"> Value-Decomposition Networks For Cooperative Multi-Agent Learning </a>by Peter Sunehag, Guy Lever, Audrunas Gruslys, Wojciech Marian Czarnecki, Vinicius Zambaldi, Max Jaderberg, Marc Lanctot, Nicolas Sonnerat, Joel Z. Leibo, Karl Tuyls, Thore Graepel. arXiv 2017 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1706.02275.pdf"> Multi-Agent Actor-Critic for Mixed Cooperative-Competitive Environments </a>by Ryan Lowe, Yi Wu, Aviv Tamar, Jean Harb, Pieter Abbeel, Igor Mordatch. arXiv 2017 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1705.08926.pdf"> Counterfactual Multi-Agent Policy Gradients </a>by Jakob Foerster, Gregory Farquhar, Triantafyllos Afouras, Nantas Nardelli, Shimon Whiteson. arXiv 2017 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/abs/2202.04427"> Revisiting QMIX: Discriminative Credit Assignment by Gradient Entropy Regularization </a>y Jian Zhao, Yue Zhang, Xunhan Hu, Weixun Wang, Wengang Zhou, Jianye Hao, Jiangcheng Zhu and Houqiang Li. arXiv 2022 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<br/>

### Communication

<details> <summary> <a href="https://www.ifaamas.org/Proceedings/aamas2021/pdfs/p964.pdf"> Multi-Agent Graph-Attention Communication and Teaming </a>by Yaru Niu, Rohan Paleja and Matthew Gombolay. ifaamas 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1804.03980"> Emergent Communication through Negotiation </a>by Kris Cao, Angeliki Lazaridou, Marc Lanctot, Joel Z Leibo, Karl Tuyls, Stephen Clark. arXiv 2018 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1804.03984"> Emergence of Linguistic Communication from Referential Games with Symbolic and Pixel Input </a>by Angeliki Lazaridou, Karl Moritz Hermann, Karl Tuyls, Stephen Clark. arXiv 2018 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1810.11187.pdf"> TarMAC: Targeted Multi-Agent Communication </a>by Abhishek Das, Théophile Gervet, Joshua Romoff, Dhruv Batra, Devi Parikh, Michael Rabbat, Joelle Pineau. arXiv 2018<a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1705.11192"> Emergence of Language with Multi-agent Games: Learning to Communicate with Sequences of Symbols </a>by Serhii Havrylov, Ivan Titov. arXiv 2017<a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1605.06676.pdf"> Learning to Communicate with Deep Multi-Agent Reinforcement Learning </a>by Jakob N. Foerster, Yannis M. Assael, Nando de Freitas, Shimon Whiteson. arXiv 2016<a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1605.07736.pdf"> Learning Multiagent Communication with Backpropagation </a>by Sainbayar Sukhbaatar, Arthur Szlam, Rob Fergus. arXiv 2016<a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/abs/2202.07741"> Disentangling Successor Features for Coordination in Multi-agent Reinforcement Learning </a>by Seung Hyun Kim, Neale Van Stralen, Girish Chowdhary and Huy T. Tran. arXiv 2022<a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/abs/2110.04495"> Multi-Agent MDP Homomorphic Networks </a>by Elise van der Pol, Herke van Hoof, Frans A. Oliehoek and Max Welling. arXiv 2021<a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<br/>

### Evaluation for MARL

<details> <summary> <a href="https://arxiv.org/pdf/2006.07869.pdf"> Benchmarking Multi-Agent Deep Reinforcement Learning Algorithms in Cooperative Tasks </a>by Georgios Papoudakis, Filippos Christianos,  Lukas Schäfer and Stefano V. Albrecht. NeurIPS 2021. <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2006.07869.pdf"> Scalable Evaluation of Multi-Agent Reinforcement Learning with Melting Pot </a>by Joel Z. Leibo, Edgar Du ́e ̃nez-Guzm ́an, Alexander Sasha Vezhnevets, John P. Agapiou, Peter Sunehag, Raphael Koster ,Jayd Matyas, Charles Beattie, Igor Mordatch and Thore Graepel. PMLR 2021. <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<br/>

### Implementation

<details> <summary> <a href="https://arxiv.org/pdf/2005.12729.pdf"> IMPLEMENTATION MATTERS IN DEEP POLICY GRADIENTS: A CASE STUDY ON PPO AND TRPO </a>by Logan Engstrom, Andrew Ilyas, Shibani Santurkar, Dimitris Tsipras, Firdaus Janoos, Larry Rudolph, and Aleksander Madry. ICLR 2020 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2103.01955.pdf"> The Surprising Effectiveness of PPO in Cooperative Multi-Agent Games </a>by Chao Yu,Akash Velu, Eugene Vinitsky, Yu Wang, Alexandre Bayen. arXiv 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2102.03479.pdf"> RETHINKING THE IMPLEMENTATION TRICKS AND MONOTONICITY CONSTRAINT IN COOPERATIVE MULTI-AGENT REINFORCEMENT LEARNING </a>by Jian Hu, Siyang Jiang, Seth Austin Harding, Haibin Wu and Shih-wei Liao. arXiv 2022 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/abs/2203.05285"> API: Boosting Multi-Agent Reinforcement Learning via Agent-Permutation-Invariant Networks </a>by Xiaotian Hao, Weixun Wang, Hangyu Mao, Yaodong Yang, Dong Li, Yan Zheng, Zhen Wang and Jianye Hao. arXiv 2022 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<br/>

### Real-world challenges

<details> <summary> <a href="https://arxiv.org/pdf/1812.02257.pdf"> On Testing Machine Learning Programs </a>by Houssem Ben Braieka, Foutse Khomh. Journal of Systems and Software 2018 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/1904.12901.pdf"> Challenges of Real-World Reinforcement Learning </a>by Gabriel Dulac-Arnold, Daniel Mankowitz and Todd Hester. ICML 2019 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/abs/2203.07676"> An Introduction to Multi-Agent Reinforcement Learning and Review of its Application to Autonomous Mobility </a>y Lukas M. Schmidt, Johanna Brosig, Axel Plinge, Bjoern M. Eskofier and Christopher Mutschler. arXiv 2022 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2010.09387.pdf"> AEvaluating the Safety of Deep Reinforcement Learning Models using Semi-Formal Verification </a>by Davide Corsi, Enrico Marchesini and Alessandro Farinelli. arXiv 2020 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2101.05507.pdf"> Evaluating the Robustness of Collaborative Agents </a>by Paul Knott, Micah Carroll, Sam Devlin, Kamil Ciosek, Katja Hofmann and A. D. Dragan. arXiv 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/pdf/2003.11881.pdf"> An empirical investigation of the challenges of real-world reinforcement learning </a>by Gabriel Dulac-Arnold, Nir Levine, Daniel J. Mankowitz, Jerry Li, Cosmin Paduraru, Sven Gowal and Todd Heste. arXiv 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<br/>

### Frameworks

<details> <summary> <a href="https://arxiv.org/pdf/2107.01460.pdf"> Mava: a research framework for distributed multi-agent reinforcement learning </a>by Arnu Pretorius, Kale-ab Tessera, Andries P. Smit, Kevin Eloff, Claude Formanek, St John Grimbly, Siphelele Danisa, Lawrence Francis, Jonathan Shock, Herman Kamper, Willie Brink, Herman Engelbrecht, Alexandre Laterre and Karim Beguir. arXiv 2021. <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8">   </a> </summary>  TODO: add abstract <br> - </details>

<br/>

### Benchmarks

<details> <summary> <a href="https://arxiv.org/pdf/1908.03568.pdf"> Behaviour Suite for Reinforcement Learning </a>by Ian Osband, Yotam Doron, Matteo Hessel, John Aslanides, Eren Sezener, Andre Saraiva, Katrina McKinney, Tor Lattimore, Csaba Szepesvari, Satinder Singh, Benjamin Van Roy, Richard Sutton, David Silver and Hado Van Hasselt. arXiv 2020 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8"></a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://arxiv.org/abs/1902.04043"> The StarCraft Multi-Agent Challenge </a>By Mikayel Samvelyan, Tabish Rashid, Christian Schroeder de Witt, Gregory Farquhar, Nantas Nardelli, Tim G. J. Rudner, Chia-Man Hung, Philip H. S. Torr, Jakob Foerster, Shimon Whiteson. arXiv 2019 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8"> </a> </summary>  TODO: add abstract <br> - </details>

<details> <summary> <a href="https://ala2021.vub.ac.be/papers/ALA2021_paper_44.pdf"> Comparative Evaluation of Cooperative Multi-Agent Deep Reinforcement Learning Algorithms </a>by Georgios Papoudakis, Filippos Christianos, Lukas Schäfer, Stefano V. Albrecht. ALA 2021 <a href="https://www.Summary.so/instadeep/Multiagent-Learning-Basics-Challenges-and-Prospect-21cb7b4294b84a4188cafd184a3deed8"> </a> </summary>  TODO: add abstract <br> - </details>

<br/>