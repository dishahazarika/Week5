//Implement a C program for a circular doubly linked list with functions to insert a node at the end and delete a node from the beginning. 
#include <stdio.h>
#include <stdlib.h>

struct node {
    int data;
    struct node *prev, *next;
};
struct node *head = NULL;

void insert_end() {
    struct node *newnode = (struct node*)malloc(sizeof(struct node));
    printf("Enter data: ");
    scanf("%d", &newnode->data);
    if (head == NULL) {
        head = newnode;
        head->next = head->prev = head;
    } else {
        struct node *last = head->prev;
        last->next = newnode;
        newnode->prev = last;
        newnode->next = head;
        head->prev = newnode;
    }
}

void delete_begin() {
    if (head == NULL)
        printf("List empty\n");
    else if (head->next == head) {
        free(head);
        head = NULL;
    } else {
        struct node *temp = head;
        struct node *last = head->prev;
        head = head->next;
        head->prev = last;
        last->next = head;
        free(temp);
    }
}

void display() {
    if (head == NULL) {
        printf("Empty list\n");
        return;
    }
    struct node *temp = head;
    printf("List: ");
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while (temp != head);
    printf("\n");
}

int main() {
    int ch;
    while (1) {
        printf("\n1.Insert at End\n2.Delete from Beginning\n3.Display\n4.Exit\nEnter choice: ");
        scanf("%d", &ch);
        switch (ch) {
            case 1: insert_end(); break;
            case 2: delete_begin(); break;
            case 3: display(); break;
            case 4: exit(0);
            default: printf("Invalid choice\n");
        }
    }
}
