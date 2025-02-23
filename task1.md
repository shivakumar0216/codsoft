# To-Do List Application

# Define a class for the To-Do List
class TodoApp:
    def __init__(self):
        self.tasks = []  # List to store tasks

    # Function to add a task
    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task '{task}' has been added.")

    # Function to remove a task
    def remove_task(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
            print(f"Task '{task}' has been removed.")
        else:
            print(f"Task '{task}' not found.")

    # Function to list all tasks
    def list_tasks(self):
        if not self.tasks:
            print("Your to-do list is empty!")
        else:
            print("Your To-Do List:")
            for index, task in enumerate(self.tasks, start=1):
                print(f"{index}. {task}")

    # Function to mark a task as completed
    def complete_task(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
            print(f"Task '{task}' marked as completed and removed from the list.")
        else:
            print(f"Task '{task}' not found.")

# Main function to interact with the user
def main():
    todo = TodoApp()  # Create an instance of the TodoApp class

    while True:
        print("\nTo-Do List Application")
        print("1. Add a Task")
        print("2. Remove a Task")
        print("3. List All Tasks")
        print("4. Mark Task as Completed")
        print("5. Exit")
        
        choice = input("Please choose an option (1-5): ")

        if choice == '1':
            task = input("Enter the task to add: ")
            todo.add_task(task)

        elif choice == '2':
            task = input("Enter the task to remove: ")
            todo.remove_task(task)

        elif choice == '3':
            todo.list_tasks()

        elif choice == '4':
            task = input("Enter the task to mark as completed: ")
            todo.complete_task(task)

        elif choice == '5':
            print("Exiting the To-Do List Application. Goodbye!")
            break  # Exit the program

        else:
            print("Invalid choice. Please choose a valid option.")

# Run the program
if __name__ == "__main__":
    main()
