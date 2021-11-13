# calculo-de-matriz
#include <conio.h>
#include <stdio.h>
#include <cstdlib>

main()
{

   int h,n;
   int sum_par,sum_imp,tot,sum_tot; 
    sum_imp=0; 
    sum_par=0; 
    sum_tot=0;
   int a,b,c,d,i,j,k;
   float matriz1[10][10],matriz2[10][10],multi[10][10];
   int opc,resp;
   int lista[n];
   do{
   
   printf("\t\t\t ***MENU***");
   printf("\n\n\tELIJA UNA OPCION\n");
   printf("\t1.- ARREGLO\n");
   printf("\t2.- MULTIPLICACION DE DOS MATRICES\n");
   scanf("%d",&opc);
   system ("cls");
   switch(opc)
   {   
       case 1:
       sum_par=0;
      sum_imp=0;
      sum_tot=0;
         printf("Dame el tamano del arreglo :");
         scanf("%d",&n);
         lista[n];
          for(h=0; h<n; h++)
          {
             printf("Dame el elemento %d: ",h);
             scanf("%d",&lista[h]);
         }
          printf("\nElementos de la lista: ");
           for(h=0; h<n; h++)
              printf("%d ",lista[h]);
            for(h=0; h<n; h++)
                 if(lista[h] %2 ==0)
                  sum_par+=lista[h];      
               else
                  sum_imp+=lista[h];
             for(h=0; h<n; h++)
               sum_tot+=lista[h];
              printf("\n\nLa suma de los numeros pares es: %d ",sum_par);
              printf("\nLa suma de los numeros impares es: %d  ",sum_imp);
               printf("\nLa suma total de los numeros es: %d  ",sum_tot);
       break;
       case 2:
          printf("\nINGRESE LA FILA DE LA PRIMERA MATRIZ\n");
         scanf("%d",&a);
         printf("\nINGRESE LA COLUMNA DE LA PRIMERA MATRIZ\n");
         scanf("%d",&b);
         printf("\nINGRESE LA FILA DE LA SEGUNDA MATRIZ\n");
         scanf("%d",&c);
         printf("\nINGRESE LA COLUMNA DE LA SEGUNDA MATRIZ\n");
         scanf("%d",&d);
            if (b==c)
            {
               printf("\n---------------------------------------------------\n");
               printf("INGRESE EL VALOR DE LA PRIMERA MATRIZ\n\n");
               //INGRESE LAS MATRICES
                  for (i=1;i<=a;i++)
                      for (j=1;j<=b;j++)
                     { printf("A(%d,%d)= ",i,j);
                        scanf ("%f",&matriz1[i][j]);
                     }
               printf("\n---------------------------------------------------\n");
               printf("\nINGRESE EL VALOR DE LA SEGUNDA MATRIZ\n\n");
                  for (i=1;i<=c;i++)
                     for (j=1;j<=d;j++)
                      { printf("B(%d,%d)= ",i,j);
                        scanf ("%f",&matriz2[i][j]);
                      }
               //OPERACION DE MULTIPLICACION
                for (i=1;i<=a;i++)
                   {for (j=1;j<=d;j++)
                         { multi[i][j]=0;
                     for (k=1;k<=b;k++)
                         {multi[i][j]=multi[i][j]+matriz1[i][k]*matriz2[k][j];
                         }
                         }
                   }
             printf("\nLA MULTIPLICACION DE LAS MATRICES ES:\n\n");
            //IMPRESION
                    for (i=1;i<=a;i++)
                        for (j=1;j<=d;j++)
                         { printf("C(%d,%d)=\t%4.2f\n",i,j,multi[i][j]);
                        }
         }
         else
         {
            printf("Estas matrices no se pueden multiplicar \n");
            printf("debido a que el numero de columnas de la\n");
            printf("matriz A es diferente al numero de filas\n");
            printf("de la matriz B, !Vuelva a intentarlo!   \n");
         }
      break;   
}      printf ("\n\nDESEA VOLVER A REPETIR EL PROGRAMA 1.- SI    2.- NO: ");
      scanf("%d",&resp);
      system ("cls");
}while(resp==1);
return 0;
}
