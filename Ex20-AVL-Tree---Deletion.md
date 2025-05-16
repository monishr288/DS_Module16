# Ex20 AVL Tree - Deletion
## DATE: 16.5.25
## AIM:
To write a C function to delete an element from an AVL Tree.
## Algorithm
  

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: MONISH R
RegisterNumber:  212223220061
*/
node * Delete(node *T,int x)
{
node *p;
if(T==NULL)
{
return NULL;
}
else
if(x > T->data) // insert in right subtree
{
T->right=Delete(T->right,x);
if(BF(T)==2)
{
if(BF(T->left)>=0)
T=LL(T);
else
T=LR(T);
}}
else
if(x<T->data)
{
T->left=Delete(T->left,x);
if(BF(T)==-2) //Rebalance during windup
{
if(BF(T->right)<=0)
T=RR(T);
else
T=RL(T);
}}
else
{
//data to be deleted is found
if(T->right!=NULL)
{ //delete its inorder succesor
p=T->right;
while(p->left!= NULL)
p=p->left;
T->data=p->data;
T->right=Delete(T->right,p->data);
if(BF(T)==2)//Rebalance during windup
{
if(BF(T->left)>=0)
T=LL(T);
else
T=LR(T);}}
else
return(T->left);
}
T->ht=height(T);
return(T);
}
```

## Output:

![Screenshot 2025-05-16 201641](https://github.com/user-attachments/assets/5e7ef5d0-7406-4219-be2a-9c5aaa4c0f5e)


## Result:
Thus, the C program to delete an element from an AVL Tree is implemented successfully.
