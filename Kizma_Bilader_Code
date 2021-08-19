#include<stdio.h>
#include<string.h>
#include<time.h>
#include<stdlib.h>
#include<windows.h>

void TamEkran();
void gotoyx();
void frame();
int intro();
void circle(int y,int x);
void table();
void coordinate();
int dice();
void game();
void coordpawns();
void placepawns();
void updatescreen();

struct pawn{
	
	int y1;
	int x1;
	int y0;
	int x0;
	int way;
	char cname;
};

struct user{
	char name[15];
	int no;
	int coordinate[44][3];
	char color[15];
	int queue;
	int dice;
	struct pawn pawn[4];
	int ongame;

};

struct user user[4];



int main () {
	//system("COLOR f0");	
	TamEkran();

	
	game();
	getch();
}

void TamEkran(){
	HWND hWnd = GetConsoleWindow();
	ShowWindow(hWnd,SW_SHOWMAXIMIZED);  // Console tam ekran yapýlýyor
}

void gotoyx(int s,int k){
	HANDLE hConsoleOutput;
	COORD ImlecYeri={k-1,s-1};
	hConsoleOutput=GetStdHandle(STD_OUTPUT_HANDLE);
	SetConsoleCursorPosition(hConsoleOutput, ImlecYeri);
}

void frame() {
	
	
	int hight=50,width=210,i,j;
	
	for(i=0;i<hight;i++){
		gotoyx(i,1);
		printf("%c",219);
		gotoyx(i,width);
		printf("%c",219);
	}
	for(j=0;j<=width;j++){
		gotoyx(1,j);
		printf("%c",219);
		gotoyx(3,4);
		printf("Ahmet Faruk Alkan");
		gotoyx(3,100);
		printf("KIZMA BILADER");
		gotoyx(3,210);
		gotoyx(hight,j);
		printf("%c",219);
	}
}
int intro(){
	
	srand(time(0));
	int number,color,i,j,k,a,team[4][2];
;
	char name[15],name1[15],name2[15],name3[15],name4[15];
	
	do{
		system("CLS");
		frame();
		gotoyx(20,96);
		printf("Kac kisi oynayacak ? ");
		scanf("%d",&number);
	}while(number<2||number>4);
	
	
	frame();
	gotoyx(20,96);
	
	system("CLS");
	frame();
	
	for(i=0;i<number;i++){
		
		gotoyx(20+3*i,92);
		user[i].no=i+1;
		user[i].queue=i+1;
		printf("%d. oyuncunun adi :",i+1);
		scanf("%s",&user[i].name);
	}
	
	system("CLS");
	frame();
	
	for(i=0;i<number;i++){
		
		again:
		team[i][0]=i+1;
		color=rand()%4+1;
		team[i][1]=color;
		if(i!=0){
			for(j=0;j<i;j++){
				if(team[i][1]==team[j][1])
					goto again;
			}
		}
		
		
		if(color==1){
			gotoyx(20+3*i,92);
			printf("%s  Kirmizi Ile Oynayacak",user[i].name);
			strcpy(user[i].color,"kirmizi");
			
		}
		if(color==2){
			gotoyx(20+3*i,92);
			printf("%s  Mavi Ile Oynayacak",user[i].name);
			strcpy(user[i].color,"mavi");
		}
		if(color==3){
			gotoyx(20+3*i,92);
			printf("%s  Yesil Ile Oynayacak",user[i].name);
			strcpy(user[i].color,"yesil");
		}
		if(color==4){
			gotoyx(20+3*i,92);
			printf("%s  Sari Ile Oynayacak",user[i].name);
			strcpy(user[i].color,"sari");
		}
	}
	
	getch();
	system("CLS");
	return number; 
}

