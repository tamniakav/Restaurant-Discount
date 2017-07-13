# Restaurant-Discount
Just another repository
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Restaurant_Discount
{
    class Program
    {
        static void Main(string[] args)
        {
            int customers = int.Parse(Console.ReadLine());
            string package = Console.ReadLine();

            string hallName = String.Empty;
            int priceForHall = 0;

            if (customers <= 50)
            {
                hallName = "Small Hall";
                priceForHall = 2500;
            }
            else if (customers <= 100)
            {
                hallName = "Terrace";
                priceForHall = 5000;
            }
            else if (customers <= 120)
            {
                hallName = "Great Hall";
                priceForHall = 7500;
            }

            int priceForPackage = 0;
            double percenatage = 0.0;

            if (package == "Normal")
            {
                percenatage = 0.95;
                priceForPackage = 500;
            }
            else if (package == "Gold")
            {
                percenatage = 0.90;
                priceForPackage = 750;
            }
            else if (package == "Platinum")
            {
                percenatage = 0.85;
                priceForPackage = 1000;
            }

            double totalPrice = priceForPackage + priceForHall;
            totalPrice *= percenatage;

            double pricePerPerson = totalPrice / customers;

            if (customers < 121)
            {
                Console.WriteLine($"We can offer you the {hallName}");
                Console.WriteLine($"The price per person is {pricePerPerson:f2}$");
            }
            else
            {
                Console.WriteLine("We do not have an appropriate hall.");
            }
        }
    }
}
