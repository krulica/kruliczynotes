DATY - zaliczeniowy
=============

###daty+funkcje-spacje

```
#include<stdio.h>
#include<stdlib.h>
#include<ctype.h>
#include<string.h>
#include<time.h>
#define MAX 64

char months [12] [MAX]={{"January"},{"February"},{"March"},{"April"},{"May"},{"June"},{"July"},{"August"},{"September"},{"October"},{"November"},{"December"}};

char days [31] [MAX]={{" the first"},{" the second"},{" the third"},{" the fourth"},{" the fifth"},{" the sixth"},{" the seventh"},{" the eighth"},{" the ninth"},{" the tenth"},{" the eleventh"},{" the twelfth"},{" the thirteenth"},{" the fourteenth"},{" the fifteenth"},{" the sixteenth"},{" the seventeenth"},{" the eighteenth"},{" the nineteenth"},{" the twentieth"},{" the twenty-first"},{" the twenty-second"},{" the twenty-third"},{" the twenty-fourth"},{" the twenty-fifth"},{" the twenty-sixth"},{" the twenty-seventh"},{" the twenty-eighth"},{" the twenty-ninth"},{" the thirtieth"},{" the thirty-first"} };

int genMies(){
    int m;
    srand(time(NULL));
    m=rand()%10;
    return m;
}

int genDzien(int m){
    int d;
    if (m==1) (d=rand()%27);
        else if ((m==0)||(m==2)||(m==4)||(m==6)||(m==7)||(m==9)||(m==11)) (d=rand()%30);
            else d=rand()%29;
    return d;
}

int wielokrotneSpacje(char odp[]){
	int i,x;
	
	if (isspace(odp[0])) for(i=0; i<strlen(odp); i++){
		odp[i]=odp[i+1];
	 }
	
		
	for(i=0; i<strlen(odp); i++){
		if (odp[i]==' ' && (odp[i+1]==' ')){
		for(x=i; x<strlen(odp); x++){
			odp[x]=odp[x+1];
			}
		i--;
		}
		
	}
	return 0;
}

int main(){
    int m,d,k,pkt=0;
    char odp[MAX], model[MAX];
    printf("Witaj! Ten program odpyta Cie z dat w jezyku angielskim.\n");

    for (k=1;k<6;k++){
        m=genMies();
        d=genDzien(m);
        strcpy(model, months[m]);
        strcat(model,days[d]);
        printf("Wpisz po angielsku date (miesiac i dzien) dla %d-%d:\n", m+1,d+1);
        gets(odp);
            
	    wielokrotneSpacje(odp);
    
	if (strcmp(model, odp)==0) (pkt=pkt+1), printf("Dobrze!\n");
    else printf("Zle! Prawidlowa odpowiedz to: %s \n", model); 
    }
    printf("Ocena z odpowiedzi:%d", pkt+1);
}
```
