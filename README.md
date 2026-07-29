# Banking-system-
class BankAccount:
    def __init__(self, name, balance):
        self.name = name
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print(f"₹{amount} deposited successfully.")

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            print(f"₹{amount} withdrawn successfully.")
        else:
            print("Insufficient balance!")

    def check_balance(self):
        print(f"Current Balance: ₹{self.balance}")


name = input("Enter Account Holder Name: ")
balance = float(input("Enter Initial Deposit: ₹"))

account = BankAccount(name, balance)

while True:
    print("\n===== BANK MENU =====")
    print("1. Deposit")
    print("2. Withdraw")
    print("3. Check Balance")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        amount = float(input("Enter Deposit Amount: ₹"))
        account.deposit(amount)

    elif choice == "2":
        amount = float(input("Enter Withdrawal Amount: ₹"))
        account.withdraw(amount)

    elif choice == "3":
        account.check_balance()

    elif choice == "4":
        print("Thank you for using our Banking System!")
        break

    else:
        print("Invalid choice. Please try again.")
