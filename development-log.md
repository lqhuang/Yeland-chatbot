# 开发日志

## 第一次运行 chatbot 的 demo 代码

```
from chatterbot.training.trainers import ListTrainer
from chatterbot import ChatBot


chatbot = ChatBot("Ron Obvious")

conversation = [
        "Hello",
        "Hi there!",
        "How are you doing",
        "I'm doing great.",
        "That is good to hear",
        "Thank you.",
        "You're welcome."
]

chatbot.set_trainer(ListTrainer)
chatbot.train(conversation)

response = chatbot.get_response("Good morning!")
print(response)
```

结果在载入 chatbot 模块的时候提醒没有合适的 sequencematcher
D:\Programs\Python35\lib\site-packages\fuzzywuzzy\fuzz.py:35: UserWarning: Using slow pure-python SequenceMatcher. Install python-Levenshtein to remove this warning
  warnings.warn('Using slow pure-python SequenceMatcher. Install python-Levenshtein to remove this warning')

尝试安装
pip install python-levenshtein
但是失败

尝试通过 wheel 安装
python_Levenshtein-0.12.0-cp35-none-win_amd64.whl 

解决