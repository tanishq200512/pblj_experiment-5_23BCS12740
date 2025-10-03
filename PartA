import java.util.*;

public class PartA {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter integers separated by space:");
        String[] tokens = sc.nextLine().split(" ");
        ArrayList<Integer> list = new ArrayList<>();
        for (String s : tokens) {
            list.add(Integer.parseInt(s));
        }
        int sum = 0;
        for (int num : list) {
            sum += num; // Autoboxing/Unboxing happens here
        }
        System.out.println("Sum: " + sum);
        sc.close();
    }
}
