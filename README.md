import random

# 参与者列表
participants = ["参与者1", "参与者2", "参与者3", "参与者4", "参与者5"]

# 问题列表
questions = [
    "问题1：什么是Python的主要用途？",
    "问题2：Python的创始人是谁？",
    "问题3：Python中如何定义一个函数？",
    "问题4：Python中的缩进是什么作用？",
]

# 抢答函数
def start_quiz():
    # 随机选择一个问题
    question = random.choice(questions)
    print(question)

    # 等待参与者回答问题
    input("按Enter键开始回答...")
    # 随机选择一个回答者
    responder = random.choice(participants)
    print(f"{responder} 抢答成功！\n")

# 主程序循环
while True:
    # 提示是否开始新的一轮
    response = input("按Enter键开始新一轮抢答，或输入 'q' 退出：")
    if response.lower() == 'q':
        break

   

