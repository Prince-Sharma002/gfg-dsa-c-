```
Input: Jobs = [[1,4,20],[2,1,1],[3,1,40],[4,1,30]]
Output: 2 60
Explanation: Job1 and Job3 can be done with maximum profit of 60 (20+40).
```


```
    bool static cmp(Job a, Job b){
        return a.dead < b.dead;
    }
    vector<int> JobScheduling(Job arr[], int n) 
    {
        sort(arr, arr+n, cmp);
        priority_queue<int, vector<int>, greater<int>> pq;
        int curr = 1;
        
        for(int i = 0; i < n; i++){
            if(arr[i].dead >= curr){
                pq.push(arr[i].profit);
                curr++;
            }else {
                if(arr[i].profit > pq.top()){
                    pq.push(arr[i].profit);
                    pq.pop();
                }
            }
        }
        
        int total = 0;
        int job = pq.size();
        
        while(!pq.empty()){
            total += pq.top();
            pq.pop();
        }
        return {job, total};
    } 
```
