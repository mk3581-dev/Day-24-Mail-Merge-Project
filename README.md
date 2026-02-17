📬 Mail Merge Project (Day 24 – 100 Days of Code)

This project is part of Day 24 of the 100 Days of Code Python Bootcamp by Dr. Angela Yu.

It is a simple automation script that reads a list of names and generates personalized invitation letters using a template.

🚀 Project Overview

The program:

Reads a template letter

Reads a list of invited names

Replaces the placeholder [name] with each person's name

Automatically generates a personalized letter for every name

Saves the letters inside an output folder

📁 Project Structure
mail-merge-project/
│
├── Input/
│   ├── Names/
│   │   └── invited_names.txt
│   └── Letters/
│       └── starting_letter.txt
│
├── Output/
│   └── ReadyToSend/
│
└── main.py

🧠 How It Works

The program reads the template letter from:

Input/Letters/starting_letter.txt


It reads all names from:

Input/Names/invited_names.txt


For each name:

Removes extra whitespace

Replaces [name] in the template

Creates a new file like:

letter_for_Aman.txt

🖥️ main.py Code
# Read letter template
with open("./Input/Letters/starting_letter.txt") as letter_file:
    letter_contents = letter_file.read()

# Read invited names
with open("./Input/Names/invited_names.txt") as names_file:
    names = names_file.readlines()

# Create personalized letters
for name in names:
    stripped_name = name.strip()
    new_letter = letter_contents.replace("[name]", stripped_name)

    with open(f"./Output/ReadyToSend/letter_for_{stripped_name}.txt", mode="w") as completed_letter:
        completed_letter.write(new_letter)

📦 Requirements

Python 3.x

No external libraries required

▶️ How to Run

Clone this repository:

git clone https://github.com/your-username/mail-merge-project.git


Navigate into the project folder:

cd mail-merge-project


Run the script:

python main.py


Check the Output/ReadyToSend folder for generated letters.

🎯 Concepts Practiced

File handling in Python

Reading and writing text files

String replacement

Looping through lists

Automating repetitive tasks

✨ Future Improvements

Support for multiple placeholders (date, venue, etc.)

Reading data from CSV files

GUI version

Email automation integration.
