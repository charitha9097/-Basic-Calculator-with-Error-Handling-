# -Basic-Calculator-with-Error-Handling-
# Basic Calculator with Error Handling

def calculator():
    print("=== Basic Calculator ===")
    print("Supported operators: +, -, *, /")
    print("Type 'q' at any time to quit.\n")

    while True:
        try:
            # Get first number
            num1 = input("Enter first number: ")
            if num1.lower() == 'q':
                break
            num1 = float(num1)

            # Get operator
            op = input("Enter operator (+, -, *, /): ")
            if op.lower() == 'q':
                break
            if op not in ['+', '-', '*', '/']:
                print("Error: Invalid operator! Try again.\n")
                continue

            # Get second number
            num2 = input("Enter second number: ")
            if num2.lower() == 'q':
                break
            num2 = float(num2)

            # Perform calculation
            if op == '+':
                result = num1 + num2
            elif op == '-':
                result = num1 - num2
            elif op == '*':
                result = num1 * num2
            elif op == '/':
                if num2 == 0:
                    raise ZeroDivisionError("Division by zero is not allowed.")
                result = num1 / num2

            print(f"Result: {num1} {op} {num2} = {result}\n")

        except ValueError:
            print("Error: Please enter a valid number.\n")
        except ZeroDivisionError as e:
            print(f"Error: {e}\n")
        except Exception as e:
            print(f"Unexpected error: {e}\n")

    print("Goodbye!")

# Run the calculator
calculator()

#ouput:


