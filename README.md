# DFS

#include<stdio.h>
#define MAX 50
int visited[MAX];
int graph[MAX][MAX];
int n;
void readGraph()
{
    printf("Enter size of the Adjacency Matrix :\n");
    scanf("%d",&n);
    printf("Enter Adjacency Matrix :\n");
    for(int i=1;i<=n;i++)
    {
        for(int j=1;j<=n;j++)
        {
            scanf("%d",&graph[i][j]);
        }
    }
}
void DFS(int v)
{
    visited[v]=1;
    printf("%d ",v);
    for(int i=1;i<=n;i++)
    {
        if(visited[i]==0 && graph[v][i]==1)
        {
                visited[i]=1;
                DFS(i);
        }
    }
}
void main()
{
    readGraph();
    printf("Depth First Search :\n");
    for(int j=1;j<=n;j++)
    {
        printf("Graph Start at vertex %d\n",j);
        for(int i=1;i<=n;i++)
        {
            visited[i]=0;
        }
        DFS(j);
        printf("\n");
    }
}

OUTPUT:
Enter size of the Adjacency Matrix :
4
Enter Adjacency Matrix :
0
1
1
0
1
0
0
1
1
0
0
1
0
1
1
0
Depth First Search :
Graph Start at vertex 1
1 2 4 3 
Graph Start at vertex 2
2 1 3 4 
Graph Start at vertex 3
3 1 2 4 
Graph Start at vertex 4
4 2 1 3 
