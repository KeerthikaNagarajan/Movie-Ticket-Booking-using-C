# Movie Ticket Booking using C

## Description:
This is a simple C program for booking movie tickets at a cinema. Users can select movies in different languages, choose time slots, calculate ticket prices, and generate booking details.

## Installation:
- Clone this repository to your local machine using `git clone`.
- Compile the code using a C compiler such as GCC.
- Run the executable file generated after compilation.

## Usage:
1. Choose the movie language (Tamil, English, or Telugu).
2. Select a movie from the available options.
3. Pick a time slot (morning, afternoon, or evening).
4. Enter the number of tickets required.
5. Choose a payment mode (UPI, Net banking, Debit card, or Credit card).

## Code:
```c
struct movie
{
    int num_of_tickets;
    int tot_num_of_tickets_slot;
    int price;
    int act_price;
    float tot_amt;
    float gst;
}mov;

struct tamil
{
    char tmov1[50];
    char tmov2[50];
    char tmov3[50];
}tam;
struct english
{
    char emov1[50];
    char emov2[50];
    char emov3[50];
}eng;
struct telugu
{
    char telmov1[50];
    char telmov2[50];
    char telmov3[50];
}tel;

#include<stdio.h>
#include <stdlib.h>
int main()
{   struct tamil tam={"Ponniyin Selvan","Asuran","Varisu"};
    struct english eng={"Interstellar","Top Gun","Black Panther:Wakanda Forever"};
    struct telugu tel={"Sita Ramam","RRR","Major"};
    char slot1[100]="Morning Show:10.00 am to 1.00 pm";
    char slot2[100]="Afternoon Show: 3:00 pm to 6.00 pm";
    char slot3[100]="Evening Show: 7.00 pm to 10.00 pm";
    int choice,slot,i,movname;
    printf("...........................PVR CINEMAS............................\n");
    printf("\nMovie Language:\nChoose any one below:");
    printf("\n1.Tamil\n2.English\n3.Telugu\n");
    printf("Enter your choice:");
    scanf("%d",&choice);
    if(choice==1)
    {
        printf("\nMovie Available in Tamil:\n");
        printf("\n1.%s\n2.%s\n3.%s\n",tam.tmov1,tam.tmov2,tam.tmov3);
    }
    else if(choice==2)
    {
        printf("Movie Available in English:\n");
        printf("\n1.%s\n2.%s\n3.%s\n",eng.emov1,eng.emov2,eng.emov3);
    }
    else if(choice==3)
    {
        printf("Movie Available in Telugu:\n");
        printf("1.%s\n2.%s\n3.%s\n",tel.telmov1,tel.telmov2,tel.telmov3);
    }
    else
    {
        printf("\nINVALID CHOICE\n");
        exit(0);
    }
    printf("\n");
    printf("Select the Movie:");
    scanf("%d",&movname);
    mov.tot_num_of_tickets_slot=100;


    printf("\n\nThe slots Available are:\n");
    printf("1.Morning Show: 10.00 am to 1.00pm\n");
    printf("2.Afternoon Show: 3:00pm to 6.00pm\n");
    printf("3.Evening Show: 7.00pm to 10.00pm\n");
    
    printf("\nSelect your slot:");
    scanf("%d",&slot);
    if(slot>3)
    {
        printf("INVALID CHOICE");
        exit(0);
    }
    mov.price=120;
    printf("Cost of per ticket:%d",mov.price);
    printf("\nEnter Number of tickets:");
    scanf("%d",&mov.num_of_tickets);
    if(mov.num_of_tickets>100)
    {
        printf("Seats Unavailable");
        exit(0);
    }
    
    mov.act_price=mov.num_of_tickets*mov.price;
    mov.gst=(mov.act_price*18)/100;
    mov.tot_amt=mov.act_price+mov.gst;
    printf("\n\nTotal Amount= %.2f",mov.tot_amt);

    
    printf("\nPayment Mode\n");
    printf("1.UPI\n");
    printf("2.Net banking\n");
    printf("3.Debit card\n");
    printf("4.Credit card\n");
    int option;
    printf("Enter your option :");
    scanf("%d",&option);
    if(option>4)
    {
        printf("INVALID CHOICE");
        exit(0);
    }
    printf("-----------------------Payment Successfull-----------------------\n");
    printf("------------------------Generating Ticket------------------------");
    printf("\n\n");
    if(choice==1)
    {
        if(movname==1)
        {
            printf("%s\n",tam.tmov1);
            printf("TAMIL,2D\n");
        }
        
        else if(movname==2)
        {
            printf("%s\n",tam.tmov2);
            printf("TAMIL,2D\n");
        }

        else
        {
            printf("%s\n",tam.tmov3);
            printf("TAMIL,2D\n");
        }
    }
    else if(choice==2)
    {
        if(movname==1)
        {
        printf("%s\n",eng.emov1);
        printf("ENGLISH,2D\n");
        }
        else if(movname==2)
        {
        printf("%s\n",eng.emov2);
        printf("ENGLISH,2D\n");
        }
        else
        {
        printf("%s\n",eng.emov3);
        printf("ENGLISH,2D\n");
        }
    }
    else
    {
        if(movname==1)
        {
        printf("%s\n",tel.telmov1);
        printf("TELUGU,2D\n");
        }
        else if(movname==2)
        {
        printf("%s\n",tel.telmov2);
        printf("TELUGU,2D\n");
        }
        else
        {
        printf("%s\n",tel.telmov3);
        printf("TELUGU,2D\n");
        }
    }
    printf("Wednesday,09 Nov\n");
    if(slot==1)
    printf("%s\n",slot1);
    else if(slot==2)
    printf("%s\n",slot2);
    else
    printf("%s\n",slot3);
    printf("PVR CINEMAS,Chennai\n");
    printf("%d Ticket(s)\n",mov.num_of_tickets);
    printf("SCREEN 1\n");
    printf("Seats: ");
    for(int i=1;i<=mov.num_of_tickets;i++)
    {
        printf("A%d ",i);
    }
    
    printf("\n\nTotal Amount:\t\t\t\t\tRs.%.2f",mov.tot_amt);
    printf("\nTicket Price(%d):\t\t\t\tRs.%d",mov.num_of_tickets,mov.act_price);
    printf("\nConvenience Fees:\t\t\t\tRs.%.2f",mov.gst);
    printf("\n\nYour ticket has been sent to your e-mail/SMS/Whatsapp within 15 minutes of booking\n");
    printf("\n\nFor more information contact:\n");
    printf("Contact Number:9954361875\n");
    printf("E-mail Id:pvrcinemas@gmail.com\n");
    printf("\n\n\t\t\t\tThank You!!! Visit Again!!!"); 
}
```

## Output:

<img width="352" alt="Screenshot 2024-03-06 205328" src="https://github.com/KeerthikaNagarajan/Movie-Ticket-Booking-using-C/assets/93427089/2cfae8d3-921f-42d2-96e6-fa5392b5bb0c">
<br>
<img width="430" alt="Screenshot 2024-03-06 205343" src="https://github.com/KeerthikaNagarajan/Movie-Ticket-Booking-using-C/assets/93427089/dc764aeb-0087-4a1c-a071-2c93ed0ad5ad">
<br>
<img width="332" alt="Screenshot 2024-03-06 205358" src="https://github.com/KeerthikaNagarajan/Movie-Ticket-Booking-using-C/assets/93427089/99f66223-500a-44a1-b7f4-4018af9c21cc">


## Conclusion:

This project demonstrates how to create a functional movie ticket booking system with user-friendly features such as movie selection, time slot options, ticket pricing, and payment modes. By providing a straightforward interface and clear instructions, we aim to make the movie ticket booking process hassle-free for users.




