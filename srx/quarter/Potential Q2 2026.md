## Technical Items

### Faster OTC
**GOAL:** Convert money first and give it to the user, then trade it.
**STAKEHOLDERS:**  tech 10
**PROBLEM:** Current OTC process causes delays in user fund availability.
**SOLUTION:** Prioritize fund conversion and user distribution before executing the underlying trade.
**RESOURCES:** 1 be
**DURATION:** 1 be => 5 days

---

### Automate Network and Currency Release
**GOAL:** Create automation for update, push and deploy setting package in different services and restart.
**STAKEHOLDERS:** product 8, marketing 7, tech 10
**PROBLEM:** At the moment adding a new network or currency is manual and takes considerable amount of time, it also increases risk of human errors.
**SOLUTION:** By automating the process as much as possible, we will reduce the time and possibility of errors by developing a script to do it.
**RESOURCES:** 2 be + 1 QA
**DURATION:** 2 be => 7 days

---

### Rewrite Algo Bot Service
**GOAL:** Market making bots should not have large amount of loss. We should be able to config each side (sell, buy) separately.
**STAKEHOLDERS:** financial 10, executive 10, marketing 7, product 8, tech 10
**PROBLEM:** Currently each feature and user data are in different databases so there is no integrated data.
**SOLUTION:** By integrating data and removing useless data we can create BI reports that provide perfect sight of system current state and let managers and financials make decisions to align business.
**RESOURCES:** 1 bd + 2 be + 1 fe + 1 QA
**DURATION:**
- 1 bd => 1 day
- 2 be => R&D 7 days, 14 days
- 1 fe => 5 days

---

### Debug Bank Transaction
**GOAL:** Identify and resolve bank transaction inconsistencies and failures.
**STAKEHOLDERS:** financial 10
**PROBLEM:** Bank transaction issues impact reconciliation, operational stability, user trust and fiat deposit/withdraw time.
**SOLUTION:** Improve bank transaction tracing, monitoring and recovery flows.
**RESOURCES:** 1 be + 1 QA
**DURATION:** Not specified

---

### Tradingview Charts or Bitycle
**GOAL:** Provide advanced charting and market analysis tools.
**STAKEHOLDERS:** product 10, marketing 8, tech 7
**PROBLEM:** The current charting infrastructure is limited and lacks advanced trading capabilities.
**SOLUTION:** Integrate TradingView infrastructure and real-time charting features.
**RESOURCES:** 1 fe + 1 QA
**DURATION:**
- 1 fe => 3 days
- 1 fd => 1 day

---

### Complete SEO
**GOAL:** Improve organic traffic and search engine visibility.
**STAKEHOLDERS:** marketing 10
**PROBLEM:** SEO implementation is incomplete and limits organic growth.
**SOLUTION:** Implement technical SEO optimization, metadata improvements and performance enhancements.
**RESOURCES:** 1 fe
**DURATION:** 1 fe => 8 days

---

### Optimize Evacuation Fee
**GOAL:** Optimize evacuation fee structure and calculation.
**STAKEHOLDERS:** financial 10, executive 10
**PROBLEM:** Current evacuation fees are not optimized.
**SOLUTION:** Analyze and optimize evacuation fee logic.
**RESOURCES:** 1 bd
**DURATION:** 1 bd => 14 days

---

### K8s Infrastructures
**GOAL:** Move infrastructure to K8s.
**STAKEHOLDERS:** tech 10
**PROBLEM:** Currently, services are deployed on several machines using Docker containers. It's hard to manage them, and to have access to logs of the service, you have to have access to the production server. Also, there is no centralized management for services.
**SOLUTION:** By moving services into K8s infra, we are able to use centralized service and access management. Reducing risk of human error and RCEs.
**RESOURCES:** 2 devops + 1 be
**DURATION:**  2 devops  => 7 days

---

### Rebalancing Core
**GOAL:** Create centralized liquidity and asset balancing system across all financial services (features) and operational modules.
**STAKEHOLDERS:** financial 9, executive 8, product 7
**PROBLEM:** Currently lack of liquidity and balances for each feature causes increase hidden costs and makes accounting of features blurry.
**SOLUTION:** Develop centralized rebalancing engine that monitors balances, liquidity requirements and exposures across all features and automatically performs balancing operations.

