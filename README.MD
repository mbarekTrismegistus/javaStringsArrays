# OOP in Java  
## Strings and Arrays – Solutions



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

## Exercise 2: First Group Verb Conjugation

### Solution 

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

## Exercise 3: String Operations Menu

```java

import java.util.Scanner;

public class StringMenu {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String text = "";
        int choice;

        do {
            System.out.println("\n--- MENU ---");
            System.out.println("1. Enter string");
            System.out.println("2. Display string");
            System.out.println("3. Reverse string");
            System.out.println("4. Number of words");
            System.out.println("0. Exit");
            System.out.print("Choice: ");
            choice = sc.nextInt();
            sc.nextLine();

            switch (choice) {
                case 1:
                    System.out.print("Enter a string: ");
                    text = sc.nextLine();
                    break;

                case 2:
                    System.out.println("String: " + text);
                    break;

                case 3:
                    String reversed = new StringBuilder(text).reverse().toString();
                    System.out.println("Reversed: " + reversed);
                    break;

                case 4:
                    String trimmed = text.trim();
                    if (trimmed.isEmpty()) {
                        System.out.println("Number of words: 0");
                    } else {
                        String[] words = trimmed.split("\\s+");
                        System.out.println("Number of words: " + words.length);
                    }
                    break;
            }

            if (choice != 0) {
                System.out.println("Press Enter to return to the menu...");
                sc.nextLine();
            }

        } while (choice != 0);
    }
}

```

## Exercise 4: Letter Occurrences


```java

import java.util.Scanner;

public class LetterOccurrences {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] nb_occurrences = new int[26];

        System.out.print("Enter a line of text (max 100 characters): ");
        String text = sc.nextLine().toUpperCase();

        for (char c : text.toCharArray()) {
            if (c >= 'A' && c <= 'Z') {
                nb_occurrences[c - 'A']++;
            }
        }

        System.out.println("The string \"" + text + "\" contains:");
        for (int i = 0; i < 26; i++) {
            if (nb_occurrences[i] > 0) {
                System.out.println(
                    nb_occurrences[i] + " occurrence(s) of the letter '" + (char) ('A' + i) + "'"
                );
            }
        }
    }
}

```
