## 1. 

```java
import java.util.LinkedList;
import java.util.Scanner;

class Main {

  public static void main(String[] args) {
    // create an LinkedList of String type
    LinkedList<String> series = new LinkedList<>();

    // take 3 String input from user
    Scanner input = new Scanner(System.in);

    String input1 = input.nextLine();
    String input2 = input.nextLine();
    String input3 = input.nextLine();

    // add elements to series
    series.add(input1);
    series.add(input2);
    series.add(input3);

    // get element at index 2 using get()
    String name = series.get(2);

    // print name
    System.out.println(name);
    input.close();
  }
}
```

## 2. 

```java
import java.util.Scanner;

// create a class name College
class College {

  // create a static field name
  static String name;

  // create a static void method
  static void display() {
    // print static field name
    System.out.println(name);
  }
}

// create a class named Main
class Main {

  // create main() method
  public static void main(String[] args) {
    // take input for college name
    Scanner input = new Scanner(System.in);
    String inputName = input.nextLine();

    // set the value of static field as user input
    College.name = inputName;

    // call the static method
    College.display();
    input.close();
  }
}



```

## 3.

    Problem Statement
    Write a program to determine if two strings are equal.
    Prompt the user to enter two strings.
    Use the equals() method to compare the strings.
    Print "Equal" if the strings are equal, and "Not Equal" if the strings are not equal.

```java
import java.util.Scanner;

class Main {

  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);

    // take input values for both string
    String str1 = input.next();
    String str2 = input.next();

    // compare two strings using equals()
    if (str1.equals(str2)) {
      System.out.println("Equal");
    } else {
      System.out.println("Not Equal");
    }

    input.close();
  }
}
```

## 4.
hashmap ~ dictinary
```java
import java.util.HashMap;

class Main {
    public static void main(String[] args) {

        // create Map of Integer key & String value
        HashMap<Integer, String> song = new HashMap<>();

        // add elements to song
        song.put(1, "yestreday");
        song.put(2, "21 guns");

        // System.out.println(song);

        // access value of song with key 2
        String value = song.get(2);

        System.out.println(value);

    }
}
```

## 5

<details>

```java
import java.util.Scanner;

public class DrawShapes {
    public static void main(String[] args) {

        Scanner scn = new Scanner(System.in);

        try {
            System.out.println("Select the shape to print");
            System.out.println("1 - Rectangle");
            System.out.println("2 - Right Triangle");
            System.out.println("3 - Isosceles Triangle");
            System.out.println("4 - Diamond");
            System.out.println("5 - Heart");
            System.out.println("0 - Exit");

            int choice = scn.nextInt();
            System.out.println();
            do {
                switch (choice) {
                case 1:
                    System.out.println("Enter the number of rows for the rectangle:");
                    int rows = scn.nextInt();
                    int columns = scn.nextInt();
                    System.out.println("Printing rectangle");
                    DrawShapes.printRectangle(rows, columns);
                    break;
                case 2:
                    System.out.println("Enter the height of the right triangle:");
                    int rowst = scn.nextInt();
                    System.out.println("Printinng right triangle:");
                    DrawShapes.printRightTriangle(rowst);
                    break;

                case 3:
                    System.out.println("Enter the height of the isosceles triangle:");
                    int h = scn.nextInt();
                    System.out.println("Printing isoceles triangle:");
                    DrawShapes.printIsoscelesTriangle(h);
                    break;
                case 4:
                    System.out.println("Enter the height of the diamond");
                    int hd = scn.nextInt();
                    System.out.println("Printing diamond:");
                    DrawShapes.printDiamond(hd);
                    break;
                case 5:
                    DrawShapes.printHeart();
                    break;
                case 0:
                    System.out.println("Program exited.");

                }

            } while (choice != 0);

        } catch (Throwable e) {
            System.out.println("Invalid input Try again,error msg: " + e.getMessage());
        } finally {
            scn.close();

        }

    }

    public static void printRectangle(int rows, int columns) {
        System.out.println("yes1");

    }

    public static void printRightTriangle(int rows) {
        System.out.println("yes2");

    }

    public static void printIsoscelesTriangle(int rows) {
        System.out.println("yes3");

    }

    public static void printDiamond(int rows) {
        System.out.println("yes4");
    }

    public static void printHeart() {
        System.out.println("yes5");
    }

}
```

</details>

<details>

