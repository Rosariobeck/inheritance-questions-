# inheritance-questions-
//question 1:      (INHERITANCE)
// Parent Class: Animal
class Animal {
    // Common properties
    String name;
    int age;

    // Constructor
    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method to represent generic animal behavior
    public void sound() {
        System.out.println("This animal makes a sound.");
    }
}

// Subclass: Dog
class Dog extends Animal {

    // Constructor
    public Dog(String name, int age) {
        super(name, age);
    }

    // Method to represent dog's behavior
    public void bark() {
        System.out.println("Dog is barking.");
    }
}

// Subclass: Cat
class Cat extends Animal {

    // Constructor
    public Cat(String name, int age) {
        super(name, age);
    }

    // Method to represent cat's behavior
    public void meow() {
        System.out.println("Cat is meowing.");
    }
}

// Subclass: Bird
class Bird extends Animal {

    // Constructor
    public Bird(String name, int age) {
        super(name, age);
    }

    // Method to represent bird's behavior
    public void fly() {
        System.out.println("Bird is flying.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create objects of each subclass
        Dog dog = new Dog("Buddy", 4);
        Cat cat = new Cat("Misty", 2);
        Bird bird = new Bird("Sky", 1);

        // Demonstrating their behaviors
        System.out.println(dog.name + " (Age: " + dog.age + ") says:");
        dog.sound();  // Generic sound
        dog.bark();   // Dog specific behavior

        System.out.println(cat.name + " (Age: " + cat.age + ") says:");
        cat.sound();  // Generic sound
        cat.meow();   // Cat specific behavior

        System.out.println(bird.name + " (Age: " + bird.age + ") says:");
        bird.sound(); // Generic sound
        bird.fly();    // Bird specific behavior
    }
}


//question 2:
// Parent Class: BankAccount
class BankAccount {
    // Common properties
    String accountHolderName;
    double balance;

    // Constructor
    public BankAccount(String accountHolderName, double initialBalance) {
        this.accountHolderName = accountHolderName;
        this.balance = initialBalance;
    }

    // Method to display the balance
    public void displayBalance() {
        System.out.println(accountHolderName + "'s account balance: $" + balance);
    }

    // Method to deposit money
    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited: $" + amount);
    }
}

// Subclass: SavingsAccount
class SavingsAccount extends BankAccount {

    // Constructor
    public SavingsAccount(String accountHolderName, double initialBalance) {
        super(accountHolderName, initialBalance);
    }

    // Method to add interest (5% increase in balance)
    public void addInterest() {
        double interest = balance * 0.05;
        balance += interest;
        System.out.println("Interest added: $" + interest);
    }
}

// Subclass: CurrentAccount
class CurrentAccount extends BankAccount {

    // Constructor
    public CurrentAccount(String accountHolderName, double initialBalance) {
        super(accountHolderName, initialBalance);
    }

    // Method to deduct maintenance fee (2% reduction in balance)
    public void deductMaintenanceFee() {
        double fee = balance * 0.02;
        balance -= fee;
        System.out.println("Maintenance fee deducted: $" + fee);
    }
}

public class Main {
    public static void main(String[] args) {
        // Create objects of each subclass
        SavingsAccount savingsAccount = new SavingsAccount("John Doe", 1000.0);
        CurrentAccount currentAccount = new CurrentAccount("Jane Smith", 1500.0);

        // Demonstrating operations on SavingsAccount
        savingsAccount.displayBalance();  // Display initial balance
        savingsAccount.deposit(500);      // Deposit money into the savings account
        savingsAccount.addInterest();     // Add interest to savings account
        savingsAccount.displayBalance();  // Display balance after interest

        System.out.println();

        // Demonstrating operations on CurrentAccount
        currentAccount.displayBalance(); // Display initial balance
        currentAccount.deposit(300);     // Deposit money into the current account
        currentAccount.deductMaintenanceFee(); // Deduct maintenance fee from current account
        currentAccount.displayBalance(); // Display balance after maintenance fee
    }
}

//question 3:

// Parent Class: Vehicle
class Vehicle {
    // Common properties
    String brand;
    String model;

    // Constructor
    public Vehicle(String brand, String model) {
        this.brand = brand;
        this.model = model;
    }

    // Method to represent common vehicle behavior
    public void start() {
        System.out.println("Vehicle is starting.");
    }
}

// Subclass: Car
class Car extends Vehicle {

