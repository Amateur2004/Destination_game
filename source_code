#include<stdio.h>
#include<stdlib.h>
#include<time.h>
#define SIZE 15
void printMatrix(int col,int row,char a[row][col]){
    for(int i=0;i<row;i++){
        for(int j=0;j<col;j++){
            printf("%c ",a[i][j]);
        }puts("");
    }
}
int position(char c, int i,int curr_pos){
    if(c=='d' || c=='r'){
        if(i+curr_pos<=SIZE-1){
            curr_pos+=i;
        }
        else{
            curr_pos+=i;
            while(!(curr_pos<=SIZE-1&&curr_pos>=0)){
                curr_pos= curr_pos-(SIZE);//to count 0th element
                
            }
        }
        return curr_pos;
    }
    if(c=='u' || c=='l'){
        if(curr_pos-i>=0){
            curr_pos-=i;
        }
        else{
            curr_pos-=i;
            while(!(curr_pos>=0 && curr_pos<=SIZE-1)){
                curr_pos= SIZE+curr_pos;//to count 0th element
                
            }
        }
        return curr_pos;
    }
}
int main(){
    char area[SIZE][SIZE];
    char inp_char;
    int inp_num;


    srand(time(NULL));
    for(int i=0;i<SIZE;i++){
        for(int j=0;j<SIZE;j++){
            area[i][j]='_';
        }
    }

    printf("Bring 1 To The Place Of 0\n");

    int curr_loc[2];
    curr_loc[0]=rand()%SIZE;
    curr_loc[1]=rand()%SIZE;
    area[curr_loc[0]][curr_loc[1]]='1';
    int row=-1,col=-1; //unassigned
   
    while( (row==curr_loc[0] && col==curr_loc[1]) || row<0||row>SIZE-1 || col<0||col>SIZE-1){
        row=rand()%SIZE;
        col=rand()%SIZE;
    }
    area[row][col]='0';
    printMatrix(SIZE,SIZE,area);
    
    
    for(int j=0;j<10;j++){
        scanf(" %c%d",&inp_char,&inp_num);
 
        area[curr_loc[0]][curr_loc[1]]='_';
        int curr_pos=1;
        if(inp_char=='u' || inp_char== 'd'){
            curr_pos=curr_loc[0];
            curr_loc[0]=position(inp_char,inp_num,curr_pos);
        }
        else if(inp_char=='l' || inp_char== 'r'){
            curr_pos=curr_loc[1];
            curr_loc[1]=position(inp_char,inp_num,curr_pos);
        }
        area[curr_loc[0]][curr_loc[1]]='1';
        printMatrix(SIZE,SIZE,area);
   
    
        printf("\n\n");
    
        printf("%d chances are left\n\n",9-j);
        if(curr_loc[0]==row && curr_loc[1]==col){
            printf("Hurrah! You have won!\n");
            break;
        }
        if(j==9){
            if(curr_loc[0]!=row || curr_loc[1]!=col){
                printf("Try again! ;) \n");
            }
        }
        
        
    }


}
