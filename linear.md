            int i, codigo, flag, cantidad;
            char op;
            int anc = 5;
           
            Console.WriteLine("Codigo de busqueda");
            codigo = int.Parse(Console.ReadLine());

            while (codigo != 0)
            {
                flag = 0;
                i = 0;

                while (flag == 0 && i < anc)
                {
                    if (codigo == vector1[i])
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
                }else
                {
                    Console.WriteLine("Ingrese la operacion a realizar.");
                    op = char.Parse(Console.ReadLine());
                    Console.WriteLine("Ingrese cantidad.");
                    cantidad = int.Parse(Console.ReadLine());

                    if (op == 'e' || op == 'E')
                    {
                        if (vector2[i] >= cantidad)
                        {
                            vector2[i] = cantidad;
                        }else
                        {
                            Console.WriteLine("Stock insuficiente.");
                        }
                    }
                }

                Console.WriteLine("COdigo de busqueda");
                codigo = int.Parse(Console.ReadLine());
            }