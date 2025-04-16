---
title: Provider and Consumption Provider
author: Cyrille Georgel < cyrille@bluerocktel.com >
tags:
  - bluerocktel
  - 3CX
  - rating
  - billing
status: Working
date: 2024-03-02
---
## Terminology

BlueRockTEL has two separate models for "Supplier" and "Provider".

A supplier is a company which BlueRockTEL's user is buying goods and/or services from. For instance, the purchase invoices will be attached to the supplier.

On the other hand, a provider is anything that provides usage or consumption. It could match a supplier (for example "Gamma" is both a supplier and a provider) or not ("3CX"  or "Cirpack" are seen as providers).
## Challenges

BlueRockTEL is proceeding data from different sources (providers), and this data is fetched by different channels, based on what the provider is offering : 

-  plain FTP
-  SFTP
-  API
-  SCP
-  rsync over ssh.
-  etc.

The goal of the current refactoring is to provide a single model being able to handle everything in on place.

Types of consumption handled by BlueRockTEL

- Telecom
	-  Voice
	-  Data
	-  SMS
	-  MMS
- Copiers
	-  Copies
	-  Services and Fees
- Cloud
	-  Licences
	-  API usages

##  New Models

###  Provider

Replacing TelcoProvider

All the provider known by BlueRockTEL
###  ConsumptionProvider

Replacing CustomDisk

The provider used by the instance / customer.
