# Simple Combined Code: Grocery Shopping List

# 1. FIXED TUPLE: Common grocery items (Data that doesn't change)
common_items = ("Milk", "Eggs", "Bread", "Cheese", "Apples")

# 2. MUTABLE LIST: The user's actual shopping list (Data that changes)
my_shopping_list = ["Potatoes", "Water"]

print("\n--- Interactive Shopping List Builder ---")
print("Common Items available to add:")
# Use a simple loop to display the available tuple items
for index, item in enumerate(common_items):
    print(f"  {index + 1}. {item}")

print("\n(Type the number of the item you want to add, or 0 to finish)")

# Start the user interaction loop
is_shopping = True
while is_shopping:
    
    # Get input and check if it's a valid number
    try:
        choice = int(input("Enter number (1-5) to add, 0 to stop: "))
        
        if choice == 0:
            is_shopping = False
            print("Shopping list finalized!")
            
        elif 1 <= choice <= len(common_items):
            # Get the item from the TUPLE using the user's number
            item_to_add = common_items[choice - 1]
            
            # Add the item to the LIST
            if item_to_add not in my_shopping_list:
                my_shopping_list.append(item_to_add)
                print(f"✅ Added {item_to_add} to your list.")
            else:
                print(f"Item '{item_to_add}' is already on the list.")
                
        else:
            print("Invalid choice. Please enter a number between 0 and 5.")
            
    except ValueError:
        print("Invalid input. Please enter a number only.")


print("\n** Your Final Shopping List **")
# Loop through the final LIST
if my_shopping_list:
    for item in sorted(my_shopping_list): # sorted() is a nice touch!
        print(f"- {item}")
else:
    print("Your list is empty!")

print("--------------------------------------")
