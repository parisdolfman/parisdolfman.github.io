---
layout: post
title:      "Linked Lists "
date:       2019-04-11 18:26:54 +0000
permalink:  linked_lists
---


A linked list is an alternative data structure to an array. Arrays have some drawbacks that can be solved using linked lists. These drawbacks we will detail further in this post.

Linked lists store the data associated with each element as well as a pointer, or link, to the next address in memory where the next element lives. Each element is referred to as a node. A linked list is comprised of nodes, with the first node being the head node and the last node being the tail. Each node has it's own memory address, a value, and the memory address of the next node. 

Javascript does not have a built in library to represent a linked list, and so we must represent reach node as an array. The first element of the node is it's value, and the second element is the next node's memory address. Example:

**let nodeOne: ['rain', 110]
let nodeTwo: ['river' , 112]
let nodeThree: ['ocean', 114 ]
let nodeFour: ['fish', null]**

**let collection = {0: nodeOne, 110:  nodeTwo, 112: nodeThree, 114: nodeFour}
let head = nodeOne**

The nodes above are being stored as an object, with each one referencing the next until we reach the tail node. Below we have written a function that returns the next node in a linked list. 

**function nextNode(node) {          
  let nextAddress = node[1]        
  return collection[nextAddress] 
}**

In the function above, we pass the node in as a parameter. When this function is called, node will be the actual argument. We then set nextAddress to equal the second element of the node passed, which is the memory addess. Finally, we access this second element of the node using collection[nextAddress]. Essentially we are traveling through the object to access the next memory address in this way: collection > node > second element of node.

Below we will write a function that accesses and returns a node at the provided index. For reference, linked lists are zero indexed.

**let nodeOne: ['rain', 110]
let nodeTwo: ['river' , 112]
let nodeThree: ['ocean', 114 ]
let nodeFour: ['fish', null]**

**let collection = {0: nodeOne, 110: nodeTwo, 112:  nodeThree, 114: nodeFour}
let head = collection[0]**

**function nextNode(node) {          
  let nextAddress = node[1]        
  return collection[nextAddress] 
}**

**function indexNode(head, index) {
  let node = head
	for (counter = 0; counter < index; counter++) {
	node = nextNode
	}
	return node
}**

First we create our object and store our nodes with values and memory addresses of their next linked node. Then we set our collection to equal our linked list array. After, we set our head to equal the first element in the linked list array. 

In our function we have two parameters set: head and index. Our node is set to equal the head node because we cannot access nodes at random. 

Using an if statement we initially set our conter to equal 0, allow the if statement to run only when the counter is lower than the index parameter, and increment the counter each time our statement executes. 

When the index number matches the counter, the node is set to equal nextNode which relies on the function we first wrote. Lastly, we return the node. 

When called using indexNode(head, 2) we see a return of ['ocean', '114'].
