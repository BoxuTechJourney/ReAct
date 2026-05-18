# ReAct 提示工程 (Prompting)

用于 ICLR 2023 论文 [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629) 的 GPT-3 原理验证与提示代码。

若要将 ReAct 应用于更多任务，可以考虑尝试 [LangChain 的 zero-shot ReAct Agent（零样本 ReAct 代理）](https://python.langchain.com/docs/modules/agents/agent_types/react.html)。

## 环境设置
您首先需要拥有一个 OpenAI API 密钥，并将其存储在环境变量 `OPENAI_API_KEY` 中（相关安全实践请参见[此处](https://help.openai.com/en/articles/5112595-best-practices-for-api-key-safety)）。

依赖包要求：`openai`，此外请按照[此处](https://github.com/alfworld/alfworld)的说明安装 `alfworld`。

## 实验
运行相关的 Notebook 文档：`{hotpotqa,fever,alfworld,webshop}.ipynb`。因为 HotpotQA 和 FEVER 拥有庞大的验证集，在示例中我们仅随机运行了 500 个样本（详情参见 notebook）。我们发现 PaLM 和 GPT-3 各自在不同的任务上表现得更好。

| 模型 | HotpotQA (500随机 dev, EM) | FEVER (500随机 dev, EM) | AlfWorld (成功率) | WebShop  (成功率) |
|--------------------|-------------------------------|----------------------------|-------------------------|-------------------------|
| PaLM-540B (论文效果)  | 29.4                          | 62.2                       | 70.9                    | 40                      |
| GPT-3 (davinci-002) | 30.4                          | 54                         | 78.4                    | 35.8                    |

## 引用

```bibtex
@inproceedings{yao2023react,
  title = {{ReAct}: Synergizing Reasoning and Acting in Language Models},
  author = {Yao, Shunyu and Zhao, Jeffrey and Yu, Dian and Du, Nan and Shafran, Izhak and Narasimhan, Karthik and Cao, Yuan},
  booktitle = {International Conference on Learning Representations (ICLR) },
  year = {2023},
  html = {https://arxiv.org/abs/2210.03629},
}
```
