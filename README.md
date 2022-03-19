# circular
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node* next;
}*newnode,*temp;
struct node* head=NULL;
struct node* tail=NULL;
//creation of circular Linked List.
void create()
{
    int value;
    int ch;
    do{
        newnode=(struct node*)malloc(sizeof(struct node));
        printf("Enter the value:");
        scanf("%d",&value);
        newnode->data=value;
        newnode->next=NULL;
        if(head==NULL)
        {
            head=newnode;
            tail=newnode;
            newnode->next=head;
        }
        else
        {
            tail->next=newnode;
            tail=newnode;
            tail->next=head;
        }
        printf("Press 1 to continue and others to exit\n");
        fflush(stdin);
        scanf("%d",&ch);
        }
        while(ch==1);
}
//Display of Circular linked list.
void display()
{
    temp=head;
    while(temp->next!=head)
    {
        printf("# %d #",temp->data);
        temp=temp->next;
    }
    printf("# %d #",temp->data);
}
//Insertion at beginning.
void insertion_at_beg()
{
    int value;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("Enter the inserted value to be inserted at the beginning:\n");
    scanf("%d",&value);
    newnode->data=value;
    newnode->next=head;
    tail->next=newnode;
    head=newnode;
}
//Insertion at ending.
void insertion_at_end()
{
    int value;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("Enter the inserted value to be inserted at the ending:\n");
    scanf("%d",&value);
    newnode->data=value;
    tail->next=newnode;
    newnode->next=head;
    tail=newnode;
}
//Insertion at specified position.
void insertion_at_pos()
{
    int value,pos;
    temp=head;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("Enter the inserted value to be inserted at specified position:\n");
    scanf("%d",&value);
    printf("Enter the position where the element is inserted:\n");
    scanf("%d",&pos);
    for(int i=0;i<pos-1;i++)
    {
        temp=temp->next;
    }
    newnode->data=value;
    newnode->next=temp->next;
    temp->next=newnode;
}
//Deletion at beginning.
void deletion_at_beg()
{
    temp=head;
    head=head->next;
    tail->next=head;
}
//Deletion at ending.
void deletion_at_end()
{
    temp=head;
    while(temp->next!=tail)
    {
        temp=temp->next;
    }
    temp->next=head;
    tail=temp;
}
//Deletion at specified position.
void deletion_at_pos()
{
    int position;
    temp=head;
    printf("Enter the position where the element is deleted:");
    scanf("%d",&position);
    for(int i=0;i<position-1;i++)
    {
        temp=temp->next;
    }
    temp->next=temp->next->next;
}
//To count the number of present in a circular linked list.
void count()
{
    int count=0;
    temp=head;
    while(temp->next!=head)
    {
        printf("# %d #",temp->data);
        temp=temp->next;
        count+=1;
    }
    printf("# %d #",temp->data);
    count+=1;
    printf("\nThe number of elements present in a circular linked list is%d\n",count);
}
void reverse()
{
struct node*current=head;
struct node* prev=NULL,next=NULL;
while(current!=NULL)
{
next=current->next;
prev->next=current;
current=prev;
prev=next;
head=prev
}
void search()
{
    struct node*current=head;
    int x;
    while(current!=NULL)
    {
        if(current->data==x)
        {
            return true;
        }
        else
        {
        current=current->next;
        return false;
        }
    }
}
//Main function.
void main()
{
    int choice=0;
    while(choice<12)
    {
        printf("\nOperations on Circular linked list\n");
        printf("1.creation of circular linked list\n");
        printf("2.display of circular linked list\n");
        printf("3.insertion at beginning\n");
        printf("4.insertion at ending\n");
        printf("5.insertion at specified position\n");
        printf("6.deletion at beginning\n");
        printf("7.deletion at ending\n");
        printf("8.deletion at specified position\n");
        printf("9.To count the number of elements present in a circular linked list\n");
        printf("others:to exit()\n");
        printf("enter your choice:\n");
        scanf("%d",&choice);
        switch(choice)
        {
            case 1:
                    create();
                    break;
            case 2:
                    display();
                    break;
            case 3:
                    insertion_at_beg();
                    break;
            case 4:
                    insertion_at_end();
                    break;
            case 5:
                    insertion_at_pos();
                    break;
            case 6:
                    deletion_at_beg();
                    break;
            case 7:
                    deletion_at_end();
                    break;
            case 8:
                    deletion_at_pos();
                    break;
            case 9:
                    count();
                    break;
            case 10:
                    riverse();
                    break;
            case 11:
                    search();
                    break;
              
        }
    }
}
