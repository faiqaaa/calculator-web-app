# calculator-web-app
import streamlit as st

# Page layout and title
st.set_page_config(page_title="Calculator", page_icon="🧮", layout="centered")

st.title("Simple Calculator")
st.write("Perform basic operations like addition, subtraction, multiplication, and division.")

# Add a large calculator icon
st.image("https://cdn-icons-png.flaticon.com/512/1665/1665731.png", width=150)

# User inputs for numbers and operation
num1 = st.number_input("Enter the first number:", value=0.0)
num2 = st.number_input("Enter the second number:", value=0.0)
operation = st.selectbox("Choose operation", ["Add", "Subtract", "Multiply", "Divide"])

# Calculator logic
if st.button("Calculate"):
    if operation == "Add":
        result = num1 + num2
    elif operation == "Subtract":
        result = num1 - num2
    elif operation == "Multiply":
        result = num1 * num2
    elif operation == "Divide":
        result = num1 / num2 if num2 != 0 else "Error (division by zero)"
    
    # Display the result
    st.write(f"Result: {result}")
