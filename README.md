# to_do.py

tasks = []

def show_tasks():
    if not tasks:
        print("📭 No tasks yet")
    else:
        for i, task in enumerate(tasks, start=1):
            print(f"{i}. {task}")

def add_task(task):
    tasks.append(task)
    print(f"✅ Task added: {task}")

def remove_task(index):
    try:
        removed = tasks.pop(index - 1)
        print(f"🗑️ Task removed: {removed}")
    except IndexError:
        print("⚠️ Invalid task number!")

while True:
    print("\n--- To-Do List ---")
    show_tasks()
    print("\nOptions: [a]dd, [r]emove, [q]uit")
    choice = input("Choose: ")

    if choice == "a":
        task = input("Enter task: ")
        add_task(task)
    elif choice == "r":
        num = int(input("Enter task number to remove: "))
        remove_task(num)
    elif choice == "q":
        print("👋 Bye!")
        break
