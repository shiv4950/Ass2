public class DatabaseConnection {
    
    private static DatabaseConnection instance;
    private DatabaseConnection() {    
    }
    public static DatabaseConnection getInstance() {
        
        if (instance == null) {
            synchronized (DatabaseConnection.class) {
                if (instance == null) {
                    instance = new DatabaseConnection();
                }}  }
        return instance;
    }
    public void getConnection() {
        
        System.out.println("Returning database connection.");
    }
public class main{
    public static void main(String[] args){
        DatabaseConnection coonectio=DatabaseConnection.getconnection();
        }
}

q2
vehicle.java
public interface Vehicle {
    void drive();
}

car.java
public class Car implements Vehicle {
    @Override
    public void drive() {
        System.out.println("Driving a car.");
    }
}
public class Bike implements Vehicle {
    @Override
    public void drive() {
        System.out.println("Riding a bike.");
    }}

    VehicleFactory.java
    public class VehicleFactory {
    public Vehicle createVehicle(String type) {
        if (type == null) {
            return null;
        }
        if (type.equalsIgnoreCase("CAR")) {
            return new Car();
        } else if (type.equalsIgnoreCase("BIKE")) {
            return new Bike();
        }
        return null;
    }
}

main.java
public class Main {
    public static void main(String[] args) {
        VehicleFactory vehicleFactory = new VehicleFactory();

        // Create a Car
        Vehicle car = vehicleFactory.createVehicle("CAR");
        car.drive(); // Output: Driving a car.

        // Create a Bike
        Vehicle bike = vehicleFactory.createVehicle("BIKE");
        bike.drive(); // Output: Riding a bike.

        // Attempt to create an unknown vehicle type
        Vehicle unknown = vehicleFactory.createVehicle("TRUCK");
        if (unknown == null) {
            System.out.println("Unknown vehicle type.");
        }
    }
}


q3

Shape.java
public interface Shape {
    Shape clone();
    void draw();
}

Circle.java
public class Circle implements Shape {
    @Override
    public Shape clone() {
        return new Circle(); // Create a new instance of Circle
    }

    @Override
    public void draw() {
        System.out.println("Drawing a Circle.");
    }
}

public class Rectangle implements Shape {
    @Override
    public Shape clone() {
        return new Rectangle(); // Create a new instance of Rectangle
    }

    @Override
    public void draw() {
        System.out.println("Drawing a Rectangle.");
    }
}

Main.java

public class Main {
    public static void main(String[] args) {
        Shape circle = new Circle();
        Shape rectangle = new Rectangle();
        Shape clonedCircle = circle.clone();
        Shape clonedRectangle = rectangle.clone();
        circle.draw(); 
        rectangle.draw(); 
        clonedCircle.draw(); 
        clonedRectangle.draw();
    }
}
