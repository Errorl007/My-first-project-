
B)	Write a ‘java’ program to copy only non-numeric data from one file to another file.
[25 M]
	import java.io.*;

public class NonNumericDataCopier {
    public static void main(String[] args) {
        // Source file
        File inputFile = new File("input.txt");
        // Destination file
        File outputFile = new File("output.txt");

        try (
            BufferedReader reader = new BufferedReader(new FileReader(inputFile));
            BufferedWriter writer = new BufferedWriter(new FileWriter(outputFile))
        ) {
            int c;
            while ((c = reader.read()) != -1) {
                if (!Character.isDigit(c)) {
                    writer.write(c);
                }
            }
            System.out.println("Copy complete. Non-numeric data transferred.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}


Q.2	Python:

A)	Write a Python program to accept n numbers in list and remove duplicates from a list.	[15 M]
# Function to remove duplicates
def remove_duplicates(input_list):
    return list(set(input_list))

# Main function to accept numbers and process the list
def main():
    # Accept the number of elements
    n = int(input("Enter the number of elements in the list: "))

    # Initialize the list
    num_list = []

    # Accepting the elements
    for _ in range(n):
        num = int(input("Enter a number: "))
        num_list.append(num)

    print("Original list:", num_list)

    # Removing duplicates
    no_duplicates_list = remove_duplicates(num_list)
    print("List after removing duplicates:", no_duplicates_list)

if __name__ == "__main__":
    main()

B)	Write Python GUI program to take accept your birthdate and output your age when a button is pressed.	[25 M]
import tkinter as tk
from tkinter import messagebox
from datetime import datetime

def calculate_age():
    birthdate = entry.get()
    try:
        birthdate_date = datetime.strptime(birthdate, "%Y-%m-%d")
        today = datetime.today()
        age = today.year - birthdate_date.year - ((today.month, today.day) < (birthdate_date.month, birthdate_date.day))
        messagebox.showinfo("Age", f"Your age is {age} years.")
    except ValueError:
        messagebox.showerror("Error", "Invalid date format. Please enter in YYYY-MM-DD format.")

# Set up the main window
root = tk.Tk()
root.title("Age Calculator")

# Add widgets
label = tk.Label(root, text="Enter your birthdate (YYYY-MM-DD):")
label.pack(pady=10)

entry = tk.Entry(root)
entry.pack(pady=10)

button = tk.Button(root, text="Calculate Age", command=calculate_age)
button.pack(pady=10)

# Run the application
root.mainloop()

