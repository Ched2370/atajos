
using System;

namespace examen
{
    class Examen
    {
        static void BuscarCliente(int anc, int[] codCliente, int[] tArticulos)
        {
            int i, codigo, flag, cantidad;
            char op;
            string linea;

            Console.WriteLine("Codigo de busqueda");
            codigo = int.Parse(Console.ReadLine());

            while (codigo != 0)
            {
                flag = 0;
                i = 0;

                while (flag == 0 && i < anc)
                {
                    if (codigo == codCliente[i])
                    {
                        flag = 1;
                    }
                    else
                    {
                        i++;
                    }
                }

                if (flag == 0)
                {
                    Console.WriteLine("Codigo inexistente.");
                }
                else
                {
                    Console.WriteLine("Ingrese la operacion a realizar. ('e' para actualizar cantidad de ventas.)");
                    linea = Console.ReadLine();
                    op = char.Parse(linea);

                    Console.WriteLine("Ingrese cantidad de articulos a actualizar.");
                    cantidad = int.Parse(Console.ReadLine());

                    if (op == 'e' || op == 'E')
                    {
                        
                        tArticulos[i] += cantidad;
                        Console.WriteLine("Cliente {0}, actualizado con exito.", codCliente[i]);
                        
                    }
                    else
                    {
                        Console.WriteLine("opcion inexistente.");
                    }
                }

                Console.WriteLine("Codigo de busqueda");
                codigo = int.Parse(Console.ReadLine());
            }
        }

        static void OrdenarCLiente(int ancho, int[] codCliente, double[] tVentas, int[] tArticulos)
        {
            int k = 0;
            int x = ancho;
            int aux;
            double auxD;

            while (k == 0)
            {
                k = 1;
                x--;
                for (int i = 0; i < x; i++)
                {
                    if (codCliente[i] > codCliente[i + 1])
                    {
                        k = 0;

                        aux = codCliente[i];
                        codCliente[i] = codCliente[i + 1];
                        codCliente[i + 1] = aux;

                        auxD = tVentas[i];
                        tVentas[i] = tVentas[i + 1];
                        tVentas[i + 1] = auxD;

                        aux = tArticulos[i];
                        tArticulos[i] = tArticulos[i+1];
                        tArticulos[i] = aux;
                    }
                }
            }
        }

        static void Main(string[] args)
        {
            int ancho = 3;
            int[] codCliente = new int[ancho];
            double[] tVentas = new double[ancho];
            int[] tArticulos = new int[ancho];
            int[] cliMas500Art = new int[ancho];

            Console.WriteLine("\u001b[32m***************************************");
            for (int i = 0; i < ancho; i++)
            {
                Console.WriteLine("---------------------------------------");
                Console.WriteLine("Ingrese el codigo del cliente.");
                codCliente[i] = int.Parse(Console.ReadLine());

                Console.WriteLine("Ingrese el total de ventas durante el mes.");
                tVentas[i] = double.Parse(Console.ReadLine());

                Console.WriteLine("Ingresa la cantidad de articulos comprados durante el mes.");
                tArticulos[i] = int.Parse(Console.ReadLine());
                Console.WriteLine("---------------------------------------");
            }
            Console.WriteLine("***************************************\u001b[0m");
            Console.WriteLine("\u001b[33m***************************************");
            BuscarCliente(ancho, codCliente, tArticulos);
            Console.WriteLine("***************************************\u001b[0m");
            for (int i = 0; i < ancho; i++)
            {
                if (tArticulos[i] > 500) //ver
                {
                    cliMas500Art[i] = codCliente[i];
                }
            }

            Console.WriteLine("\u001b[34m***************************************");
            Console.WriteLine("Clientes con mas de 500 articulos comprados:");
            for (int i = 0; i < ancho; i++)
            {
                if (cliMas500Art[i] > 0)
                {
                    Console.WriteLine("Cliente: {0}", cliMas500Art[i]);
                }
            }
            Console.WriteLine("***************************************\u001b[0m");

            OrdenarCLiente(ancho, codCliente, tVentas, tArticulos);

            Console.WriteLine("\u001b[35m***************************************");
            Console.WriteLine("Mostramos vectores: ");
            for(int i = 0; i < ancho; i++)
            {
                Console.WriteLine("----------------------------------------");
                Console.WriteLine("Cliente:___________________{0}", codCliente[i]);
                Console.WriteLine("Total Ventas mensuales:___${0:F2}", tVentas[i]);
                Console.WriteLine("Total Articulos comprados:_{0}", tArticulos[i]);
                Console.WriteLine("----------------------------------------");
            }
            Console.WriteLine("***************************************\u001b[0m");

            Console.WriteLine("\u001b[36mFELICES FIESTAS PROFE, NOS VEMOS EN INGENIERIA!!!\u001b[0m");
        }
    }
}
