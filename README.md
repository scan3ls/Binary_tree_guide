0. New Node
	- create a node with the given structure
	- return the new node

1. Insert left
	- create a node with the given structure
		as the left child of a given node
	- any existing left child nodes are set
		to the left child of the new node
	- use node insertion [method](Images/Insertion_of_binary_tree_node.PNG)
		
		With node A haiving a left-child of node B and right-child of node C
		Create new node D with values of:  
			value: any  
			parent: node A  
			left: node B  
			right: any/NULL  
		Change node A with values of:  
			value: no change  
			parent: no change  
			left: node D  
			right: no change  
		
2. Insert right
	- create a node with the given structure
	as the right child of a given node
	- any existing left child nodes are set
		to the right child of the new node
	- use node insertion [method](Images/Insertion_of_binary_tree_node.PNG)
		
		With node A haiving a left-child of node B and right-child of node C  
		Create new node D with values of:  

			value: any  
			parent: node A  
			left: any/NULL  
			right: node C
			 
		Change node A with values of:  
		
			value: no change  
			parent: no change  
			left: no change  
			right: node C  

3. Delete
	- Deletes an entire binary tree given a root node
	- recursive??
	- use [Post-order Traversal](Images/Post_order_traversal.PNG) to free lowest level first
	- free node

4. Is leaf
	- checks if given node is a leaf
	- Definition:
		Leaf − The node which does not have any child node is called the leaf node
	- Condition:
		If node is not NULL  
		and  
		If left child is NULL  
		and  
		If right child is NULL  
	- return 1 or 0

5. Is root
	- checks if given node is a root
	- Definition:
		Root − The node at the top of the tree is called root. There is only one root 
				per tree and one path from the root node to any node.
	-  Condition:
		If node is not NULL  
		and  
		If parent is NULL  
	- return 1 or 0

6. [Pre-order traversal](Images/Pre_order_traversal.PNG)
	- goes through tree using [pre-order traversal](Images/Pre_order_traversal.PNG)
	- print node value at each step

7. [In-order traversal](Images/In_order_traversal.PNG)
	- goes through tree using [in-order traversal](Images/In_order_traversal.PNG)
	- print node value at each step

8. [Post-order traversal](Images/Post_order_traversal.PNG)
	- goes through tree using [post-order traversal](Images/Post_order_traversal.PNG)
	- print node value at each step

9. Height
	- measures the height of a tree from a given node
	- use [pre-order traversal](Images/Pre_order_traversal.PNG)
	- return 0 on leaf node
	- calc left height and right height recursively
	- use larger of the two heights
	- Condition:
		If left height < right height  
			return right height + 1  
		else  
			reutrn left height + 1  

10. Depth
	- measures the dpth of a tree from a given node
	- NO RECURSION :)
	- basic loop: count all parents to root
	- return count

11. Size
	- measure size of a tree at a given node at a given node
	- use any traversal method:
		[pre-order traversal](Images/Pre_order_traversal.PNG)
		[in-order traversal](Images/In_order_traversal.PNG)
		[post-order traversal](Images/Post_order_traversal.PNG)
	- increament a counter at each step
	- return counter

12. Leaves
	- counts the number of leaf nodes in a tree at a given node
	- Definition:
		Leaf − The node which does not have any child node is called the leaf node
	- use any traversal method:
		[pre-order traversal](Images/Pre_order_traversal.PNG)  
		[in-order traversal](Images/In_order_traversal.PNG)  
		[post-order traversal](Images/Post_order_traversal.PNG)  
	- increament a counter at each step only if node is a leaf node
	- Condition:
		If (binary_tree_is_leaf(const binary_tree_t *node) == 1 (true))  
			counter + 1  
	- return counter

13. Nodes
	- counts the number of non-leaf nodes in a tree at a given node
	- Definition:
		Leaf − The node which does not have any child node is called the leaf node
	- use any traversal method:
		[pre-order traversal](Images/Pre_order_traversal.PNG)  
		[in-order traversal](Images/In_order_traversal.PNG)  
		[post-order traversal](Images/Post_order_traversal.PNG)  
	- increament a counter at each step only if node is a leaf node
	- Condition:
		If (binary_tree_is_leaf(const binary_tree_t *node) == 0 (false))  
			counter + 1  
	- return counter

14. Balance factor
	- measures the balance factor of a tree at a given node
	- Definition:  
		balanceFactor = height(leftSubTree) - height(rightSubTree)
	- height(leftSubTree) = binary_tree_height(node->left)
	- height(rightSubTree) = binary_tree_height(node->right)
	- balanceFactor = binary_tree_height(node->left) - binary_tree_height(node->right)
	- return balanceFactor

15. Is full
	- checks if a binary tree is full at a given node
	- Definition:
		A perfect binary tree is a tree in which every node has either 0 or 2 children  
		eg. Number of leaf nodes == Height of tree * 2

	- recursive
	- Conditions:  
		If empty  
			return true  
		
		If isLeafNode  
			return true  

		If left not NUll && right not NULL  
			return isFull(node->left) && isFull(node->right)  

		//base  
		return false

16. Is perfect
	- checks if a binary tree is full at a given node
	- Definition:  
		A perfect binary tree is a binary tree in which all interior nodes have two children
		and all leaves have the same depth or same level.  
		eg. Number of leaf nodes == Height of tree * 2

	- count leaf nodes -> 			leafs = binary_tree_leaves(const binary_tree_t *tree)  
	- calc height -> 				hegiht = binary_tree_height(const binary_tree_t *tree)  
	- Condition:  
		If (leafs == (height * 2))  
			return (1)  
		else  
			return (0)  

17. Sibling
	- finds the sibling of a node
	- find left and right of parent node
	- return node of different value or NULL

18. Uncle
	- finds uncle of a node
	- uncle is parent sibling
	- *binary_tree_sibling(node->parent)