# Source-code-for-waste-recycle-prototype
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
void waste(int item);
void user(char name);
float weight,amt=0;
void main()
 {
   char name[20],email[20],phone[10],lemail[20];
   //database to store all this info and check if user is using for first time user or not for the discounts
   int item;
   int choice,login,phck;
   printf("1: phone\n 2: email\n 3: guest user \n 4: cancel login \n");
   scanf("%d",&login);
   switch (login)
   {
     case 1: printf("enter the name of the user\n");
               scanf("%s",name);
               printf("enter the phone number\n");
               scanf("%s",phone);
               phck=strlen(phone);
               if(phck==10)
                  waste(item);
               else
                  printf("invalid phonenumber");
                break;
     case 2: printf("enter the name of the user\n");
               scanf("%s",name);
               printf("enter the email id of the user\n");
               scanf("%s",email);
               waste(item);
        break;
    case 3:waste(item);
          break;
    case 4:exit(0);
    default: printf("invalid option\n");
  }
}
   //sensors are to be installed to differentiate the items
   {
     printf("1:plastic waste\n 2:metal waste\n 3:glass waste \n 4: other\n");
     scanf("%d",&item);
     switch(item)
     {
     case 1:
                printf("enter the weight of the plastic user\n");
                scanf("%f",&weight);
                if (weight<=10)
                  amt+=weight*0.1;
                else if(weight<=100)
                  amt+=10*0.1+(weight-10)*0.2;
                else
                  amt+=10*0.1+100*0.2+(weight-100)*0.5;
                printf("the amount is %f\n",amt);
                  printf("THANK YOU FOR USING");
                break;
    case 2:
                printf("enter the weight of the metal waste\n");
                scanf("%f",&weight);
                if(weight<=10)
                  amt+=weight*0.5;
                else if(weight<=100)
                  amt+=10*0.1+(weight-10)*0.75;
                else
                  amt+=10*0.5+100*0.75+(weight-100)*1.25;
                printf("the amount is %f\n",amt);
                  printf("THANK YOU FOR USING");
                break;
    case 3:
                printf("enter the weight of the glass waste\n");
                scanf("%f",&weight);
                if(weight<=10)
                  amt+=10*0.45;
                else if(weight<=100)
                  amt+=10*0.45+(weight-10)*0.65;
                  else
                  amt+=10*0.45+100*0.65+(weight-100)*0.95;
                  printf("the amount is %f\n",amt);
                  printf("THANK YOU FOR USING");
                  break;
    case 4:
                printf("item not acceptable");
                break;
    default:
                printf("invalid choice");

     }
  }
