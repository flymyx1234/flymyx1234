import time

class Responder:
    def __init__(self):
        self.participants = {}
        self.responses = {}
        self.question = ""
        self.is_question_active = False

    def start_question(self, question):
        self.question = question
        self.is_question_active = True
        self.responses = {}
        print(f"问题: {question}")

    def stop_question(self):
        self.is_question_active = False

    def add_participant(self, name):
        if name not in self.participants:
            self.participants[name] = time.time()
            print(f"{name} 已加入抢答")

    def answer_question(self, name, answer):
        if self.is_question_active:
            if name in self.responses:
                print(f"{name} 已经回答过了！")
            else:
                self.responses[name] = answer
                print(f"{name} 回答: {answer}")
        else:
            print("目前没有问题可以回答")

    def display_responses(self):
        if not self.is_question_active:
            print("目前没有问题可以回答")
        else:
            print("回答情况:")
            for name, answer in self.responses.items():
                print(f"{name}: {answer}")

if __name__ == "__main__":
    responder = Responder()

    while True:
        print("\n选择操作:")
        print("1. 开始新问题")
        print("2. 停止问题")
        print("3. 加入抢答")
        print("4. 回答问题")
        print("5. 显示回答情况")
        print("6. 退出")
        choice = input("请输入操作编号: ")

        if choice == "1":
            question = input("请输入新问题: ")
            responder.start_question(question)
        elif choice == "2":
            responder.stop_question()
        elif choice == "3":
            name = input("请输入参与者的名字: ")
            responder.add_participant(name)
        elif choice == "4":
            name = input("请输入回答者的名字: ")
            answer = input("请输入答案: ")
            responder.answer_question(name, answer)
        elif choice == "5":
            responder.display_responses()
        elif choice == "6":
            break
        else:
            print("无效的操作，请重新输入。")


