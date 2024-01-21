def show_menu():
    print("To-Do List Menu:")
    print("1. View tasks")
    print("2. Add task")
    print("3. Remove task")
    print("4. Quit")


def view_tasks(tasks):
    if not tasks:
        print("No tasks found.")
    else:
        print("Tasks:")
        for index, task in enumerate(tasks, 1):
            print(f"{index}. {task}")


def add_task(tasks, new_task):
    tasks.append(new_task)
    print(f"Task '{new_task}' added successfully.")


def remove_task(tasks, task_index):
    try:
        removed_task = tasks.pop(task_index - 1)
        print(f"Task '{removed_task}' removed successfully.")
    except IndexError:
        print("Invalid task index.")


def main():
    tasks = []

    while True:
        show_menu()
        choice = input("Enter your choice (1-4): ")

        if choice == "1":
            view_tasks(tasks)
        elif choice == "2":
            new_task = input("Enter the new task: ")
            add_task(tasks, new_task)
        elif choice == "3":
            view_tasks(tasks)
            task_index = int(input("Enter the index of the task to remove: "))
            remove_task(tasks, task_index)
        elif choice == "4":
            print("Quitting the to-do list program. Goodbye!")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")


if __name__ == "__main__":
    main()

