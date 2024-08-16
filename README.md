#include<iostream>
#include<vector>
using namespace std;
vector<char> square={'1','2','3','4','5','6','7','8','9'};

int checkwin();
void game();
void board()
{
    
   cout<<"\n##############################";
   cout<<"\nTic Tac Toe\n";
    cout<<"\n##############################";
   cout<<"Player 1 (x) - player 2 (o)"<<endl<<endl;
    cout<<endl;
    cout<<"    |    |    "<<endl;
    cout<<" "<<square[0]<<"  |  "<<square[1]<<" |  "<<square[2]<<endl;
    cout<<"____|____|____"<<endl;
    cout<<"    |    |    "<<endl;
    cout<<" "<<square[3]<<"  |  "<<square[4]<<" |  "<<square[5]<<endl;
    cout<<"____|____|____"<<endl;
    cout<<"    |    |    "<<endl;
    cout<<" "<<square[6]<<"  |  "<<square[7]<<" |  "<<square[8]<<endl;
    cout<<"    |    |    "<<endl;
    
}

int main()
{
    game();

    return 0;

}


int checkwin()
{
    if(square[0]==square[1] && square[1]==square[2])
    return 1;
    else if(square[3]==square[4] && square[4]==square[5])
    return 1;
    else if(square[6]==square[6] && square[7]==square[8])
    return 1;
    else if(square[0]==square[3] && square[3]==square[6])
    return 1;
    else if(square[1]==square[4] && square[4]==square[7])
    return 1;
    else if(square[0]==square[4] && square[4]==square[8])
    return 1;
    else if(square[2]==square[5] && square[5]==square[8])
    return 1;
    else if(square[2]==square[4] && square[4]==square[6])
    return 1;

    else if(
     square[0] != '1' && 
     square[1] != '2' && 
     square[2] != '3' &&
     square[3] != '4' &&
     square[4] != '5' &&
     square[5] != '6' &&
     square[6] != '7' &&
     square[7] != '8' &&
     square[8] != '9'   )
     {return 0;}
     else
     {
        return -1;
     }

}




void game()
{
    int player=1 , i, choice; 
    char mark;    

    do
{
    board();
    if(player % 2 == 1)
    player=1;
    else
    player==2;


    choice==0;
    
    cout<<"player"<<player<<" enter the number= "; 
    cin>>choice; 

    if(player==1)
    {
        mark='x'; 
    }
    else 
    {
        mark='o'; 
    } 

    if(choice == 1 && square[0]=='1') 
    square[0]=mark;
    else if(choice == 2 && square[1]=='2') 
    square[1]=mark;
    else if(choice == 3 && square[2]=='3') 
    square[2]=mark;
    else if(choice == 4 && square[3]=='4')
    square[3]=mark;
    else if(choice == 5 && square[4]=='5')
    square[4]=mark;
    else if(choice == 6 && square[5]=='6')
    square[5]=mark;
    else if(choice == 7 && square[6]=='7')
    square[6]=mark;
    else if(choice == 8 && square[7]=='8')
    square[7]=mark;
    else if(choice == 9 && square[8]=='9')
    square[8]=mark;
    
    else
    {
        cout<<"Invalid move because u entered an invalid number ";
        player --;
        cin.ignore();
        cin.get();
    }


    i=checkwin();
    player++;

}while (i==-1);


board();
square={'1','2','3','4','5','6','7','8','9'};
    if(i==1)
    {cout<<"Player "<<--player<<" Win";
    i=0;
    
    cout<<endl<<"# Can you Replay the Game?"<<endl;
    cout<<"# If 'YES' than press 1 / If 'NO' than press 2"<<endl;
    cout<<"Enter the Number:-";
    cin>>i;

        if(i==1)
        {
            game();
        }
        else
        {
            i=checkwin();
            cout<<"Thanks for playing......";
        }
    
    }

    else
    {
    cout<<"==> \a Game draw";
    if(i==-1)
    {
        i=0;
    cout<<"Can you Replay the Game?"<<endl;
    cout<<"If 'YES' than press 1 / If 'NO' than press 2"<<endl;
    cout<<"Enter the Number:-";
    cin>>i;

        if(i==1)
        {
            game();
        }
        else
        {
            i=checkwin();
        }
    }
    }
    cin.ignore();
    cin.get();
    

}
