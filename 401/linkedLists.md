# Linked Lists


Linked Lists
What is a Linked List
A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation.

Terminology:
Linked List - A data structure that contains nodes that links/points to the next node in the list.
Singly - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.
Doubly - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.
Next - Each node contains a property called Next. This property contains the reference to the next node.
Head - The Head is a reference type of type Node to the first node in a linked list.
Current - The Current reference is a reference type of type Node that is currently being looked at. This node is traditionally used when traversing through a full linked list. When traversing, you typically reset the current to the head to guarantee you are starting from the beginning of the linked list.
What does it look like
This is what a Singly Linked List looks like

Singly Linked List

Traversal
When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing. The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.

The best way to approach a traversal is through the use of a while() loop. This allows us to continually check that the Next node in the list is not null. If we accidentally end up trying to traverse on a node that is null, a NullReferenceException gets thrown and our program will crash/end.

When traversing through a linked list, the Current node is the most helpful. The Current will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.

Example
Let’s put a use case on our traversal. We want to check whether or not our LinkedList Includes a specific value.

The pseudo-code for an Includes is as so:

		ALGORTIHM Includes (value)
		// INPUT <-- integer value
		// OUTPUT <-- boolean
			
			Current <-- Head

			WHILE Current is not NULL
				IF Current.Value is equal to value
					return TRUE

				Current <-- Current.Next

			return FALSE
Let’s talk out what exactly is happening:

We are first setting Current to the Head to guarantee we are starting from the beginning. (Remember that Head is always the first node in a Linked List)

We create a while loop. This loop will only run if the node that Current is pointing to is not null. This also means we can guarantee that we are still looking at a Node while the loop is running.

Once we are in the while loop, we are checking if the value of the current node is equal to the value we are looking for. Given the logic, if that condition is true, then we have found the value we were looking for, so we return true.

If the Current node does not contain the value we are looking for, we then must move Current to the next node that is being referenced. Again, because the condition of this while loop is to only run if we are still at a node, we can safely traverse to the next node without fear of getting a NullReferenceException.

At this point, the while loop is re-evaluated. Step 3 & 4 will continue until Current reaches the end of the LinkedList. We will know we are at the last node in the linked list because the current node will be null. Once this condition becomes true, the while loop breaks, and we now know that we are at the end.

Once we hit the end, we know that we did not find the value and return true at any point, so the value is not in the LinkedList. We return false.

Big O
The Big O of time for Includes would be O(n). This is because, at its worse case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.

The Big O of space for Includes would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.

Adding a Node
Adding O(1)
Order of operations is extremely important when it comes to working with a Linked List. What I mean by this is you must be careful that all references to each link/node is properly assigned.

An example can be with adding a node to a linked list. If we want to add a node with an O(1) efficiency, we have to replace the current Head of the linked list with the new node, without losing the reference to the next node in the list.

Here are the required steps to add a new node with an O(1) efficiency.

Set Current equal to Head. This will guarantee us that we are starting from the very beginning.
We can then instantiate the new node that we are adding. The values passed in as arguments into the Add() method will define what the value of the Node will be.
Singly Linked List

newNode.Next by default is set to null. We want to set newNode.Next property to the same location that the Head node is pointing towards. Because Head is just a reference type, we will be assigning it to the same allocation in memory as the node it is pointing too. In this case, it’s Node1.
Singly Linked List

At this point in the program we now “technically” have newNode at the beginning of the linked list, but we are not done yet. We now have to re-assign where Head is pointing too. Since Node1 is no longer the first node in the list, we want to re-assign Head to point at newNode.

While we are at it, let’s just re-assign current as well to make sure should any further operation start at the new true start of the linked list.

Singly Linked List

Code
Here is the Pseudo code for an Add method on a Linked list

		ALGORITHM Add(newNode)
		// INPUT <-- Node to add 
		// OUTPUT<-- No output

			Current <-- Head
			newNode.Next <-- Head
			Head <-- newNode
			Current <-- Head
Big O
Regardless of the number of Nodes that this linked list has, it will always be a O(1) time and space because it takes the same amount of time to add a new node to the beginning of the list, and no additional resources are being used

