# Maximum value in each Level
```
vector<int> maximumValue(Node* node) {
    queue<Node*> q;
    int maxi = INT_MIN;  // Initialize maxi to the minimum possible value
    vector<int> ans;
    
    if (node)
        q.push(node);
    
    while (!q.empty()) {
        int levelSize = q.size();  // Store the current level size
        
        for (int i = 0; i < levelSize; ++i) {
            Node* temp = q.front();
            q.pop();
            
            // Update maximum value for the current level
            maxi = max(maxi, temp->data);
            
            if (temp->left)
                q.push(temp->left);
            if (temp->right)
                q.push(temp->right);
        }
        
        ans.push_back(maxi);  // Store the maximum value for the current level
        maxi = INT_MIN;  // Reset maxi for the next level
    }
    
    return ans;
}

```