#### Rebalancing Provider
**GOAL:** Create provider abstraction layer for liquidity transfer and balancing operations.
**STAKEHOLDERS:** financial
**PROBLEM:** Each provider has different balancing logic and APIs which increases operational complexity.
**SOLUTION:** Develop unified provider layer for transfer orchestration, monitoring and automated balancing operations.
**RESOURCES:** 1 bd + 2 be + 1 QA
**DURATION:**
- 1 bd => 1 day
- 2 be => 10 days
- 1 fe => 4 days

#### Algo Bot

**RESOURCES:** 1 be + 1 QA
**DURATION:** 1 be => 2 days
#### Crypto Gateway

**RESOURCES:** 1 bd + 1 be + 1 QA
**DURATION:** 1 be => 3 days

#### OTC

**RESOURCES:** 1 bd + 1 be + 1 QA
**DURATION:** 1 be => 3 days

#### LOAN

**RESOURCES:** 1 be + 1 QA
**DURATION:** 1 be => 1 day

#### Stake

**RESOURCES:** 1 be + 1 QA
**DURATION:** 1 be => 3 days

#### Pool

**RESOURCES:** 1 be + 1 QA
**DURATION:** 1 be => 3 days

---

### Delist Coins Flow
**GOAL:** Create safe and standardized coin delisting process.
**STAKEHOLDERS:** tech 10, product 7, financial 7, support 8, marketing 7
**PROBLEM:** Current delisting operations are manual and operationally risky.
**SOLUTION:** Develop unified delisting workflow including notification, disablement and operational coordination. User should be able to know when and how we delist a coin. Financial should be able to specify converting rate and date of delisting.
**RESOURCES:** 2 be + 1 fe + 1 QA
**DURATION:**
- 2 be => 4 days
- 2 fe => 3 days
- 1 fd => 4 days

---

### Migration from Setting Service to Lens
**GOAL:** Centralize and modernize configuration management infrastructure and make configuration dynamic by moving them to database and finally edit them from admin panel. Lens service should hold all brokers configuration.
**STAKEHOLDERS:** tech 10, financial 7
**PROBLEM:** Current setting service architecture increases operational complexity and maintenance overhead.
**SOLUTION:** Migrate configuration management capabilities into Lens service. Also change all services to fetch configuration from lens instead of settings package.
**RESOURCES:** 3 be + 1 bd + 1 QA
**DURATION:** 2 be => 14 days

---

### Warehouse
**GOAL:** We should have integrated data tables that can represent current state of the system and each feature. Also we should be able to track users data in system. In addition rate of each coin at the moment that each transaction and at the moment that reports have been generated.
**STAKEHOLDERS:** financial 10, marketing 10, product 10, executive 8
**PROBLEM:** Currently each feature and user data are in different databases so there is no integrated data.
**SOLUTION:** By integrating data and removing useless data we can create BI reports that provide perfect sight of system current state and let managers and financials make decisions to align business.
**RESOURCES:** 1 bd + 2 be + 1 fe + 1 QA


#### Warehouse Core
**RESOURCES:** 2 be + 1 QA
**DURATION:** 2 be => 7 days

#### Crypto Gateway Data Fetch
**RESOURCES:** 1 bd + 2 be + 1 QA
**DURATION:**
- 1 bd => 1 day
- 2 be => 5 days

#### BI Panel
**RESOURCES:** 1 be + 1 QA
**DURATION:** 1 be => 4 days

---

### Update CMS Service
**GOAL:** Update CMS panel for marketing teams.
**STAKEHOLDERS:** marketing 10
**PROBLEM:** Current CMS capabilities are limited and create dependency on technical teams for content updates and campaign operations.
**SOLUTION:** Upgrade CMS architecture and add operational tools for content management, campaigns and SEO optimization.
**RESOURCES:** 1 be + 1 fe + 1 QA
**DURATION:** 1 be => 5 days

---

### Myket, Bazaar, Google Play, App Store Accounting
**GOAL:** create account for Myket, Bazaar, Google Play, App Store.
**STAKEHOLDERS:** Not specified
**PROBLEM:** currently account owners changed or there is no account for some store.
**SOLUTION:** we should create account in each one of these stores.
**RESOURCES:** 1 fd
**DURATION:** 1 fd => 7 days

---