Adding a Node O(n)
Adding a node to the middle of a linked list is a bit different than adding to the beginning. This is because we are working with more nodes and must re-allocate to make room for the new node.

Let’s start out with a basic Singly Linked List:
Singly Linked List

Now let’s create a new node (node6). We will set the value of node6 to be 16. The Next will be null because we haven’t yet attached it into the linked list.
Singly Linked List

Now let’s start the adding. We can do an AddBefore method or an AddAfter. For this documentation, we will do an AddBefore. The AddAfter is extremely similar…see if you can figure it out on your own!
Our AddBefore method that we will demonstrate will insert node6 before node4.

We already learned how to traverse earlier, and that is exactly what we want to do now. We will traverse while the next node is not null. Before moving Current to the next node, we want check if the value of the next node is equal to the value we are supposed to be watching for (the value of the existing node we are inserting before). If it is, we want to set the new node (node6)’s .Next equal to the existing node.

Singly Linked List

The Linked List image above is in the following state:

Current is pointing to node3.
node3.Next property is equal to node4.
Since this is the node we want to insert before, we can now set our node6.Next property also to node4. We do this at the time the node is found to prevent setting node6.Next to a node that may not exist.
Uh-Oh, now both node3 and node6 are pointing to the same next node. node6 is not quite fully apart of the linked list.
Next, we have to adjust node3.Next to point to the newly created node, node6. Since we still have Current pointing to node3 this will be a straightforward transaction. We just simply tell Current (because it is pointing to the same memory location as node3) to change it’s Next to point to the new node (node6).
Singly Linked List

And now we have a complete link list with the newly added node exactly where we wanted it.

Singly Linked List

Code
Here is the Pseudo code for an AddBefore method in a linked list

		ALGORITHM AddBefore(newNode, existingNode)
		// INPUT <-- New Node, Existing Node
		// OUTPUT <-- No Output

			Current <-- Head

			while Current.Next is not equal to NULL
				if Current.Next.Value is equal to existingNode.Value
					newNode.Next <-- existingNode
					Current.Next <-- newNode

				Current <-- Current.Next;		
Big O
The time efficiency of this transaction would be O(n) because we could be inserting the new node, worst case scenario, at the end. With n being the number of nodes possible, we would therefore have O(n) time efficiency.

Space efficiency would stay at an O(1) because, like before, no additional space is being used allocated outside of what is given to us on the input

Print Out Nodes
Printing out all of the nodes in a Linked List is very similar to what we did in the Find() method. This is because we are leveraging our Current node and a while loop to traverse through the existing linked list.

Here is the pseudo code for a method to print out all the nodes in a linked list:

		ALGORITHM Print()
		// INPUT <-- None
		// OUTPUT <-- string to console

			Current <-- Head

			while Current.Next is not equal to NULL
				OUTPUT <-- "Current.Value --> "
				Current <-- Current.Next

			OUTPUT <-- "Current.Value --> NULL"
Much like in the Find, we are creating a while loop to check and make sure we are not at the end of a linked list. Right before the while loop restarts, we move Current to equal the next node in the list.

Once we hit the end, we write out the last node, and then show that it is pointing to null.

Prerequisites
When constructing your code, a few things to keep in mind.

When making your Node class, consider requiring a value to be passed in to require that each node has a value.

When making a Linked List, you may want to require that at least one node gets passed in upon instantiation. This first node is what your Head and Current will point too.



------------------------------------------------------------------------------------------------------

Linear data structures
If we really want to understand the basics of linked lists, it’s important that we talk about what type of data structure they are.
One characteristic of linked lists is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed. We can think of a linear data structure like a game of hopscotch: in order to get to the end of the list, we have to go through all of the items in the list in order, or sequentially. Linear structures, however, are the opposite of non-linear structures. In non-linear data structures, items don’t have to be arranged in order, which means that we could traverse the data structure non-sequentially.

