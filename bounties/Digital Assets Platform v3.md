# BOUNTY PROGRAM AGREEMENT

## PROJECT NAME
Digital Asset Platform

## VERSION
3.0

## ABSTRACT
There is no doubt that the Digital Asset Platform is on the critical path to the sucess of our project. As Fermat evolves and new architecture is designed an implemented in all platforms, DAP must follow this approach and improve itself to acommodate future changes.

This bounty is mainly an architecture improvement following new guidelines to modularize our processes into smaller pieces and enable reutilization, optimization and prepare for future transactions that DAP will be supporting shortly.



## SCOPE

### 1- Architecture re design:  
New architecture implementation as in [dev.fermat.org](http://dev.fermat.org). Full implementation of 33 new plugins.

**Size:** 40%  
**Fermat components:** 

* Asset Miner Agent
* Asset Transfer, Asset Redemption, Asset Distribution, Asset Issuing, Asset Fixed Bitcoin Price Direct Private Sell and Asset Break User Business Transactions
* Asset Hold and Asset Unhold Business Transactions.
* Multi Transaction Asset Issuing, Asset Break and Asset Transfer Digital Asset Transactions
* Incoming Asset Offer and Outgoing Asset Offer Transaction
* Asset For Bitcoin and Bitcoin For Asset Swap Transactions
* Incoming Asset Metadata and Outgoing Asset Metadata
* Incoming Crypto Transaction and Outgoin Crypto Transaction
* Asset Issuer Statisc Aggregator
* Asset Transfer, Asset Issuing and Asset Swap Statistics Collector.
* Asset Specific Offer
* Digital Asset Metadata
* Asset Issuer, Asset User and Redeem Point Actor Connection.
* Statistics and Offer Network Services.

### 2- GUI re design:  
Graphic improvements to Wallets and sub apps.

**Size:** 30%  
**Fermat components:** 

* Asset Issuer Wallet
* Asset User Wallet
* Redeem Point Wallet
* Asset Factory

### 3- bitDubai Refactor:  
Refactoring existing plugins to remove bitDubai name from components. 

**Size:** 0%  
**Fermat components:** 

* All existing plugins.

### 4- Incoming Assets Notification:  
Add funcionality to allow an asset receiver to choose or deny reception of a new asset. Changes include adding:

* Settings to specify if assets are accepted by default.
* Include notifications for incoming assets.
* Modify transactions flow to enable user response.


**Size:** 10%  
**Fermat components:** 

* Asset Transfer, Asset Distribution, Asset Redemption transactions.
* Asset User and Redeem Point wallets.

### 5- Outgoing Crypto Transaction events:  
Currently only incoming crypto transactions are handled by raising events from the Crypto Reouter plugin. We are going to improve the Outgoing transactions process by using the same procedure.

**Size:** 5%  
**Fermat components:** 

* Incoming Crypto Transaction and Outgoing Crypto Transaction DAP plugins.
* Crypto Router and CryptoNetwork plugines in BCH platform.

### 6- Bitcoin Fees specification:  
Asset transactions fee is payed from the Asset Vault using Bitcoins from the Asset. We want to improve this by giving the user the chance to pay the bitcoin transaction fee from the Bitcoin Vault.

**Size:** 15%  
**Fermat components:** 

* Bitcoin and Asset Vaults.
* Asset Transfer, Asset Distribution, Asset Redemption transactions.
* Asset User and Asset Issuer wallets.


## EVALUATION
Provide the acceptance criteria for the features described on the scope.

## TERMS AND CONDITIONS: 

1.   The team agrees that project has two parts: functionality and beta testing.
 
2.  The team understands and accepts that the functionality will be considered done when all the features described on the scope of this agreement are completed and tested in an alpha stage.
 
3.    The team agrees to complete the functionality on the following conditions:
 
- **Implementation due date:** All the features will be finished before __ __ __
 
- **Implementation collateral deposit:** The team agrees to deposit the amount of ________ tokens, as a collateral to be lost if this part project is not approved before the due date.
 
- **Implementation margin:** No penalties are applied ___ calendar days after implementation due date.
 
- **Implementation penalty:** __% of the bounty for each calendar day elapses after the due date without formal acceptance from the @bounty-program-team.  
 
- **Implementation bounty:** The functionality will be __% of the total bounty. This bounty will be awarded to the development team when the @bounty-program-team considers that the functionality delivered is done.
 
4. The team understands and accepts that beta testing will be conducted by the @beta-testing-team.
 
5.  The team understands and accepts that criteria to pass beta testing are: no bug issues on beta testing due date or in a period of three (3) consecutive calendar days before the due date.
 
6.   The team agrees to complete the beta testing on the following conditions:
 
- **Beta testing due date:** Beta testing will be passed __ calendar days after getting the formal acceptance of functionality from @bounty-program-team.
 
- **Beta testing collateral deposit:** The team agrees to deposit the amount of ________ tokens, as a collateral to be lost if this part of the project is not approved before the due date.
 
- **Beta testing margin:** No penalties are applied ___ calendar days after the beta testing due date.
 
- **Beta testing penalty:** __% of the bounty for each calendar day elapses after the due date without formal acceptance from the @beta-testing-team. This penalty will be paid by the development team from the implementation bounty to the beta testing team.
 
- **Beta testing bounty:** The beta testing bounty will be __% of the total bounty. It could be awarded to the development team if it passes the beta testing on time or by @beta-testing-team if fails. It implies that development team will not get this bounty unless it succeeds in the beta testing process.

## TOTAL BOUNTY
The total amount of the bounty in Fermat tokens for this project (functionality + beta testing).

## DISTRIBUTION OF BOUNTY BY CONTRIBUTOR
The distribution of the bounty (once awarded).
