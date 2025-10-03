import java.io.*;
import java.util.*;

class Student implements Serializable {
    String name;
    int roll;
    double marks;

    public Student(String name, int roll, double marks) {
        this.name = name;
        this.roll = roll;
        this.marks = marks;
    }

    public String toString() {
        return "Name: " + name + ", Roll: " + roll + ", Marks: " + marks;
    }
}

public class PartB {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        try {
            System.out.print("Enter Student Name: ");
            String name = sc.nextLine();
            System.out.print("Enter Roll: ");
            int roll = sc.nextInt();
            System.out.print("Enter Marks: ");
            double marks = sc.nextDouble();

            Student s = new Student(name, roll, marks);
            // Serialization
            ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("student.ser"));
            oos.writeObject(s);
            oos.close();
            System.out.println("Student object serialized!");

            // Deserialization
            ObjectInputStream ois = new ObjectInputStream(new FileInputStream("student.ser"));
            Student s2 = (Student) ois.readObject();
            ois.close();
            System.out.println("Deserialized Student: " + s2);
        } catch (Exception e) {
            System.out.println("Error: " + e);
        }
        sc.close();
    }
}
