# Introduction

We are going to look at how to implement the Strategy Design Pattern in Java. Then, explaining how to leverage Java 8 features to reduce code verbosity.
The Strategy design pattern is a behavioral design pattern. This can use for change the behavior of algorithm/logic at runtime.

#  Implementation

For an example, We need to implement payment logic. A customer can choose credit card or cash as a payment method. But, there are two different logic to calculate final payment.

Create an interface, **PaymentStrategy.java**

```java
public interface PaymentStrategy {
    double pay(double amount);
}
```
Then, time to implement the payment logic.

***CashPaymentStrategy.java***

```java
public class CashPaymentStrategy implements PaymentStrategy {

    @Override
    public double pay(double amount) {
        double serviceCharge = 5.00;
        return amount + serviceCharge;
    }
}
```

***CreditCardPaymentStrategy.java***

```java
public class CreditCardStrategy implements PaymentStrategy {

    @Override
    public double pay(double amount) {
        double serviceCharge = 5.00;
        double creditCardFee = 10.00;
        return amount + serviceCharge + creditCardFee;
    }
}
```

The implementation is done. Now, we are going to test it.

```java runnable
interface PaymentStrategy {
    double pay(double amount);
}
class CashPaymentStrategy implements PaymentStrategy {

    @Override
    public double pay(double amount) {
        double serviceCharge = 5.00;
        return amount + serviceCharge;
    }
}
class CreditCardStrategy implements PaymentStrategy {

    @Override
    public double pay(double amount) {
        double serviceCharge = 5.00;
        double creditCardFee = 10.00;
        return amount + serviceCharge + creditCardFee;
    }
}
// { autofold
public class Main {

    public static void main(String[] args) {
        double price = 100;
        PaymentStrategy paymentStrategy = new CashPaymentStrategy();
        System.out.println("Cash Price: -" + paymentStrategy.pay(price));

        paymentStrategy = new CreditCardStrategy();
        System.out.println("Credit Card Price: -" + paymentStrategy.pay(price));
    }
}
//{ autofold
```
