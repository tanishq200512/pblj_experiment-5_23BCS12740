import java.io.*;
import java.util.*;

class Employee implements Serializable {
    String name;
    int id;

    public Employee(String name, int id) {
        this.name = name;
        this.id = id;
    }

    public String toString() {
        return "Name: " + name + ", ID: " + id;
    }
}

public class PartC {
    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) {
        int ch;
        do {
            System.out.println("\nEmployee Menu:");
            System.out.println("1. Add Employee");
            System.out.println("2. Display Employees");
            System.out.println("3. Exit");
            System.out.print("Enter choice: ");
            ch = sc.nextInt();
            sc.nextLine();

            switch (ch) {
                case 1:
                    addEmployee();
                    break;
                case 2:
                    displayEmployees();
                    break;
                case 3:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid choice!");
            }
        } while (ch != 3);

        sc.close();
    }

    static void addEmployee() {
        try {
            List<Employee> employees = readEmployeesFromFile();
            System.out.print("Enter Employee Name: ");
            String name = sc.nextLine();
            System.out.print("Enter Employee ID: ");
            int id = sc.nextInt();
            sc.nextLine();
            Employee emp = new Employee(name, id);
            employees.add(emp);

            ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("employees.ser"));
            oos.writeObject(employees);
            oos.close();
            System.out.println("Employee added!");
        } catch (Exception e) {
            System.out.println("Error: " + e);
        }
    }

    static void displayEmployees() {
        try {
            List<Employee> employees = readEmployeesFromFile();
            if (employees.isEmpty()) {
                System.out.println("No employees found.");
            } else {
                System.out.println("Employees:");
                for (Employee emp : employees) {
                    System.out.println(emp);
                }
            }
        } catch (Exception e) {
            System.out.println("Error: " + e);
        }
    }

    @SuppressWarnings("unchecked")
    static List<Employee> readEmployeesFromFile() {
        List<Employee> employees = new ArrayList<>();
        try {
            File file = new File("employees.ser");
            if (file.exists()) {
                ObjectInputStream ois = new ObjectInputStream(new FileInputStream(file));
                employees = (ArrayList<Employee>) ois.readObject();
                ois.close();
            }
        } catch (Exception e) {
            // Ignore, return empty list if file not found or corrupted
        }
        return employees;
    }
}
