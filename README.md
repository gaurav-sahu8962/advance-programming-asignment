# advance-programming-asignment
import java.util.ArrayList;
import java.util.Scanner;
class Library {
    private ArrayList<String> books;

    public Library() {
        this.books = new ArrayList<>();
    }

    public void addBook(String book)
    {
        books.add(book);
        System.out.println(book + "added to the library");
          }

            public void removeBook(String book) {
                if (books.contains(book)) {
                    books.remove(book);
                    System.out.println(book + "remove book from library");
                } else {
                    System.out.println(book + "is not in the library");
                }
            }

            public void displayBooks() {
                if (books.isEmpty()) {
                    System.out.println("the library is empty");
                } else {
                    System.out.println("book in the library");
                    for (String book : books) {
                        System.out.println(" - " + book);
                    }
                }
            }
            
        public static void main(String[] args) {
            Library myLibrary = new Library();
            Scanner scanner = new Scanner(System.in);
            int choice;

            do{
                System.out.println("\n---Library menu---");
                System.out.println("1. Add Book");
                System.out.println("2. Remove Book");
                System.out.println("3. Display Books");
                System.out.println("4. Exit");
                System.out.println("Enter Your Choice;");
                choice = scanner.nextInt();
                scanner.nextLine();

                switch (choice){
                    case 1:
                        System.out.println("Enter Book name to add");
                        String bookToAdd = scanner.nextLine();
                        myLibrary.addBook(bookToAdd);
                        break;
                    case 2:
                        System.out.println("Enter book name to remove");
                        String bookToRemove = scanner.nextLine();
                        myLibrary.removeBook(bookToRemove);
                        break;
                    case 3:
                        myLibrary.displayBooks();
                        break;
                    case 4:
                        System.out.println("Existing Library System");
                        break;
                    default:
                        System.out.println("Invalid Choice.Please try Again");

                }
            }while (choice != 4);
            scanner.close();
        }




}

