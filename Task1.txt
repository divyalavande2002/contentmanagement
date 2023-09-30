class ContentItem:
    def __init__(self, title, content):
        self.title = title
        self.content = content

class ContentManager:
    def __init__(self):
        self.content_items = []

    def create_content(self, title, content):
        item = ContentItem(title, content)
        self.content_items.append(item)

    def list_content(self):
        for idx, item in enumerate(self.content_items, start=1):
            print(f"{idx}. {item.title}")

    def view_content(self, index):
        if 1 <= index <= len(self.content_items):
            item = self.content_items[index - 1]
            print(f"Title: {item.title}\nContent:\n{item.content}")
        else:
            print("Invalid index")

def main():
    content_manager = ContentManager()

    while True:
        print("\nContent Management Tool")
        print("1. Create Content")
        print("2. List Content")
        print("3. View Content")
        print("4. Quit")

        choice = input("Enter your choice: ")

        if choice == "1":
            title = input("Enter the title: ")
            content = input("Enter the content: ")
            content_manager.create_content(title, content)
            print("Content created successfully!")
        elif choice == "2":
            print("\nList of Content Items:")
            content_manager.list_content()
        elif choice == "3":
            index = int(input("Enter the index of the content to view: "))
            content_manager.view_content(index)
        elif choice == "4":
            print("Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
