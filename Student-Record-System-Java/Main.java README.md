import java.io.*;
            String line;
            boolean found = false;

            while ((line = br.readLine()) != null) {
                String[] data = line.split(",");

                int roll = Integer.parseInt(data[0]);

                if (roll == searchRoll) {
                    System.out.println("
Student Found");
                    System.out.println("Roll: " + data[0]);
                    System.out.println("Name: " + data[1]);
                    System.out.println("Marks: " + data[2]);
                    found = true;
                    break;
                }
            }

            if (!found) {
                System.out.println("Student Not Found!");
            }

            br.close();

        } catch (IOException e) {
            System.out.println("Error Occurred!");
        }
    }

    public static void main(String[] args) {

        while (true) {
            System.out.println("
===== Student Record Management =====");
            System.out.println("1. Add Student");
            System.out.println("2. Display Students");
            System.out.println("3. Search Student");
            System.out.println("4. Exit");

            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    addStudent();
                    break;

                case 2:
                    displayStudents();
                    break;

                case 3:
                    searchStudent();
                    break;

                case 4:
                    System.out.println("Exiting Program...");
                    System.exit(0);

                default:
                    System.out.println("Invalid Choice!");
            }
        }
    }
}
