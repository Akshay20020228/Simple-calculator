# Simple-calculator
This is a athematic operators 
def add(a, b):
    """Add two numbers"""
    return a + b

def subtract(a, b):
    """Subtract two numbers"""
    return a - b

def multiply(a, b):
    """Multiply two numbers"""
    return a * b

def divide(a, b):
    """Divide two numbers"""
    if b == 0:
        return "Error: Division by zero"
    return a / b

def calculator():
    """Simple calculator that performs basic arithmetic operations"""
    print("=== Simple Calculator ===")
    print("Operations: +, -, *, /")
    print("Type 'quit' to exit\n")
    
    while True:
        try:
            user_input = input("Enter calculation (e.g., 10 + 5): ").strip()
            
            if user_input.lower() == 'quit':
                print("Thank you for using the calculator!")
                break
            
            # Parse the input
            parts = user_input.split()
            
            if len(parts) != 3:
                print("Invalid format. Please use: number operator number\n")
                continue
            
            num1 = float(parts[0])
            operator = parts[1]
            num2 = float(parts[2])
            
            # Perform calculation based on operator
            if operator == '+':
                result = add(num1, num2)
            elif operator == '-':
                result = subtract(num1, num2)
            elif operator == '*':
                result = multiply(num1, num2)
            elif operator == '/':
                result = divide(num1, num2)
            else:
                print("Invalid operator. Use +, -, *, or /\n")
                continue
            
            print(f"Result: {result}\n")
        
        except ValueError:
            print("Invalid input. Please enter numbers and a valid operator.\n")
        except Exception as e:
            print(f"An error occurred: {e}\n")

if __name__ == "__main__":
    calculator()
