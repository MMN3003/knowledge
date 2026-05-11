# Technical Items
## Automate Network and Currency release

GOAL: create automation for update , push and deploy setting package in different services and restart 

STAKEHOLDERS: product, marketing & tech

PROBLEM: at the moment adding a new network or currency is manual and take considerable amount of time, it also increase risk of human errors.

SOLUTION: by automating the process as much as possible , we will reduce the time and possiablity of errors by developing an script to do it.

RESOURCES: 2 be + 1 AQ
## Dex Swap
GOAL: buy and sell assets as soon as possible when they are backed by dex.

STAKEHOLDERS: financial

PROBLEM: at the moment when we sell an asset to customer which is backed by dex we actually don't obtain the asset. it will increase the risk of financial loss for exchange and the customer.

SOLUTION: when we sell an asset to the customer, we should buy the asset ASAP close to the price that we sold. It will decrease the risk of financial loss as we obtain the asset close to the price that we sold to the customer.

RESOURCES: 1 bd + 1 be  + 1 fe + 1 QA

## Add New Network in Chainpulse Polygun(EVM)
GOAL: create wallet addresses , detect deposits  ,fee calculation , withdraw  and wallets evacuation on Polygun Network.

STAKEHOLDERS: product

PROBLEM: currently system do not support Polygun Network and customers that have assets on this network can't deposit and withdraw any asset on Polygun.

SOLUTION: We should support Polygun network in chainpulse system to detect deposits, withdraw , fee calculation, evacuations and tracking each transaction status. Also we need to change Setting package , Lens services, Sarmayex, Internal wallet. New design on network list.

RESOURCES: 1 bd + 1 be  + 1 fe + 1 QA


## Warehouse
GOAL: We should have integrated data tables that can represent current state of the system and each feature. also we should be able to track users data in system.
In addition rate of each coin at the moment that each transaction and at the moment that reports have been generated. 

STAKEHOLDERS: financial, stakeholders

PROBLEM: currently each feature and user data are in different databases so there is no integrated data.

SOLUTION: By integrating data and remove useless data we can create bi reports that provide perfect sight of system current state and let managers and financials make decisions to align business .

RESOURCES:  1 be  + 1 fe + 1 QA
### Warehouse core
### crypto gateway data fetch
### Bi panel
## Rewrite Algo bot Service

## Rebalancing Core


##  Update CMS Service
## Refactor and Launch Swap feature
## Add Dusting feature
## Create Club Service / Campaign
## Handel Dex Market price failure

## Delist Coins Flow
## Debug Bank transaction

## Complete SEO 

## Sarmayex Credit Card

## Migration from Setting service to Lens