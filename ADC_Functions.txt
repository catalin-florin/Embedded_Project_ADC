#include <iostream>

using namespace std;

#define SYSTEM_VOLTAGE 17
#define RESOLUTION 1023

int ADC_Vector[8] = {0,0,0,0,0,0,0,0};
int buffer[8] = {1023,511,200,450,0,100,900,750};
enum ADC {FeedBack_V = 0, FeedBack_REZ, FeedBack_DD, FeedBack_PD, FeedBack_RDD, FeedBack_RPD, FeedBack_TC, FeedBack_TK};


void ADC_CheckChannelValue (int channel)
{
   if(ADC_Vector[channel] < 500)
   {
       cout<<"Do nothing"<<endl;
   }
   else if(ADC_Vector[channel] > 500)
   {
        cout<<"Do something"<<endl;
   }
}

void ADC_GetChannelValue ()
{

for(int i=0;i<8;i++)
   {
       ADC_Vector[i] = (SYSTEM_VOLTAGE * buffer[i]) / RESOLUTION;    /* (System_Voltage * ADC_Read) / Resolution */
   }
}

int main()
{
    ADC_GetChannelValue();
    ADC_CheckChannelValue(FeedBack_V);

    return 0;
}
