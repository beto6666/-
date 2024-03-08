# -
办事项命令行应用程序
class TodoItem:
    def __init__(self, description):
        self.description = description
        self.completed = False

class TodoList:
    def __init__(self):
        self.items = []

    def add_item(self, description):
        item = TodoItem(description)
        self.items.append(item)

    def complete_item(self, index):
        if index >= 0 and index < len(self.items):
            self.items[index].completed = True

    def display_list(self):
        for index, item in enumerate(self.items):
            status = " [x] " if item.completed else " [ ] "
            print(f"{index}. {status}{item.description}")

def main():
    todo_list = TodoList()

    while True:
        print("==== Todo List ====")
        print("1. Add item")
        print("2. Complete item")
        print("3. Display list")
        print("4. Exit")

        choice = input("Enter your choice: ")

        if choice == "1":
            description = input("Enter item description: ")
            todo_list.add_item(description)
        elif choice == "2":
            index = int(input("Enter item index: "))
            todo_list.complete_item(index)
        elif choice == "3":
            todo_list.display_list()
        elif choice == "4":
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
