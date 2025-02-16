using System;

public class Product
{
    public string Name { get; set; }
    public decimal Price { get; set; }
    
    public Product(string name, decimal price)
    {
        Name = name;
        Price = price;
    }

    public override string ToString()
    {
        return $"{Name}: ${Price}";
    }
}

class Program
{
    static void Main()
    {
        Product product1 = new Product("Laptop", 1200.99m);
        Console.WriteLine(product1.ToString()); // Outputs: Laptop: $1200.99
    }
}
public class DiscountedProduct : Product
{
    public decimal DiscountPercentage { get; set; }

    public DiscountedProduct(string name, decimal price, decimal discount) : base(name, price)
    {
        DiscountPercentage = discount;
    }

    public decimal GetDiscountPrice()
    {
        return Price - (Price * DiscountPercentage / 100);
    }

    public override string ToString()
    {
        return $"{Name}: Original Price: ${Price}, Discounted Price: ${GetDiscountPrice()}";
    }
}
