![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")
​
# Art Platform Bounty
​
## Introduction
​
The main objective of ART platform is to connect two type of fermat actors, in this case artists and fans. Provide a link to the artists websites, where the fans could buy tokens and exchange thoses tokens for songs. Other functionalities of the ART platform are list, play and manage the fan purchased songs in to the device, also this platform offers the possibility to chat between fans and artist..
​
This document describes the scope, design and timeline for this development.
​
## Scope
​
### Current developments in progress
​
​
For this version we will use **Tokenly** as an external system, Tokenly is a website to buy songs with tokens, and then download them, Tokenly has a public API that allows to consult the tokens catalog of a system user (swapbot) and check the status of exchange transactions of tokens for services (token slots), but it's in a very early stage of development, and it currently provides minimal information. We will develop a platform, Tokenly **(TKY)** to obtain all the information needed by the ART platform. This new platform will have a wallet that allows management of songs obtained through the public API Tokenly.
​
​
### Bounty scope

### Art Platform
​
### New Android Sub-App: Music Player.
This sub-app must show available songs on the local storage device purchased through the **Tokenly** site and play these songs.
​
### New Android Sub-App: Artist Community
This sub-app will provide a list of Artists Actors registered on the platform and the functionality to connect a Fermat actor with any of the artists displayed in the list.
​
### New Android Sub-App: Fan Community
This sub-app will provide a list of Fan actors registered on the platform and the functionality to connect a Fermat actor with any Fans displayed on the list.
​
### New Android Sub-App: Artist Identity
This sub-app will provide the functionality to create an identity as an Artist on the platform.
​
### New Android Sub-App: Fan Identity
This sub-app will provide the functionality to create an identity as an Fan on the platform.

### New Sub-App Module: Music Player
Sub-app module for Music Player.
​
### New Sub-App Module: Artist Community
Sub-app module for Artist Community.
​
### New Sub-App Module: Fan Community
Sub-app module for Fan Community.
​
### New Sub-App Module: Artist Identity
Sub-app module for Artist Identity.
​
### New Sub-App Module: Fan Identity
Sub-app module for Fan Identity.
​
### New Identity: Artist.
This plug-in must have the ability to create an Artist identity in Fermat.
​
### New Identity: Fan.
This plug-in must have the ability to create an Fan identity in Fermat.
​
### New Actor Connection: Artist.
This plug-in should be able to allow connections to a remote Artist and return the list of Artists connected to the system.
​
### New Actor Connection: Fan.
This plug-in should be able to allow connections to a remote Fan and return the list of fans connected to the system.

### New Actor Network Service: Artist.
This plug-in should be able to allow sending and receiving messages to a remote Artist indicating acceptance or rejection connections.
​
### New Actor Network Service: Fan.
This plug-in should be able to allow sending and receiving messages to a remote Fan indicating acceptance or rejection connections.


### TKY Platform


### New Android App: Fan song wallet.
This **Wallet** will allow the fan to review a list of artist connected to the fan that have an active account in **Tokenly**.

### New Android Sub-App: Tokenly Identity
This sub-app will provide the functionality to create tokenly identity on the platform.

### New Sub-App Module: Tokenly Identity
Sub-app module for Tokenly Identity.

### New Sub-App Module: Fan wallet
Module for Fan wallet.

### New Wallet: Tokenly Wallet
This plug-in must register songs downloaded through the **Tokenly** public API.
​
### New Identity: Artist.
This plug-in must have the ability to create a Tokenly Artist identity in Fermat.

### New Identity: Fan.
This plug-in must have the ability to create a Tokenly Fan identity in Fermat.

### New External API: Tokenly.
This plug-in must implement all the functionalities to connect with the **Tokenly** public API.

***Once approved, the design will be completed in dev.fermat.org flows with much more detail***
     
​
## Timeline
​
Based on the current workload and resouces available, the delivery date of this bounty will be **To define**.
​
## Evaluation
​
To be considered successful this bounty must pass the following tests:
​
* Create a Fan identity.
* Create an Artist identity.
* Create a Tokenly Identity.
* Link any Tokenly Identity with any ART identity.
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
* The status of the P2P Fermat platform.
* The status of Tokenly Public API.
