# ContactListApplication---py

# Initialize an empty dictionary to store contacts.
contacts = {}

# Function to add a new contact
def add_contact():
    name = input("Enter the name of the contact: ")
    phone_number = input("Enter the phone number: ")
    email = input("Enter the email address:")
    
    # Create a new contact entry in the 'contacts' dictionary
    contacts[name] = {"phone_number": phone_number, "email": email}
    print(f"{name} has been successfully added to your contacts.")

# Function to view all contacts
def view_contacts():
    if not contacts:
        print("Contact list is empty.")
    else:
        print("Contacts:")
        for name, info in contacts.items():
            print(f"Name: {name}")
            print(f"Phone Number: {info['phone_number']}")
            print(f"Email: {info['email']}")
            print()

# Function to update a contact
def update_contact():
    name = input("Enter the name of the contact you wish to update: ")
    if name in contacts:
        phone_number = input("Enter the new phone number: ")
        email = input("Enter the new email: ")
        # Update the contact's information in the 'contacts' dictionary
        contacts[name]["phone_number"] = phone_number
        contacts[name]["email"] = email
        print(f"{name}'s information has been successfully updated.")
    else:
        print("Contact not found.")

# Function to delete a contact
def delete_contact():
    name = input("Enter the name of the contact you want to delete: ")
    if name in contacts:
        # Remove the contact from the 'contacts' dictionary
        del contacts[name]
        print(f"{name} has been successfully deleted from the contacts.")
    else:
        print("Contact not found.")

# Main loop for the Contact List Application
while True:
    print("\nContact List Application Menu:")
    print("1. Add Contact")
    print("2. View Contacts")
    print("3. Update Contact")
    print("4. Delete Contact")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_contact()
    elif choice == "2":
        view_contacts()
    elif choice == "3":
        update_contact()
    elif choice == "4":
        delete_contact()
    elif choice == "5":
        print("Exiting the Contact List Application.")
        break
    else:
        print("Invalid choice. Please choose a valid option.")
