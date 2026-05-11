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

RESOURCES:  1 bd + 2 be  + 1 fe + 1 QA
### Warehouse core
RESOURCES:   2 be + 1 QA
### crypto gateway data fetch 
RESOURCES:  1 bd + 2 be  + 1 QA
### Bi panel
RESOURCES:   1 be  + 1 QA
## Rewrite Algo bot Service
GOAL: Market making bots should not have large amount of loss. We should be able to config each side(sell, buy) seperately  

STAKEHOLDERS: financial, stakeholders

PROBLEM: currently each feature and user data are in different databases so there is no integrated data.

SOLUTION: By integrating data and remove useless data we can create bi reports that provide perfect sight of system current state and let managers and financials make decisions to align business .

RESOURCES:  1 bd + 2 be  + 1 fe + 1 QA


## Rebalancing Core

STAKEHOLDERS: financial
### Rebalancing Provider
### Algo bot
### crypto gateway
### OTC
### LOAN
### Stake
### Invoice
### Pool



##  Update CMS Service
STAKEHOLDERS: marketing
## Refactor and Launch Swap feature
STAKEHOLDERS: product
## Add Dusting feature
STAKEHOLDERS: product
## Create Club Service / Campaign
GOAL: create loyalty and campaign management infrastructure.

STAKEHOLDERS: marketing , product

PROBLEM: currently there is no centralized platform for loyalty programs, campaigns and referral systems.

SOLUTION: develop dedicated club and campaign service for user engagement and retention.

RESOURCES: 1 bd + 1 be + 1 fe + 1 QA
## Handel Dex Market price failure
GOAL: prevent incorrect pricing during DEX provider failures and outages.

STAKEHOLDERS: tech

PROBLEM: DEX provider instability can result in invalid prices and financial exposure.

SOLUTION: implement fallback providers, price validation and close markets if there is not liquidity pool (price) for that coin. bots should be stoped and prevents users from placing new orders.

RESOURCES: 2 be + 1 QA

## Delist Coins Flow
GOAL: create safe and standardized coin delisting process. 

STAKEHOLDERS: tech , product, financial , support, marketing

PROBLEM: current delisting operations are manual and operationally risky.

SOLUTION: develop unified delisting workflow including notification, disablement and operational coordination. user should be able to know when and how we delist a coin. financial should be able to specify converting rate and date of delisting.

RESOURCES:  2 be + 1 fe + 1 QA
## Debug Bank transaction
GOAL: identify and resolve bank transaction inconsistencies and failures.

STAKEHOLDERS: financial

PROBLEM: bank transaction issues impact reconciliation, operational stability, user trust and fiat deposit/withdraw time.

SOLUTION: improve bank transaction tracing, monitoring and recovery flows.

RESOURCES: 1 be + 1 QA

## Complete SEO 
GOAL: improve organic traffic and search engine visibility.

STAKEHOLDERS: marketing

PROBLEM: SEO implementation is incomplete and limits organic growth.

SOLUTION: implement technical SEO optimization, metadata improvements and performance enhancements.

RESOURCES: 1 fe 

## Sarmayex Credit Card
GOAL: launch integrated branded credit card infrastructure. users should be able to order a credit card , then move some assets into corresponding account in specific order. at the moment of using this card, we should create market order to convert asset/assets to fiat and pay the billing by this fiat. we need landing page for this feature too.

STAKEHOLDERS: product

PROBLEM: users currently do not have integrated card-based spending capabilities.

SOLUTION: develop credit card infrastructure and banking integration for transaction and card management.

RESOURCES:  2 be + 2 fe + 1 QA
## Profit and Loss (PNL)
GOAL: provide accurate profit and loss reporting for users and internal teams.

STAKEHOLDERS: product

PROBLEM: users and stakeholders currently lack visibility into realized and unrealized profitability.

SOLUTION: develop centralized PNL calculation and reporting infrastructure.

RESOURCES: 2 be + 1 fe + 1 QA

## Migration from Setting service to Lens
GOAL: centralize and modernize configuration management infrastructure and make configuration dynamic by moving them to database and finally edit them from admin panel. Lens service should hold all brokers configuration.

STAKEHOLDERS: tech

PROBLEM: current setting service architecture increases operational complexity and maintenance overhead.

SOLUTION: migrate configuration management capabilities into Lens service. also change all services to fetch configuration from lens instead of settings package

RESOURCES: 3 be + 1 bd + 1 QA


## Grouped Access management
GOAL: implement scalable role and group-based access management. Admin of each department should be able to access his owned permission to sub accounts.

STAKEHOLDERS: tech, product, financial , marketing

PROBLEM: current access control model lacks flexibility and scalability. It takes a lots of time from CTO and 1 be to grant access to each account base on what they really need.

SOLUTION: develop grouped access management with hierarchical permissions and audit capabilities for each department admin.

RESOURCES: 2 be + 1 fe + 1 QA
## Match Engine Database retention of removing use less data
GOAL: reduce database growth and optimize performance by removing unnecessary historical data.

STAKEHOLDERS: tech

PROBLEM: historical data growth negatively impacts database performance and infrastructure costs.

SOLUTION: implement retention policies, cleanup automation and archival strategy.

RESOURCES: 1 be + 1 QA

## IOS first Release
GOAL: launch first production-ready IOS application.

STAKEHOLDERS: product

PROBLEM: currently there is no IOS application available for users.

SOLUTION: develop and release IOS application with trading, wallet and notification capabilities.

RESOURCES: 2 mobile + 1 QA
## Tradingview Charts or Bitycle
GOAL: provide advanced charting and market analysis tools.

STAKEHOLDERS: product

PROBLEM: current charting infrastructure is limited and lacks advanced trading capabilities.

SOLUTION: integrate Tradingview infrastructure and real-time charting features.

RESOURCES: 1 fe + 1 QA
## Internal Transaction List for each user

STAKEHOLDERS:  product

GOAL: provide visibility into internal user transactions and transfers.

PROBLEM: users  currently lack visibility into internal asset movements.

SOLUTION: develop internal transaction history and tracking module with filtering and reporting capabilities.

RESOURCES: 1 be + 1 fe + 1 QA