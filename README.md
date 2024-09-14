# Students-Grade-Tracker
This Program is basically for the people who are involved in the teaching related background. This program will help you to track records of students along with their few more details as per required by you.

/** Students Grade Tracker */


/**import java.util.ArrayList;
import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;
*/
import.java.util.*;

public class StudentGradeTracker {
    private static Scanner scanner = new Scanner(System.in);
    private static Map<String, ArrayList<Integer>> studentGrades = new HashMap<>();

    public static void main(String[] args) {
        while (true) {
            System.out.println("Student Grade Tracker");
            System.out.println("1. Add Student");
            System.out.println("2. Add Grade");
            System.out.println("3. Display Grades");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    addStudent();
                    break;
                case 2:
                    addGrade();
                    break;
                case 3:
                    displayGrades();
                    break;
                case 4:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        }
    }

    private static void addStudent() {
        System.out.print("Enter the student name: ");
        String name = scanner.nextLine();
        
        if (studentGrades.containsKey(name)) {
            System.out.println("Student already exists.");
        } else {
            studentGrades.put(name, new ArrayList<>());
            System.out.println("Student added.");
        }
    }

    private static void addGrade() {
        System.out.print("Enter the student name: ");
        String name = scanner.nextLine();
        
        if (studentGrades.containsKey(name)) {
            System.out.print("Enter the grade: ");
            int grade = scanner.nextInt();
            scanner.nextLine(); // Consume newline
            
            studentGrades.get(name).add(grade);
            System.out.println("Grade added.");
        } else {
            System.out.println("Student not found.");
        }
    }

    private static void displayGrades() {
        for (Map.Entry<String, ArrayList<Integer>> entry : studentGrades.entrySet()) {
            String name = entry.getKey();
            ArrayList<Integer> grades = entry.getValue();
            System.out.println("Student: " + name);
            System.out.println("Grades: " + grades);
        }
    }
}
