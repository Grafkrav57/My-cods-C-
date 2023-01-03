# My-cods-C-
practical work
Полиморфизм
namespace KravVas1
{
    class Program
    {
        static void Main(string[] args)
        {
            int n = 0;
            int a = 0;
            string fio = ("Работу выполнили студенты группы ИСИП 3-21 Кравченко Д. Васильева В.");
            string hash = ("##################################################################################");
            Console.WriteLine(fio);
            Console.WriteLine(hash);
            Console.WriteLine("Практическая работа №7, задание 1");
            Console.WriteLine(hash);
            NazemniTrasport date = new NazemniTrasport();
            VozdushTrasport doke = new VozdushTrasport();
            Console.Write("Введите количество данных которые вы хотите вывести: ");
            n = Convert.ToInt32(Console.ReadLine());
            Console.Write("Машину или самолет: ");
            a = Convert.ToInt32(Console.ReadLine());
            for (int i = 0; i < n; i++)
            {
                if (a == 1)
                { date.Conclusion(); }
                else if (a == 2)
                { doke.Conclusion(); }
            }
            

        }



    }
}
КЛАСС
using System;
using System.Xml.Linq;


namespace KravVas1
{


    internal class Transport
    {
        public string object1, object2, object3, object4, object5, object11, object12, object13, object14, object15, object7, object6, object8, object9;
        public string[] array1 = { "Toyota", "Mercedes-Benz", "LADA", "Shkoda", "Hundai", "Smartavia", "Boing", "Победа", "Аэрофлот", "S7" };
        public string[] array2 = { "125", "135", "140", "120", "200", "АН-22", "Мрия", "Акула", "Миг-35", "F-16" };
        public string[] array3 = { "Япония", "Германия", "Россия", "Чехия", "Южная Корея", "Беларусь", "Украина", "Франция", "Россия", "США", };
        public string[] array4 = { "2005", "2010", "2012", "2013", "2015", "400км/ч", "380км/ч", "395км/ч", "500км/ч", "600км/ч" };
        public string[] array5 = { "Красный", "Зеленый", "Синий", "Белый", "Черный", "Бежевый", "Желтый", "Бордовый", "Голубой", "Серый" };
        public string[] array6 = { "4", "8", "6", "10", "3" };
        public string[] array7 = { "Праворульная", "Леворульная" };
        public string[] array8 = { "2", "4", "6", "5", "3" };
        public string[] array9 = { "10m", "12m", "16m" };
        string hash = ("##################################################################################");

        public virtual void Conclusion()
        {
            Random rnd = new Random();
            Console.WriteLine(hash);           
            Console.WriteLine(hash);
            object7 = array7[rnd.Next(0, array7.Length)];
            object6 = array6[rnd.Next(0, array6.Length)];
            object8 = array8[rnd.Next(0, array8.Length)];
            object9 = array9[rnd.Next(0, array9.Length)];
            object1 = array1[rnd.Next(0,5)];
            object2 = array2[rnd.Next(0,5)];
            object3 = array3[rnd.Next(0,5)];
            object4 = array4[rnd.Next(0,5)];
            object5 = array5[rnd.Next(0,5)];                        
            object11 = array1[rnd.Next(5, array1.Length)];
            object12 = array2[rnd.Next(5, array2.Length)];
            object13 = array3[rnd.Next(5, array3.Length)];
            object14 = array4[rnd.Next(5, array4.Length)];
            object15 = array5[rnd.Next(5, array5.Length)];
            
            Console.WriteLine($"Название: {object11}\nСкорость: {object12}\nСтрана производитель: {object13}\nГод выпуска: {object14}\nЦвет: {object15} ");                                              
            
        }
        internal class NazemniTrasport : Transport
        {
            Random rnd = new Random();           
            public override void Conclusion()
            {
                base.Conclusion();
                
                
                    Console.WriteLine($"Количество колес: {object6}");
                    Console.WriteLine($"Располoжение руля: {object7}");
                    Console.WriteLine(hash);
                
            }
        }
        internal class VozdushTrasport : Transport
        {
            Random rnd = new Random();            
            public override void Conclusion()
            {
                base.Conclusion();
               
                
                    Console.WriteLine($"Количество двигателей: {object8}");
                    Console.WriteLine($"Длина крыльев: {object9}");
                    Console.WriteLine(hash);
                
            }
        }
    }
}
