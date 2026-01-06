# OOP in Java  
## Strings and Arrays – Solutions

**Author:** Loubna Aminou  
**Academic Year:** 2025/2026  

---

## Exercise 1: Student Grades

### Solution (Java)

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

        // Sort grades
        Arrays.sort(grades);
        System.out.println("Sorted grades: " + Arrays.toString(grades));

        // Average
        double sum = 0;
        for (double g : grades) {
            sum += g;
        }
        System.out.println("Average grade: " + sum / n);

        // Min & Max
        System.out.println("Lowest grade: " + grades[0]);
        System.out.println("Highest grade: " + grades[n - 1]);

        // Count occurrences
        System.out.print("Enter a grade to count: ");
        double value = sc.nextDouble();

        int count = 0;
        for (double g : grades) {
            if (g == value) {
                count++;
            }
        }
        System.out.println("Number of students with this grade: " + count);
    }
}

```

# Exercise 2: First Group Verb Conjugation
## Solution 

```java

import java.util.Scanner;

public class Conjugation {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Entrez un verbe du premier groupe : ");
        String verb = sc.nextLine().toLowerCase();

        if (!verb.endsWith("er")) {
            System.out.println("Ce n'est pas un verbe du premier groupe.");
            return;
        }

        String root = verb.substring(0, verb.length() - 2);

        System.out.println("je " + root + "e");
        System.out.println("tu " + root + "es");
        System.out.println("il/elle " + root + "e");
        System.out.println("nous " + root + "ons");
        System.out.println("vous " + root + "ez");
        System.out.println("ils/elles " + root + "ent");
    }
}
 
```