    // Constructor
    public Car(String brand, String model) {
        super(brand, model);
    }

    // Method specific to Car
    public void drive() {
        System.out.println("Car is driving on the highway.");
    }
}

// Subclass: Truck
class Truck extends Vehicle {

    // Constructor
    public Truck(String brand, String model) {
        super(brand, model);
    }

    // Method specific to Truck
    public void haul() {
        System.out.println("Truck is carrying heavy loads.");
    }
}

// Subclass: Motorcycle
class Motorcycle extends Vehicle {

    // Constructor
    public Motorcycle(String brand, String model) {
        super(brand, model);
    }

    // Method specific to Motorcycle
    public void race() {
        System.out.println("Motorcycle is racing on the track.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create objects of each subclass
        Car car = new Car("Toyota", "Corolla");
        Truck truck = new Truck("Ford", "F-150");
        Motorcycle motorcycle = new Motorcycle("Yamaha", "R1");

        // Demonstrating the behaviors of each vehicle type
        System.out.println(car.brand + " " + car.model + " (Car):");
        car.start();      // Common behavior (from Vehicle)
        car.drive();      // Specific to Car

        System.out.println();

        System.out.println(truck.brand + " " + truck.model + " (Truck):");
        truck.start();    // Common behavior (from Vehicle)
        truck.haul();     // Specific to Truck

        System.out.println();

        System.out.println(motorcycle.brand + " " + motorcycle.model + " (Motorcycle):");
        motorcycle.start();  // Common behavior (from Vehicle)
        motorcycle.race();   // Specific to Motorcycle
    }
}

// question 4:
// Parent Class: Person
class Person {
    // Common properties
    String name;
    int age;

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Method to introduce the person
    public void introduce() {
        System.out.println("Hello, my name is " + name + " and I am " + age + " years old.");
    }
}

// Subclass: Student
class Student extends Person {

    // Constructor
    public Student(String name, int age) {
        super(name, age);
    }

    // Method specific to Student
    public void study() {
        System.out.println("Student is studying.");
    }
}

// Subclass: Teacher
class Teacher extends Person {

    // Constructor
    public Teacher(String name, int age) {
        super(name, age);
    }

    // Method specific to Teacher
    public void teach() {
        System.out.println("Teacher is teaching.");
    }
}

// Subclass: Principal
class Principal extends Person {

    // Constructor
    public Principal(String name, int age) {
        super(name, age);
    }

    // Method specific to Principal
    public void manage() {
        System.out.println("Principal is managing the school.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create objects of each subclass
        Student student = new Student("Alice", 20);
        Teacher teacher = new Teacher("Mr. Smith", 35);
        Principal principal = new Principal("Dr. Johnson", 50);

        // Demonstrating the roles of each subclass
        System.out.println(student.name + " (Student):");
        student.introduce();  // General introduction
        student.study();      // Specific to Student

        System.out.println();

        System.out.println(teacher.name + " (Teacher):");
        teacher.introduce();  // General introduction
        teacher.teach();      // Specific to Teacher

        System.out.println();

        System.out.println(principal.name + " (Principal):");
        principal.introduce();  // General introduction
        principal.manage();     // Specific to Principal
    }
}

// question 5

// Parent Class: Product
class Product {
    // Common properties
    String productName;
    double price;

    // Constructor
    public Product(String productName, double price) {
        this.productName = productName;
        this.price = price;
    }

    // Method to display general product details
    public void displayDetails() {
        System.out.println("Product Name: " + productName);
        System.out.println("Price: $" + price);
    }
}

// Subclass: Electronics
class Electronics extends Product {

    // Constructor
    public Electronics(String productName, double price) {
        super(productName, price);
    }

    // Method specific to Electronics
    public void warrantyDetails() {
        System.out.println("Warranty: 2 years manufacturer's warranty.");
    }
}

// Subclass: Clothing
class Clothing extends Product {

    // Constructor
    public Clothing(String productName, double price) {
        super(productName, price);
    }

    // Method specific to Clothing
    public void sizeChart() {
        System.out.println("Size Chart: S, M, L, XL, XXL.");
    }
}

// Subclass: Books
class Books extends Product {

    // Constructor
    public Books(String productName, double price) {
        super(productName, price);
    }

