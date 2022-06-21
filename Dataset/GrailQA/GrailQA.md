### **RNG-KBQA: Generation Augmented Iterative Ranking for Knowledge Base Question Answering.** *Xi Ye et al.* **ACL, 2022** [(PDF)](./rng-kbqa.pdf) [(arXiv)](https://arxiv.org/abs/2109.08678) [(github)](https://github.com/salesforce/rng-kbqa) (Citations 6)<br />
  * 一句话总结：Bert排序LF + T5生成模型纠正
    ![Figure1](./Figure1.png)
    1. 从query中解析entity，在KG中查找两跳范围的路径，生成s表达式
    2. 利用BERT对s表达式排序<br />
    ![Figure2](./Figure2.png)
    3. 利用T5对最终结果泛化<br />

