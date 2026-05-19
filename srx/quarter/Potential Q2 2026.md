# Technical Items
## Automate Network and Currency release

GOAL: create automation for update , push and deploy setting package in different services and restart 

STAKEHOLDERS: product, marketing & tech

PROBLEM: at the moment adding a new network or currency is manual and take considerable amount of time, it also increase risk of human errors.

SOLUTION: by automating the process as much as possible , we will reduce the time and possiablity of errors by developing an script to do it.

RESOURCES: 2 be + 1 AQ
DURATION: 2 weeks
## Dex Swap
GOAL: buy and sell assets as soon as possible when they are backed by dex.

STAKEHOLDERS: financial

PROBLEM: at the moment when we sell an asset to customer which is backed by dex we actually don't obtain the asset. it will increase the risk of financial loss for exchange and the customer.

SOLUTION: when we sell an asset to the customer, we should buy the asset ASAP close to the price that we sold. It will decrease the risk of financial loss as we obtain the asset close to the price that we sold to the customer.

RESOURCES: 1 bd + 1 be  + 1 fe + 1 QA
DURATION: 2 weeks

## Add New Network in Chainpulse Polygun(EVM)
GOAL: create wallet addresses , detect deposits  ,fee calculation , withdraw  and wallets evacuation on Polygun Network.

STAKEHOLDERS: product

PROBLEM: currently system do not support Polygun Network and customers that have assets on this network can't deposit and withdraw any asset on Polygun.

SOLUTION: We should support Polygun network in chainpulse system to detect deposits, withdraw , fee calculation, evacuations and tracking each transaction status. Also we need to change Setting package , Lens services, Sarmayex, Internal wallet. New design on network list.

RESOURCES: 1 bd + 1 be  + 1 fe + 1 QA
DURATION: 2 weeks(automation)/ 3 weeks


## Warehouse
GOAL: We should have integrated data tables that can represent current state of the system and each feature. also we should be able to track users data in system.
In addition rate of each coin at the moment that each transaction and at the moment that reports have been generated. 

STAKEHOLDERS: financial, stakeholders

PROBLEM: currently each feature and user data are in different databases so there is no integrated data.

SOLUTION: By integrating data and remove useless data we can create bi reports that provide perfect sight of system current state and let managers and financials make decisions to align business .


RESOURCES:  1 bd + 2 be  + 1 fe + 1 QA
DURATION: 3 weeks + 3 days
### Warehouse core
RESOURCES:   2 be + 1 QA

DURATION: 2 weeks
### crypto gateway data fetch 
RESOURCES:  1 bd + 2 be  + 1 QA
DURATION: 1 weeks
### Bi panel
RESOURCES:   1 be  + 1 QA
DURATION: 3 days
## Rewrite Algo bot Service
GOAL: Market making bots should not have large amount of loss. We should be able to config each side(sell, buy) seperately  

STAKEHOLDERS: financial, stakeholders

PROBLEM: currently each feature and user data are in different databases so there is no integrated data.

SOLUTION: By integrating data and remove useless data we can create bi reports that provide perfect sight of system current state and let managers and financials make decisions to align business .

RESOURCES:  1 bd + 2 be  + 1 fe + 1 QA
DURATION: 3 weeks - 1 weeks R&D

## Rebalancing Core

GOAL: create centralized liquidity and asset balancing system across all financial services(features) and operational modules.

STAKEHOLDERS: financial

PROBLEM: currently lacks of  liquidity and balances for each feature cause increase hidden costs and make accounting of features blury.

SOLUTION: develop centralized rebalancing engine that monitors balances, liquidity requirements and exposures across all features and automatically performs balancing operations.
DURATION: 2 weeks  + 7 weeks

### Rebalancing Provider
GOAL: create provider abstraction layer for liquidity transfer and balancing operations.

STAKEHOLDERS: financial

PROBLEM: each provider has different balancing logic and APIs which increases operational complexity.