### iOS First Release
**GOAL:** Launch first production-ready iOS application.
**STAKEHOLDERS:** product 8, marketing 8
**PROBLEM:** Currently there is no iOS application available for users.
**SOLUTION:** Develop and release iOS application with trading, wallet and notification capabilities.
**RESOURCES:** 2 mobile + 1 QA
**DURATION:** 1 fd => 7 days

---

### Add New Network in Chainpulse Polygon (EVM)
**GOAL:** Create wallet addresses, detect deposits, fee calculation, withdraw and wallets evacuation on Polygon Network.
**STAKEHOLDERS:** product 8, executive 8
**PROBLEM:** Currently system does not support Polygon Network and customers that have assets on this network can't deposit and withdraw any asset on Polygon.
**SOLUTION:** We should support Polygon network in chainpulse system to detect deposits, withdraw, fee calculation, evacuations and tracking each transaction status. Also we need to change Setting package, Lens services, Sarmayex, Internal wallet. New design on network list.
**RESOURCES:** 1 bd + 1 be + 1 fe + 1 QA
**DURATION:**
- 1 bd => 7 days
- 1 be => 1 day

---

### Refactor and Launch Swap Feature
**GOAL:** Improve swap scalability, execution performance and user experience.
**STAKEHOLDERS:** product 9, marketing 5, executive 5
**PROBLEM:** Current swap implementation has architectural limitations and operational issues.
**SOLUTION:** Refactor swap infrastructure and launch production-ready version with better liquidity and execution management.
**RESOURCES:** 1 be + 1 fe + 1 QA
**DURATION:**
- Product: 2 days
- 1 be => 4 days
- 1 fe => 3 days
- 1 fd => 7 days

---

### Add Dusting Feature
**GOAL:** Allow users to convert low-value balances into usable assets.
**STAKEHOLDERS:** product 9, marketing 5, executive 5
**PROBLEM:** Users accumulate small balances that cannot be traded or withdrawn efficiently.
**SOLUTION:** Implement dust conversion feature for aggregating and converting small balances automatically by swap features.
**RESOURCES:** 2 be + 1 fe + 1 QA
**DURATION:**
- Product: 2 days
- 1 be => 4 days
- 1 fe => 4 days
- 1 fd => 5 days

---

### Create Club Service
**GOAL:** Create loyalty and campaign management infrastructure.
**STAKEHOLDERS:** marketing 10, product 6, executive 6
**PROBLEM:** Currently there is no centralized platform for loyalty programs, campaigns and referral systems.
**SOLUTION:** Develop dedicated club service for user engagement and retention. Club service should receive data from all features of the system.
**RESOURCES:** 2 be + 1 fe + 1 QA
**DURATION:**
- Product: 4 weeks
- 2 be => 7 days

#### Campaign IRT Deposits
**RESOURCES:** 2 be
**DURATION:** 2 be => 10 days
 1 fe => 4 days

---

### Sarmayex Credit Card
**GOAL:** Launch integrated branded credit card infrastructure. Users should be able to order a credit card, then move some assets into corresponding account in specific order. At the moment of using this card, we should create market order to convert asset/assets to fiat and pay the billing by this fiat. We need landing page for this feature too.
**STAKEHOLDERS:** product 7, marketing 6, executive 5
**PROBLEM:** Users currently do not have integrated card-based spending capabilities.
**SOLUTION:** Develop credit card infrastructure and banking integration for transaction and card management.
**RESOURCES:** 2 be + 2 fe + 1 QA
**DURATION:**
- Product: 2 weeks
- 2 be => 14 days
- 2 fe => 8 days
- 1 fd => 14 days

---

### Profit and Loss (PNL)
**GOAL:** Provide accurate profit and loss reporting for users and internal teams.
**STAKEHOLDERS:** product 5
**PROBLEM:** Users and stakeholders currently lack visibility into realized and unrealized profitability.
**SOLUTION:** Develop centralized PNL calculation and reporting infrastructure.
**RESOURCES:** 2 be + 1 fe + 1 QA
**DURATION:** 2 be => 14 days
1 fe => 7 days

---

### Grouped Access Management
**GOAL:** Implement scalable role and group-based access management. Admin of each department should be able to access his owned permission to sub accounts.
**STAKEHOLDERS:** tech 8, product 6, financial 8
**PROBLEM:** Current access control model lacks flexibility and scalability. It takes a lot of time from CTO and 1 be to grant access to each account base on what they really need.
**SOLUTION:** Develop grouped access management with hierarchical permissions and audit capabilities for each department admin.
**RESOURCES:** 2 be + 1 fe + 1 QA
**DURATION:** 1 be => 4 days