void circle(int y,int x){
	
	gotoyx(y+1,x);
	printf("%c",219);
	gotoyx(y-1,x);
	printf("%c",219);
	gotoyx(y,x+2);
	printf("%c",219);
	gotoyx(y,x-1);
	printf("%c",219);
	gotoyx(y+1,x+1);
	printf("%c",219);
	gotoyx(y+1,x-1);
	printf("%c",219);
	gotoyx(y-1,x+1);
	printf("%c",219);
	gotoyx(y-1,x-1);
	printf("%c",219);
	gotoyx(y+1,x+2);
	printf("%c",219);
	gotoyx(y-1,x+2);
	printf("%c",219);
	
	gotoyx(y,x);
	//printf("%d %d",y,x);
	
}
void table(){
	
	
	frame();
	int i,y=23,x=97,k;
	for(i=0;i<11;i++){
		
		circle(y,9*i+61);
		if(i!=5){
			circle(y+4,9*i+61);
		}
		circle(y+8,9*i+61);
		
		circle(7+4*i,x);
		if(i!=5){
			circle(7+4*i,x+9);
		}
		circle(7+4*i,x+18);
		
	}
	for(i=0;i<78;i++){
		gotoyx(25,i+68);
		printf("-");
		gotoyx(29,i+68);
		printf("-");
	}
	for(i=0;i<35;i++){
		gotoyx(10+i,102);
		printf("|");
		gotoyx(10+i,111);
		printf("|");
	}	
	for(i=0;i<8;i++){
		gotoyx(9,103+i);
		printf("-");
		gotoyx(45,103+i);
		printf("-");
	}
	for(i=0;i<3;i++){
		gotoyx(26+i,67);
		printf("|");
		gotoyx(26+i,146);
		printf("|");
	}
	for(i=0;i<2;i++){
		circle(47,70);	
		circle(47,70-9*i);
		circle(47-4*i,70);
		circle(47-4*i,70-9*i);
		gotoyx(47,75+i);
		printf("---------------->");
		
		circle(7,142);
		circle(7,142+9*i);
		circle(7+4*i,142);
		circle(7+4*i,142+9*i);
		gotoyx(7,122-1*i);
		printf("<----------------");
		
		circle(11,61);
		circle(11-4*i,61);
		circle(11,61+9*i);
		circle(11-4*i,61+9*i);
		for(k=14;k<20;k++){
			gotoyx(k,61);
			printf("|");
		}
		gotoyx(20,61);
		printf("v");
		
		circle(43,151);
		circle(43,151-9*i);
		circle(43+4*i,151);
		circle(43+4*i,151-9*i);
		for(k=35;k<41;k++){
			gotoyx(k,151);
			printf("|");
		}
		gotoyx(34,151);
		printf("^");
	}
	
	
	
	/*for(i=0;i<99;i++){
		gotoyx(5,58+i);
		printf("-");
		gotoyx(49,58+i);
		printf("-");
		
	}
	for(i=0;i<43;i++){
		gotoyx(i+6,57);
		printf("|");
		gotoyx(i+6,157);
		printf("|");
	}*/
}

