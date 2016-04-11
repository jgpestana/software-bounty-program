![alt text](https://github.com/bitDubai/media-kit/blob/master/MediaKit/Fermat%20Branding/Fermat%20Logotype/Fermat_Logo_3D.png "Fermat Logo")

# Digital Asset Platform v3 Bounty

## Introduction

There is no doubt that the Digital Asset Platform is on the critical path to the sucess of our project. As Fermat evolves and new architecture is designed an implemented in all platforms, DAP must follow this approach and improve itself to acommodate future changes.

This bounty is mainly an architecture improvement following new guidelines to modularize our processes into smaller pieces and enable reutilization, optimization and prepare for future transactions that DAP will be supporting shortly.

## Scope

### New Architecture implementation

Implement the architecture defined for **DAP** at [dev.fermat.org](http://dev.fermat.org)


### New User Interfaces in all three wallets and sub apps

[Links to github issues with new interfaces.]

### Extras

* **Refactor Remove BitDubai references from all plugins**: references to bitDubai will be removed from DAP.

* **Implement Wallet notifications for incomming assets**:  Asset Users and Redeem Points will have the option to accept (or deny) assets before receiving them. We will enable Wallet notifications. 

    Assets will be accepted by default, but this behaivour can be changed in the wallet settings section.
    
* **Migration of handling outgoing crypto transactions with events**: currently incoming transactions are handled with events, but for outgoing transactions each specific platform transaction plugin, request the CryptoNetwork for status. We will handle outgoing transactions equally.

* **Bitcoin fees**: fees when sending bitcoins is not specified, we will enable BCH and DAP to support fee specification when sending bitcoins.

## Coding guidelanes

* Agents will only be running when there are task to do, and will be stopped as soon as there are no pending request. We are avoiding having agent threads just wainting for things to do.

* Agents will no longer run under the ```while(true)``` schema. Instead we will be using ```ScheduledExecutorService``` to optimize this process.

* All agents must implement the ```stop``` method

* Transaction plugins must raise **events** when their task is completed, either by success or not, to allow other components use this information.

* Overall transaction progress must be tracked by higher level **Transaction Layers** at all times.

* **Plugin root** classes must only serve to pass platform references, implementation of component tasks must be in the *structure folder *inside the plugin.

     

## Timeline

31th May 2016

## Evaluation


## Distribution



