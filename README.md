# BG-s-Trader-Fix
Keeps Traders Open all the time


# BG-s-Trader-Fix
Sets Traders to open 24/7 and removes the open/closed sounds

I'd seen several Trader mod's that do the same basically, and also had seen posts on reddit as well as the 7daystodie.com forum and seeing all were using the following format for every single Trader instead of fully using the features of xpath examples below

Every Mod I ran across used the following format and of course used [@id='1'], [@id='2'], [@id='6'], [@id='7'], [@id='8']

	<set xpath="/traders/trader_info[@id='1']/@reset_interval">1</set>
	<set xpath="/traders/trader_info[@id='1']/@min_inventory">40</set>
	<set xpath="/traders/trader_info[@id='1']/@max_inventory">100</set>
	<set xpath="/traders/trader_info[@id='1']/@min_items_swapped">40</set>
	<set xpath="/traders/trader_info[@id='1']/@max_items_swapped">100</set>
 	<set xpath="/traders/trader_info[@id='1']/@open_time">0:00</set>
	<set xpath="/traders/trader_info[@id='1']/@close_time">0:00</set>

So to make things smaller and simpler I rewrote it as the following removing the need to have 4 other sections of the same size for @1d's 2,6,7,8

	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@reset_interval">1</set>
	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@min_inventory">50</set>
	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@max_inventory">100</set>
	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@min_items_swapped">50</set>
	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@max_items_swapped">100</set>
 	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@open_time">0:00</set>
	<set xpath="/traders/trader_info[@id &lt; 3 or @id &gt; 5]/@close_time">0:00</set>
  
  The other changes made were to the following:

	<set xpath="/traders/trader_info[@id='3']/@reset_interval">1</set>
	<set xpath="/traders/trader_info[@id='3']/@allow_sell">true</set>
  
  <-- And -->
  
	<set xpath="/traders/trader_info[@id='5']/@reset_interval">1</set>
	<set xpath="/traders/trader_info[@id='5']/@allow_sell">true</set>
  
I rewrote them as follows

<!-- Player Owned Or Rented Vending Machine -->
	<set xpath="/traders/trader_info[@id='3' or @id='5']/@reset_interval">1</set>
	<set xpath="/traders/trader_info[@id='3' or @id='5']/@allow_sell">true</set>

  
  
The original way used by all the others even with removing blank lines took a total of 55 lines, mine takes only 20 lines
  
Hopefully this will inspire others to use the features of xpath more often when possible, feel free to use this for your work, but if used verbatim it'd be nice to get a mention of some kind thanks :-)
