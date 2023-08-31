# Shortest path in Undirected Graph having unit distance

```
#include<unordered_map>
#include<list>
#include<queue>

vector<int> shortestPath( vector<pair<int,int>> edges , int n , int m, int s , int t){
	
	unordered_map< int , list<int>> adj;
	for( int i=0 ; i<edges.size() ; i++ ){
		int Node1 = edges[i].first;
		int Node2 = edges[i].second;

		adj[Node1].push_back(Node2);
		adj[Node2].push_back(Node1);
	}

	unordered_map<int,int> parent;
	unordered_map<int,bool> vis;

	queue<int> q;
	q.push( s );
	parent[s] = -1;
	vis[s] = true;

	while( !q.empty() ){
		int t = q.front();
		q.pop();

		for( auto i : adj[t] ){
			if( !vis[i] ){
				parent[i] = t;
				vis[i] = true;
				q.push( i );
			}
		}
	}
	
	int currNode = t;
	vector<int> ans;
	ans.push_back( t );
	while( currNode != s ){
		currNode = parent[currNode];
		ans.push_back( currNode );
	}

	reverse( ans.begin() , ans.end());
	return ans;
}
```
