#include <iostream>

using namespace std;

struct ADC
{
    int FeedBack_V, FeedBack_REZ, FeedBack_DD, FeedBack_PD, FeedBack_RDD, FeedBack_RPD, FeedBack_TC, FeedBack_TK;
}ADC_Value;

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

    ADC_Value.FeedBack_V = ADC_Vector[0];
    ADC_Value.FeedBack_REZ = ADC_Vector[1];
    ADC_Value.FeedBack_DD = ADC_Vector[2];
    ADC_Value.FeedBack_PD = ADC_Vector[3];
    ADC_Value.FeedBack_RDD = ADC_Vector[4];
    ADC_Value.FeedBack_RPD = ADC_Vector[5];
    ADC_Value.FeedBack_TC = ADC_Vector[6];
    ADC_Value.FeedBack_TK = ADC_Vector[7];

/* cout<<endl<<endl<<ADC_Value.FeedBack_V; */

    return 0;
}
