---
layout: default
title: ReadHub
permalink: /books/
nav: false
collection: books
---

> What an astonishing thing a book is. It's a flat object made from a tree with flexible parts on which are imprinted lots of funny dark squiggles. But one glance at it and you're inside the mind of another person, maybe somebody dead for thousands of years. Across the millennia, an author is speaking clearly and silently inside your head, directly to you. Writing is perhaps the greatest of human inventions, binding together people who never knew each other, citizens of distant epochs. Books break the shackles of time. A book is proof that humans are capable of working magic.
>
> -- Carl Sagan, Cosmos, Part 11: The Persistence of Memory (1980)

## Papers that I am reading, have read, or will read
- **[AI Alignment Requires Understanding How Data Shapes Structure and Generalisation](https://arxiv.org/abs/2502.05475)**  
  データの統計的性質は，loss landscapeの形状や学習プロセス，モデルが獲得したアルゴリズムに間接的に影響を与えるが，間接的なので同じデータを与えてもモデルの振る舞いが異なる時がある．（つまりデータの性質だけではモデルの振る舞いは予測できない）なので，本質的なアライメントのためには，モデル内部を知る必要があるという主張．（道具はSLT）

- **[The Geometry of Self-Verification in a Task-Specific Reasoning Model](https://arxiv.org/abs/2504.14379)**  
  Probingを使って，self-verificationに寄与しているGLUの重み(2層MLPの2層目に相当)を見つける．層の後半に多い．self-verificationする/しないのベクトルは逆を向いている．Intervention実験から，また，Attentionにおいてはprevious-token headが重要ということがわかった．層の前半に多い，(previous-token headはinduction headの1層目のhead)．つまり，いくつかのhead(論文では3つ)がself-verificationを起こすGLUのvectorをactivateさせている（GLUは入力依存なのでこれが可能）．Base Modelにもこの分析は通用する，つまりbase modelにすでに備わっているself-verificationの能力をRL-FTで強化しているのでは？ということ

- **[Shaping the Safety Boundaries: Understanding and Defending Against Jailbreaks in Large Language Models](https://arxiv.org/abs/2412.17034)**  
  Jailbreakの仕組み(ACL'25)．モデル内部にHarmfulな内容をrepresentした活性化空間がありクラスターになっている，Jailbreakはこのクラスタの境界(safety boundary)を内から外に跨ぐような攻撃．（Harmfulな活性値を良好な活性値の空間にしてしまう）この分析から新たな防御手法を提案

- **[Next-token pretraining implies in-context learning](https://arxiv.org/abs/2505.18373)**  
  Next Token PredictionでICLの能力が獲得される理論．ウェブデータのような非エルゴート的なデータの場合，次のトークンのCEを下げようとすると，モデルはコンテキストからどのデータソース（エルゴード成分）からのシーケンスであるかを識別する必要があり，この「成分の曖昧さの解消」プロセスがICLのメカニズムに重要．

- **[Language Models Are Capable of Metacognitive Monitoring and Control of Their Internal Activations](https://arxiv.org/abs/2505.13763)**  
  LLMは自分の活性値をモニタリング/制御できる．ニューロフィードバックを用いた実験．

- **[Adversarial Examples Aren't Bugs, They're... Superposition?](https://livgorton.com/adversarial-examples-superposition/)**  
  敵対的攻撃のmajorな原因はsuperpositionだという主張．敵対的攻撃に頑健なモデルはSAEのlossが低い（≒敵対的攻撃に強いと表現の重ね合わせが少ない，敵対的攻撃に弱いと表現の重ね合わせが激しい）

- **[Layer by Layer: Uncovering Hidden Representations in Language Models](https://arxiv.org/abs/2502.02013)**  
  ICML’25 spotlight，著者にルカンがいる．token embedding(N x D)のグラム行列(N x N)の固有値のエントロピーをメトリクスとして，内部表現の質を図る．（この指標が低いと少数の固有値が支配的で表現が圧縮されているということ）decoder-onlyのLLMでは，中間層でガクッと下がる(表現が良くなる)．BERT,mambaはそうならない．これはダウンストリーミングタスクの性能とも対応する．


- **[Measuring In-Context Computation Complexity via Hidden State Prediction](https://arxiv.org/abs/2503.13431)**  
  LLMの内部状態を予測するモデルを後から取り付けることで，内部の計算複雑性を測る．（著者にシュミット・フーバーがいる）

- **[A Percolation Model of Emergence: Analyzing Transformers Trained on a Formal Language](https://arxiv.org/abs/2408.12578)**  
  創発現象は概念の浸透によって起きる．（Hidenori Tanaka）

- **[Confidence Regulation Neurons in Language Models](https://arxiv.org/abs/2406.16254)**  
  LLMは最後のLayer Normの直前でunembedding行列の全ての列ベクトルに直交する方向のベクトルを使って確信度を調整している．その方向を強めることがtemplatureを操作することに近い

- **[Refusal in Language Models Is Mediated by a Single Direction](https://arxiv.org/abs/2406.11717)**  
  (Harmfulな入力の活性値)-(harmlessな入力の活性値)でrefusal directionが得られる．それを使って介入すると簡単にjailbreakができる

- **[Unlocking the Power of Function Vectors for Characterizing and Mitigating Catastrophic Forgetting in Continual Instruction Tuning](https://arxiv.org/abs/2502.11019)**  
  LLMのCatastrophic forgetting（破滅的忘却）は，特定の知識/能力が上書きされているわけでなく，内部に存在しているがそれを「呼び出す方法」を忘れている．Activation patching (Function Vector)を用いて分析．評価がめちゃ高い


- **[Looking Inward: Language Models Can Learn About Themselves by Introspection](https://arxiv.org/abs/2410.137879)**  
  LLMは内省能力があるか？あるらしい．他のモデルより自分の内部状態について自分で当てられる

- **[An exactly solvable model for emergence and scaling laws in the multitask sparse parity problem](https://arxiv.org/abs/2404.17563)**  
  段階的なスキルの獲得によって滑らかなscaling lawが説明できる