void coordinate() {
	int i,j;
	int red[44][3],blue[44][3],yellow[44][3],green [44][3];
	
	for(i=0;i<=40;i++){
		if(i<5){
			red[i][0]=i+1;
			red[i][1]=(47-4*i);
			red[i][2]=(97);
		}
		if(i>=5&&i<9){
			red[i][0]=i+1;
			red[i][1]=(31);
			red[i][2]=(97-(i-4)*9);
		}
		if(i==9){
			red[i][0]=i+1;
			red[i][1]=(27);
			red[i][2]=(61);
		}
		if(i>9&&i<15){
			red[i][0]=i+1;
			red[i][1]=23;
			red[i][2]=61+(i-10)*9;
		}
		if(i>=15&&i<19){
			red[i][0]=i+1;
			red[i][1]=19-(i-15)*4;
			red[i][2]=97;
		}
		if(i==19){
			red[i][0]=i+1;
			red[i][1]=(7);
			red[i][2]=(106);
		}	
		if(i>19&&i<25){
			red[i][0]=i+1;
			red[i][1]=7+(i-20)*4;
			red[i][2]=115;
		}	
		if(i>=25&&i<29){
			red[i][0]=i+1;
			red[i][1]=(23);
			red[i][2]=(124+(i-25)*9);
		}
		if(i==29){
			red[i][0]=i+1;
			red[i][1]=(27);
			red[i][2]=(151);
		}	
		if(i>29&&i<35){
			red[i][0]=i+1;
			red[i][1]=(31);
			red[i][2]=(151-(i-30)*9);
		}
		if(i>=35&&i<39){
			red[i][0]=i+1;
			red[i][1]=35+(i-35)*4;
			red[i][2]=115;
		}	
		if(i==39){
			red[i][0]=i+1;
			red[i][1]=(47);
			red[i][2]=(106);
		}	
	}
	
	//shift
	for(i=0;i<40;i++){

		
		yellow[i][0]=i+1;
		yellow[i][1]=red[(i+10)%40][1];
		yellow[i][2]=red[(i+10)%40][2];;
		
		blue[i][0]=i+1;
		blue[i][1]=red[(i+20)%40][1];
		blue[i][2]=red[(i+20)%40][2];
		
		green[i][0]=i+1;
		green[i][1]=red[(i+30)%40][1];
		green[i][2]=red[(i+30)%40][2];
		
	}
	
	for(j=0;j<4;j++){
		for(i=0;i<40;i++){
			if(!strcmp(user[j].color,"kirmizi")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=red[i][1];
				user[j].coordinate[i][2]=red[i][2];
			}
			if(!strcmp(user[j].color,"yesil")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=green[i][1];
				user[j].coordinate[i][2]=green[i][2];
			}
			if(!strcmp(user[j].color,"mavi")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=blue[i][1];
				user[j].coordinate[i][2]=blue[i][2];
			}
			if(!strcmp(user[j].color,"sari")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=yellow[i][1];
				user[j].coordinate[i][2]=yellow[i][2];
			}

		}
	}
	for(j=0;j<4;j++){
		for(i=40;i<44;i++){
			if(!strcmp(user[j].color,"kirmizi")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=43-(i-40)*4;
				user[j].coordinate[i][2]=106;
			}
			if(!strcmp(user[j].color,"yesil")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=27;
				user[j].coordinate[i][2]=142-(i-40)*9;
			}
			if(!strcmp(user[j].color,"mavi")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=11+(i-40)*4;
				user[j].coordinate[i][2]=106;
			}
			if(!strcmp(user[j].color,"sari")){
				user[j].coordinate[i][0]=i+1;
				user[j].coordinate[i][1]=27;
				user[j].coordinate[i][2]=70+(i-40)*9;
			}

		}
	}
	/*system("CLS");
	for(i=0;i<44;i++){
		
		//printf("%d %d %d \n",user[0].coordinate[i][0],user[0].coordinate[i][1],user[0].coordinate[i][2]);
		//printf("%d %d %d \n",user[1].coordinate[i][0],user[1].coordinate[i][1],user[1].coordinate[i][2]);
		//printf("%d %d %d \n",user[2].coordinate[i][0],user[2].coordinate[i][1],user[2].coordinate[i][2]);
		//printf("%d %d %d \n",user[3].coordinate[i][0],user[3].coordinate[i][1],user[3].coordinate[i][2]);

	}
	getch();*/
}
int dice(){
	
	
	srand(time(0));
	//sleep(2);
	return (rand()%6+1);
	
}