    // Method specific to Books
    public void authorDetails() {
        System.out.println("Author: J.K. Rowling");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create objects of each subclass
        Electronics laptop = new Electronics("Laptop", 1200.00);
        Clothing tShirt = new Clothing("T-Shirt", 25.00);
        Books book = new Books("Harry Potter", 19.99);

        // Simulating online shopping by displaying product information and specific details

        System.out.println("Electronics Product Details:");
        laptop.displayDetails();  // General product info
        laptop.warrantyDetails(); // Electronics-specific info
        System.out.println();

        System.out.println("Clothing Product Details:");
        tShirt.displayDetails();  // General product info
        tShirt.sizeChart();       // Clothing-specific info
        System.out.println();

        System.out.println("Books Product Details:");
        book.displayDetails();    // General product info
        book.authorDetails();     // Book-specific info
    }
}

question 15

// Student class with attributes and method to determine grade
class Student {
    // Attributes of the student
    private String name;
    private int marks;
    private char grade;

    // Constructor to initialize the student's name and marks
    public Student(String name, int marks) {
        this.name = name;
        this.marks = marks;
        this.grade = ' '; // Default grade is empty, will be assigned later
    }

    // Method to determine the grade based on marks
    public void determineGrade() {
        if (marks >= 90 && marks <= 100) {
            grade = 'A';
        } else if (marks >= 75 && marks < 90) {
            grade = 'B';
        } else if (marks >= 50 && marks < 75) {
            grade = 'C';
        } else {
            grade = 'F';
        }
    }

    // Method to display the student's details (name, marks, and grade)
    public void displayStudentDetails() {
        System.out.println("Student Name: " + name);
        System.out.println("Marks: " + marks);
        System.out.println("Grade: " + grade);
    }
}

// Main class to demonstrate the program
public class StudentGrade {
    public static void main(String[] args) {
        // Creating Student objects with different marks
        Student student1 = new Student("Alice", 92);
        Student student2 = new Student("Bob", 85);
        Student student3 = new Student("Charlie", 65);
        Student student4 = new Student("David", 45);

        // Determine grades for each student
        student1.determineGrade();
        student2.determineGrade();
        student3.determineGrade();
        student4.determineGrade();

        // Display details of each student
        student1.displayStudentDetails();
        student2.displayStudentDetails();
        student3.displayStudentDetails();
        student4.displayStudentDetails();
    }
}
 question 13
 // Employee class with constructor, getters, and setters
class Employee {
    // Attributes of the class
    private String name;
    private int employeeID;
    private double salary;

    // Constructor to initialize employee's details
    public Employee(String name, int employeeID, double salary) {
        this.name = name;
        this.employeeID = employeeID;
        this.salary = salary;
    }

    // Getter method for name
    public String getName() {
        return name;
    }

    // Setter method for name
    public void setName(String name) {
        this.name = name;
    }

    // Getter method for employeeID
    public int getEmployeeID() {
        return employeeID;
    }

    // Setter method for employeeID
    public void setEmployeeID(int employeeID) {
        this.employeeID = employeeID;
    }

    // Getter method for salary
    public double getSalary() {
        return salary;
    }

    // Setter method for salary
    public void setSalary(double salary) {
        this.salary = salary;
    }

    // Method to display employee's details
    public void displayDetails() {
        System.out.println("Employee Details:");
        System.out.println("Name: " + name);
        System.out.println("Employee ID: " + employeeID);
        System.out.println("Salary: " + salary);
    }
}

// Main class to create and test Employee objects
public class Main {
    public static void main(String[] args) {
        // Create an object of Employee class and pass details via the constructor
        Employee employee1 = new Employee("John Doe", 12345, 55000.50);

        // Display employee details
        employee1.displayDetails();

        // Modify employee details using setters
        employee1.setName("Jane Smith");
        employee1.setEmployeeID(67890);
        employee1.setSalary(60000.75);

        // Display updated employee details
        System.out.println("\nUpdated Employee Details:");
        employee1.displayDetails();
    }
}
 question 13
 // Employee class with constructor
class Employee {
    // Attributes of the class
    private String name;
    private int employeeID;
    private double salary;

    // Constructor to initialize employee's details
    public Employee(String name, int employeeID, double salary) {
        this.name = name;
        this.employeeID = employeeID;
        this.salary = salary;
    }

    // Getter method for name
    public String getName() {
        return name;
    }

    // Getter method for employeeID
    public int getEmployeeID() {
        return employeeID;
    }

