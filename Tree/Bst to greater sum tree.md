# Bst to greater sum tree

```
    void inorder( struct Node* root , map<int,int> &ans){
        if( !root )
            return ;
        
        inorder( root->left , ans);
        ans.insert( make_pair( root->data , root->data) );
        inorder( root->right , ans);
        
    }
    
    void modify( struct Node* root , map<int,int> &ans ){
        static int i=0;
        if( !root )
            return ;
        
        modify( root->left , ans );
        root->data = ans[root->data];
        modify( root->right , ans );
    }
    
    void transformTree(struct Node *root)
    {
        
        map< int , int > ans;
        inorder( root , ans );
        
        int s = 0;
        for( auto it = ans.rbegin() ; it != ans.rend() ; it++ ){
            int t = it->second;
            it->second = s;
            s += t;
        }
        modify( root , ans );
        
    }
```