---

### Match Engine Database Retention of Removing Useless Data
**GOAL:** Reduce database growth and optimize performance by removing unnecessary historical data.
**STAKEHOLDERS:** tech 7
**PROBLEM:** Historical data growth negatively impacts database performance and infrastructure costs.
**SOLUTION:** Implement retention policies, cleanup automation and archival strategy.
**RESOURCES:** 1 be + 1 QA
**DURATION:** 1 be => 2 days

---

### Add Iranian Exchange
**GOAL:** Add an Iranian exchange to the system in order to list coins faster.
**STAKEHOLDERS:** product 7, marketing 8
**PROBLEM:** Listing new coins is limited to the Coinex and Bitunex exchange.
**SOLUTION:** By adding a new Iranian exchange, we can list new coins as soon as possible.
**RESOURCES:** 2 bd + 1 be + 1 QA
**DURATION:**
- 1 bd => 12 days
- 1 be => 3 days

---

### Add the Market of the Current Supported Currencies
**GOAL:** Add market for currently supported currencies.
**STAKEHOLDERS:** product 10, marketing 10
**PROBLEM:** Not specified
**SOLUTION:** Not specified
**RESOURCES:** 1 be
**DURATION:** 1 be => 2 days

---

### Dex Swap
**GOAL:** Buy and sell assets as soon as possible when they are backed by DEX.
**STAKEHOLDERS:** financial 2
**PROBLEM:** At the moment when we sell an asset to a customer which is backed by DEX we actually don't obtain the asset. It will increase the risk of financial loss for exchange and the customer.
**SOLUTION:** When we sell an asset to the customer, we should buy the asset ASAP close to the price that we sold. It will decrease the risk of financial loss as we obtain the asset close to the price that we sold to the customer.
**RESOURCES:** 1 bd + 1 be + 1 fe + 1 QA
**DURATION:**
- 1 bd => 14 days
- 1 be => 5 days
- 1 fe => 4 days

---

### Handle DEX Market Price Failure
**GOAL:** Prevent incorrect pricing during DEX provider failures and outages.
**STAKEHOLDERS:** tech 10, financial 10, executive 10, product 7
**PROBLEM:** DEX provider instability can result in invalid prices and financial exposure.
**SOLUTION:** Implement fallback providers, price validation and close markets if there is no liquidity pool (price) for that coin. Bots should be stopped and prevents users from placing new orders.
**RESOURCES:** 2 be + 1 QA
**DURATION:** 2 be => 3 days

---

### Event Tracking / Attribution System (GA4, Adtrace) / Marketing Automation / CRM Journey
**GOAL:** Implement comprehensive event tracking and marketing automation.
**STAKEHOLDERS:** marketing 10, product 8
**PROBLEM:** Not specified
**SOLUTION:** Proxy data through the APIs. https://intrack.io/ https://zebline.com/
**RESOURCES:** 1 fd + 1 fe
**DURATION:**
- 1 fd => 7 days
- 1 fe => 7 days

---

### Referral and Affiliate
**GOAL:** Implement referral and affiliate system.
**STAKEHOLDERS:** marketing 10, product 7
**PROBLEM:** Fee in market not OTC, user should be able to create multiple ref codes and share fee percent with referrer. If we give 30% of profit, user can split it to 10% himself, 20% others.
**SOLUTION:** Develop multi-level referral and affiliate system.
**RESOURCES:** 2 be + 1 fe + 1 fd
**DURATION:**
- Product: 1 week
- 2 be => 7 days
- 1 fe => 2 days
- 1 fd => 2 days

---

### Create a Manual Increase Flow
**GOAL:** Create manual increase flow for specific operations.
**STAKEHOLDERS:** Not specified
**PROBLEM:** Not specified
**SOLUTION:** Not specified
**RESOURCES:** 1 be
**DURATION:** 1 be => 2 days


---

## Potential Quarter Document (Q3 2026 - Example)

