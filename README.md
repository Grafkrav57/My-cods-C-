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
Консольное окно администратора 11 практическая
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using UserSpace;
using AdminSpace;
using KravVas2;

namespace KravVas2
{


    internal class Program
    {
        static void Main(string[] args)
        {
            string hash = ("##########################################################################");
            Console.WriteLine("Работу выполнили студенты группы ИСиП-3-21 кравченко Д. и Васильева В.");
            Console.WriteLine(hash);
            Console.WriteLine("Практическая работа 11");
            Console.WriteLine(hash);
            User user = new User();
            user.login();

        }
    }
}
ЮЗЕР
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using KravVas2;
using AdminSpace;

namespace UserSpace
{
    
    internal class User
    {
        string hash = ("##########################################################################");
        public string name;
        public string password;
        public string role;
        public static string passwords()
        {
            string password = "";
            while (true)
            {
                var key = Console.ReadKey(true);
                if (key.Key == ConsoleKey.Enter) break;
                Console.Write("*");
                password += key.KeyChar;
            }
            Console.WriteLine("");
            return password;
        }

        public List<User> users = new List<User>();

        public virtual void createUser()
        {
            Console.Write("Введите имя пользователя: ");
            name = Console.ReadLine();
            Console.Write("Введите пароль пользователя: ");
            password = Console.ReadLine();
            Console.Write("Введите роль пользователя(worker, manager, director): ");
            role = Console.ReadLine();
            users.Add(new User { name = name, password = password, role = role });
            Console.WriteLine(hash);
        }
        public void UserInfo()
        {
            Console.WriteLine($"Имя пользователя: {name}");
            Console.WriteLine($"Пароль пользователя: {password}");
            Console.WriteLine($"Роль пользователя: {role}");
        }
        public void login()
        {
            users.Add(new User { name = "Admin", password = "qwerty", role = "Administrator" });
            Console.Write("Введите логин: ");
            name = Console.ReadLine();
            Console.Write("Введите пароль: ");
            password = passwords();
            Console.WriteLine(hash);
            if (users.Exists(u => u.name == name && u.password == password && u.role == "Administrator" ))
            {
                Console.WriteLine("Вы вошли как администратор");
                Console.WriteLine(hash);
                Admin admin = new Admin();
                Console.WriteLine("Добро пожаловать в режим администратора.");
                Console.WriteLine(hash);
                admin.menu();

            }

        }
    }
}
АДМИН
using KravVas2;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using UserSpace;

namespace AdminSpace
{
    internal class Admin : User
    {
        string hash = ("##########################################################################");
        public static int check()
        {
            string word = Console.ReadLine();
            while (!int.TryParse(word, out int number))
            {
                Console.WriteLine("Это не число, попробуйте еще раз.");
                Console.Write("Повторите ещё раз: ");
                word = Console.ReadLine();
            }
            return Convert.ToInt32(word);
        }
        
        public void menu()
        {
            Console.WriteLine("Выберите что хотите сделать: ");
            Console.WriteLine("1) Создать пользователя\n2) Редактировать пользователя\n3) Посмотреть данные о пользователях\n4) Удалить пользователя");
            Console.WriteLine(hash);
            Console.Write("Ваш выбор: ");
            int choice = check();
            Console.WriteLine(hash);
            switch (choice)
            {
                case 1:                   
                    createUser();
                    break;
                case 2:
                    editUser();
                    break;
                case 3:
                    seeUser();
                    break;
                case 4:
                    deleteUser();
                    break;
                default:
                    break;
            }
        }
        public override void createUser()
        {
            Console.Write("Сколько пользователей вы хотите создать?: ");
            int n = check();
            Console.WriteLine(hash);
            for (int i = 0; i < n; i++)
            {
                base.createUser();
                Console.WriteLine("Пользователь был успешно добавлен!");
                Console.WriteLine(hash);
            }
            menu();
        }
        public void editUser()
        {
            Console.Write("Введите имя пользователя, которого нужно изменить: ");
            string who = Console.ReadLine();
            Console.WriteLine("Что нужно изменить?\n1) Имя пользователя\n2) Пароль");
            Console.WriteLine(hash);
            Console.Write("Ваш выбор: ");
            int n = check();
            Console.WriteLine(hash);
            if (n == 1)
            {
                Console.Write("Введите новое имя пользователя: ");
                name = Console.ReadLine();
                int m = Convert.ToInt32(users.FindIndex(x => x.name.Contains(who)));
                users[m].name = name;
                Console.WriteLine(hash);
                Console.WriteLine("Имя успешно изменено: ");
                Console.WriteLine(hash);
            }
            if (n == 2)
            {
                Console.Write("Введите новый пароль пользователя: ");
                password = Console.ReadLine();
                int m = Convert.ToInt32(users.FindIndex(x => x.name.Contains(who)));
                users[m].password = password;
                Console.WriteLine(hash);
                Console.WriteLine("пароль успешно сменен: ");
                Console.WriteLine(hash);
            }
            menu();
        }
        public void seeUser()
        {
            for (int i = 0; i < users.Count; i++)
            {
                if (users.Count > 0)
                {
                    Console.WriteLine($"Пользователь №{i + 1}.");
                    Console.WriteLine($"Имя пользователя: {users[i].name} ");
                    Console.WriteLine($"Пароль пользователя: {users[i].password}");
                    Console.WriteLine($"Роль пользователя: {users[i].role}");
                    Console.WriteLine(hash);
                }
                else
                {
                    Console.WriteLine("Вы еще не добавили пользователей!");
                    Console.WriteLine(hash);
                }
            }
            menu();
        }
        public void deleteUser()
        {
            Console.Write("Введите имя пользователя, которого нужно удалить: ");
            string who = Console.ReadLine();
            users.Remove(users.Find(x => x.name.Contains(who)));
            Console.WriteLine(hash);
            Console.WriteLine("Пользователь успешно удалён!");
            Console.WriteLine(hash);
            menu();
        }
    }
}
