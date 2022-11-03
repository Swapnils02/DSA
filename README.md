#include <stdio.h>  
#include<string.h>
#include<stdlib.h>

struct club
{
    char name[20];
    int prn;
    struct club *prv;
    struct club *next;
    
};
void inserts(struct club *); 
void insertm(struct club *);
void deletep(struct club *);
void deletes(struct club *);
void deletem(struct club *);
void count(struct club *);
void reverse(struct club *);
void display(struct club *);

void main()
{ 
    struct club *head;
    head=(struct club *)malloc(sizeof(struct club));
    printf("Enter name of President:");
    scanf(" %s",head->name);
    printf("Enter PRN of President:");
    scanf("%d",&head->prn);
    head->next=NULL;
    head->prv=NULL;
    inserts(head); 
    int choice,y;
    do{
        printf("\n1.insert member \n2.delete president \n3.delete secreatary \n4.delete member \n5.count \n6.reverse \n7.display");
        printf("Enter your choice");
        scanf("%d",&choice); 
        switch(choice){
           
         case 1:insertm(head);
                break;
       /* case 2:deletep(head);
                break;
        case 3:deletes(head);
                break;
        case 4:deletem(head);
                break;
        case 5:count(head);
                break;
        case 6:reverse(head);
                break;
        case 7:display(head);
                break;*/
        default:
                printf("Invalid choice");
        } 
        printf("Do you wAnt to continue (0/1)");
        scanf("%d",&y);
    } 
    while(y==1);
} 
void inserts(struct club *head)
{ 
    struct club *new;
    new=(struct club *)malloc(sizeof(struct club));
    printf("Enter Name of Secreatary:");
    scanf(" %s",new->name);
    printf("Enter PRN of secreatary:");
    scanf("%d",&new->prn);
    new->next=NULL;
    new->prv=NULL; 
    head->next=new;
    new->prv=head;
    
} 
void insertm(struct club *head)
{
    struct club *new,*temp;
    new=(struct club *)malloc(sizeof(struct club));
    printf("Enter Name of Secreatary:");
    scanf(" %s",new->name);
    printf("Enter PRN of secreatary:");
    scanf("%d",&new->prn); 
    new->prv=NULL;
    new->next=NULL;
    temp=head->next;
    head->next=new;
    new->prv=head;
    new->next=temp;
    temp->prv=new;
}

