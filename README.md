# package-orders

![](https://github.com/gokemon/tuts-plus/blob/master/images/builtWith/git-short.png)![](https://github.com/gokemon/tuts-plus/blob/master/images/builtWith/github-short.png) ![](https://github.com/gokemon/tuts-plus/blob/master/images/builtWith/node-long.png)

Logistical shipping for orders and package tracking

You place an order on a website for a book, and then sometime later a package arrives with your book.

This is my simplified ordering and package tracking system as well as I can design it.

These are my base notes.

I need a database, and ordering system front-end, and a pick system, and a packing system, and a shipping system.

Each part needs to follow the other, and right now, I have plenty of thoughts about the shipping system.

In short, a package with your order in it rolls down the belt at some point; One of thousands per day. 
Its scanned to a cage, so we need to define a cage. Time created, who created it, what it's starting location is. Next what packages are scanned into it.
Close the cage, who closed it. Who printed a label for it. Where did it move to next, and who moved it. When does it get committed to a truck.

Trucks, who created it, who opened it. Who scanned the cage into it and when.
What cages are loaded into it, hence what packages are loaded to it. 

Where do these trucks go? What's next for your package?


