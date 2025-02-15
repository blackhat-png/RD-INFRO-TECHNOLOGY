# RD-INFRO-TECHNOLOGY
import re

def check_password_strength(password):
    strength = 0
    criteria = {
        "length": len(password) >= 8,
        "uppercase": bool(re.search(r"[A-Z]", password)),
        "lowercase": bool(re.search(r"[a-z]", password)),
        "digit": bool(re.search(r"\d", password)),
        "special": bool(re.search(r"[!@#$%^&*(),.?\":{}|<>]", password)),
    }

    strength = sum(criteria.values())

    if strength == 5:
        return "Strong Password"
    elif strength >= 3:
        return "Moderate Password"
    else:
        return "Weak Password"

password = input("Enter your password: ")
print(check_password_strength(password))
