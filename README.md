# A-greedy-algorithm
(1) Find the point which has the minimum cost to the goal state as the current point
from the open table;
(2) Input the current point into the close table;
(3) Test 8 points of the current point( 8 directions：up, down, right, left, right-up, left-up, right-down,
left-down), if thosepoints exist and are not in the close table, repeat below works:
(4) If one of them equal the goal state, the current point is the parent point and exit
loop;
(5) If one of them does not exist in the open table, calculate the cost from it to the
goal state and make the current point as its parent point, and add it into the open
table;
(6) If one of them exists in the open table, compare the cost from it to the goal state
with that of the current point. If the cost of it is smaller, the current is the parent
point. At the same time, resort values 

If we complete the loop, we can find a whole path, from the goal state, search for the
parent point until find the start point.
If it is hard to make it sense, we can use the below pseudo-code to help understand
better. pseudo-code

While(open table is not null){
Get a point x from the open table, and delete it from the open table;
If (x equals the goal state){
Get the right path;
Return the right path;}
For (each son node Y of point x){
If (Y does not exist in the open table and the close table){
Calculate the cost from Y to the goal state;
Add Y into the open table;
}else if(Y exists in the open table){
If(the cost from Y to the goal state is smaller than that of the optimal
node of the open table){
Update the cost of the optimal node of the open table;}
Else{//Y exists in the close table
If(the cost from Y to the goal state is smaller than that of the optimal
node of the close table){
Update the cost of the optimal node of the close table;
Add Y into the open table;}
}
}
Input point x into the close table;
Resort the open table by the cost of each point;
}



Further Question
At this time, I found a question that if we have some known goal states, we have to
plan a appropriate route. Because if we just make the agent get to each goal state
orderly, it is likely to waste much cost and time. So in order to avoid extra cost and
time, I think we can sequence all goal states in the order of small to large, which
means the agent always chooses the closest goal to get to.

This question mainly tells us when we have several targets at the same
time, not only does we need to use A* algorithm to get a optimal route to each
target, but also sequence these targets according to their own distances that from
the start state to their goal states.
