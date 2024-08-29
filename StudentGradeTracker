import java.util.Scanner;

public class StudentGradeTracker {
    private Student[] students;
    private int studentCount;

    public StudentGradeTracker(int capacity) {
        this.students = new Student[capacity];
        this.studentCount = 0;
    }

    public void addStudent(String name) {
        if (studentCount < students.length) {
            students[studentCount] = new Student(name);
            studentCount++;
        } else {
            System.out.println("Student list is full.");
        }
    }

    public void addGrade(String name, String subject, double grade) {
        for (int i = 0; i < studentCount; i++) {
            if (students[i].getName().equals(name)) {
                students[i].addGrade(subject, grade);
                return;
            }
        }
        System.out.println("Student not found.");
    }

    public void printGrades(String name) {
        for (int i = 0; i < studentCount; i++) {
            if (students[i].getName().equals(name)) {
                students[i].printGrades();
                return;
            }
        }
        System.out.println("Student not found.");
    }

    public void printAverageGrade(String name) {
        for (int i = 0; i < studentCount; i++) {
            if (students[i].getName().equals(name)) {
                students[i].printAverageGrade();
                return;
            }
        }
        System.out.println("Student not found.");
    }

    public static void main(String[] args) {
        StudentGradeTracker tracker = new StudentGradeTracker(10);
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("1. Add student");
            System.out.println("2. Add grade");
            System.out.println("3. Print grades");
            System.out.println("4. Print average grade");
            System.out.println("5. Exit");

            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline left-over

            switch (choice) {
                case 1:
                    System.out.println("Enter student name:");
                    String name = scanner.nextLine();
                    tracker.addStudent(name);
                    break;
                case 2:
                    System.out.println("Enter student name:");
                    name = scanner.nextLine();
                    System.out.println("Enter subject:");
                    String subject = scanner.nextLine();
                    System.out.println("Enter grade:");
                    double grade = scanner.nextDouble();
                    scanner.nextLine(); // Consume newline left-over
                    tracker.addGrade(name, subject, grade);
                    break;
                case 3:
                    System.out.println("Enter student name:");
                    name = scanner.nextLine();
                    tracker.printGrades(name);
                    break;
                case 4:
                    System.out.println("Enter student name:");
                    name = scanner.nextLine();
                    tracker.printAverageGrade(name);
                    break;
                case 5:
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}

class Student {
    private String name;
    private Grade[] grades;
    private int gradeCount;

    public Student(String name) {
        this.name = name;
        this.grades = new Grade[10];
        this.gradeCount = 0;
    }

    public void addGrade(String subject, double grade) {
        if (gradeCount < grades.length) {
            grades[gradeCount] = new Grade(subject, grade);
            gradeCount++;
        } else {
            System.out.println("Grade list is full.");
        }
    }

    public void printGrades() {
        System.out.println("Grades for " + name + ":");
        for (int i = 0; i < gradeCount; i++) {
            System.out.println(grades[i].getSubject() + ": " + grades[i].getGrade());
        }
    }

    public void printAverageGrade() {
        double sum = 0;
        for (int i = 0; i < gradeCount; i++) {
            sum += grades[i].getGrade();
        }
        double average = sum / gradeCount;
        System.out.println("Average grade for " + name + ": " + average);
    }

    public String getName() {
        return name;
    }
}

class Grade {
    private String subject;
    private double grade;

    public Grade(String subject, double grade) {
        this.subject = subject;
        this.grade = grade;
    }

    public String getSubject() {
        return subject;
    }

    public double getGrade() {
        return grade;
    }
}
