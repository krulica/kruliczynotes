#22.02.2014
##Rozwiązane zadania

###Dodawanie

```
#include <stdio.h>
    main(){
        int a,b;
        printf("Podaj dwie liczby\n");
        scanf("%d %d",&a, &b);
        printf("%d+%d=%d\n",a,b,a+b);
        printf("%d-%d=%d\n",a,b,a-b);
        printf("%d*%d=%d\n",a,b,a*b);
        printf("%d/%d=%lf\n",a,b,(double)a/b);
        getchar();getchar();
        return 0;
      }
```

###Konwertowanie stopni

```
#include <stdio.h>
  int main(){
  double fahr=0;
  do{
    printf("%3.0lf %7.2lf\n", fahr,(5.0/9)*(fahr-32));
    fahr=fahr+20;
  }
  while(fahr<=300);
return 0;
}
```

###Fibonacci

```
#include<stdio.h>
  int main(){
  int a1=1,a2=1,a3,n=2;
  printf("1,1,");
  do{
    a3=a1+a2;
    printf("%d,",a3);
    a1=a2;
    a2=a3;
    n++;
  }
  while (n<=45);
  return 0;
  }
```

###Trójkąt

```
#include<stdio.h>
#define znak '*'

    main(){
        int lbwier; //liczba
        int lw; //licznik
        int lodst;
        int j;

        printf ("ile wierszy?");
        scanf ("%d", &lbwier);

        for (lw=0; lw<lbwier; lw++){
            lodst=lbwier-lw-1;
                for(j=0; j<lodst; j++) putchar (' ');
                    for(j=0; j<2*lw+1; j++) putchar (znak);
                    putchar('\n');
        }

    }
```

###Zadanie 1

```
//#include<stdio.h>
//int main(){
//  int calk;
//  for (calk=0;calk<=32;calk=calk+1){
//  printf("%d\n",calk);
//  }
// return 0;
//}

//#include<stdio.h>
//int main(){
//  int calk=0;
//  while (calk<=32){
//  printf("%d\n",calk);
//  calk++;
//  }
//return 0;
//}

#include<stdio.h>
int main(){
    int calk=0;
    do{
        printf("%d\n",calk);
        calk++;
    }
    while (calk<=32);
    return 0;
}
```

###Zadanie 2

```
//#include<stdio.h>
//main(){
//  float licz, step=0.5;
//  for (licz=-3.5; licz<=7.5; licz=licz+step){
//  printf ("%f\n",licz);
//  }
//return 0;
//}

#include<stdio.h>
main(){
    float licz=-3.5, step=0.5;
    while (licz<=7.5){
    printf("%f\n",licz);
    licz=licz+step;
    }
return 0;
}
```

###Zadanie 3

```
//#include<stdio.h>
//int main(){
//  int a,licz;
//  printf("Podaj liczbe:\n");
//  scanf("%d", &licz);
//  for(a=1; a<=licz; a++){
//      printf ("%d %d\n",a*a,a*a*a);
//  }
//return 0;
//
//}

//#include<stdio.h>
//int main(){
//  int a=1,licz;
//  printf("podaj liczbe:\n");
//  scanf("%d", &licz);
//  while (a<=licz){
//      printf ("%d %d\n",a*a,a*a*a);
//      a++;
//  }
//return 0;
//}

#include<stdio.h>
int main(){
int a=1,licz;
printf("podaj liczbe:\n");
scanf("%d", &licz);
    do {
        printf ("%d %d\n",a*a,a*a*a);
        a++;
    }
    while (a<=licz);
return 0;
}
```

###Zadanie 4

```
#include<stdio.h>
int suma=0,kwadrat,liczba=3;
int main(){
    //for(liczba=3; liczba<=15; liczba++){
        // kwadrat=liczba*liczba;
        // suma=suma+kwadrat;
    //}

    while (liczba<=15){
        kwadrat=liczba*liczba;
        suma=suma+kwadrat;
        liczba++;
    }

    printf("Suma kwadratow liczb od 3 do 15 to:%d", suma);
    return 0;
}
```

###Zadanie 5
```
#include<stdio.h>
#include<math.h>
int main(){
    int kat,krok=30;
    for(kat=0; kat<=180; kat=kat+krok){
        printf("sinus %d:%lf\n", kat,sin(kat*M_PI/180));
        printf("cosinus %d: %lf\n", kat,cos(kat*M_PI/180));

    }
return 0;
}
```
