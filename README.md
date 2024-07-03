# PRODIGY_CS_03
## Description 
The Password Complexity Checker is a Python-based tool designed to evaluate the strength of passwords. By analyzing various criteria, this tool provides immediate feedback on whether a password is weak, good, or strong. It serves as a practical example of how to enforce password security standards in applications.

## Code 📃
```
import re

def password_complexity_checker(password):
    # Check length
    length_score = len(password) >= 8

    # Check for uppercase letters
    uppercase_score = bool(re.search(r'[A-Z]', password))

    # Check for lowercase letters
    lowercase_score = bool(re.search(r'[a-z]', password))

    # Check for numbers
    number_score = bool(re.search(r'[0-9]', password))

    # Check for special characters
    special_char_score = bool(re.search(r'[!@#$%^&*(),.?":{}|<>]', password))

    # Calculate total score
    total_score = length_score + uppercase_score + lowercase_score + number_score + special_char_score

    # Provide feedback based on total score
    if total_score == 5:
        return "Strong password"
    elif total_score >= 3:
        return "Good password"
    else:
        return "Weak password"

password = input("Enter your password: ")
strength = password_complexity_checker(password)
print(f"Password strength: {strength}")
```
