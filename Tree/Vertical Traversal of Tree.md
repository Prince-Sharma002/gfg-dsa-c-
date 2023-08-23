# Vertical Traversal of Tree


### using map and recursion traversal
```
void getVerticalOrder(Node* root, int hd,
                      map<int, vector<int> >& m)
{
    // Base case
    if (root == NULL)
        return;
 
    // Store current node in map 'm'
    m[hd].push_back(root->data);
 
    // Store nodes in left subtree
    getVerticalOrder(root->left, hd - 1, m);
 
    // Store nodes in right subtree
    getVerticalOrder(root->right, hd + 1, m);
}
    
    
    vector<int> verticalOrder(Node *root)
    {
        map<int, vector<int> > m;
        int hd = 0;
        getVerticalOrder(root, hd, m);
        vector<int> ans;
        
        map<int, vector<int> >::iterator it;
        for (it = m.begin(); it != m.end(); it++) {
            for (int i = 0; i < it->second.size(); ++i)
                ans.push_back( it->second[i] );
        }
    
    return ans;
    
    }

```

### By using queue
```
vector <int> res;
        //creating a map to store nodes at a particular horizontal distance.
        map<int,vector<int>>mp;
        
        //creating empty queue for level order traversal.
        queue<pair<Node*,int>>q;
        q.push({root,0});
        
        while(!q.empty())
        {
            pair<Node*,int> temp=q.front();
            Node* temp_root=temp.first;
            int distance=temp.second;
            mp[distance].push_back(temp_root->data);
            q.pop();
            
            //if left child of temp_root exists, pushing it in
            //the queue with the horizontal distance.
            if(temp_root->left)
            {
                q.push({temp_root->left,distance-1});
            }
            //if right child of temp_root exists, pushing it in
            //the queue with the horizontal distance.
            if(temp_root->right)
            {
                q.push({temp_root->right,distance+1});
            }
        }
        
        //traversing the map and storing the nodes in list 
        //at every horizontal distance.
        for(auto it=mp.begin();it!=mp.end();it++)
        {
            vector<int> ans=it->second;
            
            for(auto x:ans)
                res.push_back (x);
        }
        //returning the output list.
        return res;
```




```