Memory management
The biggest differentiator between arrays and linked lists is the way that they use memory in our machines. Those of us who work with dynamically typed languages like Ruby, JavaScript, or Python don’t have to think about how much memory an array uses when we write our code on a day to day basis because there are several layers of abstraction that end up with us not having to worry about memory allocation at all.
But that doesn’t mean that memory allocation isn’t happening! Abstraction isn’t magic, it’s just the simplicity of hiding away things that you don’t need to see or deal with all of the time. Even if we don’t have to think about memory allocation when we write code, if we want to truly understand what’s going on in a linked list and what makes it powerful, we have to get down to the rudimentary level.
We’ve already learned about binary and how data can be broken up into bits and bytes. Just as characters, numbers, words, sentences require bytes of memory to represent them, so do data structures.
When an array is created, it needs a certain amount of memory. If we had 7 letters that we needed to store in an array, we would need 7 bytes of memory to represent that array. But, we’d need all of that memory in one contiguous block. That is to say, our computer would need to locate 7 bytes of memory that was free, one byte next to the another, all together, in one place.
On the other hand, when a linked list is born, it doesn’t need 7 bytes of memory all in one place. One byte could live somewhere, while the next byte could be stored in another place in memory altogether! Linked lists don’t need to take up a single block of memory; instead, the memory that they use can be scattered throughout.

The fundamental difference between arrays and linked lists is that arrays are static data structures, while linked lists are dynamic data structures. A static data structure needs all of its resources to be allocated when the structure is created; this means that even if the structure was to grow or shrink in size and elements were to be added or removed, it still always needs a given size and amount of memory. If more elements needed to be added to a static data structure and it didn’t have enough memory, you’d need to copy the data of that array, for example, and recreate it with more memory, so that you could add elements to it.
On the other hand, a dynamic data structure can shrink and grow in memory. It doesn’t need a set amount of memory to be allocated in order to exist, and its size and shape can change, and the amount of memory it needs can change as well.
By now, we can already begin to see some major differences between arrays and linked lists. But this begs the question: what allows a linked list to have its memory scattered everywhere? To answer this question, we need to look at the way that a linked list is structured.

Parts of a linked list
A linked list can be small or huge, but no matter the size, the parts that make it up are actually fairly simple. A linked list is made up of a series of nodes, which are the elements of the list.
The starting point of the list is a reference to the first node, which is referred to as the head. Nearly all linked lists must have a head, because this is effectively the only entry point to the list and all of its elements, and without it, you wouldn’t know where to start! The end of the list isn’t a node, but rather a node that points to null, or an empty value.

A single node is also pretty simple. It has just two parts: data, or the information that the node contains, and a reference to the next node.
If we can wrap our heads around this, then we’re halfway there. The way that nodes work is super important, and super powerful, and could be summarized as this:
A node only knows about what data it contains, and who its neighbor is.

A single node doesn’t know how long the linked list is, and it may not necessarily even know where it starts, or where it ends. All a node is concerned with is the data it contains, and which node its pointer references to — the next node in the list.
And this is the very reason why a linked list doesn’t need a contiguous block of memory. Because a single node has the “address” or a reference to the next node, they don’t need to live right next to one another, the way that the elements have to in an array. Instead, we can just rely on the fact that we can traverse our list by leaning on the pointer references to the next node, which means that our machines don’t need to block off a single chunk of memory in order to represent our list.
This is also the explanation for why linked lists can grow and shrink dynamically during a program’s execution. Adding or removing a node with a linked list becomes as simple as rearranging some pointers, rather than copying over the elements of an array! However, there are also some drawbacks to linked lists that I’m not mentioning to you just yet — but more on those next week.
For now, we’ll just bask in the glory of how cool linked lists are!

Lists for all shapes and sizes
Even though the parts of a linked list don’t change, the way that we structure our linked lists can be quite different. Like most things in software, depending on the problem that we’re trying to solve, one type of linked lists might be a better tool for the job than another.
Singly linked lists are the simplest type of linked list, based solely on the fact that they only go in one direction. There is a single track that we can traverse the list in; we start at the head node, and traverse from the root until the last node, which will end at an empty null value.
But just as a node can reference its subsequent neighbor node, it can also have a reference pointer to its preceding node, too! This is what we call a doubly linked list, because there are two references contained within each node: a reference to the next node, as well as the previous node. This can be helpful if we wanted to be able to traverse our data structure not just in a single track or direction, but also backwards, too.
For example, if we wanted to be able to hop between one node and the node previous without having to go back to the very beginning of the list, a doubly linked list would be a better data structure than a singly linked list. However, everything requires space and memory, so if our node had to store two reference pointers instead of just one, that would be another thing to consider.

