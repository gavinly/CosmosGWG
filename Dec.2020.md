# Cosmos Hub Governance Working Group
## December 2020 Topic Calls
[Discuss in forum](https://forum.cosmos.network/t/gwg-community-calls-updates/3238/12) and [Telegram channel](https://t.me/hubgov)

Date: Tu Dec 15, 2020 - [Add to calendar!](https://calendar.google.com/event?action=TEMPLATE&tmeid=MTU3amd1OXY3bmhrOTR2aGJlcXQzb251MWwgZmlnbWVudC5jYXBpdGFsX29iYnZqMnVsNWI3MGFyNTg4amY4dnUxanFrQGc&tmsrc=figment.capital_obbvj2ul5b70ar588jf8vu1jqk%40group.calendar.google.com)

Time: 17:00 UTC

Duration: 55 minutes

Host: Gavin Birch ([Figment](https://figment.io))

[Audio recording can be found here!](https://drive.google.com/file/d/196SkDM4sLvOHZk4lB34cw-shLd9401XC/view?usp=sharing)

## Prior to the meeting
1. [Join us!](http://bit.ly/2sukvxa) Please share any contact information that you feel comfortable sharing.
2. Check out [Sikka's work, which is based on this proposal.](https://hubble.figment.io/cosmos/chains/cosmoshub-3/governance/proposals/31)
3. Check out [Regen's Groups Module work.](https://github.com/regen-network/cosmos-modules/tree/master/incubator/group)
2. Please indicate [your primary governance interests here](https://docs.google.com/document/d/1jdSwln5L7KLvEkkM91GhlblniSynmAjMyAWSLONxTGQ/edit?usp=sharing).

## Agenda

#### 1. Updates
- GWG reboot: with support from ICF, Gavin will be focused on fostering community discussions about governance and developments in the Cosmos Hub.
- governance work updates
  - updates planned for for [community-spend docs](https://github.com/gavinly/CosmosCommunitySpend) & [parameter-change docs](https://github.com/gavinly/CosmosParametersWiki) to be compatible with the Stargate upgrade, with additional docs added for protocol upgrades.
  - Governance [Prop31](https://hubble.figment.io/cosmos/chains/cosmoshub-3/governance/proposals/31) & [Prop32](https://hubble.figment.io/cosmos/chains/cosmoshub-3/governance/proposals/32) recently passed, payment and approval for the work to split a single account's voting power to different voting options eg. 40% of staked ATOM can vote yes while 60% abstains.

#### 2. Introductions - Sikka & Regen
15 attendees in total
#### 3. Proposed Topic: How can community pool funds be more effectively distributed?
A number of entities are working on ways to improve the governance mechanism and practices, such the [CosmWasm team's subkeys.](https://docs.cosmwasm.com/cw-plus/cw1/subkeys.html#) Sikka is leading the way to improve the Hub in small, incremental ways, funded in smaller denominations from the community pool. Should the Hub get used to more frequent proposal activity, which can be enabled by subkeys? or should we use the Groups Module to budget a designated budget (eg. petty cash) for smaller expenses?


#### a) **AMA w Sikka** (15 mins) - Sikka has been approved and funded by Hub governance to [implement split voting in Hub governance](https://hubble.figment.io/cosmos/chains/cosmoshub-3/governance/proposals/31)

**What was the problem you saw here? How will this solve the problem, and how do you expect it to be used?**

Governance vote splitting is useful for custodians and companies with a common account and different stakeholders.

Currently in Hub governance it's one address, one vote for those staked ATOMs--which makes sense for individuals, but that's not always the case. An address could represent a DAO, or a company for which they want to split their vote, especially within a validator operator entity. Custodians and exchanges have many stakeholders represented by a single address and this could enable a single account's voting power to different voting options eg. 40% of staked ATOM can vote yes while 60% abstains, enabling a single entity to effectively exercisw the governance rights of the token owners.

**What would you like to see built with it?**

First users will be DAOs, particularly with interchain accounts, and companies. Then we'll likely see custodians implement this feature. It will be interesting to see if large exchanges like Binance will enable this for their users.

**Are there some interesting edge cases? Could this be developed further?**

Integrations with eg. Groups module, or interchain accounts, and exchanges will be interesting. Sikka chose this as the first because it seems relatively non-contentious and stands on its own.

**Thoughts on funding?**

The overhead on governance proposals is pretty high. Every new feature needs a 512 deposit and a written proposal. One of the proposals almost didn't make quorum, so Sunny had to reach out to ask certain stakeholders to vote. Others aren't in the same position to make that happen. Sunny thinks maybe using a sub-committee via Groups module could make the process more effective and accessible, and has had similar experience in directing funding as a university student: batch payments for dedicated working groups that are specialized to distribute funds according to their expertise and ability to evaluate proposals.

Sunny (Sikka) asked **How do we avoid quorum issues in the future? Incentivization vs Motivation**

Sunny suggested a backwards-looking proposal to reward previous voters with an airdrop. Gavin likes that it can get people hooked on voting, but doesn't like that it could drive the wrong kinds of voting behaviour. Regardless, how much can we possibly reward the voting addresses? Gavin would rather direct those resources to people who are good at engaging people that encourage community participation.

Sam (Interchain Foundation) noted that **The USD price of the ATOM has changed, but the deposit requirement has remained 512 ATOM--could adjust the deposit accordingly?**

Gavin agrees that we should lower the barrier, but perhaps only for community-spend proposals and not for parameter-change proposals. Perhaps the deposit amount could be a proportion of the number of ATOMs being asked for in the proposal.

Sunny asked Gavin **Do you have ideas for motivating people to vote besides monetary incentives?**

Gavin doesn't have specific ideas, but thinks that defining being a Cosmos Hub community member as one who votes. Having on-chain governance differentiates the Hub and what defines its community from networks that don't have on-chain governance. Aaron (Regen Network) suggests **adjusting voting power relative to governance participation.** Cory notes that we're used to your stake being your voting power, and Gavin notes that some communities have experimented with voting power being based on voluntary lockups. In this case there could be game theory based on and affecting voting power rather than monetary power. Matthew (Simply VC) notes that people may use scripts to automatically vote, and Sunny thinks that there may not enough incentive to automate this in order to "game" the system. Basically, if you don't care enough about governance to vote, you may also not care about your voting power decaying or increasing.

Sam suggests **Flagging accounts that have had approved previously to allow them to bypass deposits in future** could 

#### b) **AMA w Regen** (15 mins) - Regen has been funded by the ICF to create the [Groups Module](https://github.com/regen-network/cosmos-modules/tree/master/incubator/group)

**What was the problem you saw here? What inspired this work?**
Initially I was think about how to use blockchain in a real-world use-case. Within an organization, how can you delegate different powers or permissions to perform certain actions on behalf of the organization? Regen Network team as an organization has these needs, and also envision "community staking DAOs" that hold a large of amount of tokens that are staked and have a lot of governance power that need to be able to do things on-chain.

**Overview of the work you're doing**
The Groups Module has an abstraction around a group of keys where there's a threshold voting power for each key. There are operations to change the membership of the group. The group can correspond to one or more accounts, and each account has a voting policy based on the keys that are in that group.

eg. You can have the same group of people with different voting policies for different operations, and in order to assign operations to diff groups or individuals, Regen is working on on Authorization Module that enables delegating any operation to another account. They're working a third for fee grants to enable an account to pay fees on behalf of another account.

**How do you expect your work to be used?**
Currently a single person can perform on-chain transactions like sending funds, voting, or staking. With Groups Module, you can designate a collection of transactions that will only be executed if the vote is passed.

Both the Group and Authorization Modules could be used by working groups on the Hub (but would need to figure out how to integrate the existing Gov Module with the Groups Module). Cory sees the Group Module as a means to instantiate a set of members of the group, each with their own weights and some decision making threshold eg. 5 people with a weight of 1, and if you get 3/5, that will let a message go through. Potentially a successful gov proposal could have funds distributed to a group that administers the execution of that proposal rather than directly to a single proposer's account.

Aaron thinks that if the root governance was made into an account, then root governance could delegate permissions to a sub-group. Is that useful? In this case the governance power of the Gov Module could be assigned to an account or a group of accounts. In one sense you can send funds from the Community Pool to a group, whereas the Authorization Module could enable a group to spend directly from the Community Pool.

**What is the status of the work?**
Doing an internal review and within the first weeks of the new year we should have things stable. Authorization module has been waiting for review until after Stargate and hasn't been through the ADR process for open discussion because they were told that the SDK didn't have the bandwidth--still looking for a clear answer to begin the ADR process.

#### c) **Open discussion** (20 mins)
(left off at 50:54 in recording, will continue recording notes)

#### 4. Future planning
Stick around for a few minutes after the call (if you can). What single topics are current priorities for the next call?

#### Chat log
```From Abhishek | FreeFlix Media to Everyone:  12:23 PM
Suggestion: Can we do temperature checks like on ETH for the really interested ones?
From Shahan shahan@interchain.berlin to Everyone:  12:26 PM
What do you think about checkpoints? E.g. if a proposal hits between 20% and less than 40% you lose a small portion of the deposit, and higher portion is lost with <20% votes.
@Abhishek. What's the temperature check proposal?
From Abhishek | FreeFlix Media to Everyone:  12:30 PM
@Shahan - Sounds good so that they dont lose their entire deposit!
Temperature check is a proposal before the actual proposal that passes with a lower quorum or min. threshold so that it can be determined whether the actual proposal should be issued on-chain or not
Nothing standard. It is just a way of describing a draft proposal
Maybe give NFTs for pariticipation!
So that they are good council members
And next time, those accounts can be reached out to for increased participation
From Shahan shahan@interchain.berlin to Everyone:  12:30 PM
I like this idea of 'decaying voting power'. Like penalizing a staker if they aren't present for voting/validation
From Abhishek | FreeFlix Media to Everyone:  12:31 PM
Dynamic staking rewards based on participation
Yep! Both incentivization and penalization can happen
From Volker | blockscape to Everyone:  12:31 PM
I like this idea too.
From Abhishek | FreeFlix Media to Everyone:  12:32 PM
How does a badge sound?
Like how it happens in Forums, but with these badges, we have the ability to choose governance proposals
If accounts are public and starnames are enabled, maybe we can always choose to touch base with individuals/accounts that voted for specific proposals in the past
From Cory Levinson to Everyone:  12:35 PM
https://github.com/regen-network/regen-ledger/tree/marie/136-x-group/x/group
^Current status of Regen Network’s group module. There’s a nice readme directly in the x/group directory
From Abhishek | FreeFlix Media to Everyone:  12:42 PM
Thank You for sharing this Cory.
A gov. vote can trigger a set of actions/workflow basically! Sounds pretty useful for on-chain automation of tasks
From Sunny Aggarwal to Everyone:  12:44 PM
Thats what new Proposal types does right?
But that’s if everything to be executed is “automatic”.  If you need human decision making, delegate executing to a Group
From Abhishek | FreeFlix Media to Everyone:  12:45 PM
Got it. So, 31 and 32 is fully automated while Group can be used to follow a specific workflow with human intervention.
From Me to Everyone:  12:45 PM
yes
From Abhishek | FreeFlix Media to Everyone:  12:49 PM
Q: With this module, can we see a recurring 10 ATOM/mo subscription proposal for specific services to the Hub? Would that be too low a denomination?
From Shahan shahan@interchain.berlin to Everyone:  12:58 PM
I have to drop now. Great call everyone! Looking forward to looking through the modules!
From Abhishek | FreeFlix Media to Everyone:  12:58 PM
Yes, my bad. I meant recurring funding as Andy mentioned.
From Aaron C to Everyone:  12:59 PM
with the authz module you could authorize 10k atoms/month to spend from community pool
as long as that authorization type is defined (recurring spend limit)
From Me to Everyone:  01:00 PM
Thanks!
We're about out of time, maybe i'll just collect some ideas for the next topic
From Aaron C to Everyone:  01:00 PM
gotta jump to another call
From wimel | DelegaNetworks to Everyone:  01:00 PM
thanks guys!
From Abhishek | FreeFlix Media to Everyone:  01:05 PM
Thank You for answering that Sam
Will it look like maybe snapshot with discussions?
A small thought in terms of revenue for applications --- Can I, as a delegator, redirect a % of my staking rewards to my wallet provider or a service I use?
Yes
That's right. But onchain but with discussions
Wow! Lovely!
From Me to Everyone:  01:05 PM
@gavinly
From Abhishek | FreeFlix Media to Everyone:  01:07 PM
Sounds great! We'll definitely ping you about it
Thank You Gavin!```