```java
    import java.util.Scanner;

    public class DrawShapes {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            String option;

            do {
                System.out.println("Select the shape to print:");
                System.out.println("1 - Rectangle");
                System.out.println("2 - Right Triangle");
                System.out.println("3 - Isosceles Triangle");
                System.out.println("4 - Diamond");
                System.out.println("5 - Heart");
                System.out.println("0 - Exit");
                option = scanner.next();

                switch (option) {
                    case "1":
                        System.out.println("Enter the number of rows for the rectangle:");
                        int rows = scanner.nextInt();
                        System.out.println("Enter the number of columns for the rectangle:");
                        int columns = scanner.nextInt();
                        printRectangle(rows, columns);
                        break;
                    case "2":
                        System.out.println("Enter the height of the right triangle:");
                        int rightTriangleRows = scanner.nextInt();
                        printRightTriangle(rightTriangleRows);
                        break;
                    case "3":
                        System.out.println("Enter the height of the isosceles triangle:");
                        int isoscelesTriangleRows = scanner.nextInt();
                        printIsoscelesTriangle(isoscelesTriangleRows);
                        break;
                    case "4":
                        System.out.println("Enter the height of the diamond:");
                        int diamondRows = scanner.nextInt();
                        printDiamond(diamondRows);
                        break;
                    case "5":
                        printHeart();
                        break;
                    case "0":
                        System.out.println("Program exited.");
                        break;
                    default:
                        System.out.println("Invalid option. Please select again.");
                        break;
                }
            } while (!option.equals("0"));

            scanner.close();
        }

        public static void printRectangle(int rows, int columns) {
            System.out.println("Printing rectangle:");
            for (int i = 0; i < rows; i++) {
                for (int j = 0; j < columns; j++) {
                    System.out.print("*");
                }
                System.out.println();
            }
            System.out.println();
        }

        public static void printRightTriangle(int rows) {
            System.out.println("Printing right triangle:");
            for (int i = 0; i < rows; i++) {
                for (int j = 0; j <= i; j++) {
                    System.out.print("*");
                }
                System.out.println();
            }
            System.out.println();
        }

        public static void printIsoscelesTriangle(int rows) {
            System.out.println("Printing isosceles triangle:");
            for (int i = 0; i < rows; i++) {
                for (int j = rows - i; j > 1; j--) {
                    System.out.print(" ");
                }
                for (int k = 0; k <= i; k++) {
                    System.out.print("* ");
                }
                System.out.println();
            }
            System.out.println();
        }

        public static void printDiamond(int rows) {
            rows = rows / 2 + 1;
            System.out.println("Printing diamond:");
            for (int i = 0; i < rows; i++) {
                for (int j = rows - i; j > 1; j--) {
                    System.out.print(" ");
                }
                for (int k = 0; k <= i; k++) {
                    System.out.print("* ");
                }
                System.out.println();
            }
            for (int i = rows - 2; i >= 0; i--) {
                for (int j = rows - i; j > 1; j--) {
                    System.out.print(" ");
                }
                for (int k = 0; k <= i; k++) {
                    System.out.print("* ");
                }
                System.out.println();
            }
            System.out.println();
        }

        public static void printHeart() {
            int height = 8;
            int Q = height / 2 - 1; // Determine the number of lines in the top part
            int W = height - 2; // Determine the number of asterisks in the bottom of the top part
            // Loop to generate the top part
            for (int i = 1; i <= Q; i++) {
                // Generate the first space triangle
                for (int a = Q; a > i - 1; a--) {
                    System.out.print(" ");
                    System.out.print(" ");
                }
                // Generate the first protruding triangle
                for (int b = 1; b < i + 1; b++) {
                    System.out.print("*");
                    System.out.print(" ");
                }
                for (int d = 1; d < i + 1; d++) {
                    System.out.print("*");
                    System.out.print(" ");
                }
                // Generate the middle space triangle
                for (int r = Q; r >= i + 1; r--) {
                    System.out.print(" ");
                    System.out.print(" ");
                }
                for (int t = Q + 1; t >= i + 1; t--) {
                    System.out.print(" ");
                    System.out.print(" ");
                }
                // Generate the trailing protruding triangle
                for (int b = 1; b < i + 1; b++) {
                    System.out.print("*");
                    System.out.print(" ");
                }
                for (int d = 1; d < i + 1; d++) {
                    System.out.print("*");
                    System.out.print(" ");
                }
                System.out.println();
            }
            // Generate the bottom part
            for (int w = 1; w <= height; w++) {
                for (int e = 1; e < w; e++) {
                    System.out.print(" ");
                    System.out.print(" ");
                }
                for (int r = height; r >= w; r--) {
                    System.out.print("*");
                    System.out.print(" ");
                }
                for (int t = height; t > w; t--) {
                    System.out.print("*");
                    System.out.print(" ");
                }
                System.out.println();
            }
        }

    }
```

</details>


## 6
<!-- sdas -->
