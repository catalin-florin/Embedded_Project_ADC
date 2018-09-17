#include <iostream>

using namespace std;


int ADC_Vector[8] = {0,0,0,0,0,0,0,0};
int buffer[8] = {1023,511,200,450,0,100,900,750};
enum ADC {FeedBack_V = 0, FeedBack_REZ, FeedBack_DD, FeedBack_PD, FeedBack_RDD, FeedBack_RPD, FeedBack_TC, FeedBack_TK};

int main()
{

int ADC_Vector[8]={0,0,0,0,0,0,0,0};
   int buffer[8]={1023,511,200,450,0,100,900,750};
   int i=0;

   for(i=0;i<8;i++)
   {
       ADC_Vector[i]=(buffer[i]/51)*100;

    /* cout<< ADC_Value[i]<<endl; */
   }

   cout<<ADC_Vector[FeedBack_V]<<endl;

    return 0;
}
