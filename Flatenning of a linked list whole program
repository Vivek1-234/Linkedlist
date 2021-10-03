//code of a flatenning of a linnked list  -->>>>>

#include<iostream>
using namespace std;
class node{
    public:
    int data ;
    node* down;
    node* right;


    node(int val){
        data = val;
        right= NULL;
        down= NULL;
    }
};

node * merge(node* &a , node* &b){

    node* result ; 

    if(a==NULL ){
     return b ;
    }
    if(b==NULL ){
     return a ;
    }
    
    if(a->data<b->data){
        result = a;
        result->down = merge(a->down , b);
    }
    else{
        result = b ;
        result->down = merge(a , b->down);  

    }
    return result ;
}

node * flatenning(node* root ){

  if(root == NULL || root->right == NULL){
      return root ;
  }
    root->right = flatenning(root->right);
     
     root = merge(root , root->right);

     return root ;

}





node* push(node* &head , int val) {
    node* newnode = new node(val);
    newnode->down = head;
    head = newnode;

    return head;
}

void display(node* head)
{
    node* temp = head ; 
    while(temp!=NULL){
        cout<<temp->data<<" ";
        temp = temp->down;
    }
    cout<<endl;
}
int main(){
    node* head = NULL;
push(head  , 20);
push(head  , 10);
push(head  , 5);
push(head  , 2);

push(head->right , 50);
push(head->right , 40);
push(head->right , 30);
push(head->right , 8);
push(head->right , 3);

push(head->right->right , 200);
push(head->right->right , 180);
push(head->right->right , 170);
push(head->right->right , 160);
push(head->right->right , 150);

 flatenning(head);
display(head);


return 0;
 }
