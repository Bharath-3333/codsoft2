import tkinter as tk
from tkinter import messagebox

class ContactBookApp:
    def _init_(self, root):
        self.root = root
        self.root.title("Contact Book")

        self.contacts = []

        self.create_widgets()

    def create_widgets(self):
        # Labels and entry widgets
        tk.Label(self.root, text="Name:").grid(row=0, column=0, sticky=tk.E)
        self.name_entry = tk.Entry(self.root)
        self.name_entry.grid(row=0, column=1)

        tk.Label(self.root, text="Phone:").grid(row=1, column=0, sticky=tk.E)
        self.phone_entry = tk.Entry(self.root)
        self.phone_entry.grid(row=1, column=1)

        # Buttons
        tk.Button(self.root, text="Add Contact", command=self.add_contact).grid(row=2, column=0, columnspan=2, pady=10)
        tk.Button(self.root, text="Show Contacts", command=self.show_contacts).grid(row=3, column=0, columnspan=2, pady=10)

    def add_contact(self):
        name = self.name_entry.get()
        phone = self.phone_entry.get()

        if name and phone:
            contact = {"Name": name, "Phone": phone}
            self.contacts.append(contact)
            messagebox.showinfo("Contact Added", "Contact successfully added.")
            self.clear_entries()
        else:
            messagebox.showwarning("Missing Information", "Please enter both name and phone.")

    def show_contacts(self):
        if not self.contacts:
            messagebox.showinfo("No Contacts", "No contacts available.")
        else:
            contact_list = "\n".join([f"{contact['Name']}: {contact['Phone']}" for contact in self.contacts])
            messagebox.showinfo("Contacts", contact_list)

    def clear_entries(self):
        self.name_entry.delete(0, tk.END)
        self.phone_entry.delete(0, tk.END)

if _name_ == "_main_":
    root = tk.Tk()
    app = ContactBookApp(root)
    root.mainloop()
