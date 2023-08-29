# Adjancy list Graph Implementation 

```
#include <iostream>
#include <queue>
#include <unordered_map>
#include <list>
using namespace std;

class graph{
   public:
   unordered_map<int , list<int>> adj;
       
   void addEdge( int u , int v , int dir ){
    //    dir = 0 is directed graph
       if( dir == 0)
       {
           
            adj[u].push_back(v);
       }
       
   }
    
    void printGraph(  ){
        for( auto i : adj ){
            cout << i.first << "->";
            for( auto j : i.second ){
                cout << j << " ";
            }
            cout << endl;
        }
    }
    
} ;


// Driver code
int main()
{
    int n;
    cout << "enter number of nodes : " << endl;
    cin >> n;
    
    cout << endl;

    int m;
    cout << "enter number of edges : " << endl;
    cin >> m;
    
    graph g;
    cout << "insert edges : " << endl;
    for( int i=0 ; i<m ; i++ ){
        int u , v;
        cin >> u >> v ;
        g.addEdge( u , v , 0 );
    }
    
    g.printGraph();
    
   return 0;
}
```
