**Factory Method** is a [[Creational Design Pattern]] that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.![[factory-method-img.png]]
``` C#
using System;

// Abstract Product
abstract class Vehicle
{
    public abstract void Drive();
}

// Concrete Products
class Car : Vehicle
{
    public override void Drive()
    {
        Console.WriteLine("Driving a Car");
    }
}

class Truck : Vehicle
{
    public override void Drive()
    {
        Console.WriteLine("Driving a Truck");
    }
}

// Abstract Creator
abstract class VehicleFactory
{
    public abstract Vehicle CreateVehicle();
}

// Concrete Creators
class CarFactory : VehicleFactory
{
    public override Vehicle CreateVehicle()
    {
        return new Car();
    }
}

class TruckFactory : VehicleFactory
{
    public override Vehicle CreateVehicle()
    {
        return new Truck();
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Client code
        VehicleFactory carFactory = new CarFactory();
        Vehicle car = carFactory.CreateVehicle();
        car.Drive(); // Output: Driving a Car

        VehicleFactory truckFactory = new TruckFactory();
        Vehicle truck = truckFactory.CreateVehicle();
        truck.Drive(); // Output: Driving a Truck
    }
}

```

- `Vehicle` is an abstract class representing a product (in this case, different types of vehicles).
- `Car` and `Truck` are concrete implementations of the `Vehicle` abstract class.
- `VehicleFactory` is an abstract class representing a factory for creating vehicles.
- `CarFactory` and `TruckFactory` are concrete implementations of the `VehicleFactory` abstract class, each responsible for creating a specific type of vehicle.
- The `Main` method demonstrates how clients can use the factory method to create objects without knowing their concrete types. They interact with the factory through the abstract `VehicleFactory` interface.

>_there are several sides here
>first one is: 