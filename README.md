## WTF What happened?
The rabbit hole can be extracted in the previous code design. In the EGGS contract, the token in the chef will also be debased, too. However, the mechanism of CARROT is different, which causes the incompatibility between the contracts.
Because the balance of chef is a too small amount after too many ppl withdraw 👇
* the function `updatePool` will be called after anyone called `claim` function.
* `pool.accRewardPerShare` will be updated to a large number bc the lpSupply (the carrot balance of chef) is small.
* then the pending rewards of users will be updated large.

That's how the rabbit hole mint huge amounts a few hours ago.

## What's the next?
We will not re-launch new carrots, but open source the contract which had been fixed. Finally, thank you to all the rabbits who participated in this experiment, and feel so sorry for the rabbits who have been hurt.

## Warning
All of the project fork from carrot should update their contracts. The team should not give up ownership and roles prematurely, timelocker is a better substitute.