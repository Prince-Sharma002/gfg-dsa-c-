```
Input:
N = 3
arr = {2, 4, 3}
Output: 1
```

```
    struct Node {
        public:
        int data;
        Node* left;
        Node* right;
        Node(int data) {
            this->data = data;
            this->left = NULL;
            this->right = NULL;
        }
    }; 
    
    Node* solve(vector<pair<int, bool>> &vis, int mini, int maxi, int &i) {
        if (i >= vis.size())
            return NULL;

        if (vis[i].first > maxi || vis[i].first < mini)
            return NULL;

        Node* node = new Node(vis[i].first);
        vis[i].second = true;
        i++;

        node->left = solve(vis, mini, node->data, i);
        node->right = solve(vis, node->data, maxi, i);

        return node;
    }

    public:
        int canRepresentBST(int arr[], int N) {
        
        vector<pair<int, bool>> vis;
        for( int i=0 ;i<N ; i++ ){
            vis.push_back( { arr[i] , false } );
        }
        
        int i=0;
        
        Node* temp = solve(vis, INT_MIN , INT_MAX , i );
        
        for( int j=0 ; j<vis.size() ; j++ ){
            if(  vis[j].second == false )
                return 0;
        }   
        
        return 1;
    
    }
```
