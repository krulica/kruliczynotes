#*22.02.2014*
##*Rozwiązane zadania*

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
int main(){
    int suma=0,kwadrat,liczba=3;
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

###Zadanie 6

```
#include<stdio.h>
int main(){
    int liczba,suma=0,i,wyraz;
    double srednia;
    printf("Podaj dlugosc ciagu\n");
    scanf("%d", &liczba);
    for (i=1; i<=liczba; i++){
        printf("Podaj %d wyraz ciagu\n", i);
        scanf("%d", &wyraz);
        suma=suma+wyraz;
        }
        printf("Suma wyrazow ciagu to:%d\n", suma);
        printf("Srednia arytmetyczna wyrazow ciagu to:%lf", (double)suma/liczba);
    return 0;
}
```

###Zadanie 7

```
#include<stdio.h>
int main(){
    int dzies,szes,i;
    for(i=97; i<=107; i++){
        printf("%c, %d, %x\n", i,i,i);
    }
    for(i=107; i>=97; i--){
        printf("%c, %d, %x\n", i,i,i);
    }
    return 0;
}

```

###Zadanie 8

```
#include<stdio.h>
main(){
    int znak;

    printf("Podaj ciąg znakow:\n");
    while ((znak=getchar())!='x'){
        putchar (znak);
    }
return 0;
}
```

###Zadanie 9

```
#include<stdio.h>
int main(){
    int liczba,mnoznik,i;

    for(liczba=1;liczba<=13;liczba++){
        for (i=1; i<=13; i++){
            printf("%d*%d=%d \n", liczba,i,liczba*i);
        }
    }
return 0;
}
```

###Zadanie 10

```
#include<stdio.h>
#include<math.h>
int main(){
    int a,b,c;
    for(a=3; a<=100; a++){
        for(b=4; b<=100; b++){
            for(c=5; c<=100; c++){
                if (a*a+b*b==c*c &&a>b) printf("%d,%d,%d\n", a,b,c);
            }
        }
    }
return 0;
}
```

###Zadanie 11

```
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
int main(){
    srand(time(NULL));
    int x,y,wynik;
    x=rand()%11;
    y=rand()%11;
    printf("Ile jest %d razy %d? ", x,y);
    scanf("%d", &wynik);
        while(x*y!=wynik){
            printf("Sprobuj jeszcze raz!\n");
            scanf("%d", &wynik);
        }
        printf("Bardzo dobrze!");
return 0;
}
```

##*23.02.2014*


###Zadanie 11b

```
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
int main(){
    srand(time(NULL));
    int x,y,wynik,i,pkt=0;
    for(i=1; i<=10; i++){
        x=rand()%10+1;
        y=rand()%10+1;
        printf("Ile jest %d razy %d? ", x,y);
        scanf("%d", &wynik);
        if(x*y==wynik) pkt++;
    }
    printf("Ocena:%d", pkt/2);
return 0;
}
```

###Zadanie 12

```
#include<stdio.h>
int main(){
    int n,dziel,suma=0;
    printf("Podaj liczbe:\n");
    scanf("%d", &n);
    for(dziel=n-1; dziel>0; dziel--){
        if (n%dziel==0) suma=suma+dziel;
    }
    if(suma==n) printf("Ta liczba jest liczba doskonala!\n");
    else printf("Ta liczba nie jest liczba doskonala!\n");
return 0;
}
```

###Zadanie 12b in progress

```
#include<stdio.h>
int main(){
    int licz,dziel,suma=0;
    for(licz=1; licz<=10000; licz++){
        for(dziel=licz-1; dziel>0; dziel--){
        if (licz%dziel==0) suma=suma+dziel;
        if (suma==licz) printf("%d", licz);
        }
    }
return 0;
}
```

#12.14.2014

###Kula

```
#include<stdio.h>
#include<math.h.>

double pole(double r){
	return((4*M_PI*(r*r)));
	}
	
	int main(){
		double r;
		printf ("Podaj promien kuli:\n");
		scanf ("%lf", &r);
		printf ("Pole kuli o promieniu %lf to: %lf", r, pole(r));
			}

```

###Wart Bezwgledna

```
#include<stdio.h>
#include<math.h.>
#include<limits.h>

unsigned int wartBezwzgledna(int n){
	if (n<0) return (-n);
	else return (n);
	}
	int main(){
		int n;
		printf("Podaj liczbe calkowita:\n");
		scanf("%d", &n);
		n=INT_MIN;
		printf("Watrosc bezwzgledna tej liczby to:%u", wartBezwzgledna(n));
	}
```

###Potega

```
#include<stdio.h>
#include<math.h>

int potega(int a, unsigned int n){
	int i, wynik=1;
	for (i=1.;i<=n; i++){
		(wynik=wynik*a);
	}
	return (wynik);
}
	int main(){
		int a;
		unsigned int n;
		printf("Podaj liczbe:");
		scanf("%d", &a);
		printf("Podaj potege:");
		scanf("%u", &n);
		printf ("%d do potegi %u wynosi %d", a, n, potega(a,n));
	}
```

###Pierwiosnek

```
#include<stdio.h>
#include<math.h>

double pierwiosnek(double a){
	double x=a/3, eps=1e-8;
	do {
	x=((x+a/x)/2);}
	while ((fabs(x-(a/x)))>=eps);	
	return (x);
}
	int main(){
		double a;
		printf("Podaj liczbe:\n");
		scanf("%lf", &a);
		printf("Pierwiastek liczby %lf wynosi %lf", a,pierwiosnek(a));
	}
```

```
#include<stdio.h>
#include<math.h>

double pierwiosnek(double a){
	double x=1, eps=1e-8;
	do {
	x=0.5*(x+a/x);}
	while ((fabs(x-(a/x)))>=eps*x);	
	return (x);
}
	int main(){
		double a;
		printf("Podaj liczbe:\n");
		scanf("%lf", &a);
		printf("Pierwiastek liczby %lf wynosi %lf\n", a,pierwiosnek(a));
		printf("Pierwiastek wg funkcji bibliotecznej %lf\n", sqrt(a));
		printf("Blad wzgledny wynosi %le", (fabs(sqrt(a)-(pierwiosnek(a)))/sqrt(a)));
		
	}
```

```
#include<stdio.h>
#include<math.h>

double pierwiosnek(double a){
	double x=1, eps=1e-8;
	do {
	x=0.5*(x+a/x);}
	while ((fabs(x-(a/x)))>=eps*x);	
	return (x);
}
	int main(){
		double a;
		printf("Podaj liczbe:\n");
		scanf("%lf", &a);
		printf("Pierwiastek liczby %lf wynosi %lf\n", a,pierwiosnek(a));
		printf("Pierwiastek wg funkcji bibliotecznej %lf\n", sqrt(a));
		printf("Blad wzgledny wynosi %le", (fabs(sqrt(a)-(pierwiosnek(a)))/sqrt(a)));
		
	}
```

###Potegowanie

```
#include<stdio.h>
#include<stdio.h>

int potegowanie(int a, int n){
	int p=1, q=a, i;
	for (i=n; i>0; i=i/2){
		if ((i%2)!=0) p=p*q, q=q*q;
		else q=q*q;
	}
	return (p);
	}
int main(){
	int a,n;
	printf("Podaj liczbe:\n");
	scanf("%d", &a);
	printf("Podaj wykladnik:\n");
	scanf("%d", &n);
	printf("%d do potegi %d wynosi %d", a,n,potegowanie(a,n));
		
}	
	
```

### Potegowanie2

```
#include<stdio.h>
#include<stdio.h>

double potegowanie(double a, int n){
	double p=1, q=a;
	int i;
	for (i=n; i!=0; i=i/2){
		if ((i%2)!=0) p=p*q, q=q*q;
		else q=q*q;
	}
	if (n<0) return (1/p);
	else return (p);
	}
int main(){
	double a;
	int n;
	printf("Podaj liczbe:\n");
	scanf("%lf", &a);
	printf("Podaj wykladnik:\n");
	scanf("%d", &n);
	printf("%lf do potegi %d wynosi %lf", a,n,potegowanie(a,n));
		
}	
```
