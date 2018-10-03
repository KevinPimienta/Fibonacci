# Fibonacci
Tarea 2
class Program

    {   public  int FibonacciFor(int n)
        {
			int Time = 0;
            int Numb = 1;
			for (int i = 0; i<n; i++)
			{
				int temp = Time;
                Time = Numb;
				Numb = temp + Numb;
			}
			return Time;
		}
        public int Fibonachi(int n)
        {
           if(n==0||n==1)
            {
                return 1;
            }
            else
            {
                return Fibonachi(n - 1) + Fibonachi(n - 2);
            }
        }
        static void Main(string[] args)
        {
            Console.ForegroundColor = ConsoleColor.Black;
            Console.BackgroundColor = ConsoleColor.White;
            Console.Clear();
            Program obj = new Program();
            int op = 0;    
            while (op != 3)
            {
                Console.WriteLine("-Interativo ciclo. ");
                Console.WriteLine("-Interativo recursividad. ");
                op = int.Parse(Console.ReadLine());
                Console.Clear();
                switch (op)
                {
                    case 1:
                        TimeSpan stop;
                        TimeSpan start = new TimeSpan(DateTime.Now.Ticks);
                        int ep = 0;
                        Console.WriteLine("Ingrese un número: ");
                        ep = int.Parse(Console.ReadLine());
                        Console.WriteLine();
                        for (int i = 0; i < ep; i++)
                        {
                          Console.WriteLine(obj.FibonacciFor(i));
                        }
                        stop = new TimeSpan(DateTime.Now.Ticks);
                        Console.WriteLine("Segundos de ejecución:" + stop.Subtract(start).TotalSeconds);
                        break;
                    case 2:
                       // TimeSpan Stop;
                        TimeSpan Start = new TimeSpan(DateTime.Now.Ticks);
                        int ap = 0;
                        Console.WriteLine("Ingrese un número: ");
                        ap = int.Parse(Console.ReadLine());
                        Console.WriteLine();
                        Console.Write("El fibonacci de " + ap + " es ");
                        for (int u = 0; u < ap; u++)
                        {
                            Console.WriteLine(obj.Fibonachi(u));
                        }
                        stop = new TimeSpan(DateTime.Now.Ticks);
                        Console.WriteLine("Segundos de ejecución:" + stop.Subtract(Start).TotalSeconds);
                        break;
                }
             }
             Console.ReadKey();
        }
    }
