static void ordenarDatos(){
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
}

static void buscarDatos(){
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

    Console.WriteLine("Codigo de busqueda");
    codigo = int.Parse(Console.ReadLine());
  }
}

static void maxmin(){
  int i = 0;
  int flag = 0;
  int winner = -1, numWin = -1;
  int loser = -1, numLose = -1;

  while (i < ancho)
  {
    if (flag == 0)
    {
    winner = tTotal[i];
    numWin = atleta[i];
    loser = tTotal[i];
    numLose = atleta[i];
    flag = 1;
    }
    else
    {
      if (winner > tTotal[i])
      {
        winner = tTotal[i];
        numWin = atleta[i];
      }
      
      if (loser < tTotal[i])
      {
        loser = tTotal[i];
        numLose = atleta[i];
      }
    }
    i++;
  }
}

r3vtosRJR5gtrU82zVLU%haYG2VPQ3@#Rg4P$$$k