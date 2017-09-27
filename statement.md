## Introduction

We are going to look at how to implement the Strategy Design Pattern in Java. Then, explaining how to leverage Java 8 features to reduce code verbosity.
The Strategy design pattern is a behavioral design pattern. This can use for change the behavior of algorithm/logic at runtime.

##  Implementation

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

```java
// { autofold
public class Main {

public static void main(String[] args) {
// }

String message = "Hello World!";
System.out.println(message);

//{ autofold
}

}
//}
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Java template](https://tech.io/select-repo/385)
