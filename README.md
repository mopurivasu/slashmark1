import java.util.ArrayList;
import java.util.Scanner;

public class TaskList {

    public static void main(String[] args) {
        ArrayList<String> tasks = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.println("\nTask List Menu:");
            System.out.println("1. Add Task");
            System.out.println("2. Remove Task");
            System.out.println("3. View Tasks");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");

            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline character

            switch (choice) {
                case 1:
                    System.out.print("Enter task to add: ");
                    String newTask = scanner.nextLine();
                    tasks.add(newTask);
                    System.out.println("Task added: " + newTask);
                    break;
                case 2:
                    if (tasks.isEmpty()) {
                        System.out.println("Task list is empty.");
                    } else {
                        System.out.print("Enter index of task to remove (0-" + (tasks.size() - 1) + "): ");
                        int index = scanner.nextInt();
                        scanner.nextLine(); // Consume newline character

                        if (index >= 0 && index < tasks.size()) {
                            String removedTask = tasks.remove(index);
                            System.out.println("Task removed: " + removedTask);
                        } else {
                            System.out.println("Invalid index.");
                        }
                    }
                    break;
                case 3:
                    if (tasks.isEmpty()) {
                        System.out.println("Task list is empty.");
                    } else {
                        System.out.println("\nTasks:");
                        for (int i = 0; i < tasks.size(); i++) {
                            System.out.println((i + 1) + ". " + tasks.get(i));
                        }
                    }
                    break;
                case 4:
                    System.out.println("Exiting program.");
                    scanner.close();
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice. Please enter a number between 1 and 4.");
                    break;
            }
        }
    }
}
