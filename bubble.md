            int k = 0;
            int x = 5;
            int aux;

            while (k == 0)
            {
                k = 1;
                x--;
                for (int i = 0; i < x; i++)
                {
                    if (promedio[i] < promedio[i + 1])
                    {
                        k = 0;

                        aux = promedio[i];
                        promedio[i] = promedio[i + 1];
                        promedio[i + 1] = aux;

                        aux = legajo[i];
                        legajo[i] = legajo[i + 1];
                        legajo[i + 1] = aux;
                    }
                }
            }