<h1>Prime Number Calculator</h1>

<h2>Description</h2>
The **Prime Number Calculator** is a Java program that determines prime numbers based on user input. The program supports two different functionalities:

1. **Finding a specific number of prime numbers**  
   - The user specifies how many prime numbers they want, and the program calculates and displays them.

2. **Finding all prime numbers up to a given limit**  
   - The user provides a limit, and the program lists all prime numbers from 2 up to that limit.

This project demonstrates **looping structures**, **conditional statements**, **modulus operations**, and **basic user input handling in Java**.

<br />

<h2>Languages and Tools Used</h2>

- <b>Java</b>
- <b>Scanner Class</b> (for user input)
- <b>Loops and Conditionals</b> (for prime number calculations)

<h2>Program Walk-through</h2>

1. **Prompt User for Input**:
   - The user is asked whether they want to:
     - Find a specific number of prime numbers (**Assignment #1**).
     - Find all prime numbers up to a specific limit (**Assignment #2**).
   - The program captures user input using a `Scanner`.

2. **Prime Number Calculation**:
   - The program uses loops to find prime numbers.
   - The modulus operator (`%`) checks divisibility to determine whether a number is prime.
   - If a number is **only divisible by 1 and itself**, it is considered prime.

3. **Display Results**:
   - The prime numbers are printed in sequence, either:
     - The first **X** prime numbers.
     - All prime numbers up to **Y**.

<h2>Example Code</h2>

```java
import java.util.Scanner;

public class PrimeNumberCalculator {
    public static void main(String[] args) {
        Scanner keyboard = new Scanner(System.in);
        
        System.out.println("Choose an option:");
        System.out.println("1. Find first X prime numbers");
        System.out.println("2. Find all prime numbers up to Y");
        int choice = keyboard.nextInt();

        if (choice == 1) {
            System.out.print("How many prime numbers would you like to calculate: ");
            int numPrimes = keyboard.nextInt();
            findFirstNPrimes(numPrimes);
        } else if (choice == 2) {
            System.out.print("What is the limit to the prime numbers: ");
            int limit = keyboard.nextInt();
            findPrimesUpTo(limit);
        } else {
            System.out.println("Invalid choice. Please restart the program.");
        }

        keyboard.close();
    }

    public static void findFirstNPrimes(int count) {
        int primesFound = 0, num = 2;
        while (primesFound < count) {
            if (isPrime(num)) {
                System.out.print(num + " ");
                primesFound++;
            }
            num++;
        }
        System.out.println();
    }

    public static void findPrimesUpTo(int limit) {
        System.out.print("Prime numbers from 2 to " + limit + " are: ");
        for (int num = 2; num <= limit; num++) {
            if (isPrime(num)) {
                System.out.print(num + " ");
            }
        }
        System.out.println();
    }

    public static boolean isPrime(int num) {
        if (num < 2) return false;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) return false;
        }
        return true;
    }
}# -Prime-Number-calculator-project
