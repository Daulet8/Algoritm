 from collections import deque

class BankQueue:
    def __init__(self):
        self.queue = deque()

    # Добавление клиента
    def add_client(self, name):
        self.queue.append(name)
        print(f"Клиент {name} добавлен в очередь")

    # Обслуживание клиента
    def serve_client(self):
        if self.queue:
            client = self.queue.popleft()
            print(f"Обслуживается клиент: {client}")
        else:
            print("Очередь пуста")

    # Показ текущей очереди
    def show_queue(self):
        if not self.queue:
            print("Очередь пуста")
        else:
            print("Текущая очередь:")
            for i, client in enumerate(self.queue, 1):
                print(f"{i}. {client}")


# Пример работы
bank = BankQueue()

bank.add_client("Алия")
bank.add_client("Бек")
bank.add_client("Сергей")

bank.show_queue()

bank.serve_client()
bank.show_queue()


Клиент Алия добавлен в очередь
Клиент Бек добавлен в очередь
Клиент Сергей добавлен в очередь

Текущая очередь:
1. Алия
2. Бек
3. Сергей

Обслуживается клиент: Алия

Текущая очередь:
1. Бек
2. Сергей

Пояснение

Программа моделирует реальную очередь:

клиенты добавляются в конец;
обслуживаются с начала;
порядок строго сохраняется.
