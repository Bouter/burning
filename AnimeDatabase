#define _CRT_SECURE_NO_WARNINGS
//#define NULL 0
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>

void anime_zoeken();
void anime_lijst_bekijken();
void anime_toevoegen();
void anime_verwijderen();
void keuze(int keuze);
void errorhandling(int keus);
void streaming();
int main()
{
  
	int keuze;
	int i;
//	int j;
	printf("%s","\t\t  *");
	for(i=0;i<24;i++){
		printf("%s","*");
	}
	printf("\n");
	
	printf("%s","\t\t * 1. Anime toevoegen.     *\n");
	
	printf("%s","\t\t * 2. Anime lijst bekijken.*\n");
	printf("%s","\t\t * 3. Anime zoeken.        *\n");
	
	printf("%s","\t\t * 4. Exit.                *\n");
	printf("%s","\t\t  *");
	for(i=0;i<24;i++){
		printf("%s","*");
	}
	
	scanf("%d",&keuze);
	_flushall();
	errorhandling(keuze);
	

return 0;
}



void anime_zoeken()
{
	FILE  *anime =fopen("anime1.txt","r");
	char naam[20];
	char naam1 =' ';
	int i=0;
	int u=0;
	int j=0;
	char d=0;
	char c;
	char e;
	char r;
	char hoofdmenu = ' ';
	int y = 0;
	char te_zoeken_naam[20];
	unsigned int m;
	char te_zoekn_naam[20];
	int z;
	char naam2[20];
	system("CLS");
	
	printf("%s","Geef de naam van de anime die je zoekt:");
	naam1 = getchar();
	//printf("%i",(int)naam1);
	while(naam1 != '\n')
	{
		naam[u]=naam1;
		u++;
		//printf("%i",(int)naam1);
		//printf("%i\n",u);
		naam1 = getchar();
	}	
	
	//printf("%s",naam);
	while(!feof(anime))
   {
	  fgets(te_zoeken_naam, 256, anime);
	  m=strlen(naam);
	  
	  for(z=0;z<u+1;z++)
	  {
		  c=te_zoeken_naam[z];
		  d=tolower(c);
		  te_zoekn_naam[z]=d;
		  e=naam[z];
		  r=tolower(e);
		  naam2[z]=r;
		  
	  }
		  
		  if( strncmp(te_zoekn_naam,naam2,u)==0)
		  {
			 printf("Match gevonden\n");
			 //printf("%u",m);
			 printf("Titel: %s\n", te_zoeken_naam);
			 y = y++;
			 printf("---\n");
         
		  }
	  
	}
		
	if(y == 0)
	{
	printf("%s","Geen match gevonden!\n");
	//printf("%u",m);
	}
	printf("%s","Typ Y om terug naar het hoofdmenu te gaan!\n");
	printf("%s","Typ N om verder te zoeken!\n");
	
	while(hoofdmenu != 'Y' || hoofdmenu != 'N' || hoofdmenu != 'y' || hoofdmenu != 'n' ){
		scanf("%c",&hoofdmenu);
		_flushall();
		break;
		}
	if (hoofdmenu == 'Y' || hoofdmenu == 'y'){ 
		system("CLS");
		main();
	}
	if(hoofdmenu == 'N' || hoofdmenu == 'n'){
			fclose(anime);
			anime_zoeken();
		}
	}

void anime_lijst_bekijken()
{
	char hoofdmenu =' ';
	while(hoofdmenu != 'Y' || hoofdmenu != 'y')
	{
		char c=' ';
		FILE  *anime =fopen("anime1.txt","r");
		system("CLS");
		while((c = getc(anime))!=EOF)
		{
			putchar(c);
		}
		fclose (anime);
		printf("%s","Typ Y om terug naar het hoofdmenu te gaan!\n");
		scanf("%c",&hoofdmenu);
	}
	system("CLS");
	main();
}
void anime_toevoegen()
{
	FILE  *anime;
	FILE *outpFile;
	char naam1[100];
	char naam = ' ';
	char te_zoeken_naam[256];
	int i=0;
	int j=0;
	int m=0;
	char keuze=' ';
	system("CLS");
	printf("%s","Typ & om te stoppen met toevoegen!\n");
	printf("%s","Geef de naam: ");
	naam = getchar();
		while(naam != '&')
		{
			while(naam != '\n')
			{
				naam1[i] = naam;
				i++;
				naam = getchar();
			}
			anime =fopen("anime1.txt","r");
			naam1[i]='\n';
			m=strlen(naam1);
			
			while(!feof(anime))
			{
				fgets(te_zoeken_naam, 256, anime);
				if(strncmp(te_zoeken_naam,naam1,m)==0)
				{
					printf("%s","De opgeven naam bestaat al!! Druk Y om opnieuw in te geven ");
					while(keuze != 'Y' || keuze != 'y')
					{
						keuze=getchar();
					}
					_flushall();
					fclose(anime);
					anime_toevoegen();
				}
			}
		fclose(anime);
		outpFile =fopen("anime1.txt","a+");
		fprintf(outpFile,"%s",naam1);
		fprintf(outpFile,"%c",'\n');
		fclose (outpFile);
		system("CLS");
		anime_toevoegen();			
		}
		system("CLS");
		main();
}
void keuze(int keuze)
{
//	char naam[100];
	switch(keuze){
	case 1:	
		anime_toevoegen();
		break;
	case 2:
		anime_lijst_bekijken();
		break;
	case 3:
		anime_zoeken();
		break;
	}
	
}
void errorhandling(int keus)
{
	
	if (keus > 4) 
	{
		system("CLS");
		printf("%s", "Gelieve een getal in te geven van 1 tot 4!\n");
		main();
	}else{
		if(keus == 4)
		{
			exit(0);
		}else{
			keuze(keus);
		}
}
}
void streaming()
{
	printf("%s","http://www.animeram.com/kiba/1/");
}
void anime_verwijderen()
{
	FILE *anime;
	anime = fopen("anime1.txt","a+");
	printf("%s","Typ naam anime die je wilt verwijderen: ");



}