balance = 1000

def show_menu():
    print("\n=== Money Withdrawal System ===")
    print("1 - Withdraw")
    print("2 - Check Balance")
    print("3 - Exit")

while True:
    show_menu()
    choice = input("Enter your choice: ")

    try:
        if choice == "1":
            amount = float(input("Enter amount: "))

            if amount <= 0:
                print("Invalid amount.")

            elif amount > balance:
                print("Insufficient funds.")

                while True:
                    print("\nWhat would you like to do?")
                    print("1 - Try Again")
                    print("2 - Check Balance")
                    print("3 - Exit")

                    option = input("Enter option: ")

                    if option == "1":
                        break
                    elif option == "2":
                        print(f"Balance: {balance}")
                    elif option == "3":
                        print("Exiting program...")
                        exit()
                    else:
                        print("Invalid choice.")

            else:
                balance -= amount
                print(f"Successfully withdrawn!")
                print(f"New balance: {balance}")

        elif choice == "2":
            print(f"Your balance is: {balance}")

        elif choice == "3":
            print("Goodbye!")
            break

        else:
            print("Invalid menu choice.")

    except ValueError:
        print("Please enter a valid number only.")

    except Exception:
        print("Something went wrong. Try again.")
