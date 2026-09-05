import java.util.ArrayList;
import java.util.Scanner;

// User Management
class User {
    int id;
    String name;
    String email;

    User(int id, String name, String email) {
        this.id = id;
        this.name = name;
        this.email = email;
    }
}

// Content Management
class Content {
    int id;
    String title;
    String description;

    Content(int id, String title, String description) {
        this.id = id;
        this.title = title;
        this.description = description;
    }
}

// Media Management
class Media {
    int id;
    String fileName;
    String type;

    Media(int id, String fileName, String type) {
        this.id = id;
        this.fileName = fileName;
        this.type = type;
    }
}

// Main Class
public class Main {

    static Scanner sc = new Scanner(System.in);

    static ArrayList<User> users = new ArrayList<User>();
    static ArrayList<Content> contents = new ArrayList<Content>();
    static ArrayList<Media> mediaList = new ArrayList<Media>();

    // Add User
    static void addUser() {
        System.out.print("Enter User ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter User Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Email: ");
        String email = sc.nextLine();

        users.add(new User(id, name, email));

        System.out.println("User added successfully!");
    }

    // View Users
    static void viewUsers() {
        System.out.println("\n--- USER MANAGEMENT ---");

        if (users.size() == 0) {
            System.out.println("No users found.");
        } else {
            for (User u : users) {
                System.out.println("User ID : " + u.id);
                System.out.println("Name    : " + u.name);
                System.out.println("Email   : " + u.email);
                System.out.println("----------------------");
            }
        }
    }

    // Add Content
    static void addContent() {
        System.out.print("Enter Content ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Content Title: ");
        String title = sc.nextLine();

        System.out.print("Enter Description: ");
        String description = sc.nextLine();

        contents.add(new Content(id, title, description));

        System.out.println("Content added successfully!");
    }

    // View Content
    static void viewContent() {
        System.out.println("\n--- CONTENT MANAGEMENT ---");

        if (contents.size() == 0) {
            System.out.println("No content found.");
        } else {
            for (Content c : contents) {
                System.out.println("Content ID : " + c.id);
                System.out.println("Title      : " + c.title);
                System.out.println("Description: " + c.description);
                System.out.println("--------------------------");
            }
        }
    }

    // Add Media
    static void addMedia() {
        System.out.print("Enter Media ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter File Name: ");
        String fileName = sc.nextLine();

        System.out.print("Enter Media Type: ");
        String type = sc.nextLine();

        mediaList.add(new Media(id, fileName, type));

        System.out.println("Media added successfully!");
    }

    // View Media
    static void viewMedia() {
        System.out.println("\n--- MEDIA MANAGEMENT ---");

        if (mediaList.size() == 0) {
            System.out.println("No media found.");
        } else {
            for (Media m : mediaList) {
                System.out.println("Media ID  : " + m.id);
                System.out.println("File Name : " + m.fileName);
                System.out.println("Media Type: " + m.type);
                System.out.println("------------------------");
            }
        }
    }

    // Administrator and Reports
    static void generateReport() {
        System.out.println("\n===== WEBSITE ADMINISTRATOR REPORT =====");

        System.out.println("Total Users    : " + users.size());
        System.out.println("Total Contents : " + contents.size());
        System.out.println("Total Media    : " + mediaList.size());

        System.out.println("========================================");
    }

    // Main Method
    public static void main(String[] args) {

        int choice;

        do {
            System.out.println("\n======================================");
            System.out.println("     WEBSITE MANAGEMENT SYSTEM");
            System.out.println("======================================");
            System.out.println("1. User Management");
            System.out.println("2. View Users");
            System.out.println("3. Content Management");
            System.out.println("4. View Content");
            System.out.println("5. Media Management");
            System.out.println("6. View Media");
            System.out.println("7. Administrator & Reports");
            System.out.println("8. Exit");
            System.out.println("======================================");

            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {

                case 1:
                    addUser();
                    break;

                case 2:
                    viewUsers();
                    break;

                case 3:
                    addContent();
                    break;

                case 4:
                    viewContent();
                    break;

                case 5:
                    addMedia();
                    break;

                case 6:
                    viewMedia();
                    break;

                case 7:
                    generateReport();
                    break;

                case 8:
                    System.out.println("Thank you!");
                    break;

                default:
                    System.out.println("Invalid choice!");
            }

        } while (choice != 8);

        sc.close();
    }
}