void coordpawns(){
	
	int i,j;
	for(i=0;i<4;i++){
		user[i].ongame=0;
		for(j=0;j<4;j++){
			user[i].pawn[j].way=-1;
			
			if(!strcmp(user[i].color,"kirmizi")){
				if(j==0){
					user[i].pawn[j].y0=47;
					user[i].pawn[j].x0=70;
					user[i].pawn[j].y1=47;
					user[i].pawn[j].x1=70;
					user[i].pawn[j].cname='K';
				}
				if(j==1){
					user[i].pawn[j].y0=47;
					user[i].pawn[j].x0=61;
					user[i].pawn[j].y1=47;
					user[i].pawn[j].x1=61;
					user[i].pawn[j].cname='K';
				}
				if(j==2){
					user[i].pawn[j].y0=43;
					user[i].pawn[j].x0=61;
					user[i].pawn[j].y1=43;
					user[i].pawn[j].x1=61;
					user[i].pawn[j].cname='K';
				}
				if(j==3){
					user[i].pawn[j].y0=43;
					user[i].pawn[j].x0=70;
					user[i].pawn[j].y1=43;
					user[i].pawn[j].x1=70;
					user[i].pawn[j].cname='K';
				}
				
				
			}
			if(!strcmp(user[i].color,"mavi")){
				if(j==0){
					user[i].pawn[j].y0=7;
					user[i].pawn[j].x0=142;
					user[i].pawn[j].y1=7;
					user[i].pawn[j].x1=142;
					user[i].pawn[j].cname='M';
				}
				if(j==1){
					user[i].pawn[j].y0=7;
					user[i].pawn[j].x0=151;
					user[i].pawn[j].y1=7;
					user[i].pawn[j].x1=151;
					user[i].pawn[j].cname='M';
				}
				if(j==2){
					user[i].pawn[j].y0=11;
					user[i].pawn[j].x0=142;
					user[i].pawn[j].y1=11;
					user[i].pawn[j].x1=142;
					user[i].pawn[j].cname='M';
				}
				if(j==3){
					user[i].pawn[j].y0=11;
					user[i].pawn[j].x0=151;
					user[i].pawn[j].y1=11;
					user[i].pawn[j].x1=151;
					user[i].pawn[j].cname='M';
				}
			}
			if(!strcmp(user[i].color,"yesil")){
				if(j==0){
					user[i].pawn[j].y0=43;
					user[i].pawn[j].x0=151;
					user[i].pawn[j].y1=43;
					user[i].pawn[j].x1=151;
					user[i].pawn[j].cname='Y';
				}
				if(j==1){
					user[i].pawn[j].y0=43;
					user[i].pawn[j].x0=142;
					user[i].pawn[j].y1=43;
					user[i].pawn[j].x1=142;
					user[i].pawn[j].cname='Y';
				}
				if(j==2){
					user[i].pawn[j].y0=47;
					user[i].pawn[j].x0=151;
					user[i].pawn[j].y1=47;
					user[i].pawn[j].x1=151;
					user[i].pawn[j].cname='Y';
				}
				if(j==3){
					user[i].pawn[j].y0=47;
					user[i].pawn[j].x0=142;
					user[i].pawn[j].y1=47;
					user[i].pawn[j].x1=142;
					user[i].pawn[j].cname='Y';
				}
			}
			if(!strcmp(user[i].color,"sari")){
				if(j==0){
					user[i].pawn[j].y0=11;
					user[i].pawn[j].x0=61;
					user[i].pawn[j].y1=11;
					user[i].pawn[j].x1=61;
					user[i].pawn[j].cname='S';
				}
				if(j==1){
					user[i].pawn[j].y0=11;
					user[i].pawn[j].x0=70;
					user[i].pawn[j].y1=11;
					user[i].pawn[j].x1=70;
					user[i].pawn[j].cname='S';
				}
				if(j==2){
					user[i].pawn[j].y0=7;
					user[i].pawn[j].x0=61;
					user[i].pawn[j].y1=7;
					user[i].pawn[j].x1=61;
					user[i].pawn[j].cname='S';
				}
				if(j==3){
					user[i].pawn[j].y0=7;
					user[i].pawn[j].x0=70;
					user[i].pawn[j].y1=7;
					user[i].pawn[j].x1=70;
					user[i].pawn[j].cname='S';
				}
			}
		}
	}
	
}

void placepawns(){
	int i,j;
	
	for(i=0;i<4;i++){
		for(j=0;j<4;j++){
			if(strcmp(user[i].color,"\0")){
				gotoyx(user[i].pawn[j].y1,user[i].pawn[j].x1);
				printf("%c%d",user[i].pawn[j].cname,j+1);
			}
			
			
		}
	}
	
}

void updatescreen(){
	system("CLS");
	table();
	placepawns();
}