A circular linked list is a little odd in that it doesn’t end with a node pointing to a null value. Instead, it has a node that acts as the tail of the list (rather than the conventional head node), and the node after the tail node is the beginning of the list. This organization structure makes it really easy to add something to the end of the list, because you can begin traversing it at the tail node, as the first element and last element point to one another. Circular linked lists can start to get really crazy because we can turn both a singly linked list and a doubly linked list into a circular linked list!
But no matter how complicated a linked list is, if we can remember the fundamentals of a node and how it works and how the different pointer references in our list are structured, there’s no linked list we can’t tackle!
Next week, in part 2 of this series, we’ll sink our teeth into the space time complexity of linked lists, and how they compare to their cousin, the array. I promise that it’s actually a lot more fun than it sounds!

Hey, so, what even is Big O?

Most of us have probably heard the term “Big O Notation”, even if we had no idea what it meant the first time that we heard someone use it. My personal experience with it has always been in the context of designing algorithms (or being asked to evaluate the efficiency of an algorithm). But Big O is really all over and omnipresent within computer science.
The reason for this is that computer science — and effectively, anything that we code — is all about efficiency and tradeoffs. Whether you’re building software as a service, choosing a front end framework, or just trying to make your code DRY and more elegant, that’s what all of us are striving towards: being efficient with our software, and choosing things that are important to what we’re building, all while being aware of the tradeoffs that we’ll ultimately have to make.
The same goes for Big O Notation, but on a much lower level. Big O Notation is a way of evaluating the performance of an algorithm.
There are two major points to consider when thinking about how an algorithm performs: how much time it requires at runtime given how much time and memory it needs.
One way to think about Big O notation is a way to express the amount of time that a function, action, or algorithm takes to run based on how many elements we pass to that function.
For example, if we have a list of the number 1–10, and we wanted to write an algorithm that multiplied each number by 10, we’d think about how much time that algorithm would take to multiply ten numbers. But what if instead of ten numbers, we had ten thousand? Or a million? Or tens of millions? That’s exactly what Big O Notation takes into account: the speed and efficiency with which something functions when its input grows to be any (crazy big!) size.
I really love the way that Parker Phinney describes what Big O notation is used for in his awesome Interview Cake blog post. The way that he explains it, Big O Notation is all about the way an algorithm grows when it runs:
Some external factors affect the time it takes for a function to run: the speed of the processor, what else the computer is running, etc. So it’s hard to make strong statements about the exact runtime of an algorithm. Instead we use big O notation to express how quickly its runtime grows.
If you do a little bit of research on Big O Notation, you’ll quickly find that there are a ton of different equations used to define the space and time complexity of an algorithm, and most of them involve an O (referred to as just “O” or sometimes as “order”), and a variable n, where n is the size of the input (think back to our our ten, thousands, or millions of numbers).
As far as linked lists go, however, the two types of Big O equations to remember are O(1) and O(n).
Image for post
Basic Big O Notation Equations
An O(1) function takes constant time, which is to say that it doesn’t matter how many elements we have, or how huge our input is: it’ll always take the same amount of time and memory to run our algorithm. An O(n) function is linear, which means that as our input grows (from ten numbers, to ten thousand, to ten million), the space and time that we need to run that algorithm grows linearly.
For a little contrast, we can also compare these two functions to something starkly different: an O(n²) function, which clearly takes exponentially more time and memory the more elements that you have. It’s pretty safe to say that we want to avoid O(n²) algorithms, just from looking at that crazy red line!


