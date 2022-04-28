.net
**  binary traingle**
using System;

namespace ConsoleApp3
{
    class BinaryTriangle
    {
        static void Main(String[] args)
        {
            int number, digit = 1;
            Console.Write("\nEnter The number of lines:");
            number = Convert.ToInt32(Console.ReadLine());
            for(int i=1;i<=number;i++)
            {
                for(int space=number-i;space>0;space--)
                {
                    Console.Write(" ");

                }
                for (int j = 0; j < i; j++)
                {
                    Console.Write(digit+" ");
                    digit = (digit == 1) ? 0 : 1;
                }
                Console.Write("\n");
            }
        }
    }
}
**using System;

namespace ConsoleApp3
{
    class BinaryTriangle
    {
        static void Main(String[] args)
        {
            int number, digit = 1;
            Console.Write("\nEnter The number of lines:");
            number = Convert.ToInt32(Console.ReadLine());
            for(int i=1;i<=number;i++)
            {
                for(int space=number-i;space>0;space--)
                {
                    Console.Write(" ");

                }
                for (int j = 0; j < i; j++)
                {
                    Console.Write(digit+" ");
                    digit = (digit == 1) ? 0 : 1;
                }
                Console.Write("\n");
            }
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165690950-14fc6945-f6e3-465c-9075-f809b17f34df.png)

**  amicable number**
using System;
namespace Exercises
{
    class AmicableNumber
    {
        static void Main(String[] args)
        {
            int num1,num2,sum1=0,sum2=0;
            Console.WriteLine("\n........AMICABLE NUMBERS........\n");
            Console.Write("\nEnter the First Number:");
            num1 = Convert.ToInt32(Console.ReadLine());
            Console.Write("\nEnter the Second Number:");
            num2 = Convert.ToInt32(Console.ReadLine());
            for (int i = 1; i < num1; i++)
            {
                if (num1 % i == 0)
                {
                    sum1 += i;
                }
            }
            for (int i = 1; i < num2; i++)
            {
                if (num2 % i == 0)
                {
                    sum2 += i;
                }
            }
            if(num1 == sum2 && num2 == sum1)
            {
                Console.WriteLine("\nThe numbers {0} and {1} are amicable.", num1, num2);
            }
            else
            {
                Console.WriteLine("\nThe numbers {0} and {1} are not amicable.", num1, num2);
            }
        }
    }
}
<br>
**  output **
![image](https://user-images.githubusercontent.com/104187589/165691337-f26b8273-cab0-4e46-8ca6-37b1406718b9.png)
![image](https://user-images.githubusercontent.com/104187589/165691456-e928d4a3-a34a-4361-b282-7ea08ff30ca5.png)
**  gray code*
using System;
namespace Exercises
{
    class GrayCode
    {
        static int getGray(int n)
        {
            return n ^ (n >> 1);
        }
        static void Main(string[] args)
        {
            int InputNum, GrayNum;
            Console.Write("\n Enter the decimal number:");
            InputNum = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("\n Binary equivalent of{0}:{1}", InputNum, Convert.ToString(InputNum, 2));
            GrayNum = getGray(InputNum);
            Console.WriteLine("\n Gray code equivalent of{0}:{1}", InputNum, Convert.ToString(GrayNum, 2));
        }
    }
}
<br>
**   output**
![image](https://user-images.githubusercontent.com/104187589/165691950-195dfc74-4e02-4c7e-846b-28a6c2ff4209.png)

**  volume of boxes**
using System;
namespace Exercises
{
    class Box
    {
        float width;
        float height;
        float length;
        public float volume
        {
            get { return width * height * length; }
        }
        public Box(float width, float height, float length)
        {
            this.width = width;
            this.height = height;
            this.length = length;
        }
        public static float operator +(Box box1, Box box2)
        {
            return box1.volume + box2.volume;
        }
        public override string ToString()
        {
            return "box with width" + width + ",height" + height + " and length" + length;
        }
    }
    class operatoroverloading
    {
        public static void Main()
        {
            Box box1 = new Box(10, 20, 30);
            Box box2 = new Box(25, 32, 15);
            Console.WriteLine("volume of {0} is:{1}", box1, box1.volume);
            Console.WriteLine("volume of {0} is:{1}", box2, box2.volume);
            Console.WriteLine("volume after adding boxes:{0}", box1 + box2);
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165692202-3ffcb55e-9718-49cf-b9c0-665c91822583.png)

**  delegate**
using System;
namespace Exercises
{
    class Delegates
    {
        delegate String UppercaseDelegate(string input);
        static string UppercaseFirst(string input)
        {
            char[] buffer = input.ToCharArray();
            buffer[0] = char.ToUpper(buffer[0]);
            return new string(buffer);
        }
        static string UppercaseLast(string input)
        {
            char[] buffer = input.ToCharArray();
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);
            return new string(buffer);
        }
        static string UppercaseAll(string input)
        {
            return input.ToUpper();
        }
        static void writeOutput(string input, UppercaseDelegate del)
        {
            Console.WriteLine("Input string:{0}", input);
            Console.WriteLine("Output string:{0}", del(input));
        }
        static void Main()
        {
            writeOutput("tom", new UppercaseDelegate(UppercaseFirst));
            writeOutput("tom", new UppercaseDelegate(UppercaseLast));
            writeOutput("tom", new UppercaseDelegate(UppercaseAll));
            Console.ReadLine();
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165692436-80a93c8c-ac01-4c77-b5b5-e8fb8f2a4877.png)

**  constructor**
using System;
namespace Exercises
{
    class RegisterNum
    {
        int regNo;
        static int startNum;
        static RegisterNum()
        {
            startNum = 20210000;
        }
        RegisterNum()
        {
            regNo = ++startNum;
        }
        public static void Main(string[] args)
        {
            for (int i = 0; i < 100; i++)
            {
                RegisterNum Student = new RegisterNum();
                Console.WriteLine("Student {0}:{1}", i + 1, Student.regNo);
            }
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165692776-77b1e95d-65c3-4492-bc80-b2b9fb0bf9d2.png)
![image](https://user-images.githubusercontent.com/104187589/165692910-2573c48f-110d-4ad8-9501-1de04c111778.png)
![image](https://user-images.githubusercontent.com/104187589/165692978-894e7077-6fcc-402b-af96-2363853f30a9.png)
![image](https://user-images.githubusercontent.com/104187589/165693035-dec8cefd-b5e9-4b9a-9645-7caa340a14ae.png)

**  frequency of the word**
using System;
namespace Exercises
{
    class FrequencyIS
    {
        static void Main(string[] args)
        {
            int count = 0;
            String inputString;
            Console.WriteLine("\n     Frequency of word 'is'   ");
            Console.Write("\n Enter the input string :");
            inputString = Console.ReadLine();
            char[] separator = { ',', ' ', '.', '!', '\n' };
            string testString = inputString.ToLower();
            String[] outcomes = testString.Split(separator);
            foreach (String s in outcomes)
            {
                Console.WriteLine(s);
                if (s == "is")
                    count++;
            }
            Console.WriteLine("\n Number of 'is' in"+ inputString +" is:" +count);
                }
    }
}
 <br>
 **  output**
 ![image](https://user-images.githubusercontent.com/104187589/165693556-d5fa22f5-f4fe-4136-8e8b-c179909bcbde.png)

**  jagged array**
using System;
using System.Diagnostics; 
namespace Exrecises
{
    class BenchmarkAllocation
    {
        const int _max= 100000;
        static void Main(string[] args)
        {
            var Arr2D = new int[100,100];
            var ArrJagged = new int[100][];
            for (int i = 0; i < 100; i++)
            {
                ArrJagged[i] = new int[100];
            }
            var Stopwatch2D = Stopwatch.StartNew();
            for (int i = 0; i < _max; i++)
            {
                for (int j = 0; j < 100; j++)
                {
                    for (int k = 0; k < 100; k++)
                    {
                        Arr2D[j, k] = k;
                    }
                }
            }
            Stopwatch2D.Stop();
            var StopwatchJagged = Stopwatch.StartNew();
            for (int i = 0; i < _max; i++)
            {
                for (int j = 0; j < 100; j++)
                {
                    for (int k = 0; k < 100; k++)
                    {
                        ArrJagged[j][k] = k;
                    }
                }
            }
            StopwatchJagged.Stop();
            Console.Write("\n Time taken for allocation in case of 2D array:");
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "millisecods");
            Console.Write("\n Time taken for allocation in case of Jagged array:");
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165693831-54e825e7-12f5-4267-ba4e-f4b1e60f05d9.png)

**  sum**
using System;
namespace Exercises
{
    class SumOfDiagonals
    {
        static void Main(string[] args)
        {
            int MaxRow, Maxcol, Sum = 0;
            int[,] Matrix;
            Console.WriteLine("\n -----SUM OF DIAGONAL OF A MATRIX ----\n");
            Console.Write("\n Enter the number of rows:");
            MaxRow = Convert.ToInt32(Console.ReadLine());
            Console.Write("\n Enter the number of columns:");
            Maxcol = Convert.ToInt32(Console.ReadLine());
            if (MaxRow != Maxcol)
            {
                Console.WriteLine("\n The Dimensions entered are not of Square Matrix.");
                Console.WriteLine("\n Exiting the program.");
                return;
            }
            Matrix = new int[MaxRow, Maxcol];
            for (int i = 0; i < MaxRow; i++)
            {
                for (int j = 0; j < Maxcol; j++)
                {
                    Console.Write("\n Enter the ({0},{1})th element of the matrix:", (i + 1), (j + 1));
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());
                }
            }
            Console.WriteLine("\n The entered Matrix is:");
            for (int i = 0; i < MaxRow; i++)
            {
                for (int j = 0; j < Maxcol; j++)
                {
                    Console.Write(" " + Matrix[i, j]);
                    if (i == j)
                    {
                        Sum += Matrix[i, j];
                    }
                }
                Console.WriteLine();
            }
            Console.WriteLine("\n The Sum of Diagonal is" + Sum);
        }
        }
        }
        <br>
        **  output**
        ![image](https://user-images.githubusercontent.com/104187589/165694215-c89e9aa8-5aac-4f19-8da4-7153defc0bf6.png)
![image](https://user-images.githubusercontent.com/104187589/165694300-c53fdfce-cac5-4d0a-b023-a5c6ff959d46.png)


**  file read**
using System;
using System.IO;
namespace Exercises
{
    class FileRead
    {
        public static void Main()
        {
            string fileName;
            while (true)
            {
                Console.WriteLine("\n -----MENU-------\n");
                Console.WriteLine("\n 1.Create a file");
                Console.WriteLine("\n 2.Existence of the file");
                Console.WriteLine("\n 3.Read the contents of the file");
                Console.WriteLine("\n 4.Exit");
                Console.Write("\n Enter your choice:");
                int ch = int.Parse(Console.ReadLine());
                switch (ch)
                {
                    case 1:
                        Console.Write("\n Enter the file name to create:");
                        fileName = Console.ReadLine();
                        Console.WriteLine("\n write the Contents to the file:\n");
                        string r = Console.ReadLine();
                        using (StreamWriter fileStr = File.CreateText(fileName))
                        {
                            fileStr.WriteLine(r);
                        }
                        Console.WriteLine("file is Created...");
                        break;
                    case 2:
                        Console.Write("\n Enter the file name:");
                        fileName = Console.ReadLine();
                        if (File.Exists(fileName))
                        {
                            Console.WriteLine("File exists...");

                        }
                        else
                        {
                            Console.WriteLine("File does not exist in the current directory!");
                        }
                        break;
                    case 3:
                        Console.Write("enter the file name to read the contents:\n");
                        fileName = Console.ReadLine();
                        if (File.Exists(fileName))
                        {
                            using (StreamReader sr = File.OpenText(fileName))
                            {
                                string s = " ";
                                Console.WriteLine("Here is the content of the file:");
                                while ((s = sr.ReadLine()) != null)
                                {
                                    Console.WriteLine(s);
                                }
                                Console.WriteLine(" ");
                            }
                        }
                        else
                        {
                            Console.WriteLine("File does not exists");
                        }
                        break;
                    case 4:
                        Console.WriteLine("\n Exiting...");
                        return;
                    default:
                        Console.WriteLine("\n Invalid choice");
                        break;
                }
            }
        }
    }
}

<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165694963-f316a836-7426-43f2-8a31-56ec16979cd0.png)
![image](https://user-images.githubusercontent.com/104187589/165695029-b0097812-ca05-4011-a4b9-9d3d4671be2c.png)
![image](https://user-images.githubusercontent.com/104187589/165695146-06da573f-4f93-44f0-98e5-642ca221a235.png)

**  file comparison**
using System;
using System.IO;
namespace Exercises
{
    class FileRead
    {
        public static void Main()
        {
            string file1;
            string file2;
            Console.Write("Enter the first file path:");
            file1 = Console.ReadLine();
            Console.Write("Enter the second file path:");
            file2 = Console.ReadLine();
            if (!File.Exists(file1))
            {
                Console.WriteLine("First file does not exist!");
            }
            else if (!File.Exists(file2))
            {
                Console.WriteLine("second file does not exist!");
            }
            else if (File.ReadAllText(file1) == File.ReadAllText(file2))
            {
                Console.WriteLine("Both files contain the same content");
            }
            else
            {
                Console.WriteLine("Contents of files are not same");
            }
        }
    }
}
 <br>
 **  output**
![image](https://user-images.githubusercontent.com/104187589/165696144-1b35972b-e3f7-401c-b954-d2a82ae4157d.png)
![image](https://user-images.githubusercontent.com/104187589/165696386-ac79ec35-c693-409f-95ea-b544fedebb43.png)

**  Icomparable**
using System;
namespace Exercises
{
    class Fraction : IComparable
    {
        int z, n;
        public Fraction(int z, int n)
        {
            this.z = z;
            this.n = n;
        }
        public static Fraction operator +(Fraction a, Fraction b)
        {
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);
        }
        public static Fraction operator *(Fraction a, Fraction b)
        {
            return new Fraction(a.z * b.z, a.n * b.n);
        }
        public int CompareTo(object obj)
        {
            Fraction f = (Fraction)obj;
            if ((float)z / n < (float)f.z / f.n)
                return -1;
            else if ((float)z / n > (float)f.z / f.n)
                return 1;
            else
                return 0;
        }
        public override string ToString()
        {
            return z + "/" + n;
        }
    }
    class IcompInterface
    {
        public static void Main()
        {
            Fraction[] a = {
                new Fraction(5, 2),
                new Fraction(29, 6),
                new Fraction(4, 5),
                new Fraction(10, 8),
                new Fraction(34, 7)
            };
            Array.Sort(a);
            Console.WriteLine("Implementing the Icomparable Interface in" + "Displaying Fractions:");
            foreach (Fraction f in a)
            {
                Console.WriteLine(f + " ");
            }
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165696653-443a0a28-9519-4945-aee8-5a64454c21e9.png)

**  thread**
using System;
using System.Threading;
namespace Exercises
{
    class ThreadPoolProg
    {
        public void ThreadFun1(object obj)
        {
            int loop = 0;
            for (loop = 0; loop <= 4; loop++)
            {
                Console.WriteLine("Thread1 is executing");
            }
        }
        public void ThreadFun2(object obj)
        {
            int loop = 0;
            for (loop = 0; loop <= 4; loop++)
            {
                Console.WriteLine("Thread2 is executing");
            }
        }
        public static void Main()
        {
            ThreadPoolProg TP = new ThreadPoolProg();
            for (int i = 0; i < 2; i++)
            {
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));
            }
            Console.ReadKey();
        }
    }
}
<br>
**  output**
![image](https://user-images.githubusercontent.com/104187589/165696967-4538ee8f-4277-4b94-bf53-b08c2385f230.png)


            

 
