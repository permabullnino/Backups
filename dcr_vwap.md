Decred On-Chain: The Ticket Pool VWAP

Introduction / Roadmap

In my previous piece "DCR On-Chain: A Look at Block Subsidies", we explored the ultimate Network-Based indicator - block rewards, and their relationship to network valuation from the point of view of the network itself, miners, stakers, and the DCR treasury. Within this article we will begin to explore and uncover the magic behind the ultimate Decred User-Based indicator - ticket data, and show how it provides a means for effectively gauging the HODL behavior of users within the Decred Network. This article aims to be a foundational piece in understanding ticket data for future pieces, explain why it's worthwhile analyzing, and hopefully provide some color for Decred-curious on-chain analysts within the cryptocurrency space. Below are the topics that will be covered within:

(1) Decred Tickets: What they are, functions they serve, and ticket parameters
(2) Analysis of User-Based Indicators in Crypto-Networks
(3) How Decred Tickets Break the Mold for User-Based Indicators
(4) Definitions of "HODLing" in Different Crypto-Networks
(5) Introducing the Ticket Pool VWAP
(6) Analysis of 14, 28, and 140 Day DCRUSD Ticket Pool VWAP
(7) Analysis of 14, 28, and 140 Day DCRBTC Ticket Pool VWAP
(8) Lifetime DCRUSD VWAP, Lifetime DCRBTC VWAP, and Cumulative Cap
(9) Closing Thoughts

Decred Tickets: What They Are, Functions They Serve and Ticket Parameters

Tickets are the semi-scarce asset of Decred's Proof of Stake mechanism. Just like Proof of Work, which is semi-scarce as a function of (1) difficulty retargeting based on demand for hash and (2) profitability in acquiring additional units of hash - tickets are semi-scarce as a function of (1) ticket price regularly retargeting based on demand for tickets and (2) the scarcity of available DCR on the market to purchase tickets. In the case of Proof of Work, people compete for hash in order to receive block rewards. Decred tickets are similar, as stakers compete for tickets in order to (1) receive block rewards and (2) participate in the network's governance. This combination of scarcity, incentive to compete for the scarce object, and making the pricing of the scarce object determined by purely market driven forces are what make Decred's Proof of Stake / Ticketing mechanism a reliable second authentication layer as it relates to enforcing digital scarcity, and ultimately a grand innovation in applying the principles which make Proof of Work special in a stake-based scheme.

[INSERT TABLE HERE]

Security for cryptocurrencies depend on the foundations listed in the table above - incentivizing people to contribute to the network is mission critical for the longevity of any crypto-network. These incentives to contribute are upheld not only by competing over scarce objects, but also by making the game for competing over these scarce objects *provably* fair. Fairness in distributed systems such as cryptocurrencies are best managed by the market itself, so fairness can be proven via (1) transparency of data, (2) data completeness, and (3) established / widely accepted quantitative measures.

Proof of Work offers transparency by allowing users to check the validity of hashes that supposedly fall below the network difficulty target. Futhermore, Proof of Work offers high data completeness as it's impossible for mining not to leave an on-chain footprint. Lastly - difficulty retargetings establish the fair balance between supply and demand, which can be checked on by looking at the frequency of which blocks are being discovered. All three things considered - Proof of Work is *provably* fair.

Decred's Proof of Stake Tickets offers transparency by allowing users to check the validity of any given ticket being chosen to vote - which is a fucntion of the previous block's hash. Tickets are a consensus-critical part of Decred, so all ticket purchases and votes occur on-chain, so there is no missing data surrounding tickets for network stakeholders. And to finish things off - Decred tickets have ticket price retargetings which aim to establish a certain amount of ticket buying volume, which can be checked to determine if the retargeting is properly regulating supply and demand.

Both PoW and Decred's PoS Tickets are built on the foundations of randomness, which is also incredibly important. If one party could game the system and win the PoW/PoS competitions consistently while not putting forth the appropriate amount of work/stake, then by definition these systems wouldn't be fair. PoW imposes this fairness by making block discovery a brute force process - forcing miners to plug nonces relentlessly until they find a hash below the network difficulty target. Decred's PoS leverages the randomness from PoW to its advantage, by making ticket selection pseudo-randomly derived from the previous block's hash.

[INSERT TABLE HERE]

Fairness matters - analyzing competition over scarce resources in these crypto-systems is substantially less interesting and predictive of user behavior if they aren't fair. Proof of stake systems are *generally* stamped as being "unfair", but that is not the case with Decred's ticketing system.

---

We have covered that tickets are scarce resources that are fairly competed over. However, it's also important to also understand that tickets are incredibly useful, wearing multiple hats within the network itself. More emphatically speaking, tickets drive the vast majority of operations that users leverage Decred for, including:

(1) A means for users to accumulate as much of the 21 million DCR supply as possible
(2) An additional authentication layer for newly discovered blocks
(3) On-chain voting to push consensus changes
(4) Off-chain voting to allocate treasury funds
(5) Provide fungibility
(6) Time-locked, trustless, custody of funds
(7) Provide network participants with high signal data 

When users lock their DCR in tickets, they're gaining access to everything listed above, and opting out of them when foregoing ticket purchases. In a later section we will do a deeper on the dynamics at play related to users opting in or out of tickets.

---

Thus far we have established that tickets are a scarce resource, that are competed for fairly, and provide a great deal of utility for network participants / the network itself. Now it's time to discuss the specific parameters of the ticketing system. These specifics build the backbone of ticket scarcity, competitive fairness, and utility that they provide. Understanding the specifics not only help us lock down these foundational bits, but also set the stage for us to compare ticket data to other User-Based indicators in crypto. After this comparison we can leverage this information to better analyze the TVWAP (Ticket Pool VWAP). The parameters of the Decred ticket system are as follows:

(1) Target Ticket Pool Size: 40,960 tickets
(2) Ticket Votes per Block: 5 - please note tickets get released from ticket pool after voting and need to be repurchased at the most recent ticket price
(3) Block Times: ~5 minutes on average
(4) Difficulty Adjustment: every 144 blocks - this 144 block period will be referred to as a "ticket window" herein
(5) Ticket Voting: Pseudo-random

We can take these base parameters and point out a few extra noteworthy aspects of the Decred ticket system:

(1) Ticket Votes per Ticket Window: 720 votes (5 votes per block * 144 blocks per ticket window)
(2) Ticket Window Duration: ~12 hours (144 blocks per ticket window * 5 minutes per block)

Before moving forward, it's worth taking a second to remind those who are less familiar with Decred tickets that the goal of the ticket difficulty retargeting algorithm is to match supply and demand reliably. As such - if 720 tickets are getting released from the ticket pool during a ticket window, then the goal is to replace those tickets with another 720 tickets:

(1) Ticket Windows to Fill Ticket Pool: 56 (40,960 target ticket pool size / ~720 tickets purchased per ticket window)
(2) Days to Fill Ticket Pool: ~28 (56 ticket windows to fill pool / 2 ticket window periods per day)






