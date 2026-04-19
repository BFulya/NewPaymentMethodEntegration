<h1 align="center" style="color:red;">🚀 NewPaymentMethodEntegration</h1>

<h3 align="center">1st Homework N11</h3>

---

<h2 style="color:red;">📌 Overview</h2>

This project has been developed as part of an assignment focusing on the application of SOLID design principles in a real-world inspired scenario. The main objective is to design a flexible and maintainable payment system that supports the integration of new payment methods without altering existing code.

---

<h2 style="color:red;">🎯 Objective</h2>

The system simulates a payment processing application where:

- At least one existing payment method (Credit Card) is already implemented
- A new payment method (PayPal) is introduced
- The architecture must support extensibility in accordance with Open/Closed Principle (OCP)
- Each component should adhere to Single Responsibility Principle (SRP)

---

<h2 style="color:red;">⚙️ Architectural Components</h2>

<b>Abstraction Layer</b>
PaymentMethod: Defines a common interface for all payment operations

<b>Implementation Layer</b>
CreditCardPayment: Represents the existing payment method
PayPalPayment: Represents the newly integrated payment method

<b>Service Layer</b>
PaymentProcessor: Responsible for executing payment operations

---

<h2 style="color:red;">📦 Project Structure</h2>

<pre>
com.payment
│
├── abstraction # Interfaces (PaymentMethod)
├── implementation # Concrete payment methods
│ ├── CreditCardPayment
│ └── PayPalPayment
│
├── service # Business logic
│ └── PaymentProcessor
│
└── Main.java # Entry point
</pre>

---

<h2 style="color:red;">🧠 SOLID Principles Applied</h2>

<b>🔹 Single Responsibility Principle (SRP)</b>
Each class has a single responsibility:
PaymentProcessor → handles payment processing
PaymentMethod implementations → handle specific payment logic

---

<b>🔹 Open/Closed Principle (OCP)</b>
The system is open for extension but closed for modification.

👉 New payment methods can be added like this:

<pre>
class ApplePayPayment implements PaymentMethod {
@Override
public void pay(double amount) {
System.out.println("Paid with Apple Pay: " + amount);
}
}
</pre>

---

<b>🔹 Dependency Inversion Principle (DIP)</b>
High-level modules depend on abstractions, not concrete classes.

<pre>
public void processPayment(PaymentMethod paymentMethod, double amount)
</pre>
