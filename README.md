# TIC-TAC-TOE-GAME
/this game created using the programming language c++
#include<iostream>
using namespace std;
char A[10] = {'0','1','2','3','4','5','6','7','8','9'};
void board();
int checkwin ();
int main()
{
    int player = 1,i,choice;
    char mark;
    do 
    {
          board();
          if(player%2 == 1)
          player = 1;
          else
          player = 2;
          cout<<" player "<<player<<"  enter a number :";
          cin>>choice;
          if(player == 1)
          {
              mark = 'x';       
          }
          else
          {
             mark =  'o';    
          }
          if(choice == 1 && A[1] == '1')
          A[1] = mark;
           else if(choice == 2 && A[2] == '2')
          A[2] = mark;
           else if(choice == 3 && A[3] == '3')
          A[3] = mark;
           else if(choice == 4 && A[4] == '4')
          A[4] = mark;
           else if(choice == 5 && A[5] == '5')
          A[5] = mark;
           else if(choice == 6 && A[6] == '6')
          A[6] = mark;
           else if(choice == 7 && A[7] == '7')
          A[7] = mark;
           else if(choice == 8 && A[8] == '8')
          A[8] = mark;
           else if(choice == 9 && A[9] == '9')
          A[9] = mark;
          else
          {
            cout<<" invalid number ";
            player--;
            cin.ignore();
            cin.get();
          } 
          i=checkwin();
          player++;    
    }
    while(i == -1);
    board ();
    if(i == 1)
    cout<<" \a player "<<--player<<" - win ";
    else{
     cout<<"\a game draw ";
     cin.ignore();
     cin.get();}
     return 0;
    
}

void board()
{
    system("cls");
    cout<<"\n*WELCOME*\n"<<endl;
    cout<<"-----TIC TAC TOE-----\n"<<endl;
    cout<<" player 1 ->(X) , player 2 ->(O)"<<endl;
    cout<<"     |     |     "<<endl;
    cout<<"  "<<A[1]<<"  |  "<<A[2]<<"  |  "<<A[3]<<endl;
    cout<<"||_"<<endl;
    cout<<"     |     |      "<<endl;
    cout<<"  "<<A[4]<<"  |  "<<A[5]<<"  |  "<<A[6]<<endl;
    cout<<"||_"<<endl;
    cout<<"     |     |   "<<endl;
    cout<<"  "<<A[7]<<"  |  "<<A[8]<<"  |  "<<A[9]<<endl;
    cout<<"     |     |   "<<endl;  
}

int checkwin()
{
    if(A[1] == A[2] && A[2] == A[3])
    return 1;
    else if(A[4] == A[5] && A[5] == A[6])
    return 1;
    else if(A[7] == A[8] && A[8] == A[9])
    return 1;
    else if(A[1] == A[4] && A[4] == A[7])
    return 1;
    else if(A[2] == A[5] && A[5] == A[8])
    return 1;
    else if(A[3] == A[6] && A[6] == A[9])
    return 1;
    else if(A[1] == A[5] && A[5] == A[9])
    return 1;
    else if(A[3] == A[5] && A[5] == A[7])
    return 1;
    else if(A[1]!='1'&&A[2]!='2'&&A[3]!='3'&&
    A[4]!='4'&&A[5]!='5'&&A[6]!='6'&&A[7]!='7' 
    &&A[8]!='8'&&A[9]!='9')
    return 0;
    else{
          return -1;
    }
}
