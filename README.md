# package-orders

![](https://github.com/gokemon/tuts-plus/blob/master/images/builtWith/git-short.png)![](https://github.com/gokemon/tuts-plus/blob/master/images/builtWith/github-short.png) ![](https://github.com/gokemon/tuts-plus/blob/master/images/builtWith/node-long.png)

Logistical shipping on orders and package tracking
You place an order on a website for a book, and then sometime later a package arrives with your book.
This is my simplified ordering and package tracking system, as well as I, can design it.
These are my base notes.
I need a database, and ordering system front-end, and a pick system, and a packing system, and a shipping system.
Each part needs to follow the other, and right now, I have plenty of thoughts about the shipping system.
In short, a package with your order in it rolls down the belt at some point; One of the thousands per day. Its scanned to a cage, so we need to define a cage. Time created, who created it, what it's starting location is. Next what packages are scanned into it. Close the cage, who closed it. Who printed a label for it. Where did it move next, and who moved it. When does it get committed to a truck?
Trucks, who created it, who opened it. Who scanned the cage into it and when. What cages are loaded into it, hence what packages are loaded into it?

Where do these trucks go? What's next for your package?

<hr>

An order needs;

A customer, which has a name, address, etc.... that goes off to billing, tracking of what they look at, what they put in a shopping cart, etc.

A product, which has cost, weight, dimensions, quantity in stock, which leads to its vendor, stock on hand, reorder levels, etc.

So the customer orders a product.

The product is routed to a fulfillment center. There would most likely be an Algorithm for picking which center. Then it gets picked off the self, to be packed.
So the Center has products, Inventory, which tells the Picking System where to get the product from.
Once, the item is picked up, it then goes to packing.
Of course, the Center has an Inventory System, which I won't go into at this time.

Each Order is either a full order or partial order allotment.
But whatever it is, those products that were picked to fulfill this allotment are sent to packing.

This allotment is given a "SPEW". A bar-code sticker applied to the box is linked up to an order number. Each allotment is "thought about" by some Algorithm to determine the best box to use.
So there will need to be a supply of boxes and other packing materials on hand. Each box has a size, and weight limit.
The products of each order allotment are packed in the box, which currently has a spew sticker on it, which links the order. Then a shipping label is created by the system.

At some point, this box with its known items inside will roll across a scale. The spew is linked to the items inside the box, which have known weights. So the weight of the box should pretty closely match the weight of the box and the items it should have in it. Ether it will match and be passed through, or it will be over or underweight. Overweight tells us that something extra is in the box, and underweight tells us something is missing. And an alert is raised.

If the scale weight is correct, the box is sealed, and a packing label applied and the package moves to shipping.

When it arrives along with a belt to shipping, words tell us what route cage it goes to. The bar-code on the shipping label "load" it to the cage.

Each cage is "Opened" at the certain location, and given the opening time. As each package is loaded to it, the package count is added, the weight and package dimensions are also added. We can also track who added the package to the cage and when. The cage is also "closed" and its closing time is tracked. Who opened it and who closed it is also recorded. Then a cage label is printed and the cage moved to a holding location, which is also added to the data pile, who dropped it at the location and when is also added.

At some point, the cage is then loaded to a truck. The label is scanned. This "loads" the packages, their weight and count to the truck.

In theory, each person working on loading a truck should log the target location of the truck with their scanner gun, indicating they are working on the truck, and scan again when they leave a truck.

Of course, the truck needs to be "created" and "opened" at the certain door location, along with when and who are added to the trucks data pile. 
As each cage is added to the truck via the cages label, the user who scanned it and time is recorded. 
I am guessing there is a way that we can tell, by scale, or some method how well the truck is being loaded. Is it over or under utilized. 
Of course, the number of packages and their dimensions and weight are being taken into account. 

The truck is of course "closed" and locked, with the time and user being recorded as well. 

From here, my ideas on where the truck go, and how the package arrives at the customers location is a bit foggy. 

