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