| Project | Duration | Resources | Stakeholders | Priority |
|---------|----------|-----------|--------------|----------|
| Faster OTC | 5 days | 1 be | product 8, marketing 7, tech 10 | High |
| Automate Network and Currency Release | 7 days | 2 be + 1 QA | product 8, marketing 7, tech 10 | High |
| Rewrite Algo Bot Service | 1+7+14+5 days | 1 bd + 2 be + 1 fe + 1 QA | financial 10, executive 10, marketing 7, product 8, tech 10 | Critical |
| Debug Bank Transaction | TBD | 1 be + 1 QA | financial 10 | High |
| Tradingview Charts | 3+1 days | 1 fe + 1 QA | product 10, marketing 8, tech 7 | Medium |
| Complete SEO | 8 days | 1 fe | marketing 10 | High |
| Optimize Evacuation Fee | 14 days | 1 bd | financial 10, executive 10 | Medium |
| K8s Infrastructures | TBD | 2 devops + 1 be | tech 10 | Critical |
| Rebalancing Core | TBD | TBD | financial 9, executive 8, product 7 | High |
| Rebalancing Provider | 1+10+4 days | 1 bd + 2 be + 1 QA | financial | High |
| Algo Bot | 2 days | 1 be + 1 QA | TBD | Medium |
| Crypto Gateway | 3 days | 1 bd + 1 be + 1 QA | TBD | Medium |
| OTC | 3 days | 1 bd + 1 be + 1 QA | TBD | Medium |
| LOAN | 1 day | 1 be + 1 QA | TBD | Low |
| Stake | 3 days | 1 be + 1 QA | TBD | Medium |
| Pool | 3 days | 1 be + 1 QA | TBD | Medium |
| Delist Coins Flow | 4+3+4 days | 2 be + 1 fe + 1 QA | tech 10, product 7, financial 7, support 8, marketing 7 | High |
| Migration to Lens | 14 days | 3 be + 1 bd + 1 QA | tech 10, financial 7 | Critical |
| Warehouse (Core + Gateway + BI) | 7+1+5+4 days | 1 bd + 2 be + 1 fe + 1 QA | financial 10, marketing 10, product 10, executive 8 | Critical |
| Update CMS Service | TBD | 1 be + 1 fe + 1 QA | marketing 10 | Medium |
| App Store Accounting | 7 days | 1 fd | TBD | Low |
| iOS First Release | 7 days | 2 mobile + 1 QA | product 8, marketing 8 | High |
| Add Polygon Network | 7+1 days | 1 bd + 1 be + 1 fe + 1 QA | product 8, executive 8 | High |
| Refactor Swap | 2+4+3+7 days | 1 be + 1 fe + 1 QA | product 9, marketing 5, executive 5 | High |
| Dusting Feature | 2+4+4+5 days | 2 be + 1 fe + 1 QA | product 9, marketing 5, executive 5 | Medium |
| Club Service | 4w + 7+10+4 days | 2 be + 1 fe + 1 QA | marketing 10, product 6, executive 6 | High |
| Sarmayex Credit Card | 2w + 14+8+14 days | 2 be + 2 fe + 1 QA | product 7, marketing 6, executive 5 | High |
| PNL | TBD | 2 be + 1 fe + 1 QA | product 5 | Medium |
| Grouped Access Management | 4 days | 2 be + 1 fe + 1 QA | tech 8, product 6, financial 8 | High |
| Match Engine Retention | 2 days | 1 be + 1 QA | tech 7 | Low |
| Add Iranian Exchange | 12+3 days | 2 bd + 1 be + 1 QA | product 7, marketing 8 | Medium |
| Add Market for Currencies | 2 days | 1 be | product 10, marketing 10 | Medium |
| Dex Swap | 14+5+4 days | 1 bd + 1 be + 1 fe + 1 QA | financial 2 | Medium |
| Handle DEX Price Failure | 3 days | 2 be + 1 QA | tech 10, financial 10, executive 10, product 7 | High |
| Event Tracking & Marketing Automation | 7+7 days | 1 fd + 1 fe | marketing 10, product 8 | High |
| Referral and Affiliate | 1w + 7+2+2 days | 2 be + 1 fe + 1 fd | marketing 10, product 7 | High |
| Manual Increase Flow | 2 days | 1 be | TBD | Low |
| Website Accessibility During Outages | TBD | TBD | marketing 10 | Medium |
| Internal Transaction List | 1 day | 1 be + 1 fe + 1 fd + 1 QA | product 8 | Low |