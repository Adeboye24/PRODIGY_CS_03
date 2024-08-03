
Creating a Password Complexity Checker Tool with Python
Objective: To Build a tool that assesses the strength of a password based on criteria such as; length, presence of upper case and lower case letters, numbers, and special characters. Provide feedback to users on the password strength.
Steps Followed:
1.	Setting Up and Installation of Python:
Installed Python and ensured it was added to the system PATH.
Used IDLE for initial development and testing of the script.
2.	 Python Script Writing :
Created a script named password_strength_checker.py.
Implemented functions to check for password length, uppercase letters, lowercase letters, numbers, and special characters.
Combined these functions to assess password strength and provide feedback.
3.	 Script Testing:
Ran the script using IDLE to verify functionality and ensure correct output.
Tested various passwords to check for accurate strength assessment.
4.	Run Script via Command Prompt/ IDLE:
Opened Command Prompt on Windows.
Navigated to the script’s directory using the cd command.
Executed the script using the python password_strength_checker.py command.
Provided input and observed the output to validate script performance.
Using IDLE
  1. Open IDLE
•	Windows: Search for "IDLE" in the Start menu.
•	macOS: You can find IDLE in your Applications folder under Python.
•	Linux: You may need to install IDLE separately if it’s not included in your Python installation.
2. Create a New Python File
1.	Open IDLE.
2.	In the IDLE shell window, go to File > New File to open a new editor window.
3.	Save the new file as password_strength_checker.py (or any name you prefer).
3. Write Your Code
4. Run Your Script
1.	To run your script, go back to the editor window and select Run > Run Module (or press F5).You’ll see a prompt in the IDLE shell asking for your password input.
Outcome: Successfully created a functional password strength assessment tool that evaluates and provides feedback on password security based on common criteria.

# PRODIGY_CS_03
Password_Complexity_Checker.py
import re

def check_length(password):
    min_length = 9
    return len(password) >= min_length

def check_uppercase(password):
    return bool(re.search(r'[A-Z]', password))

def check_lowercase(password):
    return bool(re.search(r'[a-z]', password))

def check_number(password):
    return bool(re.search(r'[0-9]', password))

def check_special(password):
    return bool(re.search(r'[!@#$%^&*(),.?":{}|<>]', password))

def assess_password_strength(password):
    length_valid = check_length(password)
    uppercase_valid = check_uppercase(password)
    lowercase_valid = check_lowercase(password)
    number_valid = check_number(password)
    special_valid = check_special(password)

    if length_valid and uppercase_valid and lowercase_valid and number_valid and special_valid:
        return "Strong"
    elif length_valid and (uppercase_valid or lowercase_valid) and (number_valid or special_valid):
        return "Moderate"
    else:
        return "Weak"

def main():
    password = input("Enter your password: ")
    strength = assess_password_strength(password)
    print(f"Password strength: {strength}")

if __name__ == "__main__":
    main()
