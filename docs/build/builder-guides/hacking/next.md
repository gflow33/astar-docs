---
sidebar_position: 4
---


# Next step
Here comes the fun! Time to build your own dApp.
Here you will find a list of ideas to implement in any of the smart contract environments.


## Enter Community

- Join Astar Discord and Post GM.
- Follow Twitter.
- Create an account on Stack Exchange.
- Create an account, Post Hi on Forum (A thread just for this purpose).
- Subscribe to Astar Newsletter.

## Ideas to build
These ideas can be implemented as WASM or EVM smart contract. Main intention is for the ink! developers.

### Pool Together 
Explore this [project](https://app.pooltogether.com/) and build your own version in ink!

### Voting
Use ink4 from Swanky-node to develop a smart contract which allows people to vote The rules are:

* Contract owner initializes a set of candidates (2-10). 
* Lets anyone vote for the candidates.
* Each voter is limited to only one ote (per address).
* Displays the vote totals received by each candidate.

### Tamagotchi
    1. Requirements TBA, WIP
    
### Charity Raffle

Use ink4 from Swanky-node to develop a smart contract which allows people to enter a charity raffle. The rules are:

* A user can send in anywhere between 0.01 and 0.1 tokens.
* A user can only play once.
* A user is added to the pool with one submission, regardless of money that was sent in.
* There can be a maximum of 2 winners.
* The raffle must go on for 15 minutes before a draw can be initiated, but the 15 minute countdown only starts once there are at least 5 players in the pool.
* Anyone can call the draw function at any time, but it will only draw a winner when the 15 minute timer has expired.
* The draw function can be called twice for a maximum of two winners.
* The winners get nothing (it’s a raffle for a real world item, like a t-shirt, so ignore on-chain effects of a win) but they need to be clearly exposed by the contract, i.e. the list of winners has to be a public value dapps and users can read from the contract.
* The collected money from the pot is automatically sent to a pre-defined address when the second winner is drawn.

Happy coding!