SOLUTION: develop unified provider layer for transfer orchestration, monitoring and automated balancing operations.
RESOURCES:  1 bd +2 be + 1 QA

DURATION: 2 weeks

### Algo bot
RESOURCES:  1 be + 1 QA
DURATION: 1 weeks
### crypto gateway
RESOURCES:  1 bd + 1 be + 1 QA
DURATION: 1 weeks
### OTC
RESOURCES:  1 bd + 1 be + 1 QA
DURATION: 1 weeks
### LOAN
RESOURCES:  1 be + 1 QA
DURATION: 1 weeks
### Stake
RESOURCES:  1 be + 1 QA
DURATION: 1 weeks
### Invoice
RESOURCES:  1 be + 1 QA
DURATION: 1 weeks
### Pool
RESOURCES:  1 be + 1 QA
DURATION: 1 weeks



##  Update CMS Service
GOAL: Update CMS panel for marketing teams.

STAKEHOLDERS: marketing

PROBLEM: current CMS capabilities are limited and create dependency on technical teams for content updates and campaign operations.

SOLUTION: upgrade CMS architecture and add operational tools for content management, campaigns and SEO optimization.

RESOURCES: 1 be + 1 fe + 1 QA
DURATION: 1 weeks
## Refactor and Launch Swap feature
GOAL: improve swap scalability, execution performance and user experience.

STAKEHOLDERS: product

PROBLEM: current swap implementation has architectural limitations and operational issues.

SOLUTION: refactor swap infrastructure and launch production-ready version with better liquidity and execution management.

RESOURCES: 1 be + 1 fe + 1 QA
DURATION: 2 weeks
## Add Dusting feature
GOAL: allow users to convert low-value balances into usable assets.

STAKEHOLDERS: product

PROBLEM: users accumulate small balances that cannot be traded or withdrawn efficiently.

SOLUTION: implement dust conversion feature for aggregating and converting small balances automatically by swap features.

RESOURCES: 2 be + 1 fe + 1 QA
DURATION: 2 weeks

## Create Club Service / Campaign
GOAL: create loyalty and campaign management infrastructure.

STAKEHOLDERS: marketing , product

PROBLEM: currently there is no centralized platform for loyalty programs, campaigns and referral systems.

SOLUTION: develop dedicated club service for user engagement and retention. club service should received data from all features of the system.

RESOURCES: 2 be + 1 fe + 1 QA
DURATION: 3 weeks
## Handel Dex Market price failure
GOAL: prevent incorrect pricing during DEX provider failures and outages.

STAKEHOLDERS: tech

PROBLEM: DEX provider instability can result in invalid prices and financial exposure.

SOLUTION: implement fallback providers, price validation and close markets if there is not liquidity pool (price) for that coin. bots should be stoped and prevents users from placing new orders.

RESOURCES: 2 be + 1 QA
DURATION: 2 weeks
## Delist Coins Flow
GOAL: create safe and standardized coin delisting process. 

STAKEHOLDERS: tech , product, financial , support, marketing

PROBLEM: current delisting operations are manual and operationally risky.

SOLUTION: develop unified delisting workflow including notification, disablement and operational coordination. user should be able to know when and how we delist a coin. financial should be able to specify converting rate and date of delisting.

RESOURCES:  2 be + 1 fe + 1 QA
DURATION: 2 weeks
## Debug Bank transaction
GOAL: identify and resolve bank transaction inconsistencies and failures.

STAKEHOLDERS: financial

PROBLEM: bank transaction issues impact reconciliation, operational stability, user trust and fiat deposit/withdraw time.

SOLUTION: improve bank transaction tracing, monitoring and recovery flows.

RESOURCES: 1 be + 1 QA
DURATION: 1 weeks
## Complete SEO 
GOAL: improve organic traffic and search engine visibility.

STAKEHOLDERS: marketing

PROBLEM: SEO implementation is incomplete and limits organic growth.

