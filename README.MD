# Exercise 1 – Student Grades

## Problem
Write a Java program that stores student grades entered via the keyboard in an array named `grades` and allows the following operations:

1. Sort and display the grades  
2. Display the average grade  
3. Display the highest and lowest grades  
4. Display the number of students having a grade entered by the user  

Use `Arrays.sort()`.

---

## Solution

```java
import java.util.Arrays;
import java.util.Scanner;

public class GradesManager {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of students: ");
        int n = sc.nextInt();

        double[] grades = new double[n];

        for (int i = 0; i < n; i++) {
            System.out.print("Enter grade " + (i + 1) + ": ");
            grades[i] = sc.nextDouble();
        }

        Arrays.sort(grades);
        System.out.println("Sorted grades: " + Arrays.toString(grades));

        double sum = 0;
        for (double g : grades) sum += g;
        System.out.println("Average grade: " + sum / n);

        System.out.println("Lowest grade: " + grades[0]);
        System.out.println("Highest grade: " + grades[n - 1]);

        System.out.print("Enter a grade to count: ");
        double value = sc.nextDouble();

        int count = 0;
        for (double g : grades) {
            if (g == value) count++;
        }

        System.out.println("Number of students with this grade: " + count);
    }
}

