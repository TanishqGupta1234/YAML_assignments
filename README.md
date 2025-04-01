
# 📖 Python YAML Use Case


## 🚀 Step-by-Step Guide

## 🛠 Step 1: Install Required Packages

To handle YAML files in Python, you need the PyYAML library. If you haven't installed it yet, run:

```bash
pip install pyyaml
```

## 📜 Step 2: Create the YAML File

Create a YAML file named students.yaml. This file contains student information like names, ages, majors, and GPAs. Example:

```bash
students:
  - name: Alice
    age: 21
    major: Computer Science
    gpa: 3.8
  - name: Bob
    age: 22
    major: Mathematics
    gpa: 3.5
  - name: Charlie
    age: 20
    major: Physics
    gpa: 3.9
  - name: David
    age: 23
    major: Chemistry
    gpa: 3.2
  - name: Eva
    age: 21
    major: Computer Science
    gpa: 3.7
```

## 🔍 YAML Structure Explained:

students: A list of dictionaries, where each dictionary represents a student.

Each student has attributes:

name: The student's name 🏷️

age: The student's age 🎂

major: The student's field of study 📚

gpa: The student's Grade Point Average 🎯


## 🖥️ Step 3: Write the Python Application

Create a Python script app.py to read the YAML file, display all students, and filter them by GPA.

```bash
import yaml

def load_data(file_path):
    """ Load data from a YAML file. """
    with open(file_path, 'r') as file:
        data = yaml.safe_load(file)  # Load YAML as Python dictionary
    return data

def display_students(students):
    """ Display information about all students. """
    print("\n📋 All Students:")
    for student in students:
        print(f"👤 Name: {student['name']}, 🎂 Age: {student['age']}, 🎓 Major: {student['major']}, 📊 GPA: {student['gpa']}")

def filter_students_by_gpa(students, min_gpa):
    """ Filter and display students with GPA above a given threshold. """
    filtered_students = [s for s in students if s['gpa'] >= min_gpa]
    
    print(f"\n🔍 Students with GPA >= {min_gpa}:")
    if filtered_students:
        for student in filtered_students:
            print(f"👤 Name: {student['name']}, 🎂 Age: {student['age']}, 🎓 Major: {student['major']}, 📊 GPA: {student['gpa']}")
    else:
        print("❌ No students found.")

def main():
    data = load_data('students.yaml')
    students = data['students']
    
    display_students(students)
    
    min_gpa = float(input("\n🔢 Enter minimum GPA to filter students: "))
    filter_students_by_gpa(students, min_gpa)

if __name__ == "__main__":
    main()
```

## 📌 Explanation of the Code

📥 Importing the Library:

import yaml – To work with YAML files in Python.

📂 Loading Data:

load_data() function reads and converts YAML data into a Python dictionary using yaml.safe_load().

📋 Displaying Students:

display_students() prints all student details.

🔍 Filtering Students:

filter_students_by_gpa() filters students based on a minimum GPA.

🎯 Main Function:

main() calls functions to load data, display students, and filter them based on user input.

🚀 Execution Block:

if __name__ == "__main__": ensures the script runs only when executed directly.

## ▶️ Step 4: Run the Application

Ensure app.py and students.yaml are in the same directory.

Open the terminal, navigate to the directory, and run:

```bash
python app.py
```
## 🎯 Expected Output

```bash
📋 All Students:
👤 Name: Alice, 🎂 Age: 21, 🎓 Major: Computer Science, 📊 GPA: 3.8
👤 Name: Bob, 🎂 Age: 22, 🎓 Major: Mathematics, 📊 GPA: 3.5
👤 Name: Charlie, 🎂 Age: 20, 🎓 Major: Physics, 📊 GPA: 3.9
👤 Name: David, 🎂 Age: 23, 🎓 Major: Chemistry, 📊 GPA: 3.2
👤 Name: Eva, 🎂 Age: 21, 🎓 Major: Computer Science, 📊 GPA: 3.7

🔢 Enter minimum GPA to filter students: 3.6

🔍 Students with GPA >= 3.6:
👤 Name: Alice, 🎂 Age: 21, 🎓 Major: Computer Science, 📊 GPA: 3.8
👤 Name: Charlie, 🎂 Age: 20, 🎓 Major: Physics, 📊 GPA: 3.9
👤 Name: Eva, 🎂 Age: 21, 🎓 Major: Computer Science, 📊 GPA: 3.7
```

## 🎉 Conclusion

This Python application demonstrates how to read and use YAML data efficiently. You can extend this project by:

✨ Adding sorting features

📝 Updating student information

💾 Saving modified data back to the YAML file

🔗 Happy Coding! 🚀