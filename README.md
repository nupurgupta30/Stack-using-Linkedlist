# Stack-using-Linkedlist
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
struct stack
{int data;
struct stack *next;
}*first = NULL , *top = NULL;
void push()
{
char ch='y';
do
{struct stack *newStack=(struct stack*)malloc(sizeof(struct stack));
newStack->next = NULL;
printf("\nEnter Data :");
scanf("%d",&newStack->data);
if( first == NULL )
first = newStack;
else
top->next = newStack;
top = newStack;
printf("Done");
printf("\tAdd More?? Y or N:");
ch=getch();
printf("%c",ch);
}while(ch=='y' || ch=='Y');
}
void pop()
{int ch='y';
do
{struct stack *temp = first;
if(first == NULL && top==NULL)
{printf("\nSTACK UNDERFLOW!!");
break;
}
else if (first->next==NULL)
{printf("\nData Deleted : %d",first->data);
first = NULL;
top = NULL;
}
else
{printf("\nData Deleted : %d",top->data);
while(temp->next->next!=NULL)
temp = temp->next;
temp->next = NULL;
top = temp;
}
printf("\tDelete More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y'||ch=='Y');
}
void display()
{struct stack *d = first;
if(top==NULL)
{printf("\nEmpty STACK");
}
else
{printf("\nFIRST->");
while(d!=NULL)
{printf("%d ",d->data);
d=d->next;
}
printf("<-TOP");
}
}
int main()
{int c,size,i,x=1;
do
{printf("\n-----------------------------------------------------------\n");
printf("1.PUSH Value   \t2.POP Value    \t3.Display Stack\n4.Exit");
printf("\n\t\tEnter Choice :");
scanf("%d",&c);
printf("--------------------------------------------------------------");
switch(c)
{case 1: {push(); break; }
case 2: {pop(); break; }
case 3: {display(); break; }
case 4: {x=0;break;exit(0);    }
default:{printf("\n\n\t\tError!!!!!"); break;}
}
}while(x);
return 0;
}

