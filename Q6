// Write a C program that uses linked lists to represent two polynomials, adds them, and displays the resulting polynomial.
#include <stdio.h>
#include <stdlib.h>

struct node {
    int coeff, pow;
    struct node *next;
};

struct node* insert(struct node *head, int c, int p) {
    struct node *newnode = (struct node*)malloc(sizeof(struct node));
    newnode->coeff = c;
    newnode->pow = p;
    newnode->next = NULL;
    if (head == NULL)
        return newnode;
    struct node *temp = head;
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newnode;
    return head;
}

struct node* add(struct node *p1, struct node *p2) {
    struct node *res = NULL;
    while (p1 && p2) {
        if (p1->pow == p2->pow) {
            res = insert(res, p1->coeff + p2->coeff, p1->pow);
            p1 = p1->next; p2 = p2->next;
        } else if (p1->pow > p2->pow) {
            res = insert(res, p1->coeff, p1->pow);
            p1 = p1->next;
        } else {
            res = insert(res, p2->coeff, p2->pow);
            p2 = p2->next;
        }
    }
    while (p1) {
        res = insert(res, p1->coeff, p1->pow);
        p1 = p1->next;
    }
    while (p2) {
        res = insert(res, p2->coeff, p2->pow);
        p2 = p2->next;
    }
    return res;
}

void display(struct node *head) {
    struct node *temp = head;
    while (temp != NULL) {
        printf("%dx^%d", temp->coeff, temp->pow);
        if (temp->next != NULL)
            printf(" + ");
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct node *p1 = NULL, *p2 = NULL, *sum = NULL;
    int n, c, p;
    printf("Enter number of terms in first polynomial: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter coeff and power: ");
        scanf("%d%d", &c, &p);
        p1 = insert(p1, c, p);
    }

    printf("Enter number of terms in second polynomial: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter coeff and power: ");
        scanf("%d%d", &c, &p);
        p2 = insert(p2, c, p);
    }

    printf("\nFirst Polynomial: ");
    display(p1);
    printf("Second Polynomial: ");
    display(p2);

    sum = add(p1, p2);
    printf("Sum = ");
    display(sum);
}