void game(){
	
	int number=intro();
	coordinate();
	
	int i,j;
	
	system("CLS");
	frame();
	
	for(i=0;i<number;i++){
		
		gotoyx(6+2*i,6);
		
		if(!strcmp(user[i].color,"kirmizi")){
			printf("%s (%s) zar atacak : ",user[i].name,user[i].color);
			again1:
			user[i].dice=dice();
			for(j=0;j<number;j++){
				if(user[i].dice==user[j].dice&&i!=j){
					goto again1;
				}
			}
			printf("%d",user[i].dice);sleep(2);
			
		}
		if(!strcmp(user[i].color,"mavi")){
			printf("%s (%s) zar atacak : ",user[i].name,user[i].color);
			again2:
			user[i].dice=dice();
			for(j=0;j<number;j++){
				if(user[i].dice==user[j].dice&&i!=j){
					goto again2;
				}
			}
			printf("%d",user[i].dice);sleep(2);
		}
		if(!strcmp(user[i].color,"yesil")){
			printf("%s (%s) zar atacak : ",user[i].name,user[i].color);
			again3:
			user[i].dice=dice();
			for(j=0;j<number;j++){
				if(user[i].dice==user[j].dice&&i!=j){
					goto again3;
				}
			}
			printf("%d",user[i].dice);sleep(2);
			
		}
		if(!strcmp(user[i].color,"sari")){
			printf("%s (%s) zar atacak : ",user[i].name,user[i].color);
			again4:
			user[i].dice=dice();
			for(j=0;j<number;j++){
				if(user[i].dice==user[j].dice&&i!=j){
					goto again4;
				}
			}
			printf("%d",user[i].dice);sleep(2);
			
		}
	}
	

	int t;
	for(i=0;i<number;i++){
		for(j=i;j<number;j++){
			if(user[i].dice<user[j].dice){
				t=user[i].queue;
				user[i].queue=user[j].queue;
				user[j].queue=t;
			}
				
		}
	}
	system("CLS");
	frame();
	for(i=1;i<=number;i++){
		for(j=0;j<4;j++){
			if(user[j].queue==i){
				gotoyx(6+2*i,6);
				printf("%s (%s) %d. sirada",user[j].name,user[j].color,user[j].queue);
			}
		}
	}
	getch();
	coordpawns();
	table();
	placepawns();
	
	int q,no,k,l,stabil=0,win=0;
	for(q=1;q<=4;q++){
		
		for(i=0;i<4;i++){
			if(user[i].queue==q){
				dice6:
				updatescreen();
				user[i].dice=dice();
				error:
				
				gotoyx(6,6);
				printf("%s (%s) zar atiyor : %d",user[i].name,user[i].color,user[i].dice);
				
				if(!strcmp(user[i].color,"kirmizi"))
					system("COLOR 4f");
				else if(!strcmp(user[i].color,"mavi"))
					system("COLOR 1f");
				else if(!strcmp(user[i].color,"sari"))
					system("COLOR 6f");
				else if(!strcmp(user[i].color,"yesil"))
					system("COLOR 2f");
				
				//sleep(2);
				gotoyx(8,6);
				
				stabil=0;
				
				if(user[i].ongame==0&&user[i].dice!=6){
					sleep(2);
					past:
					/*gotoyx(9,6);	
					printf("1");
					getch();*/
					continue;
				}
				else if((user[i].pawn[0].way+user[i].dice>=44)&&(user[i].pawn[1].way+user[i].dice>=44)&&(user[i].pawn[2].way+user[i].dice>=44)&&(user[i].pawn[3].way+user[i].dice>=44)&&user[i].ongame!=0){
					sleep(2);
					/*gotoyx(9,6);	
					printf("2");
					getch();*/
					continue;
				}
				else {
					
					for(k=0;k<4;k++){
						if(user[i].pawn[k].way==-1&&user[i].dice!=6){
							stabil++;
						}
						else if((user[i].pawn[k].way+user[i].dice>43)&&user[i].pawn[k].way!=-1){
							stabil++;
						}
						else {
							for(l=0;l<4;l++){
								if((user[i].pawn[k].way+user[i].dice==user[i].pawn[l].way)&&user[i].pawn[k].way!=-1&&user[i].pawn[l].way!=-1&&(k!=l)){
									stabil++;
								}
							}
						}
					}
					if(stabil==4){
						sleep(2);
						/*gotoyx(9,6);	
						printf("3");
						getch();*/
						continue;
					}
				}
				
				
				printf("Kac numarali zari oynayacaksin ? ");
				scanf("%d",&no);
				
				
				
				if(no>4||no<1){
					updatescreen();
					goto error;
				}
					
					
				if(user[i].pawn[no-1].x0==user[i].pawn[no-1].x1&&user[i].pawn[no-1].y0==user[i].pawn[no-1].y1&&user[i].dice==6){
					user[i].pawn[no-1].y1=user[i].coordinate[0][1];
					user[i].pawn[no-1].x1=user[i].coordinate[0][2];
					user[i].pawn[no-1].way=0;
					user[i].ongame++;
					for(j=0;j<4;j++){
						if(((no-1)!=j)&&(user[i].pawn[no-1].x1==user[i].pawn[j].x1)&&(user[i].pawn[no-1].y1==user[i].pawn[j].y1)&&(user[i].pawn[no-1].y1==user[i].coordinate[0][1])&&(user[i].pawn[no-1].x1==user[i].coordinate[0][2])){
							user[i].pawn[no-1].x1=user[i].pawn[no-1].x0;
							user[i].pawn[no-1].y1=user[i].pawn[no-1].y0;
							user[i].pawn[no-1].way=-1;
							user[i].ongame--;
							updatescreen();
							goto error;
						}
					}
					
					
				}
				
				else if((user[i].pawn[no-1].x0!=user[i].pawn[no-1].x1)||(user[i].pawn[no-1].y0!=user[i].pawn[no-1].y1)){
					if(user[i].pawn[no-1].way+user[i].dice<44){
						user[i].pawn[no-1].y1=user[i].coordinate[user[i].pawn[no-1].way+user[i].dice][1];
						user[i].pawn[no-1].x1=user[i].coordinate[user[i].pawn[no-1].way+user[i].dice][2];
						user[i].pawn[no-1].way+=user[i].dice;
					
						for(j=0;j<4;j++){
							if(j!=(no-1)&&user[i].pawn[no-1].x1==user[i].pawn[j].x1&&user[i].pawn[no-1].y1==user[i].pawn[j].y1){
								user[i].pawn[no-1].y1=user[i].coordinate[user[i].pawn[no-1].way-user[i].dice][1];
								user[i].pawn[no-1].x1=user[i].coordinate[user[i].pawn[no-1].way-user[i].dice][2];
								user[i].pawn[no-1].way-=user[i].dice;
								updatescreen();
								goto error;
							}
						}
					}
					else{
						for(k=0;k<4;k++){
							if(k!=(no-1)&&(user[i].pawn[k].way+user[i].dice<44)&&user[i].pawn[k].way!=-1){
								for(l=0;l<4;l++){
									if(l!=k&&user[i].pawn[k].way+user[i].dice!=user[i].pawn[l].way&&user[i].pawn[l].way!=-1){
										updatescreen();
										goto error;
									}
								}
							}
						}
						if(user[i].dice==6){
							updatescreen();
							goto error;
						}
						goto past;
					}

					
				}
				else if(user[i].pawn[no-1].x0==user[i].pawn[no-1].x1&&user[i].pawn[no-1].y0==user[i].pawn[no-1].y1&&user[i].dice!=6&&(user[i].ongame!=0)){
					updatescreen();
					goto error;
				}

				
				
				
				for(j=0;j<4;j++){
					for(k=0;k<4;k++){
						if(j!=i&&(user[j].pawn[k].x1==user[i].pawn[no-1].x1)&&user[j].pawn[k].y1==user[i].pawn[no-1].y1){
							user[j].pawn[k].x1=user[j].pawn[k].x0;
							user[j].pawn[k].y1=user[j].pawn[k].y0;
							user[j].ongame--;
							user[j].pawn[k].way=-1;
						}
					}
				}
				
				updatescreen();
				
				if(user[i].dice==6){
					
					goto dice6;
				}
				
				win=0;
				for(j=0;j<4;j++){
					for(k=40;k<44;k++){
						if(user[i].pawn[j].y1==user[i].coordinate[k][1]&&user[i].pawn[j].x1==user[i].coordinate[k][2]){
							win++;
						}
					}
					
				}
				if(win==4){
					sleep(3);
					system("CLS");
					frame();
					gotoyx(24,101);
					printf("%s WINNER!",user[i].name);
					getch();
					gotoyx(50,210);
					exit(1);
				}
			
				
			}
		}
		
		
		
		if(q==4)
			q=0;
	}
	
}
