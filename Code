Task # 03
Password Complexity Checker
Build a tool that assesses the strength of a password based on criteria 
such as length, presence of uppercase and lowercase letters, numbers, and 
special characters. Provide feedback to users on the password's strength.
'''

import re

def assess_password_strength(password):
    # Criteria for password strength
    length_criteria = len(password) >= 8
    lowercase_criteria = re.search(r'[a-z]', password) is not None
    uppercase_criteria = re.search(r'[A-Z]', password) is not None
    digit_criteria = re.search(r'\d', password) is not None
    special_criteria = re.search(r'[\W_]', password) is not None
    
    # Strength calculation
    strength = 0
    if length_criteria:
        strength += 1
    if lowercase_criteria:
        strength += 1
    if uppercase_criteria:
        strength += 1
    if digit_criteria:
        strength += 1
    if special_criteria:
        strength += 1
    
    # Feedback based on strength
    if strength == 5:
        feedback = "Very strong"
    elif strength == 4:
        feedback = "Strong"
    elif strength == 3:
        feedback = "Moderate"
    elif strength == 2:
        feedback = "Weak"
    else:
        feedback = "Very weak"

    # Detailed feedback
    detailed_feedback = []
    if not length_criteria:
        detailed_feedback.append("Password should be at least 8 characters long.")
    if not lowercase_criteria:
        detailed_feedback.append("Password should contain at least one lowercase letter.")
    if not uppercase_criteria:
        detailed_feedback.append("Password should contain at least one uppercase letter.")
    if not digit_criteria:
        detailed_feedback.append("Password should contain at least one digit.")
    if not special_criteria:
        detailed_feedback.append("Password should contain at least one special character.")

    return feedback, detailed_feedback

# Example usage
if __name__ == "__main__":
    password = input("Enter a password to assess: ")
    feedback, detailed_feedback = assess_password_strength(password)
    
    print(f"Password strength: {feedback}")
    if detailed_feedback:
        print("Suggestions to improve your password:")
        for suggestion in detailed_feedback:
            print(f"- {suggestion}")