Growing a linked list
We already know what linked lists are made of, and how their non-contiguous memory allocation makes them uniquely different from their seemingly more popular cousin, the array.
So how do they work, exactly? Well, just like with an array, we can add elements and remove elements from a linked list. But unlike arrays, we don’t need to allocate memory in advance or copy and re-create our linked list, since we won’t “run out of space” the way we might with a pre-allocated array.
Instead, all we really need to do is rearrange our pointers. We know that a linked list is made up a single node, and a node always contains some data and, most importantly, a pointer to the next node or null. So, all we need to do in order to add something to our linked list is figure out which pointer needs to point to where.
For simplicity’s sake, we’ll work with a singly linked list in these examples. We’ll start with the simplest place we can insert an element into a linked list: at the very beginning. This is fairly easy to do, since we don’t need to go through our entire list; instead we just start at the beginning.
First, we find the head node of the linked list.
Next, we’ll make our new node, and set its pointer to the current first node of the list.
Lastly, we rearrange our head node’s pointer to point at our new node.
That’s it, we’re done! Well, almost. This looks easy, and it is — just as long as we do those three steps in the right order. If we accidentally end up doing step 3 before step 2, we end up in a bit of a mess. The reason being that if we point our head node to the new node before connecting the new, still-to-be-inserted, node to the rest of the list that comes afterwards, we’d end up in a cyclical structure, with only two nodes, and we’d effectively lose all of our other data in the list. Talk about a bad day!
Still, that process isn’t too hard to implement (and hopefully shouldn’t be too difficult to code) once you can remember those three steps.
Inserting an element at the beginning of a linked list is particularly nice and efficient because it takes the same amount of time, no matter how long our list is, which is to say it has a space time complexity that is constant, or But inserting an element at the end of a linked list is a different story. The interesting thing here is that the steps you take to actually do the inserting are the exact same:
Find the node we want to change the pointer of (in this case, the last node)
Create the new node we want to insert and set its pointer (in this case, to null)
Direct the preceding node’s pointer to our new node
However, there’s an added complexity here: we’re not adding something to the beginning of the list, at the head node. Nope — instead, we’re adding something after the last node. So we will need to find the last node. Which means that we’ll need to traverse through the entire linked list to find it. And we know that linked lists are distributed, non-contiguous in memory, which means that each node will live at a totally different “address” in memory! So traversing is going to take time — it’s going to take more time with the more nodes we have.
Hopefully, we can start to see what kind of space time complexity this type of inserting will leave us with: a linear O(n). If we had a linked list of 100 nodes, that might not actually take that long. Even a 1000 might be pretty fast. But imagine if we wanted to add an element to the end of a linked list with a billion items! This insert algorithm would take as much time as the number of elements in our list, which, depending on our list, could be a very bad day for us.
To list or not to list?
No human is perfect, and neither is a linked list. Here’s the thing: sometimes, a linked list can be really awesome — for example, when you want to insert or remove something at the beginning of the list. But, as we’ve learned, they can sometimes be…less than ideal (imagine having a million nodes and just wanting to delete the last one!)
Even if you don’t have to work with them every day, it’s useful to know just enough about data structures like linked lists so that you can both recognize them when you see them, and know when to reach for them when the time is right.
A good rule of thumb for remember the characteristics of linked lists is this:
a linked list is usually efficient when it comes to adding and removing most elements, but can be very slow to search and find a single element.
If you ever find yourself having to do something that requires a lot of traversal, iteration, or quick index-level access, a linked list could be your worst enemy. In those situations, an array might be a better solution, since you can find things quickly (a single chunk of allocated memory), and you can use an index to quickly retrieve a random element in the middle or end of the list without having to take the time to traverse through the whole entire thing.

However, if you find yourself wanting to add a bunch of elements to a list and aren’t worried about finding elements again later, or if you know that you won’t need to traverse through the entirety of the list, a linked list could be your new best friend.
For the longest time, I never knew what linked lists were. And when I finally did learn about them, I didn’t know what on earth they would ever be used for. Now that I realize what they do well, I can see both their benefits and drawbacks. And if the time ever comes, I’ll know when to reach for them to help me out.
Hopefully, you’re with me on this and feel the same way about linked lists, too!