#include<iostream>
#include<cstdlib>
using namespace std;
struct node
{
	int data;
	struct node *left,*right;
};
struct node *Newnode(int val)
{
	 struct node* temp = (struct node *) malloc(sizeof(struct node *));
	 temp->data=val;
	 temp->left=temp->right=NULL;
	 return(temp);
}

struct node *insert(int val,struct node* root)
{
	 if(root==NULL) return Newnode(val);
	 else if(val<root->data)
	 {
	 	 root->left=insert(val,root->left);
	 }
	 else if(val>=root->data)
	 {
	 	root->right= insert(val,root->right);
	 }
	   return (root);
	 }

	 void inorder(struct node* root)
	 {
	 	 if(root!=NULL)
	 	 
	 	   {  inorder(root->left);
	 	 	 cout<<"\t"<<root->data;
	 	 	 inorder(root->right);
	 	 }
	 }

int main()
{
	 struct node* root=NULL;
	 root=insert(7,root);
	 insert(60,root);
	 insert(40,root);
	 insert(30,root);
	 insert(45,root);
	 insert(70,root);
	 insert(55,root);
	 inorder(root);
	 return (0);
}
