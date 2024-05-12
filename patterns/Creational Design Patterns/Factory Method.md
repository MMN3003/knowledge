**Factory Method** is a [[Creational Design Pattern]] that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.![[factory-method-img.png]]
``` C#
using System;

// Product interface
public interface IProduct
{
    void DoStuff();
}

// Concrete Product A
public class ConcreteProductA : IProduct
{
    public void DoStuff()
    {
        Console.WriteLine("Doing stuff in ConcreteProductA");
    }
}

// Concrete Product B
public class ConcreteProductB : IProduct
{
    public void DoStuff()
    {
        Console.WriteLine("Doing stuff in ConcreteProductB");
    }
}

// Creator class
public abstract class Creator
{
    public abstract IProduct CreateProduct();

    public void SomeOperation()
    {
        // Use the created product
        IProduct product = CreateProduct();
        product.DoStuff();
    }
}

// Concrete Creator A
public class ConcreteCreatorA : Creator
{
    public override IProduct CreateProduct()
    {
        return new ConcreteProductA();
    }
}

// Concrete Creator B
public class ConcreteCreatorB : Creator
{
    public override IProduct CreateProduct()
    {
        return new ConcreteProductB();
    }
}

class Program
{
    static void Main(string[] args)
    {
        Creator creatorA = new ConcreteCreatorA();
        Creator creatorB = new ConcreteCreatorB();

        creatorA.SomeOperation();
        creatorB.SomeOperation();
    }
}
```

