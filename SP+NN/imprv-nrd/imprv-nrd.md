### **Improved Neural Relation Detection for Knowledge Base Question Answering.** *Mo Yu et al.* **ACL, 2017** [(PDF)](./imprv-nrd.pdf) [(arXiv)](https://arxiv.org/abs/1704.06194) (Citations 266)
  * 一句话总结：Bert排序LF + T5生成模型纠正
    ![Figure1](./Figure1.png)
    1. 从query中解析entity，在KG中查找两跳范围的路径，生成s表达式
    2. 利用BERT对s表达式排序<br />
    ![Figure2](./Figure2.png)
    3. 利用T5对最终结果泛化<br />