    // Getter method for salary
    public double getSalary() {
        return salary;
    }

    // Method to display employee's details
    public void displayDetails() {
        System.out.println("Employee Details:");
        System.out.println("Name: " + name);
        System.out.println("Employee ID: " + employeeID);
        System.out.println("Salary: " + salary);
    }
}

// Main class to create and test Employee objects
public class Main {
    public static void main(String[] args) {
        // Create an object of Employee class and pass details via the constructor
        Employee employee1 = new Employee("John Doe", 12345, 55000.50);

        // Display employee details
        employee1.displayDetails();
    }
}
question 11
// Appliance class
class Appliance {
    // Attributes of the class
    String name;
    int powerUsage;

    // Constructor to initialize the appliance's name and power usage
    public Appliance(String name, int powerUsage) {
        this.name = name;
        this.powerUsage = powerUsage;
    }

    // Method to check power efficiency
    public String checkPowerEfficiency() {
        if (powerUsage <= 100) {
            return "Efficient";
        } else {
            return "Inefficient";
        }
    }

    // Method to display appliance details and efficiency status
    public void displayDetails() {
        System.out.println("Appliance Name: " + name);
        System.out.println("Power Usage: " + powerUsage + " watts");
        System.out.println("Efficiency Status: " + checkPowerEfficiency());
    }
}

// Main class to create and test Appliance objects
public class Main {
    public static void main(String[] args) {
        // Create an object of Appliance class and pass details via the constructor
        Appliance appliance1 = new Appliance("Air Conditioner", 150);

        // Display appliance details and its efficiency status
        appliance1.displayDetails();

        // Create another object with efficient power usage
        Appliance appliance2 = new Appliance("LED Bulb", 30);

        // Display appliance details and its efficiency status
        appliance2.displayDetails();
    }
}
question 6
// Library class
class Library {
    // Attributes of the class
    String name;
    String location;
    int numberOfBooks;

    // Constructor to initialize the library's name, location, and number of books
    public Library(String name, String location) {
        this.name = name;
        this.location = location;
        this.numberOfBooks = 0; // Initially, no books are added
    }

    // Method to add books to the library
    public void addBook(int numBooks) {
        this.numberOfBooks += numBooks;
        System.out.println(numBooks + " book(s) added to the library.");
    }

    // Method to display library information
    public void displayLibraryInfo() {
        System.out.println("Library Name: " + name);
        System.out.println("Location: " + location);
        System.out.println("Number of Books: " + numberOfBooks);
    }
}

// Main class to create and test Library objects
public class Main {
    public static void main(String[] args) {
        // Create an object of Library class and initialize with name and location
        Library library = new Library("City Central Library", "Downtown");

        // Display library information before adding books
        library.displayLibraryInfo();

        // Add books to the library
        library.addBook(50);  // Adding 50 books
        library.addBook(30);  // Adding 30 more books

        // Display library information after adding books
        library.displayLibraryInfo();
    }
}

 QUESTION FILE HANDLING 
 import java.io.*;

public class EmployeeFileReader {
    
    public static void main(String[] args) {
        // File path where employee data is stored
        String filePath = "employee_details.txt";
        
        // Read the employee details from the file
        readEmployeeDetails(filePath);
    }

    // Method to read employee details from the file and display them
    public static void readEmployeeDetails(String filePath) {
        // Create a BufferedReader to read the file
        BufferedReader reader = null;

        try {
            // Create a BufferedReader to read the file line by line
            reader = new BufferedReader(new FileReader(filePath));

            String line;
            // Read the file line by line
            while ((line = reader.readLine()) != null) {
                // Split the line into name, employeeID, and salary
                String[] employeeData = line.split(",");
                
                // Display the employee details
                System.out.println("Name: " + employeeData[0]);
                System.out.println("Employee ID: " + employeeData[1]);
                System.out.println("Salary: " + employeeData[2]);
                System.out.println("----------------------------");
            }
        } catch (FileNotFoundException e) {
            // Handle case where file is not found
            System.out.println("Error: The file could not be found.");
        } catch (IOException e) {
            // Handle any other I/O errors
            System.out.println("Error: An I/O error occurred.");
        } finally {
            // Close the BufferedReader in the finally block to ensure it is closed
            try {
                if (reader != null) {
                    reader.close();
                }
            } catch (IOException e) {
                System.out.println("Error: Failed to close the file.");
            }
        }
    }
}


