---
title: Payments Systems in the U.S.
draft: true
date: 2025-12-28
---
## Payments System Overview
- A payment is a transfer of value from a sender to a receiver
- There are three main parts of any payments system
	- Payment initiation: in some systems, this can be initiated by the receiver
	- Payment funding by the sender
	- Payment receipt by the receiver
- Two models for payment systems
	- Open loop: intermediaries like banks bring parties into the system. If two parties want to send money to each other, they need to go through the intermediaries (avoids having parties having to establish direct relationships to banks)
		- This is the most common model. It scales well and liability is on intermediaries (e.g. if a dispute happens, banks often have to take the hit)
	- Closed loop: no intermediaries and parties have direct relationships to payments system. Often used in proprietary systems, like Macy's or Venmo
- Push payment: Party A is sending money to Party B
	- Bank of A will debit itself, Bank of B will credit itself
	- Examples: wire transfers, ACH direct deposit
- Pull payment: Party A is collection money from Party B
	- Examples: checks, cards and ACH debit
	- Pull payments are subject to bouncing, where Party B may not have enough funds, and authorization issues (A may not have the credentials to pull money from B)
	- Card networks have "guaranteed pulls" where they first send an authorization message to the network to determine if the account has sufficient funds before actually making the payment