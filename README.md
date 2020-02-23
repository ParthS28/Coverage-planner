# Coverage-planner

In this repository I have implemented two algorithms for effective complete coverage of a given map with obstacles.

# Leftwall algorithm

In this algorithm, I have tried to incorporate the leftwall sticking algorithm which effectively a maze solving algorithm to colve this problem. 

First, I have assumed that we would know the starting position. I have assumed it is sticking to the top wall first but you can change it to your liking by changing the initial direction and starting position. 
Each time it covers a cell, that cell is marked by changing its value and not allowing the to overlap those cells. Each time it comes to a cell already visited or if comes to an endpoint, it takes a right turn.

Effectively, we are just making sure that it always has a wall or an already visited cell to the left of it. 

Now, when it reaches a dead point it would complete a whole 360 degree turn without finding a direction to move in. So, to solve this I have implemented Dijkstra's shortest path algorithm to get the next free spot. After reaching the next free spot it continues the same traversal algorithm as before.

# Cellular decomposition

For this algorithm, I have tried to implement the paper I have uploaded in the repository. Unfortunately, I was not able to implement it properly but it works satisfactory.

I have used https://blog.csdn.net/u013859301/article/details/83747866 as a reference, although I have not used the same exact code, I am inspired by this and I would not have been able to do it without it. Do check it out if you want.

If you read the paper, it would be quite clear what I have done. But I will still brief it up in a few lines.
First, we need to divide the map into smaller cells so that we can cover each cell effectively with least overlap. There are several ways to decompose your map into cells, I happen to use this one. After dividing your map, we need to traverse these cells in an order which minimizes the overlap. This is done using DFS, which is a graph theory. To implement this, I consider each cell as a node in the graph. After we have the order, the problem is just to traverse the cells. Since all our cells rectangle, this problem becomes easy. All I have to do is traverse the cell going up-down till I reach the end of the cell and after this I enter the next cell in the order using the closest entry point(the vertices of the rectangle). 

Note: I will soon add comments to the code, but till then feel free to contact me if you want to discuss something. 
Email: parthshukla285@gmail.com