SOLUTION: implement technical SEO optimization, metadata improvements and performance enhancements.

RESOURCES: 1 fe 
DURATION: 2 weeks
## Sarmayex Credit Card
GOAL: launch integrated branded credit card infrastructure. users should be able to order a credit card , then move some assets into corresponding account in specific order. at the moment of using this card, we should create market order to convert asset/assets to fiat and pay the billing by this fiat. we need landing page for this feature too.

STAKEHOLDERS: product

PROBLEM: users currently do not have integrated card-based spending capabilities.

SOLUTION: develop credit card infrastructure and banking integration for transaction and card management.

RESOURCES:  2 be + 2 fe + 1 QA
DURATION: 6 weeks
## Profit and Loss (PNL)
GOAL: provide accurate profit and loss reporting for users and internal teams.

STAKEHOLDERS: product

PROBLEM: users and stakeholders currently lack visibility into realized and unrealized profitability.

SOLUTION: develop centralized PNL calculation and reporting infrastructure.

RESOURCES: 2 be + 1 fe + 1 QA
DURATION: 3 weeks
## Migration from Setting service to Lens
GOAL: centralize and modernize configuration management infrastructure and make configuration dynamic by moving them to database and finally edit them from admin panel. Lens service should hold all brokers configuration.

STAKEHOLDERS: tech

PROBLEM: current setting service architecture increases operational complexity and maintenance overhead.

SOLUTION: migrate configuration management capabilities into Lens service. also change all services to fetch configuration from lens instead of settings package

RESOURCES: 3 be + 1 bd + 1 QA
DURATION: 3 weeks 

## Grouped Access management
GOAL: implement scalable role and group-based access management. Admin of each department should be able to access his owned permission to sub accounts.

STAKEHOLDERS: tech, product, financial , marketing

PROBLEM: current access control model lacks flexibility and scalability. It takes a lots of time from CTO and 1 be to grant access to each account base on what they really need.

SOLUTION: develop grouped access management with hierarchical permissions and audit capabilities for each department admin.

RESOURCES: 2 be + 1 fe + 1 QA
DURATION: 1 week and 2 days
## Match Engine Database retention of removing use less data
GOAL: reduce database growth and optimize performance by removing unnecessary historical data.

STAKEHOLDERS: tech

PROBLEM: historical data growth negatively impacts database performance and infrastructure costs.

SOLUTION: implement retention policies, cleanup automation and archival strategy.

RESOURCES: 1 be + 1 QA
DURATION: 3 days
## IOS first Release
GOAL: launch first production-ready IOS application.

STAKEHOLDERS: product

PROBLEM: currently there is no IOS application available for users.

SOLUTION: develop and release IOS application with trading, wallet and notification capabilities.

RESOURCES: 2 mobile + 1 QA
DURATION: 2 weeks
## Tradingview Charts or Bitycle
GOAL: provide advanced charting and market analysis tools.

STAKEHOLDERS: product

PROBLEM: current charting infrastructure is limited and lacks advanced trading capabilities.

SOLUTION: integrate Tradingview infrastructure and real-time charting features.

RESOURCES: 1 fe + 1 QA
DURATION: 3 days
## Internal Transaction List for each user

STAKEHOLDERS:  product

GOAL: provide visibility into internal user transactions and transfers.

PROBLEM: users  currently lack visibility into internal asset movements.

SOLUTION: develop internal transaction history and tracking module with filtering and reporting capabilities.

RESOURCES: 1 be + 1 fe + 1 fd + 1 QA
DURATION: 2 weeks

## add iranian exchange 

STAKEHOLDERS:  product

GOAL: add an iranian exchange to the system in order to list coins faster.

PROBLEM: listing new coins are limited to the coinex and bitunex exchange.

SOLUTION: by adding a new iranian exchange we can list new coins as soon as possible.

RESOURCES: 2 bd + 1 be +  1 QA
DURATION: 2 weeks
