```
Input:
N = 4
start[] = {1, 3, 2, 5}
end[] = {2, 4, 3, 6}
Output: 
3
Explanation:
A person can perform activities 1, 2
and 4.


    //comparator function used in sorting the list of pairs 
    //according to increasing order of the finish day.
    static bool pairCompare(const pair<pair<int, int>, int> &a,
                     const pair<pair<int, int>, int> &b) 
    {
        if (a.first.second != b.first.second) {
            return a.first.second < b.first.second;
        }
        return a.second < b.second;
    }
    
    
    //Function to find the maximum number of activities that can
    //be performed by a single person.
    int activitySelection(vector<int> start, vector<int> end, int n)
    {
    
        vector<pair<pair<int, int>, int>> x;
     
        //pushing the pair of starting and finish day and their 
        //index as pair in another list.
        for (int i = 0; i < n; i++) 
        x.push_back({{start[i], end[i]}, i + 1});
    
        //sorting the list.
        sort(x.begin(), x.end(), pairCompare);
        int last = 0;
        int res = 0;
        
        for (int i = 0; i < n; i++)
        {
            //if the starting day of this activity is greater than or equal
            //to the finish day of previously selected day then 
            //we increment the counter and update last.
            if (x[i].first.first > last) 
            {
                res++;
                last = x[i].first.second;
            }
        }
        //returning the counter.
        return res;
    }
```
