# Data Info API (Operators)

## This Document
This document will detail a route to implement the Data Info API on the Operator side. This will look at issues, likely questions, a brief architecture and other related items.

### Each Operator is Different
We understand that each operator is different and any system given below will not be compatible will all operators. Saying this, operators should feel free to use this information as a guideline on how such a system could work, and also should feel free to suggest edits where needed by issueing a Pull Request. 

## APIs
This project's goal is to develop an API for use on web applications and operating systems. For this to work a number of APIs will need to be developed which will integrate with mobile network operator systems. Below is a description of each.

Three APIs will be needed:
* Web apis - PLEASE ADD
* Device api - PLEASE ADD
* Carrier api - PLEASE ADD

Note: Browser could happen, but device api is easier

## Issues
Brain dump of issues, need to clean this up:

### Delays
5 mins delay common

### Data Plan Cases
* Roaming
 * could be more instantaneous if you’re roaming
 * roaming use case - depends on the foreign carrier, some up to date, some just get a CSV 3 days later
 * international roaming versus US roaming
* Pre pay 
* Shared Data Plans
* Unlimited data
* Zero-Rating

### Bill shock(!)
Need to make sure the user’s bill then matches the costs which are showing on their device as an outcome of the Data Info API. 

### Authenticate the customer against the device 
How do we do this?
oath could work
sms could also work
silent sms on ffos

### Legal
FCC rules - need to check this

### Typical Questions Operators will Receive
* How does Authentication work?
* Sharing data - do we want this?




