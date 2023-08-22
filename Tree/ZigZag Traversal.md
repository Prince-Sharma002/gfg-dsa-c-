#ZigZag Travsersal
```
    //Function to store the zig zag order traversal of tree in a list.
    vector <int> zigZagTraversal(Node* root)
    {
        stack<Node*> st1;
        stack<Node*> st2;
        vector<int> ans;
        bool dir = true;
        
        st1.push(root);
        while( !st1.empty() ){
            Node* temp = st1.top();
            st1.pop();
            
            ans.push_back( temp->data );
            
            if( temp ){
                if( dir ){
                    if( temp->left )
                        st2.push( temp->left);                    
                    if(temp->right)
                        st2.push(temp->right);
                }
                else{
                    if(temp->right)
                        st2.push(temp->right);
                    if( temp->left )
                        st2.push( temp->left);                     
                }
                
            }
            
            if( st1.empty() ){
                dir = !dir;
                swap( st1, st2 );
            }
        }
        
        return ans;
    }
```
