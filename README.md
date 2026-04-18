# NewPaymentMethodEntegration
1st Homework N11

📌 Overview
This project has been developed as part of an assignment focusing on the application of SOLID design principles in a real-world inspired scenario. The main objective is to design a flexible and maintainable payment system that supports the integration of new payment methods without altering existing code.

🎯 Objective
The system simulates a payment processing application where:
At least one existing payment method (Credit Card) is already implemented
A new payment method (PayPal) is introduced
The architecture must support extensibility in accordance with Open/Closed Principle (OCP)
Each component should adhere to Single Responsibility Principle (SRP)



⚙️ Architectural Components
Abstraction Layer
PaymentMethod: Defines a common interface for all payment operations
Implementation Layer
CreditCardPayment: Represents the existing payment method
PayPalPayment: Represents the newly integrated payment method
Service Layer
PaymentProcessor: Responsible for executing payment operations

📦 Project Structure
com.payment
│
├── abstraction        # Interfaces (PaymentMethod)
├── implementation     # Concrete payment methods
│     ├── CreditCardPayment
│     └── PayPalPayment
│
├── service            # Business logic
│     └── PaymentProcessor
│
├── factory            # Object creation (optional)
│     └── PaymentFactory
│
└── Main.java          # Entry point


🧠SOLID Principles Applied

🔹 Single Responsibility Principle (SRP)
Each class has a single responsibility:
PaymentProcessor → handles payment processing
PaymentMethod implementations → handle specific payment logic

🔹 Open/Closed Principle (OCP)
The system is open for extension but closed for modification.

👉 New payment methods can be added like this:

class ApplePayPayment implements PaymentMethod {
    @Override
    public void pay(double amount) {
        System.out.println("Paid with Apple Pay: " + amount);
    }
}

🔹 Dependency Inversion Principle (DIP)
High-level modules depend on abstractions, not concrete classes.
public void processPayment(PaymentMethod paymentMethod, double amount)

