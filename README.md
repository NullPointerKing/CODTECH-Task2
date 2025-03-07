# 📊 Grade Calculator Application

## 📋 Project Overview

This project contains a simple Grade Calculator application developed in Java during my internship at Codtech IT Solutions. The calculator allows users to enter grades for multiple subjects and calculates the average grade, letter grade, and GPA.

## 👨‍💼 Intern Details

- **Name:** Abhinav Dyan Samantara
- **Company:** Codtech IT Solutions
- **ID:** CT12DS1738
- **Domain:** Java Programming
- **Duration:** July to September 2024

## 📜 Description

The Grade Calculator application allows users to:
- Enter grades for multiple subjects.
- Calculate the average grade.
- Determine the corresponding letter grade.
- Calculate the GPA based on the average grade.

The user is prompted to enter the number of subjects and the grades for each subject. Special values such as -1 for ABS (exam not given) and -2 for M (malpractice) are handled appropriately.

## 💻 How to Use

1. **Compile the Java code**:
   ```bash
   javac GradeCalculator.java


2. **Run the compiled Java program**:
   ```bash
   java GradeCalculator
3. **Follow the on-screen instructions to choose an operation and input numbers.**


## 📝 Code

**The main code for the Grade calculator application is as follows:**

```bash
import java.util.Scanner;
import java.util.ArrayList;

public class GradeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Double> grades = new ArrayList<>();

        System.out.println("Welcome to the Grade Calculator!");
        System.out.print("Enter the number of subjects: ");
        int numSubjects = scanner.nextInt();

        for (int i = 0; i < numSubjects; i++) {
            double grade;
            while (true) {
                System.out.print("Enter grade for subject " + (i + 1) + ": ");
                grade = scanner.nextDouble();
                if (isValidGrade(grade)) {
                    break;
                } else {
                    System.out.println("Invalid grade. Please enter a non-negative grade or -1 for ABS (exam not given) or -2 for M (malpractice).");
                }
            }
            grades.add(grade);
        }

        if (grades.isEmpty()) {
            System.out.println("No grades were entered.");
        } else {
            double average = calculateAverage(grades);
            String letterGrade = getLetterGrade(average);
            double gpa = getGPA(average);

            System.out.println("\nGrade Report:");
            System.out.printf("Average Grade: %.2f%n", average);
            System.out.println("Letter Grade: " + letterGrade);
            System.out.printf("GPA (out of 10): %.2f%n", gpa);
        }

        scanner.close();
    }

    private static boolean isValidGrade(double grade) {
        return grade >= -2 && grade <= 100;
    }

    private static double calculateAverage(ArrayList<Double> grades) {
        double sum = 0;
        int count = 0;
        for (double grade : grades) {
            if (grade != -1 && grade != -2) {
                sum += grade;
                count++;
            }
        }
        if (count == 0) {
            return 0;
        }
        return sum / count;
    }

    private static String getLetterGrade(double average) {
        if (average == -1) {
            return "ABS";
        } else if (average == -2) {
            return "M";
        } else if (average >= 90) {
            return "O";
        } else if (average >= 80) {
            return "A+";
        } else if (average >= 70) {
            return "A";
        } else if (average >= 60) {
            return "B+";
        } else if (average >= 50) {
            return "B";
        } else if (average >= 45) {
            return "C";
        } else if (average >= 40) {
            return "D";
        } else {
            return "F";
        }
    }

    private static double getGPA(double average) {
        if (average == -1) {
            return 0.0;
        } else if (average == -2) {
            return 0.0;
        } else if (average >= 90) {
            return 10.0;
        } else if (average >= 80) {
            return 9.0;
        } else if (average >= 70) {
            return 8.0;
        } else if (average >= 60) {
            return 7.0;
        } else if (average >= 50) {
            return 6.0;
        } else if (average >= 45) {
            return 5.0;
        } else if (average >= 40) {
            return 4.0;
        } else {
            return 0.0;
        }
    }
}

```

## ✨ Features

* Grade Input: Enter grades for multiple subjects.
* Average Calculation: Calculates the average grade, excluding special values.
* Letter Grade: Determines the corresponding letter grade based on the average.
* GPA Calculation: Calculates the GPA on a 10-point scale.

## 👨‍🎓 Author

* Abhinav Dyan Samantara

## 📄 License
This project is for educational purposes during the internship and is not licensed for commercial use.
