# Codsoft
Random password generating
print("Choose an operator to perform:")
print("1.ADD")
print("2.SUB")
print("3.MUL")
print("4.DIV")

operation = input()

if operation == "1":
    a = float(input("Enter first number: "))
    b = float(input("Enter second number: "))
    print("The sum is " +str(a + b))
elif operation == "2":
    a = float(input("Enter first number: "))
    b = float(input("Enter second number: "))
    print("The sum is " + str(a - b))
elif operation == "3":
     a = float(input("Enter first number: "))
     b = float(input("Enter second number: "))
     print("The sum is " + str(a * b))
elif operation == "4":
    a = float(input("Enter first number: "))
    b = float(input("Enter second number: "))
    print("The sum is " + str (a / b))
else:
    print("Invalid ")
