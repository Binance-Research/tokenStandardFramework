
# Blockchain-Based Token Standard Framework (initial draft by Binance Research)

Following [our recent report on tokenization](https://info.binance.com/en/research/marketresearch/tokenization.html), we decided to develop a simple framework to evaluate blockchain tokens based on both the underlying source code and its technological implementation.

The first section introduces the framework and its set of criteria. The second segment applies this framework to a set of existing blockchain-based tokens. 

## 1. Framework definition

This subsection discusses and introduces a multi-criteria framework to analyze and distinguish tokens based on both the underlying source code and its technological implementation.

### (1) Blockchain(s) and layer(s)

The first element refers to the blockchain(s) where the token is issued. As an example, USD Coin (USDC) is an asset, running solely on the Ethereum blockchain.

Conversely, some assets exist on multiple blockchains. USD Tether runs on four different networks: Bitcoin (through the Omni layer), EOS, Ethereum, and Tron. Similarly, Binance GBP Stablecoin (BGBP) runs on both Ethereum and Binance Chain.

Furthermore, tokens may exist on first or second layer.

Examples of first-layer tokens include USDC (on Ethereum) or BTT (on Tron), while second-layer tokens include USDH (on the Simple Ledger Protocol, running on Bitcoin Cash) and USDT (running on the Omni layer, built on Bitcoin).  

### (2) Ownership Model: UTXO vs. Account-Based Model

This second criterion refers to the ownership of the tokens.

Many blockchains such as Ethereum or NEO rely on an account-based model. Token ownership is reflected based on looking at balances for each address.

On the other hand, the UTXO (Unspent Transaction Output) model is used by Plasma side-chains. Token ownership links to the ability to use the private key, which allows a UTXO to be spent. 

### (3) Native vs. Constructed Standard

A native standard refers to a blockchain which natively supports the creation of specific tokens on its chain, Binance Chain being a prime example with the BEP-2 standard. For example - from a code perspective - tokens built on the Binance Chain all run natively. 

As a result, BNB (the Binance Chain Native Token) is similar to other tokens issued under the BEP-2 standard (e.g., MITH), which all run natively on the Binance Chain.

On the other hand, a constructed standard refers to a blockchain whose tokens run owing to the deployment of a smart-contract. Ethereum's ERC-20 and Tron's TRC-20 are two familiar standards. For instance, ERC-20 tokens are not recognized at the blockchain level and run on a Virtual Machine (e.g., the Ethereum Virtual Machine).

### (4) Fungibility Status

Another critical distinction relates to each token’s fungibility status. Tokens can exist as fungible, non-fungible, and partially fungible. A fungible token refers to tokens whose value is the same with no distinct features between each other. In short, fungible tokens are interchangeable.

A non-fungible token (NFT) is a particular type of tokens that represents something unique (e.g., a CryptoKitty). As a result, NFT (even from the same type) are not interchangeable.

A partially fungible token is a type of token whose ownership can be divided into different partitions with partitions being fungible and non-fungible. An example relates to security tokens where the non-fungible token partition may have specific covenants (e.g., vesting period specific to the token-owner).

### (5) Transfer and Ownership Restrictions

From a code perspective, the main distinction between a utility and security token refers to whether there are restrictions on transfers and ownership.

Prominent examples include Ethereum's ERC-1400 set of standards which can impose restrictions such as limited transfers between two addresses or the blacklisting of some addresses.

On the other hand, the vast majority of ERC-20 tokens do not incorporate ownership or transfer restrictions.

### (6) Scarcity: Mint-ability and Fixed Maximum Supply

Tokens can either have a fixed supply or a supply that may vary over time. Different functions can be incorporated in a  smart-contract (or natively), such as the burn and mint functions, which allow future changes in the supply.

Furthermore, there is a distinction between which address can effectively call these “supply changing functions”. These functions can either be performed by a single address ("central call model") or by multiple addresses ("open call model").


### (7) Divisibility and Precision Level

There are some criteria on whether a token is divisible and the maximum precision level.

Some fungible tokens are indivisible where others allow specific precision levels such as 18 decimals. On the other hand, non-fungible tokens are, by nature, indivisible as each token has unique characteristics.

### (8) Privacy Features

This criterion refers to whether the token can be transferred through private transactions. Some privacy features can exist at the blockchain level (e.g, Dusk Network) or through a second layer implementation.

### (9) Governance and Other Additional Functions

Another final component relates to whether additional functions are built in the token smart contract. Some tokens carry voting rights or governance functions. For instance, Maker (MKR) holders can participate in the on-chain governance process, setting up the stability fee for CDPs ([Collateralized Debt Positions](https://cdp.makerdao.com/help/what-is-a-collateralized-debt-position-cdp)). 

## 2. Case studies

In this section, six tokens are randomly selected and analyzed through the lens of the Binance’s token framework, which was defined previously.

### 2.1 Basic Attention Token (BAT)

-   Blockchain(s): [Ethereum](https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef)

-   Account-based
    
-   ERC-20 - Constructed Standard
    
-   Fungible Token
    
-   Utility purpose with no transfer/ownership restriction
    
-   Fixed Maximum Supply: 1,500,000,000 units
    
-   Divisibility: Yes, 18 decimals

-   Privacy: No
    
-   Additional functions: Yes ([https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef#readContract](https://etherscan.io/token/0x0d8775f648430679a709e98d2b0cb6250d2887ef#readContract))
    

### 2.2 Enjin Coin (ENJ)

-   Blockchain(s): [Ethereum](https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c)

-   Account-based

-   ERC-20 - Constructed Standard
    
-   Fungible Token
    
-   Utility purpose with no transfer/ownership restriction
    
-   Fixed Maximum Supply: 1,000,000,000 units
    
-   Divisibility: Yes, 18 decimals

-   Privacy: No
    
-   Additional functions: Yes ([https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c#readContract](https://etherscan.io/token/0xf629cbd94d3791c9250152bd8dfbdf380e2a3b9c#readContract))
    

### 2.3 Binance GBP Stablecoin (BGBP)

-   Blockchain(s): [Ethereum](https://etherscan.io/address/0xc9a2c4868f0f96faaa739b59934dc9cb304112ec#code), [Binance Chain](https://explorer.binance.org/asset/BGBP-CF3)
    
-   ERC-20 - Constructed Standard / BEP-2 - Native Standard

-   Account-based
    
-   Fungible Token
    
-   Transfer and ownership restriction with the possibility to freeze funds (Ethereum token).
    
-   Fixed Maximum Supply: No. Minting/Burning functions.
    
-   Divisibility: Yes, 18 decimals (Ethereum). 8 decimals (Binance Chain)

-   Privacy: No
    
-   Additional functions: No
    

### 2.4 BitTorrent (BTT)

-   Blockchain(s): [Tron](https://tronscan.org/#/token/1002000)

-   Account-based
    
-   TRC-10 - Native Standard
    
-   Fungible Token
    
-   No transfer/ownership restriction
    
-   Fixed Maximum Supply: 990,000,000,000 units
    
-   Divisibility: Yes. 6 decimals.

-   Privacy: No
    
-   Additional functions: TODO
    

### 2.5 Mithril (MITH)

-   Blockchain(s): [Binance Chain](https://explorer.binance.org/asset/MITH-C76)

-   Account-based

-   BEP-2 - Native Standard
    
-   Fungible token
    
-   No transfer/ownership restriction
    
-   Fixed Maximum Supply: Yes. 994,903,806 units
    
-   Divisibility: Yes. 8 decimals.

-   Privacy: No
    
-   Additional functions: No
    

### 2.6 CryptoKitty (#4334)

-   Blockchain: [Ethereum](https://etherscan.io/token/0x06012c8cf97bead5deae237070f9587f8e7a266d?a=4334#inventory)

-   Account-based 
    
-   ERC-721 - Constructed Standard
    
-   Non-fungible token
    
-   No transfer/ownership restriction
    
-   Fixed Maximum Supply: N/A
    
-   Divisibility: No

-   Privacy: No
    
-   Additional functions: No
 

  

