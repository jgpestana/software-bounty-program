![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")
​
# Art Platform Bounty
​
## Introduction
​
The main objective of ART platform is to connect two type of fermat actors , in this case artists and fans. Provide a link to the artists websites, where the fans could buy tokens and exchange thoses tokens by songs. Other  functionality of the ART platform is list , play and manage the fan purchased songs in to the device, also this platform offer the posibility to chat between fans and artist..
​
This document describes the scope, design and timeline for this development.
​
## Scope
​
### Current developments in progress
​
​
For this version we will use **Tokenly** as external system, Tokenly is a website to buy  song with tokens, and then download it, Tokenly has a public API who allows to consult the tokens catalog of a system user (swapbot) and check the status of exchange transactions of tokens for services (token slots),  but it's in a very early stage of development, and it currently provide minimal information. We will develop a platform, Tokenly  **(TKY)** to obtain all the information who need the ART platform. This new platform will have a wallet that allows management of songs obtained through the public API Tokenly.
​
​
### Bounty scope

### Art Platform
​
### New Android App: Fan song wallet.
This **Wallet** will allow the fan to review a list of artist connected to the fan that have an active account in **Tokenly**. Also, it must show available songs on the local storage device and display songs purchased through **Tokenly**.

### New Android Sub-App: Music Player.
This will be an sub app that plays a song obtained through the TKY platform..
​
### New Android Sub-App: Artist Community
This sub app will provide a list of Artists Actors registered on the platform and the functionality to connect a Fermat actor with any of the artist displayed in the list.
​
### New Android Sub-App: Fan Community
This sub app will provide a list of Fans actors registered on the platform and the functionality to connect a Fermat actor with any Fans displayed in the list.
​
### New Android Sub-App: Artist Identity
This sub app will provide the functionality to create an identity as an Artist on the platform.
​
### New Android Sub-App: Fan Community
This sub app will provide the functionality to create an identity as an Fan on the platform.
​
### New Wallet Module: Fan song wallet
Wallet module for Fan song wallet.

### New Sub app Module: Fan song wallet
Sub app module for Fan song wallet.
​
### New Sub app Module: Artist Community
Sub app module for Artist Community.
​
### New Sub app Module: Fan Community
Sub app module for Fan Community.
​
### New Sub app Module: Artist Identity
Sub app module for Artist Identity.
​
### New Sub app Module: Fan Identity
Sub app module for Fan Identity.
​
### New Identity: Artist.
This plugin must have the ability to create an Artist identity in Fermat.
​
### New Identity: Fan.
This plugin must have the ability to create an Fan identity in Fermat.
​
### New Actor Network Service: Artist.
This plugin should be able to allow connections to a remote Artist and return the list of Artists connected to the system.
​
### New Actor Network Service: Fan.
This plugin should be able to allow connections to a remote Fan and return the list of fans connected to the system.

### New External API: Tokenly.
This plugin should be able to allow interaction between **ART** platform and **TKY** platform.

### TKY Platform

### New Android Sub-App: Tokenly Identity
This sub app will provide the functionality to create tokenly identity on the platform.

### New Sub app Module: Tokenly Identity
Sub app module for Tokenly Identity.

### New Wallet: Tokenly Wallet
This plugin must register credits and debits of songs obtained through **Tokenly** public API.
​
### New World: Tokenly
This plugin must implement all the functionality to connect with **Tokenly** public API.

### New Identity: Tokenly.
This plugin must have the ability to create a Tokenly identity in Fermat.

***Once approved, the design will be completed in dev.fermat.org flows with much more detail***
     
​
## Timeline
​
Based on current workload and resouces available, the delivery date of this bounty will be **To define**.
​
## Evaluation
​
To be considered success this bounty must pass the following tests:
​
​
* Create a Fan identity.
* Create an Artist identity.
* Create a Tokenly Identity.
* Link Tokenly Identity with any ART identity.
* Display artists connected to a Fan.
* Allow the device to route the URL to the external management system of tokens.
* Display the list of songs purchased through the external management system of tokens.
* Play a song on the device.
​
*[Evaluation results to be completed after evaluation]*
​
## Limitations
​
The following limitations when evaluating the platform should be considered:
​
​
* The state of the P2P Fermat platform.
