# Password Strength Meter
# Objective: Build a password strength meter in python that evaluates the strength of a password based on the following criteria:
# 1. Length: At least 8 characters
# 2. Contains both uppercase and lowercase letters
# 3. Contains at least one digit
# 4. Contains at least one special character
# 5. Is not a common password
# 6. Is not a dictionary word

import re
import streamlit as st

st.set_page_config(page_title="Password Strength Meter", page_icon=":lock:" ,layout="centered")

#costum css
st.markdown(
    """
    <style>
    .main{text-align: center; }
    .stTextInput{width: 60% !important margin:auto;}
    .stButton{width: 50%; background-color: #000000; color: #ffffff; font-size: 18px;}
    .stButton:hover{background-color: #000000; color: #ffffff;}

 </style>
""",unsafe_allow_html=True)

# Page title
st.title("Password Strength Meter")
st.write("Check the strength of your password")

# Function to check password strength

def check_password_strength(password):
    score = 0
    feedback = []

    if len(password) >= 8:
        score += 1 
        
    else:
        feedback.append("Password must be at **least 8 characters long**")

        
    if re.search(r'[A-Z]', password) and re.search(r'[a-z]', password):
        score += 1

    else:
        feedback.append("Password must contain both **uppercase and lowercase letters**")

    if re.search(r'\d', password):
        score += 1

    else:
        feedback.append("Password must contain at least one number **[0 to 9]**")

    if re.search(r'[!@#$%^&*(),.?":{}|<>]', password):
        score += 1

    else:
        feedback.append("Password must contain at least one special character(**[!@#$%^&*(),.?**)")
        
        
    # display feedback
    if score == 4:
        st.success("Password is strong")

    elif score == 3:
        st.warning("Password is medium")
    else:
        st.error("Password is weak - Follow the instructions to improve it")


    # feedback
    if feedback:
        with st.expander("**Improve your password strength**"):
            for item in feedback:
                st.markdown(item)


# password input

password = st.text_input("Enter your password", type="password" , help="Ensure your password is strong and secure")

# button
if st.button("Check Password Strength"):
    if password:
        check_password_strength(password)

    else:
        st.error("Please enter a password")
            

# footer
st.markdown("---")
st.write("Developed by [@Muhammad Maaz](https://github.com/Moaz-khan/passwordstrengthmanager)")


