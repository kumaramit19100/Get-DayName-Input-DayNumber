using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace DayNameFromDayNumberInput
{
    class Program
    {
        static void Main(string[] args)
        {
            DateTime mydate = DateTime.Now;
            var FirstDate = new DateTime(mydate.Year, mydate.Month, 1);
            Console.WriteLine("Enter Day Name wit Prefix : 1st, 2nd, 3rd, 4th, 4th");
            string[] DayName = Console.ReadLine().Split(' ');
            int i = 0;
            for (i = 0; i < 7; i++)
            {
                if (FirstDate.AddDays(i).DayOfWeek.ToString() == DayName[1])
                    break;
            }

            int Number = (int)char.GetNumericValue( DayName[0].ToCharArray()[0]);
            DateTime name = new DateTime(FirstDate.Year,FirstDate.Month,(i+1)+(7*(Number-1)));
            Console.WriteLine(name.ToString("dddd dd/MM/yyyy"));
            Console.ReadLine();
        }
    }
}
