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