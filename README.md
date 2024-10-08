# pra-5-B
# stack implementation using linked list #

#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *next;
};

struct node *TOP = 0; // used as head
void push(int x)
{

    struct node *new;
    new = (struct node *)malloc(sizeof(struct node));
    new->data = x;
    new->next = TOP;
    TOP = new;
}
void pop()
{
    struct node *t;
    if (TOP == NULL)
        printf("underflow\n");
    else
    {

        t = TOP;
        TOP = TOP->next;
        free(t);
        t = NULL;
    }
}
// printf final ans.
void display()
{
    struct node *p;
    p = TOP;

    if (TOP == 0)
        printf("list is empty");
    else
    {
        while (p != NULL)
        {

            printf("%d -> ", p->data);
            p = p->next;
        }
    }
}

void main()
{

    push(10);
    push(20);
    push(30);
    pop();
    push(40);
    display();
}
