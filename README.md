# average_games.aleo


## Summary

### -Project Description
Guess of Average (GoA) is derived from Alan Ledoux's "Guess 2/3 of the Average" game. In this game, each player is asked to give a number. The player whose given number is closest to the average will be the winner. 


### -Application Values
1. Guess of Average (GoA) is a natural GameFi game.  Participants/players adjust  their game strategies by evaluating the average consensus of other participants/players.

2. Player uses the address of Aleo wallet as the unique Digital Identity. In theory, players can use the same identity for community activities within Aleo ecosystem or even across various web3 networks which are Aleo compatible.

3. GoA takes advantage of the features of zk-SNARKs and put each given number into a dark pool, which prevents each player's game stragy in privacy.


## User Flow
-- Game moderator starts the game.

-- Players in a community enter the game zone.

-- Each player gives out a number and waits for the final result.

-- System prints the average number and show the winners' ID (Aleo wallet address) to terminal of each player after last player done.


## How to Build

To compile this Aleo program, run:
```bash
aleo build
```

## How to Run
```bash
leo run place_bid 'address'
```
After the moderator starts the game, participants/players submit wallet addresses to participate in the game. The system will return objects containing parameters such as game address, participant's own wallet address, guess value, total number, etc


```bash
leo run resolve 'Bid' 'Bid'
```
Participants/players submit the number closest to the average in the previous round and the guessed value of the current participant. The system returns the new number closest to the average. The first participant enters the same value for both parameters. If there is a next participant, continue to execute place_ Bid and resolve methods.

```bash
leo run finish 'Bid'
```
End the game, the moderator submits the approximate final average value, and the system returns information such as the guess value and wallet address submitted by the winner

## Parameter Description

Bid =>   {
	`owner: address,`【Event address】
	`gates: u64,`【commission】
	`bidder: address,`【Player Address】
	`amount: u64,`【Number of participants/players】
	`place: u64,`【Guess value】
	`totel: u64,`【total】
	`is_winner: bool,`【Win or not (this value will be updated when the game ends)】
}

