# link_list
#include <iostream>
#include <cstddef>
using namespace std;

class Node{
    public:
        int data;
    Node * next;
};

void print_list(Node  *n)
{
    cout<<"print list of node"<<endl;

    while(n != NULL){
        cout<<n->data<<endl;
        n = n->next;
    }
}

void push(struct Node **head_ref ,  int new_data)
{
    struct Node * new_node = (struct Node * ) malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = (* head_ref);
    (* head_ref) = new_node;

}


int main()
{
    cout<<"link list"<<endl;
    Node * head ;
    Node * second;


    head = new Node();
    second = new Node();

    head->data = 12;
    head->next = second;

    second->data = 13;
    second->next = NULL;

    // cout<< "head data "<< head->data<<endl;
    // cout<< "second data "<< second->data<<endl;

    print_list(head);
    push(&head,1000);
    cout<<"after push"<<endl;
    print_list(head);

    return 0;
}
