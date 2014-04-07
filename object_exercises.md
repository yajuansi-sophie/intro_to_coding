Objects, Classes and Modules
============================

### ABCTree

Write a class that implements the [Tree](https://en.wikipedia.org/wiki/Tree_data_structure) data structure. This isn't nearly as hard as you might think.

A simple way to do this would be to write two classes: `ABCTree` and `ABCTreeNode`.

`ABCTree` should be a fairly vanilla wrapper class. You should give it the property `root_node` which specifies the "topmost" node in the tree.

`ABCTreeNode` should have a few properties: `parent`, which specifies the parent node; `children`, which specifies a given node's child nodes; and `value`, the value of the node.

Each node manages its position in tree by keeping track of its parent and its children.

Remember to give yourself the option of setting the properties in the initialize method for each class.

### Search Module

Write a method that implements [Depth First Search](https://en.wikipedia.org/wiki/Depth-first_search). Searching for a value using DFS means that all child nodes are visited before any neighbors are visited.

Write a second method that implements [Breadth First Search](https://en.wikipedia.org/wiki/Breadth-first_search). Searching for a value using BFS means that all neighbor nodes are visited before any children are visited.

For each search method, print out the node values as your traverse the tree.

Include the module in your `ABCTree` and attempt to search the tree for a specific node.
