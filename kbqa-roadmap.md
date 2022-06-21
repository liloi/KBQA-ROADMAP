# KBQA ROADMAP
## What's KBQA?
Knowledge base question answering (KBQA) is an important task in natural language processing. It aims to answer a question over a knowledge base (KB).
## KBQA Evolutional Diagram (2013 ~ now)
```mermaid
flowchart TB
  %% 根节点
  id_kbqa[KBQA]
  click id_kbqa "./Survey/" "kbqa_survey"
  %% SP & IR两大方向
  id_kbqa --> id_sp[Semantic Parser]
  click id_sp "./SP+NN/Survey/"
  id_kbqa --> id_ir[Information Retrive]
  id_kbqa --> id_other[Other]

  %% SP中的LF专题
  id_sp --Logical Form--> λ-Calculas --> λ-DCS
  click λ-DCS "./SP+NN/lambdaDCS/lambdaDCS.md" "lambdaDCS"


  %% SP主流方法
  id_sp ==Query Graph==> STAGG
  click STAGG "./SP+NN/stagg/stagg.md" "STAGG"
  STAGG ==+ constraint type==> MultiCG
  click MultiCG "./SP+NN/multicg/multicg.md" "MultiCG"
  MultiCG ==+ biLSTM==> ImprvNRD
  click ImprvNRD "./SP+NN/imprv-nrd/imprv-nrd.md" "ImproveNRD"
  id_sp --> CBR-KBQA
  id_sp --> RNG-KBQA
  click RNG-KBQA "./SP+NN/rng-kbqa/rng-kbqa.md" "RNG-KBQA"

  %% IR主流方法
  id_ir --> id_mn[Memory Network]
  id_ir --> id_1[balabala1]
  id_ir --> id_2[balabala2]

  %% 其他方法
  id_other --> id_nsm[NSM]
```
## KBQA Dataset
| Name | Year | KB-based | Leaderboard | Download |
| :--: | :--: | ---- | ---- | :--: |
| WebQuestions | 2015 | Freebase | [leaderboard](https://paperswithcode.com/sota/question-answering-on-webquestions) | ---- | :--: |
| WebQuestionsSP | 2016 | Freebase | [leaderboard](https://paperswithcode.com/sota/semantic-parsing-on-webquestionssp) | [Download](https://www.microsoft.com/en-us/research/publication/the-value-of-semantic-parse-labeling-for-knowledge-base-question-answering-2/) | :--: |
| [ComplexQuestions](./SP+NN/multicg/multicg.md) | 2016 | Freebase | []() | [Download]() | :--: |
| [GrailQA](./Dataset/GrailQA/GrailQA.md) | 2021 | Freebase | [leaderboard](https://dki-lab.github.io/GrailQA/) | ---- |
| [KQA](./Dataset/KQA/KQA.md) | 2022 | Wikidata | -- | [download](http://thukeg.gitee.io/kqa-pro/) |
